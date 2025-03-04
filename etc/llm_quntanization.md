일반적으로 LLM(대형 언어 모델)의 양자화 정도를 말할 때, **FP16 (16-bit floating point), INT8 (8-bit integer), 그리고 INT4 (4-bit integer)** 등이 주로 사용됩니다.  

### **일반적인 LLM 양자화 수준**
- **FP16 (Half Precision Floating Point)**  
  - 대부분의 모델이 기본적으로 사용하는 수준 (예: GPT-3, LLaMA-2 등)
  - 정확도를 거의 유지하면서도 FP32 대비 메모리 사용량을 절반으로 줄일 수 있음
  - GPU에서 연산 최적화 가능 (NVIDIA Tensor Core 활용 가능)

- **INT8 (8-bit Integer Quantization)**  
  - 모델 크기를 FP16 대비 절반으로 줄일 수 있음
  - 속도가 크게 향상되며, 정확도 손실은 보통 1~2% 이내
  - TensorRT, ONNX Runtime, QNNPACK, TFLite 등을 통해 가속 가능
  - GPT-4, LLaMA-2, Falcon 등의 일부 가속 버전에서 지원됨

- **INT4 (4-bit Integer Quantization)**  
  - 메모리 사용량을 크게 줄일 수 있음 (FP16 대비 4배 감소)
  - 속도 향상 효과가 크지만 정확도 손실이 INT8보다 더 큼
  - `GPTQ (Generalized Post-Training Quantization)`, `AWQ (Activation-aware Weight Quantization)`, `Bitsandbytes` 등의 프레임워크에서 지원
  - LLaMA-2, Mistral-7B 등의 양자화된 모델들이 공개됨

---

### **인퍼런스 속도와 파라미터 개수 관계**
- 같은 모델이라도 **양자화가 낮을수록(예: INT4)** 연산량이 줄어들어 인퍼런스 속도가 빨라짐.
- 하지만 LLM의 크기에 따라 차이가 있음:
  - **GPT-4 (~1조 개 파라미터 추정)** → FP16/INT8이 일반적, INT4는 거의 사용 안 함.
  - **LLaMA-2 13B** → FP16 기본, INT8 및 INT4 지원.
  - **Mistral 7B, LLaMA-3 (예상)** → INT8/INT4 양자화된 모델 활용 가능.

보통 개인이 로컬에서 빠르게 실행하려면 **INT4 또는 INT8 정도로 양자화된 모델**을 선택하는 것이 좋습니다.


<br>
<br>
<br>

LLM의 인퍼런스나 학습 속도를 측정하는 단위는 보통 **FLOPs, TFLOPs, latency(ms), tokens per second(TPS)** 같은 개념으로 표현됩니다. 각각의 의미를 설명하면 다음과 같습니다.

---

### **1. FLOPs (Floating Point Operations) / TFLOPs**
- **FLOPs (부동소수점 연산 횟수)**  
  - LLM이 한 번의 추론(inference) 또는 훈련(training)에서 수행하는 부동소수점 연산 횟수.
  - FLOPs가 많을수록 연산량이 크고, 더 강력한 GPU나 TPU가 필요함.
  - **예시:** GPT-3의 훈련에 사용된 연산량 ≈ 3.14 × 10²³ FLOPs

- **TFLOPs (TeraFLOPs, 초당 1조 FLOPs)**  
  - 1초 동안 수행할 수 있는 연산량을 나타내는 단위.
  - GPU 성능을 나타낼 때 자주 사용됨.
  - **예시:** NVIDIA A100 GPU ≈ 19.5 TFLOPs (FP32 기준)

---

### **2. Latency (지연 시간, 단위: ms)**
- 하나의 요청을 처리하는 데 걸리는 시간(밀리초, ms 단위).
- 낮을수록 빠른 응답이 가능함.
- 서버 환경에서는 주로 "end-to-end latency"를 측정함 (입력부터 출력까지 걸리는 전체 시간).
- **예시:** 
  - GPT-3 API 호출 시 평균 응답 시간 ≈ 100~500ms
  - 로컬에서 LLaMA-2 13B INT4 모델 실행 시 ≈ 50~200ms (CPU/GPU에 따라 다름)

---

### **3. Tokens per Second (TPS, 초당 토큰 처리 속도)**
- LLM이 **1초 동안 생성할 수 있는 토큰 개수**를 의미.
- LLM을 사용할 때 **추론 속도를 가장 직관적으로 측정**하는 단위.
- **예시:**
  - OpenAI GPT-4 API (2024년 기준)  
    - **GPT-4-turbo**: 100~200 TPS (INT8/FP16)
    - **GPT-4**: 30~50 TPS (FP16)
  - LLaMA-2 13B (로컬 실행 시)  
    - **FP16 (GPU)**: 20~50 TPS  
    - **INT4 (CPU)**: 5~10 TPS  

---

### **4. Training Speed (훈련 속도, Tokens per Second)**
- LLM을 학습시킬 때 1초에 처리할 수 있는 토큰 개수로 표현됨.
- 훈련 환경(GPU 개수, 모델 크기, 배치 크기 등)에 따라 크게 달라짐.
- **예시:**  
  - GPT-3 훈련 시 **355 A100 GPUs**로 학습 속도 ≈ **5,000~10,000 TPS**
  - LLaMA-2 65B 훈련 시 **TPU Pod 사용**, TPS ≈ **15,000+**  

---

### **요약**
| 단위 | 의미 | 사용 예시 |
|------|------|---------|
| **FLOPs** | 한 번의 훈련/추론에서 수행되는 연산량 | "GPT-3 학습에 3.14 × 10²³ FLOPs 필요" |
| **TFLOPs** | 초당 연산량 (GPU 성능 비교) | "NVIDIA A100: 19.5 TFLOPs" |
| **Latency (ms)** | 요청-응답까지 걸리는 시간 | "GPT-4 API 응답 시간 ≈ 200ms" |
| **Tokens per Second (TPS)** | 초당 생성할 수 있는 토큰 개수 | "GPT-4: 50 TPS, LLaMA-2 7B: 20 TPS" |

실제 모델을 선택할 때 **TPS와 Latency**가 가장 중요한 지표입니다.
