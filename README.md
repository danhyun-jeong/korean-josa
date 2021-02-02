# 조사 선택 파이썬 모듈 Korean Josa Python Module

음운 환경(즉 조사 앞에 오는 음절이 끝소리를 갖는지 아닌지)에 따라 이형태를 갖는 한국어 조사를 선택해주는 파이썬 모듈입니다.  
This is a module to choose 'josa' in Korean language which has two different form, according to what comes before josa.

## 지원 범위

조사는 '은/는', '이/가', '을/를', '와/과' 4가지를 지원합니다.

조사 앞에 오는 단어 또는 어구로는 한글, 영문, 숫자를 지원합니다. (숫자의 경우 str이어도 되고 그렇지 않아도 작동합니다.) 단, 라틴 문자(로마자)가 올 경우 이를 영어식으로 읽는다고 간주합니다. (다시 말해 영어 외에 라틴 문자를 표기 수단으로 삼는 다른 언어는 제대로 지원하는 것이 아닙니다.) 또한, 'a', 'b', 'c' 등과 같이 하나의 라틴 문자만 올 경우, 이것은 단어가 아니라 기호로 간주되며 따라서 해당 문자의 영어식 발음을 토대로 조사가 결정됩니다. 모두 대문자인 어구가 올 경우, 이를 약어로 판단하여 앞의 경우와 마찬가지 규칙이 적용됩니다.  
조사 앞에 오는 단어 또는 어구가 따옴표, 괄호 및 낫표 등으로 감싸져 있을 경우에도 작동됩니다. 애석하게도 한자는 아직 지원하지 않습니다. 또한 옛한글 역시 아직 지원하지 않습니다.

지원하지 않는 문자나 기호가 왔을 경우 '은(는)'과 같은 꼴로 값을 반환합니다.

참고: 영단어의 한국식 발음 및 한글 표기의 경우 규칙에 대한 예외가 상당수 존재하므로, 모든 경우를 완벽하게 지원하다고 말하기 어렵습니다.

## 포함된 함수

아래의 모든 함수는 조사와 결합될, 조사 앞에 오는 단어 또는 어구를 변수로 가집니다.  
'take'로 시작하는 함수는 조사를 단순히 **고르기만** 합니다. 따라서 자동으로 단어 또는 어구 **뒤에 조사를 결합**시킨 값을 반환받고 싶을 때는 'add'로 시작하는 함수를 사용해야 합니다.

1. 은/는 : `take_eun_or_neun()`, `add_eun_or_neun()`
2. 이/가 : `take_yi_or_ga()`, `add_yi_or_ga()`
3. 을/를 : `take_eul_or_reul()`, `add_eul_or_reul()`
4. 와/과 : `take_wa_or_gwa()`, `add_wa_or_gwa()`

## 테스트

다음을 실행시켜 테스트해볼 수 있습니다.

```python
print(add_eul_or_reul("cake"), "먹자")
print(add_eul_or_reul("click"), "하면 실행됩니다")
print(add_eun_or_neun("K"), add_eul_or_reul("L"), "좋아했다")
print("2001~2020년 한국의", add_eun_or_neun("GDP"), "다음 그래프와 같다")
print(add_eun_or_neun("12"), "3보다 크다")
print(add_eun_or_neun(3), "6보다 작다")
print(add_eun_or_neun("『오리엔탈리즘』"), "이제는 고전에 반열에 오른 책이다")
print("연암은", add_eul_or_reul("『열하일기』"), "썼다")
```

## 활용 예제

다음과 같은 경우에 유용하게 적용할 수 있습니다.

```python
waiting_list = ["지현", "태호", "John", "Mr.Kennedy"]
for person in waiting_list:
    print(f"{person}{take_eun_or_neun(person)} 5분만 더 기다려주세요")

waiting_list = ["지현", "태호", "John", "Mr.Kennedy"]
for person in waiting_list:
    print(add_eun_or_neun(person), "5분만 더 기다려주세요")
```
