[abort vs cancel]   
https://stackoverflow.com/questions/9837926/abort-vs-cancel-button-when-do-i-use-abort-when-cancel


[status vs state]  
[status vs state](https://w.cublr.com/programming/different-between-state-status/#:~:text=State%EB%8A%94%20%ED%98%84%EC%9E%AC%20%EC%A7%84%ED%96%89%20%EC%83%81%ED%83%9C,%EC%97%90%20%EC%82%AC%EC%9A%A9%ED%95%9C%EB%8B%A4%EA%B3%A0%20%EB%B3%B4%EB%A9%B4%20%EB%90%98%EA%B2%A0%EB%8B%A4)


[json vs yaml]   
Python에서 YAML과 JSON은 각각의 특성과 용도에 따라 선택할 수 있는 데이터 직렬화 형식입니다. 어느 것이 더 나은지는 특정 상황과 요구사항에 따라 다릅니다. 아래에서 YAML과 JSON의 주요 특성과 장단점을 살펴보겠습니다.

### JSON (JavaScript Object Notation)

#### 장점
1. **간단하고 읽기 쉬움**: JSON은 간단한 구조를 가지고 있으며, 대부분의 프로그래밍 언어에서 쉽게 파싱할 수 있습니다.
2. **광범위한 지원**: 거의 모든 프로그래밍 언어에서 JSON을 지원하며, 웹 API와 데이터 교환에 널리 사용됩니다.
3. **빠른 파싱 속도**: JSON은 간단한 구조 덕분에 파싱 속도가 빠릅니다.

#### 단점
1. **제한된 데이터 타입**: JSON은 문자열, 숫자, 배열, 객체, 불리언, null과 같은 기본 데이터 타입만 지원합니다. 날짜나 복잡한 객체는 별도로 직렬화가 필요합니다.
2. **가독성 문제**: 간단한 구조는 읽기 쉽지만, 복잡한 데이터 구조에서는 가독성이 떨어질 수 있습니다.

#### 파이썬 예제
```python
import json

data = {
    "name": "Alice",
    "age": 30,
    "is_student": False
}

# JSON 직렬화
json_data = json.dumps(data)
print(json_data)

# JSON 역직렬화
parsed_data = json.loads(json_data)
print(parsed_data)
```

### YAML (YAML Ain't Markup Language)

#### 장점
1. **가독성**: YAML은 사람이 읽기 쉬운 형식으로 데이터를 표현합니다. 들여쓰기와 공백을 사용하여 구조를 나타내기 때문에 복잡한 데이터도 쉽게 읽을 수 있습니다.
2. **유연한 데이터 표현**: YAML은 JSON보다 더 다양한 데이터 타입을 지원합니다(예: 날짜, 시간, 정규 표현식 등).
3. **주석 지원**: YAML은 주석을 지원하여 데이터 파일에 추가 설명을 넣을 수 있습니다.

#### 단점
1. **파싱 속도**: JSON보다 파싱 속도가 느릴 수 있습니다.
2. **복잡성**: YAML의 유연성과 다양한 기능 때문에 간단한 용도에서는 오히려 복잡하게 느껴질 수 있습니다.

#### 파이썬 예제
```python
import yaml

data = {
    "name": "Alice",
    "age": 30,
    "is_student": False
}

# YAML 직렬화
yaml_data = yaml.dump(data)
print(yaml_data)

# YAML 역직렬화
parsed_data = yaml.load(yaml_data, Loader=yaml.FullLoader)
print(parsed_data)
```

### 어떤 것을 선택할까?

#### JSON을 선택할 때
- 웹 API와 데이터 교환: JSON은 대부분의 웹 API에서 표준으로 사용됩니다.
- 간단한 데이터 구조: 데이터 구조가 단순하고 파싱 속도가 중요한 경우 JSON이 적합합니다.

#### YAML을 선택할 때
- 설정 파일: YAML은 가독성이 좋아 설정 파일에 많이 사용됩니다. 예를 들어, Kubernetes, Ansible, Docker Compose 등의 설정 파일은 YAML 형식을 사용합니다.
- 복잡한 데이터 구조: 다양한 데이터 타입을 지원하고, 사람이 읽기 쉬운 형식이 필요할 때 YAML이 적합합니다.

결론적으로, **JSON은 간단하고 빠른 파싱이 필요한 경우에 적합**하며, **YAML은 가독성과 유연성이 필요한 경우에 적합**합니다. 특정 상황과 요구사항에 맞게 적절한 형식을 선택하는 것이 중요합니다. 

이런 자료를 참고했어요.
[1] Quora - What does YAML do better than JSON? (https://www.quora.com/What-does-YAML-do-better-than-JSON)
[2] KodeKloud - YAML vs. JSON: Breaking Down the Key Differences (https://kodekloud.com/blog/yaml-vs-json/)
[3] FAUN — Developer Community 🐾 - Python Trick: Working with JSON Vs YAML | by Sunil Kumar (https://faun.pub/python-tips-working-with-json-vs-yaml-70c100ca458b)
[4] Amazon Web Services - YAML과 JSON 비교 - 데이터 직렬화 형식 간의 차이 (https://aws.amazon.com/ko/compare/the-difference-between-yaml-and-json/) 
