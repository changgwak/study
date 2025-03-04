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
