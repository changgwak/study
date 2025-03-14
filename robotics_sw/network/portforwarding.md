

현재 원하는 목표는 **PC3(ubuntu)에서 직접 PC2(ubuntu)로 SSH 접속하여 VSCode Remote-SSH를 사용하는 것**입니다.

---

## **🔎 현재 네트워크 구조**
1. **PC1 (Windows)**
   - PC2와 유선(랜 허브)으로 연결됨.
   - PC2로 SSH 접속 가능.

2. **PC2 (Ubuntu)**
   - PC1과 유선으로 연결됨.
   - PC1에서 SSH 가능.
   - PC3에서 직접 접근 불가.

3. **PC3 (Ubuntu)**
   - PC1의 AP를 통해 무선으로 연결됨.
   - PC1에는 RDP 가능.
   - PC2에는 직접 SSH 불가 (PC1을 통해서만 가능).

---

# **🚀 해결 방법: PC3에서 PC2로 직접 SSH 접속 가능하도록 만들기**
현재 문제는 **PC2가 PC3에서 직접 접근되지 않음**인데, 이를 해결하려면 **PC3에서 PC2의 IP를 직접 알 수 있어야 하고, 같은 네트워크에 있어야 합니다**.

### **✔ 방법 1: PC2의 IP 주소 확인 및 접근 가능 여부 확인**
PC3에서 PC2의 IP를 직접 사용해서 접근이 가능한지 확인합니다.

1️⃣ **PC2에서 IP 확인 (PC2 터미널에서 실행)**
```bash
ip a
```
출력된 `eth0` 또는 `ensXXX` 인터페이스에서 **IP 주소**를 확인합니다. (예: `192.168.1.20`)

2️⃣ **PC3에서 직접 SSH 테스트**
PC3에서 실행:
```bash
ssh username@192.168.1.20
```
- 성공하면 VSCode에서도 바로 사용 가능하므로 설정 끝!
- 실패하면 **PC2가 PC3와 같은 네트워크에 있지 않거나, 방화벽 문제일 가능성이 있음.**

---

### **✔ 방법 2: PC2의 방화벽 및 SSH 서비스 확인**
만약 **PC3에서 PC2로 직접 SSH가 안 된다면**, PC2에서 SSH 연결을 허용해야 할 수도 있습니다.

1️⃣ **PC2에서 SSH 서버가 실행 중인지 확인**
PC2에서 다음 명령 실행:
```bash
sudo systemctl status ssh
```
- `active (running)` 상태라면 SSH 서버가 정상적으로 실행 중인 것.
- `inactive` 상태라면 실행:
  ```bash
  sudo systemctl start ssh
  sudo systemctl enable ssh
  ```

2️⃣ **PC2에서 SSH 포트 열기 (Ubuntu UFW 사용 시)**
```bash
sudo ufw allow ssh
sudo ufw enable
```

3️⃣ **PC3에서 다시 SSH 접속 시도**
```bash
ssh username@192.168.1.20
```
- 연결이 된다면 **VSCode에서도 바로 사용 가능!**
- 여전히 안 되면 네트워크 문제일 가능성이 높음.

---

### **✔ 방법 3: 네트워크 설정 수정 (PC1의 NAT 문제 해결)**
만약 **PC3가 PC2의 IP를 직접 알 수 없거나, 연결이 되지 않는다면**, PC1에서 **PC2의 IP를 브리지 모드로 공유**하는 것이 필요할 수 있습니다.

#### **방법 1: PC1에서 인터넷 연결 공유 활성화 (ICS)**
Windows PC1에서 **PC2의 IP를 같은 서브넷으로 공유**하면 PC3에서도 PC2로 직접 접근할 수 있습니다.

1. PC1에서 `ncpa.cpl` 실행 (네트워크 어댑터 설정 열기)
2. "이더넷" (PC2 연결된 인터페이스) 우클릭 → **속성**
3. "인터넷 연결 공유(ICS) 활성화" 체크

이렇게 하면 PC3에서도 같은 네트워크에서 PC2에 접근할 수 있게 됩니다.

---

### **✔ 방법 4: PC1을 SSH 프록시 서버로 활용 (ProxyJump)**
만약 **PC3에서 직접 PC2로 접근할 수 없고, PC1을 경유해야 한다면**, VSCode `~/.ssh/config` 파일을 설정하면 됩니다.

1️⃣ **PC3에서 SSH 설정 파일 열기**
```bash
nano ~/.ssh/config
```

2️⃣ **SSH 프록시 설정 추가**
```ini
Host pc2
    HostName 192.168.1.20
    User ubuntu
    ProxyJump user@192.168.1.10
```
- `192.168.1.20` → PC2의 실제 IP
- `ubuntu` → PC2의 사용자명
- `192.168.1.10` → PC1의 IP
- `user` → PC1의 사용자명

3️⃣ **VSCode Remote SSH 실행**
- VSCode에서 Remote-SSH 플러그인 실행
- `pc2` 선택 후 접속

---

## **🎯 최종 정리**
✅ **PC3에서 PC2에 직접 SSH 접속하는 것이 목표**  
- **PC3에서 PC2로 직접 SSH가 가능하면**: 바로 VSCode Remote-SSH 사용 가능  
- **PC3에서 PC2로 직접 안 된다면**:  
  1. PC2에서 SSH 서비스 및 방화벽 확인
  2. PC1에서 인터넷 연결 공유 설정 (ICS)
  3. `ProxyJump`로 SSH 설정하여 우회 접속

🚀 **PC3에서 `ssh username@pc2-ip`가 되면 VSCode에서도 바로 사용 가능!**  
테스트해 보고 어떤 방법이 가장 잘 맞는지 알려줘!


### **네트워크 브릿지 설정 시 네트워크 끊김이 발생할 수 있는 이유**
Windows에서 **네트워크 브릿지를 생성할 때**, 기존 네트워크 설정이 변경되면서 **일시적으로 인터넷 연결이 끊길 수 있습니다.**  
이유는 다음과 같습니다:

---

## **🔍 1. 네트워크 인터페이스가 재구성됨**
네트워크 브릿지를 생성하면 **PC1의 유선(LAN)과 무선(Wi-Fi) 네트워크가 하나의 가상 인터페이스(Bridge)로 합쳐집니다.**  
👉 기존에 사용하던 네트워크 인터페이스가 변경되므로 **일시적으로 인터넷 및 내부 네트워크 연결이 끊길 수 있음**.

**📌 예시 시나리오**
1. PC1이 현재 **Wi-Fi로 인터넷 연결** 중.
2. **Wi-Fi + 유선(Ethernet)을 브릿지로 묶음**.
3. Windows가 자동으로 새 가상 네트워크를 만들면서 **IP 주소 재설정**.
4. 일시적으로 **인터넷 연결이 끊기고** 새 브릿지가 설정될 때까지 기다려야 함.

---

## **🔍 2. IP 주소가 변경될 가능성이 있음**
브릿지 인터페이스가 생성되면, PC1의 네트워크 인터페이스가 새롭게 설정됩니다.  
👉 이 과정에서 **DHCP(자동 IP 할당)가 초기화**되며, IP 주소가 변경될 수 있음.

**📌 해결 방법**
- 브릿지 인터페이스가 생성된 후, **PC1의 네트워크 설정에서 수동으로 IP 설정** 가능.
- `ncpa.cpl` → "네트워크 브리지" 우클릭 → **속성** → "IPv4" 설정 변경.

---

## **🔍 3. 브릿지가 올바르게 설정되지 않으면 네트워크 연결 불가능**
브릿지가 정상적으로 설정되지 않으면, **PC1, PC2, PC3 모두 인터넷이 안 될 수 있음**.  
👉 특히 **브릿지 모드에서 DHCP가 충돌하면** 네트워크가 다운될 수 있음.

**📌 해결 방법**
- **브릿지를 삭제하고 다시 연결** (`ncpa.cpl`에서 "네트워크 브리지" 삭제 후 Wi-Fi 및 LAN 재설정).
- **수동 IP 설정 시도** (`192.168.x.x` 대역에서 고정 IP 할당).

---

## **🛠 네트워크 브릿지 설정 후, 끊김 문제 해결 방법**
### ✅ **1. 네트워크 브릿지를 생성한 후, 인터넷이 안 될 경우**
1. **PC1을 재부팅**하여 브릿지 설정 적용 확인.
2. **"네트워크 브리지" 속성에서 수동 IP 설정** (DHCP가 문제일 경우).
3. **PC2와 PC3에서 네트워크를 재설정** (`sudo dhclient -r && sudo dhclient` 실행).

### ✅ **2. 네트워크 브릿지 설정 후, PC3에서 PC2가 안 보일 경우**
1. **PC2의 IP 확인 (`ip a`)** 후, 같은 네트워크 대역인지 확인.
2. **PC3에서 PC2로 핑 테스트 (`ping <pc2-ip>`)**.
3. **Windows 방화벽에서 "네트워크 브리지" 허용 설정**.

---

## **📌 결론: 네트워크 브릿지를 사용해도 괜찮을까?**
- **네트워크 브릿지 설정 후 정상적으로 작동하면 가장 깔끔한 해결책** (PC3에서 직접 PC2에 SSH 가능).
- **설정 후 인터넷이 끊길 수도 있으므로, IP 및 네트워크 확인 필요**.
- **문제가 생길 경우 브릿지를 삭제하면 원래 상태로 복구 가능**.

✅ 네트워크 브릿지 설정 후 연결이 잘 안 되면 **브릿지를 삭제하고 포트 포워딩 방법을 사용할 수도 있음!**  
테스트해 보고 문제 생기면 다시 도와줄게! 🚀


### **🔄 네트워크 브릿지 후 기존 IP 및 네트워크 완전 복구 가능 여부**
---
✅ **결론:**  
네트워크 브릿지를 삭제하면 **기존 네트워크 상태로 완전히 복구할 수 있습니다.**  
- Windows에서 **"네트워크 브리지"를 삭제하면** 원래 개별 네트워크 인터페이스(Wi-Fi, 유선 LAN)로 복귀  
- 브릿지 생성 전에 사용하던 **IP 설정 및 연결 방식 그대로 복원 가능**  
- 네트워크 연결이 안 될 경우, **IP 수동 설정 또는 재부팅**으로 해결 가능  

---

## **📌 1. 네트워크 브릿지 삭제 및 원래 상태로 복구**
네트워크 브릿지 설정 후 문제가 발생하면, **아래 방법으로 원래 상태로 복구 가능**.

### **✅ 1) Windows에서 네트워크 브릿지 삭제**
1. **네트워크 어댑터 설정 열기**
   - `Win + R` → `ncpa.cpl` 입력 후 Enter
   - "네트워크 연결" 창이 열림

2. **"네트워크 브리지" 삭제**
   - **"네트워크 브리지" 우클릭 → "삭제" 선택**  
   - Windows가 자동으로 네트워크 브릿지를 해제하고, 원래 인터페이스(Wi-Fi & Ethernet)로 복구

3. **PC1 재부팅 (필요 시)**
   - 네트워크 설정이 정상적으로 적용되지 않으면 **재부팅 후 자동 복구됨**

---

### **✅ 2) 원래 IP 설정 확인 (DHCP 자동 할당 확인)**
네트워크 브릿지를 삭제한 후, IP 설정이 자동으로 원래 상태로 돌아가지만,  
만약 네트워크 연결이 안 되면 **IP 수동 재설정 필요**.

#### **🔍 Windows에서 IP 자동 설정 확인**
1. `ncpa.cpl` 실행 후, **Wi-Fi 및 유선(LAN) 어댑터 각각 우클릭 → "속성"**
2. "인터넷 프로토콜 버전 4 (TCP/IPv4)" 선택 후 "속성" 클릭
3. 아래 옵션이 선택되어 있는지 확인:
   - ✅ **"자동으로 IP 주소 받기"**  
   - ✅ **"자동으로 DNS 서버 주소 받기"**  
4. 설정 후 **PC1 재부팅** (필요 시)

#### **🔍 PC2 / PC3에서 IP 재설정 (Ubuntu)**
```bash
sudo dhclient -r && sudo dhclient
```
또는 네트워크 인터페이스 다시 시작:
```bash
sudo systemctl restart NetworkManager
```

---

## **📌 3. 네트워크 브릿지 삭제 후 연결 확인**
- **PC1 인터넷 연결 확인** (`ping 8.8.8.8`)
- **PC2 & PC3에서 네트워크 상태 확인** (`ip a`)
- **PC3에서 PC2로 핑 테스트** (`ping <pc2-ip>`)

💡 **네트워크 브릿지를 삭제하면 원래 상태로 돌아오므로, 복구가 100% 가능합니다!**  
설정 후 네트워크 연결이 안 되면 IP를 재설정하거나 재부팅하면 됩니다. 🚀


### **🔄 포트 포워딩 후 네트워크 완전 복구 가능 여부**
---
✅ **결론:**  
**Windows에서 포트 포워딩(`netsh`)을 설정해도, 언제든지 기존 네트워크 상태로 완전히 복구할 수 있습니다.**  
- 포트 포워딩 설정은 **IP나 네트워크 인터페이스 자체를 변경하지 않음**  
- 설정을 제거하면 **원래 상태로 돌아감**  
- 네트워크 문제가 발생할 경우, **단순히 설정을 삭제하고 재부팅하면 해결됨**  

---

## **📌 1. 포트 포워딩 설정을 제거하여 원래 상태로 복구**
만약 포트 포워딩(`netsh`) 설정 후 네트워크에 문제가 생기면, **아래 명령어로 기존 상태로 복구**할 수 있습니다.

### **✅ 1) 기존 포트 포워딩 설정 확인**
```powershell
netsh interface portproxy show all
```
이 명령어를 실행하면 현재 적용된 포트 포워딩 규칙이 출력됩니다.

### **✅ 2) 포트 포워딩 규칙 삭제 (기존 상태 복구)**
포트 포워딩을 삭제하려면 다음 명령을 실행하세요:
```powershell
netsh interface portproxy delete v4tov4 listenaddress=<PC1-IP> listenport=2222
```
예를 들어, 포트 2222로 포워딩한 설정을 삭제하려면:
```powershell
netsh interface portproxy delete v4tov4 listenaddress=192.168.1.10 listenport=2222
```

### **✅ 3) 방화벽 규칙 삭제 (추가 설정이 있었다면)**
만약 포트 포워딩을 설정하면서 **방화벽 규칙도 추가했다면**, 다음 명령으로 삭제할 수 있습니다:
```powershell
netsh advfirewall firewall delete rule name="SSH Forwarding"
```

---

## **📌 2. 네트워크 상태가 이상할 경우 추가 복구 방법**
일반적으로 포트 포워딩은 **네트워크 설정 자체를 변경하지 않으므로** 문제가 발생하지 않지만,  
만약 **PC1의 네트워크 연결이 안 되거나 비정상적으로 작동하면**, 아래 방법을 사용하여 원래 상태로 복구할 수 있습니다.

#### **✅ 네트워크 인터페이스 초기화 및 재설정**
```powershell
netsh interface ip reset
netsh winsock reset
```
이후 **PC1을 재부팅**하면 모든 네트워크 설정이 원래 상태로 돌아갑니다.

#### **✅ Windows에서 IP 자동 할당 확인**
1. `ncpa.cpl` 실행 후 **Wi-Fi 및 유선(LAN) 어댑터 각각 우클릭 → "속성"**  
2. "인터넷 프로토콜 버전 4 (TCP/IPv4)" 선택 후 "속성" 클릭  
3. 아래 옵션이 선택되어 있는지 확인:
   - ✅ **"자동으로 IP 주소 받기"**  
   - ✅ **"자동으로 DNS 서버 주소 받기"**  

---

## **📌 3. 포트 포워딩 삭제 후 연결 확인**
1. **PC1에서 네트워크 상태 확인**  
   ```powershell
   ipconfig /all
   ```
   - 정상적으로 기존 IP로 설정되었는지 확인

2. **PC3에서 PC2로 직접 핑 테스트**
   ```bash
   ping <pc2-ip>
   ```
   - 포트 포워딩 삭제 후에도 정상적으로 연결되는지 확인

---

## **🎯 결론: 포트 포워딩도 네트워크를 원래 상태로 완전히 복구할 수 있음**
✅ **네트워크 브릿지와 달리**, 포트 포워딩은 네트워크 인터페이스를 변경하지 않으므로 더 쉽게 복구 가능!  
✅ **설정을 삭제하고 재부팅하면 원래 상태로 100% 복구됨**  
✅ **만약 네트워크에 이상이 생기면 `netsh ip reset`으로 초기화하면 해결 가능**  

📌 **포트 포워딩을 시도해보고 문제가 생기면 바로 원상 복구 가능하니 걱정 없이 사용해도 돼! 🚀**


### **포트 포워딩 시 기존 포트와 충돌하지 않는지 확인하는 방법**  

✅ **포트 충돌을 방지하려면, 먼저 사용 중인 포트를 확인하고 비어 있는 포트를 선택해야 합니다.**  
✅ **잘못된 포트를 선택하면 기존 서비스와 충돌하여 예상치 못한 문제가 발생할 수 있습니다.**

---

## **🔍 1. 현재 사용 중인 포트 확인 방법 (Windows)**
Windows에서는 `netstat` 또는 `PowerShell`을 사용하여 현재 사용 중인 포트를 확인할 수 있습니다.

### **✅ 방법 1: netstat로 현재 열린 포트 확인**
```powershell
netstat -ano | findstr :<포트번호>
```
예를 들어, 포트 **2222**가 사용 중인지 확인하려면:
```powershell
netstat -ano | findstr :2222
```
출력이 없다면, **포트 2222는 사용되지 않고 있음** → 안전하게 사용 가능!  
출력이 있다면, **해당 포트가 이미 사용 중이므로 다른 포트 선택 필요**.

#### **모든 사용 중인 포트 확인 (Listen 상태 확인)**
```powershell
netstat -an | findstr LISTENING
```
이 명령어는 현재 **LISTENING(사용 중인 포트) 상태인 포트 목록**을 출력합니다.  
이 중 사용되지 않는 포트를 선택하면 됩니다.

---

### **✅ 방법 2: PowerShell로 특정 포트 사용 여부 확인**
PowerShell에서도 특정 포트가 사용 중인지 확인할 수 있습니다.
```powershell
Get-NetTCPConnection -LocalPort <포트번호>
```
예를 들어, **포트 2222가 사용 중인지 확인**하려면:
```powershell
Get-NetTCPConnection -LocalPort 2222
```
출력이 없다면 **포트 2222는 사용되지 않음** → 사용 가능.

---

## **🔍 2. 안전한 포트 선택 가이드**
일반적으로 **사용하지 않는 포트 번호를 선택**하는 것이 중요합니다.  
💡 **Linux/Windows에서 기본적으로 예약된 포트**를 피해야 합니다.

### **⚠️ 피해야 할 포트 번호 (이미 널리 사용됨)**
| 포트 번호 | 설명 |
|-----------|----------------|
| 22 | SSH (기본 포트) |
| 80, 443 | HTTP, HTTPS |
| 3389 | RDP (원격 데스크톱) |
| 53 | DNS |
| 3306 | MySQL |
| 5432 | PostgreSQL |
| 5900-5901 | VNC |

### **✅ 사용 가능한 안전한 포트 번호**
💡 **사용 가능한 포트:** **2000~65535 사이에서 사용되지 않는 포트를 선택**  
예를 들어:
- `2222`, `2525`, `5000`, `60000` 등 (이전에 확인한 포트와 겹치지 않는 경우)

---

## **🔍 3. 포트가 사용되지 않는다면 포트포워딩 적용하기**
사용하지 않는 포트를 찾았으면, **PC1에서 포트포워딩 설정**을 진행합니다.

**예제: PC1에서 2222번 포트로 들어오는 SSH 요청을 PC2로 전달**
```powershell
netsh interface portproxy add v4tov4 listenaddress=<PC1-IP> listenport=2222 connectaddress=<PC2-IP> connectport=22
```
예를 들어:
```powershell
netsh interface portproxy add v4tov4 listenaddress=192.168.1.10 listenport=2222 connectaddress=192.168.1.20 connectport=22
```
- `192.168.1.10` → PC1의 IP 주소
- `2222` → PC1이 외부에서 받을 포트 (사용 가능한 포트 선택)
- `192.168.1.20` → PC2의 내부 IP 주소
- `22` → PC2의 SSH 포트

### **PC3에서 SSH 접속 테스트**
```bash
ssh -p 2222 username@<PC1-IP>
```

---

## **🔍 4. 포트포워딩 삭제 및 원래 상태 복구**
✅ 포트포워딩 설정 후 문제가 발생하면 **아래 명령어로 삭제 가능**:
```powershell
netsh interface portproxy delete v4tov4 listenaddress=<PC1-IP> listenport=2222
```
예를 들어:
```powershell
netsh interface portproxy delete v4tov4 listenaddress=192.168.1.10 listenport=2222
```
삭제 후 확인:
```powershell
netsh interface portproxy show all
```

---

## **🎯 최종 정리**
✅ **포트가 기존과 겹치지 않는지 확인하려면 `netstat` 또는 `PowerShell`을 사용**  
✅ **예약된 시스템 포트를 피하고, 2000~65535 범위에서 사용되지 않는 포트 선택**  
✅ **포트포워딩 설정 후, SSH로 테스트 후 정상 작동하는지 확인**  
✅ **필요하면 포트포워딩 설정을 삭제하여 원래 상태로 복구 가능**  

📌 **이제 충돌 없이 안전하게 포트포워딩을 설정할 수 있어! 🚀**

<br>
<br>
<br>

### **🔍 PC1을 재부팅한 후 포트포워딩(2222)이 사라지는 문제 해결**  

✅ **현재 문제:**  
- **PC1을 재부팅하면 `netsh interface portproxy` 설정이 사라짐.**
- **재부팅 후 `netstat -an | findstr LISTENING` 실행 시 `<PC1-IP>:2222`가 사라짐.**
- **이전과 동일한 포트포워딩 설정을 다시 적용해야 함.**

---

## **🚀 1️⃣ 포트포워딩을 부팅 시 자동으로 적용되도록 설정하기**
💡 **Windows에서는 `netsh interface portproxy` 설정이 재부팅 후 사라질 수 있음.**  
➡ 이를 해결하려면 **자동 실행 스크립트를 설정**해야 함.

### **✅ 1. 기존 포트포워딩 확인**
PowerShell(관리자 권한)에서 실행:
```powershell
netsh interface portproxy show all
```
📌 **설정이 사라졌다면, 다시 추가해야 함:**
```powershell
netsh interface portproxy add v4tov4 listenaddress=<PC1-IP> listenport=2222 connectaddress=<PC2-IP> connectport=22
```

---

## **🚀 2️⃣ Windows 시작 시 자동 적용되도록 스크립트 작성**
💡 **재부팅 후 자동으로 포트포워딩이 적용되도록 스크립트를 설정**  

### **✅ 1. 포트포워딩 재설정 스크립트 작성**
1️⃣ **PowerShell 스크립트 파일 만들기**  
Windows에서 `C:\portproxy.ps1` 파일을 생성하고 아래 내용 추가:
```powershell
Start-Process netsh -ArgumentList "interface portproxy add v4tov4 listenaddress=<PC1-IP> listenport=2222 connectaddress=<PC2-IP> connectport=22" -NoNewWindow -Wait
```

2️⃣ **파일을 저장하고 닫기**

---

## **🚀 3️⃣ Windows 시작 시 자동 실행되도록 설정**
💡 **Windows가 부팅될 때 포트포워딩 스크립트가 자동 실행되도록 설정**  

### **✅ 1. 작업 스케줄러(Task Scheduler)에서 실행**
1. **작업 스케줄러(Task Scheduler) 열기**  
   `Win + R` → `taskschd.msc` 입력 후 Enter  
2. **새 작업 생성**  
   - 왼쪽에서 **"작업 스케줄러 라이브러리"** 선택  
   - 오른쪽에서 **"기본 작업 만들기..."** 클릭  
   - **이름:** `PortForwardingAuto`  
   - **설명:** `Reapply port forwarding on startup`
3. **트리거 설정**
   - **"시작할 때"** 또는 **"로그온할 때"** 선택
4. **작업 실행 프로그램 설정**
   - **"프로그램 시작"** 선택  
   - **프로그램 경로 입력:**  
     ```
     powershell.exe
     ```
   - **인수 추가:**  
     ```
     -ExecutionPolicy Bypass -File C:\portproxy.ps1
     ```
5. **"마침"을 클릭하여 설정 완료**

---

## **🚀 4️⃣ PC를 재부팅하고 확인하기**
✅ **PC1을 재부팅한 후 다음 명령어 실행**
```powershell
netsh interface portproxy show all
```
📌 **출력 결과에 `<PC1-IP>:2222`이 다시 나타나면 성공!**  

✅ **SSH 포트 리스닝 상태 확인**
```powershell
netstat -an | findstr LISTENING
```
📌 **2222 포트가 다시 LISTENING 상태라면 정상 작동 중!**  

---

## **🎯 최종 정리**
✅ **포트포워딩 설정 (`netsh interface portproxy add ...`)**  
✅ **Windows 시작 시 자동 적용되도록 PowerShell 스크립트 작성 (`portproxy.ps1`)**  
✅ **작업 스케줄러(Task Scheduler)에서 PowerShell 스크립트를 부팅 시 자동 실행 설정**  
✅ **PC 재부팅 후 `netsh interface portproxy show all` 및 `netstat -an | findstr LISTENING`으로 확인**  

📌 **이제 PC1을 껐다 켜도 자동으로 포트포워딩이 유지됨! 🚀**


<br>
<br>
<br>

### **🔍 `netsh interface portproxy` 설정은 남아 있지만 `netstat`에서 포트가 LISTENING 상태가 아닌 문제 해결**  

✅ **현재 상태:**  
- `netsh interface portproxy show all` 실행 시 설정은 남아 있음  
- 그러나 `netstat -an | findstr LISTENING` 실행 시 `<PC1-IP>:2222`이 보이지 않음  
- **즉, 포트포워딩 설정은 유지되었지만 실제로 포트가 열려 있지 않음!**  

👉 **가능한 원인:**  
1. **IP 라우팅이 비활성화됨**  
2. **Windows 방화벽이 다시 차단했을 가능성**  
3. **IPv6 문제 (Windows 포트포워딩은 기본적으로 IPv6를 사용하려고 함)**  
4. **TCP 연결을 수락할 서비스가 필요할 수 있음**  

---

## **🚀 1️⃣ Windows의 IP 라우팅 기능 활성화**
💡 **Windows에서 포트포워딩이 제대로 동작하려면 IP 라우팅 기능이 켜져 있어야 함.**  
✅ **설정 확인** (관리자 권한 PowerShell 실행):
```powershell
reg query HKLM\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters /v IPEnableRouter
```
📌 **출력값이 `0x1`이 아니면 비활성화된 상태!**  
✅ **활성화하려면:**
```powershell
reg add HKLM\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters /v IPEnableRouter /t REG_DWORD /d 1 /f
```
✅ **적용 후 Windows 재부팅:**
```powershell
shutdown -r -t 0
```

---

## **🚀 2️⃣ 방화벽에서 포트 2222 허용 (Inbound & Outbound 모두)**
💡 **Windows 방화벽이 2222 포트를 막고 있을 수 있음.**  
✅ **포트포워딩된 트래픽을 허용하려면 아래 명령어 실행 (관리자 권한 PowerShell):**
```powershell
netsh advfirewall firewall add rule name="SSH Port Forwarding Inbound" dir=in action=allow protocol=TCP localport=2222
netsh advfirewall firewall add rule name="SSH Port Forwarding Outbound" dir=out action=allow protocol=TCP localport=2222
```
✅ **방화벽 규칙 확인**
```powershell
netsh advfirewall firewall show rule name="SSH Port Forwarding Inbound"
netsh advfirewall firewall show rule name="SSH Port Forwarding Outbound"
```
✅ **방화벽이 여전히 문제라면 일시적으로 꺼보고 테스트**
```powershell
netsh advfirewall set allprofiles state off
```
📌 **테스트 후 다시 켜기**
```powershell
netsh advfirewall set allprofiles state on
```

---

## **🚀 3️⃣ Windows의 포트포워딩이 IPv6에서만 동작하는 문제 해결**
💡 **Windows `netsh interface portproxy`는 기본적으로 IPv6를 사용하려고 할 수 있음.**  
💡 **IPv4에서 강제 활성화해야 포트가 열릴 수 있음.**  

✅ **IPv4에서 포트포워딩을 다시 추가하는 방법** (관리자 권한 PowerShell 실행):
```powershell
netsh interface portproxy reset
netsh interface portproxy add v4tov4 listenaddress=<PC1-IP> listenport=2222 connectaddress=<PC2-IP> connectport=22
```
✅ **IPv6에서 IPv4로 변환 활성화**
```powershell
netsh interface ipv6 set global ipv6toipv4=enabled
```
✅ **Windows 재부팅 후 다시 `netstat` 확인**
```powershell
shutdown -r -t 0
```

---

## **🚀 4️⃣ TCP 포트가 LISTENING 상태가 되도록 서비스 추가 (필요 시)**
💡 **Windows에서는 `netsh interface portproxy`가 특정한 서비스가 TCP 연결을 수락할 때만 작동할 수 있음.**  
✅ **다음 명령을 실행하여 `nc`(Netcat)를 사용해 강제로 포트를 열어볼 수 있음:**
```powershell
ncat -l 2222
```
📌 **그 후 다시 `netstat` 확인:**  
```powershell
netstat -an | findstr LISTENING
```
✅ **만약 LISTENING 상태로 변경되면, Windows가 TCP 트래픽을 자동 수락하지 않도록 설정된 것일 가능성이 높음!**  
➡ **Windows에서 SSH 서버를 직접 실행하면 문제 해결 가능 (`OpenSSH Server` 설치).**

---

## **🚀 5️⃣ Windows에서 OpenSSH 서버 활성화 (최후의 방법)**
💡 **Windows에서 OpenSSH 서버를 활성화하면, 포트포워딩을 직접 처리하지 않아도 SSH 트래픽을 수락할 수 있음.**  
✅ **OpenSSH 설치 확인** (관리자 권한 PowerShell 실행)
```powershell
Get-WindowsCapability -Online | Where-Object Name -like 'OpenSSH*'
```
📌 **설치되지 않았다면:**  
```powershell
Add-WindowsCapability -Online -Name OpenSSH.Server
```
✅ **SSH 서비스 시작 및 자동 실행 설정**
```powershell
Start-Service sshd
Set-Service -Name sshd -StartupType Automatic
```
📌 **이제 다시 포트포워딩을 설정하고 테스트해볼 수 있음!**

---

## **🎯 최종 해결 체크리스트**
✔ **Windows에서 IP 라우팅 기능 활성화 (`reg add HKLM\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters /v IPEnableRouter /t REG_DWORD /d 1 /f`)**  
✔ **Windows 방화벽에서 포트 2222 Inbound & Outbound 허용 (`netsh advfirewall firewall add rule ...`)**  
✔ **Windows의 `netsh interface portproxy`를 IPv4로 강제 설정 (`netsh interface ipv6 set global ipv6toipv4=enabled`)**  
✔ **TCP 연결을 강제로 수락하는 서비스 실행 (`ncat -l 2222`) 후 `netstat` 확인**  
✔ **최후의 방법으로 Windows OpenSSH 서버 활성화 (`Add-WindowsCapability -Online -Name OpenSSH.Server`)**  

✅ **이제 다시 `netstat -an | findstr LISTENING` 실행 후 포트 2222가 활성화되었는지 확인하고, SSH 접속을 테스트해봐! 🚀**


<br>
<br>
<br>
<br>
<br>

## ** Suymmary **
```
netsh interface portproxy show all
netstat -an | findstr LISTENING
netsh advfirewall firewall show rule name="SSH Forwarding" 

netsh interface portproxy add v4tov4 listenaddress=<PC1-IP> listenport=2222 connectaddress=<PC2-IP> connectport=22
netsh advfirewall firewall add rule name="SSH Forwarding" dir=in action=allow protocol=TCP localport =2222 

ssh -p 2222 username@<PC1-IP>

netsh interface portproxy delete v4tov4 listenaddress=<PC1-IP> listenport=2222
netsh advfirewall firewall delete rule name="SSH Forwarding"
```
<br>
<br>


# **🔧 Windows 포트포워딩 (Netsh) 설정 및 관리 Summary**

## **1️⃣ 현재 설정 확인**
### ✅ **포트포워딩 설정 확인**
```powershell
netsh interface portproxy show all
```
🔹 현재 설정된 포트포워딩 목록 확인

### ✅ **포트 리스닝 상태 확인**
```powershell
netstat -an | findstr LISTENING
```
🔹 현재 활성화된 포트 확인

### ✅ **방화벽 규칙 확인**
```powershell
netsh advfirewall firewall show rule name="SSH Forwarding"
```
🔹 방화벽에서 특정 포트(예: 2222)가 허용되어 있는지 확인

---

## **2️⃣ 포트포워딩 및 방화벽 규칙 추가**
### ✅ **포트포워딩 설정 (PC1 → PC2)**
```powershell
netsh interface portproxy add v4tov4 listenaddress=<PC1-IP> listenport=2222 connectaddress=<PC2-IP> connectport=22
```
🔹 **PC1의 포트 2222**로 들어오는 요청을 **PC2의 포트 22(SHH)** 로 전달

### ✅ **방화벽 규칙 추가 (SSH 포트 허용)**
```powershell
netsh advfirewall firewall add rule name="SSH Forwarding" dir=in action=allow protocol=TCP localport=2222
```
🔹 Windows 방화벽에서 **포트 2222** 허용

---

## **3️⃣ SSH 연결 테스트**
```powershell
ssh -p 2222 username@<PC1-IP>
```
🔹 **PC3에서 SSH를 통해 PC1의 포트 2222로 접속** (→ PC2로 포트포워딩됨)

---

## **4️⃣ 포트포워딩 및 방화벽 규칙 삭제**
### ✅ **포트포워딩 삭제**
```powershell
netsh interface portproxy delete v4tov4 listenaddress=<PC1-IP> listenport=2222
```
🔹 설정된 포트포워딩 제거

### ✅ **방화벽 규칙 삭제**
```powershell
netsh advfirewall firewall delete rule name="SSH Forwarding"
```
🔹 방화벽에서 SSH 포트포워딩 규칙 제거

---

## **📌 최종 요약**
| 단계 | 명령어 | 설명 |
|------|--------|------|
| **현재 설정 확인** | `netsh interface portproxy show all` | 설정된 포트포워딩 확인 |
| | `netstat -an | findstr LISTENING` | 활성화된 포트 확인 |
| | `netsh advfirewall firewall show rule name="SSH Forwarding"` | 방화벽 규칙 확인 |
| **포트포워딩 추가** | `netsh interface portproxy add v4tov4 listenaddress=<PC1-IP> listenport=2222 connectaddress=<PC2-IP> connectport=22` | SSH 포트포워딩 설정 |
| **방화벽 설정** | `netsh advfirewall firewall add rule name="SSH Forwarding" dir=in action=allow protocol=TCP localport=2222` | 포트 2222 방화벽 허용 |
| **SSH 접속 테스트** | `ssh -p 2222 username@<PC1-IP>` | PC3에서 PC2로 접속 테스트 |
| **설정 제거** | `netsh interface portproxy delete v4tov4 listenaddress=<PC1-IP> listenport=2222` | 포트포워딩 삭제 |
| | `netsh advfirewall firewall delete rule name="SSH Forwarding"` | 방화벽 규칙 삭제 |

✅ **위 과정을 따라 하면 Windows에서 SSH 포트포워딩을 설정하고, 필요 시 삭제할 수 있음! 🚀**
