### **🔧 PC1에서 스크립트를 실행하여 PC2를 종료하고, 종료된 것을 확인한 후 PC1도 종료하는 스크립트**

✅ **기능:**  
1. **PC1에서 SSH를 통해 PC2를 종료**  
2. **PC2의 종료 상태를 확인**  
3. **PC2가 완전히 종료되었으면 PC1도 종료**

---

## **🚀 1️⃣ 스크립트 작성 (Windows PowerShell)**
📌 **PC1에서 실행할 PowerShell 스크립트 (`shutdown_pc2_then_pc1.ps1`)**
```powershell
# PC2 접속 정보
$pc2_user = "<PC2-사용자명>"
$pc2_ip = "<PC2-IP>"
$pc2_ssh_port = "22"  # 포트포워딩을 사용할 경우 2222

# PC2 종료 명령 실행 (SSH 사용)
Write-Host "🔌 Shutting down PC2 ($pc2_ip)..."
ssh -p $pc2_ssh_port $pc2_user@$pc2_ip "sudo shutdown -h now"

# PC2의 종료 상태 확인 (ping 사용)
Write-Host "⏳ Waiting for PC2 to shut down..."
while ($true) {
    $ping = Test-Connection -ComputerName $pc2_ip -Count 1 -Quiet
    if (-not $ping) {
        Write-Host "✅ PC2 is completely shut down!"
        break
    }
    Start-Sleep -Seconds 5  # 5초 대기 후 다시 확인
}

# PC1 종료
Write-Host "🔌 Shutting down PC1..."
Stop-Computer -Force
```

---

## **🚀 2️⃣ 실행 방법**
1. **PowerShell을 관리자 권한으로 실행**  
2. **스크립트를 실행할 수 있도록 실행 정책 변경 (한 번만 실행하면 됨)**  
   ```powershell
   Set-ExecutionPolicy RemoteSigned -Scope Process
   ```
3. **스크립트 실행**
   ```powershell
   .\shutdown_pc2_then_pc1.ps1
   ```

---

## **🔍 3️⃣ 설명**
1. **PC1에서 SSH로 PC2에 접속하여 종료 명령 (`sudo shutdown -h now`) 실행**
2. **PC2가 종료될 때까지 `ping`으로 상태 확인**
3. **PC2가 완전히 종료되면, PC1도 `Stop-Computer -Force` 명령으로 종료**

---

## **📌 추가 설정 (비밀번호 없이 SSH 실행)**
PC2의 종료 명령을 실행할 때 **비밀번호 입력 없이 SSH가 가능하도록 설정하면 자동화 가능**  
✅ **PC1에서 SSH 키를 사용하여 PC2에 비밀번호 없이 접속 가능하도록 설정**
```powershell
ssh-keygen -t rsa -b 4096
ssh-copy-id -p 2222 <PC2-사용자명>@<PC2-IP>
```

📌 **이제 실행하면 자동으로 PC2 종료 후 PC1도 종료됨! 🚀**
