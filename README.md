# Korean Josa Python Module

This is a module to choose 'josa' in Korean language which has two different form, according to what comes before josa.  
음운 환경(즉 조사 앞에 오는 음절이 끝소리를 갖는지 아닌지)에 따라 이형태를 갖는 한국어 조사를 선택해주는 파이썬 모듈입니다.

## 테스트

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

다음과 같이 쓸 수 있습니다.

```python
waiting_list = ["지현", "태호", "John", "Mr.Kennedy"]
for person in waiting_list:
    print(f"{person}{take_eun_or_neun(person)} 5분만 더 기다려주세요")

waiting_list = ["지현", "태호", "John", "Mr.Kennedy"]
for person in waiting_list:
    print(add_eun_or_neun(person), "5분만 더 기다려주세요")
```
