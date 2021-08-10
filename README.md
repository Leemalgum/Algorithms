#### 📘 [한빛미디어] 이것이 취업을 위한 코딩 테스트다 with 파이썬 (나동빈 저)
## 반올림 함수
round(반올림 할 숫자, 표시할 소수점 자리)함수 

## 리스트 자료형 
여러 개의 데이터를 연속적으로 담아 처리하기 위한 자료형  
배열 혹은 테이블이라 부르기도 함  
빈 리스트 선언 -> list = []  
슬라이싱 -> list[시작 인덱스:끝 인덱스+1]  
리스트 컴프리헨션 -> array = [i for i in range(10) if i % 2 == 1]  
n X m 2차원 리스트 초기화 -> array = [[0] * m for _ in range(n)]

### 리스트 관련 메서드
<img width=70% alt="스크린샷 2021-08-07 오전 1 12 48" src="https://user-images.githubusercontent.com/60692335/128540410-2ea71f4f-ba86-46a1-9a44-6c7ab3a7b83c.png" />

-> 리스트에서 특정 값을 가지는 원소를 모두 제거하기
```
a = [1, 2, 3, 4, 5, 5]
remove_set = {3, 5} 집합 자료형
result = [i for i in a if i not in remove_set]
print(result)
실행 결과 = [1, 2, 4]
```

## 문자열
덧셈 -> 문자열이 더해져서 연결  
곱셈 -> 문자열이 그 값만큼 여러 번 덧셈  
lmmutable -> 인덱싱과 슬라이싱은 가능하지만 특정 인덱스의 값 변경은 불가 

## 튜플 자료형
리스트는 [] 튜플은 (), 기본 문법은 동일  
한 번 선언된 값은 변경 불가

### 사용하면 좋은 경우
서로 다른 성질의 데이터를 묶어서 관리해야 할 때 ex (비용, 노드 번호)  
데이터의 나열을 해싱의 키 값으로 사용해야 할 때 = 값 변경이 불가하기 때문에  
리스트보다 메모리를 효율적으로 사용해야 할 때

## 사전 자료형
키와 값의 쌍을 데이터로 가지는 자료형  
원하는 '변경 불가능한 자료형'을 키로 사용할 수 있음  
사전 자료형은 해시 테이블을 이용하므로 데이터의 조회 및 수정에 있어서 O(1)의 시간에 처리 가능  
사용 예시 -> 키 값('사과')로 데이터를 조회 할 수 있음
```
data = dict()
data['사과'] = 'Apple'
print(data)
실행 경과 = {'사과':'Apple'}
```

### 사전 자료형 메서드
변수명.keys()함수 -> 키 데이터만 뽑아서 리스트로 이용  
변수명.values()함수 -> 값 데이터만 뽑아서 리스트로 이용

## 집합 자료형
중복 허용 X, 순서 X -> 데이터의 존재 유무를 판단할 때 효율적  
리스트 혹은 문자열을 이용해 초기화 가능 -> set()함수 이용  
{}안에 ,를 기준으로 구분하여 삽입함으로써 초기화 가능  
데이터의 조회 및 수정에 O(1)시간에 처리 가능
```
data = set([1, 2, 3, 4])
data = {1, 2, 3, 4}
```

### 집합 연산
합집합 AUB = A|B  
교집합 AnB = A&B  
차집합 A-B = A-B  

### 집합 자료형 메서드
변수명.add(4)함수 -> 새로운 원소 추가  
변수명.update([5, 6])함수 -> 새로운 원소 여러개 추가  
변수명.remove(4)함수 -> 특정한 값을 갖는 원소 삭제  

### 사전 자료형과 집합 자료형의 특징
순서가 없기 때문에 인덱싱으로 값을 얻을 수 없음  
사전의 키 혹은 집합의 원소를 이용해 O(1)의 시간 복잡도로 조회  
이때 키나 원소의 값은 변경 불가한 문자열/튜플과 같은 객체를 사용해야 함

## 자주 사용되는 표준 입력 방법
input() -> 한 줄의 문자열을 입력받는 함수  
map() -> 리스트의 모든 원소에 각각 특정한 함수를 적용할 때 사용  
사용 예시 -> 공백 기준으로 데이터 입력 받을 시 = list(map(int, input()).split()))  
사용 예시 -> 공백 기준 데이터의 개수가 많지 않다면 = a, b, c = map(int, input().split())

## 빠르게 입력 받기
input()함수보다 빠르게 입력 받아야 할 경우 -> 많은 양의 데이터를 받을경우 시간초과가 날 수도 있음
```
import sys
data = sys.stdin.readline().rstrip()  
```
입력 후 엔터가 줄 바꿈으로 입력 되므로 rstrip() 메서드 함께 이용

## 자주 사용되는 표준 출력 방법
print()는 기본적으로 출력 이후 줄바꿈을 수행 -> end=" " 사용시 줄 바꿈 수행 X  

### f-string 예제
```
answer=7
print(f"정답은 {answer}입니다.")

실행경과 = 정답은 7입니다.
```

## 기타 연산자
리스트, 튜플, 문자열, 딕셔너리 모두 사용 가능
x in 리스트 -> 리스트 안에 x가 있을 때 참  
x not in 문자열 -> 문자열 안에 x가 없을 때 참

## pass 키워드
디버깅 과정에서 조건문의 형태만 만들어 놓고 처리 부분은 비워놓고 싶은 경우 사용  

## 조건부 표현식
if ~ else문을 한 줄에 작성할 수 있다
```
score = 85
result = "Success" if score >= 80 else "Fail"

print(result)
실행결과 = Success
```

## 조건문 내에서의 부등식
타 프로그래밍 언어와 다르게 조건문 내에서 0 < x < 20 과 같은 부등식을 그대로 사용할 수 있다  
대부분의 언어는 연산자가 여러 개일 경우 왼쪽부터 순차적으로 처리하기 때문에 제대로 된 조건문이 실행되지 않는다  

## 반복문 for문
```
for 변수 in 리스트:
  실행할 코드
```
연속적인 값을 순회할 때는 range(시작 값, 끝 값+1)를 사용  

## 함수
```
def 함수명(매개변수):
  실행할 코드
  return 반환 값
```

## global 키워드
global 키워드로 변수를 지정하면 해당 함수에서 지역 변수를 만들지 않고, 함수 바깥에 선언된 변수를 참조  
지역변수와 전연변수의 이름이 같다면 지역변수를 참조  

## 여러 개의 반환값
c언어처럼 구조체나 포인터의 사용없이 파이썬에서 함수는 여러 개의 반환 값을 가질 수 있다  

## 람다 표현식
<img width=60% alt="스크린샷 2021-08-10 오후 11 20 07" src="https://user-images.githubusercontent.com/60692335/128884428-e7bbd164-ebcf-42a5-923c-15eac497a754.png">
<img width=60% alt="스크린샷 2021-08-10 오후 11 21 37" src="https://user-images.githubusercontent.com/60692335/128884531-178875db-8a52-4330-aefb-69c8ceba8869.png">
<img width=60% alt="스크린샷 2021-08-10 오후 11 22 32" src="https://user-images.githubusercontent.com/60692335/128884564-cf99b2cc-a6c5-4884-9f5f-6d067e39b7ea.png">

## 실전에서 유용한 표준 라이브러리
<img width=70% alt="스크린샷 2021-08-10 오후 11 26 33" src="https://user-images.githubusercontent.com/60692335/128885477-4bef40e0-21f7-4903-b4da-ab0d981fc620.png">

## 자주 사용되는 내장 함수
sum()  
min(), max()  
eval() -> 사람이 사용하는 수식을 계산해줌  
sorted()  
sorted() with key  
<img width=70% alt="스크린샷 2021-08-10 오후 11 29 48" src="https://user-images.githubusercontent.com/60692335/128885532-d25fcaaa-0d9b-4564-b895-77e773c2a231.png">
<img width=70% alt="스크린샷 2021-08-10 오후 11 30 01" src="https://user-images.githubusercontent.com/60692335/128885578-5baa4fe7-24a0-4dfe-9517-02ffae6345f6.png">

## 순열과 조합
<img width=70% alt="스크린샷 2021-08-10 오후 11 32 10" src="https://user-images.githubusercontent.com/60692335/128886530-be9f01ca-c06a-474b-8c30-09d1145d5c60.png">
<img width=70% alt="스크린샷 2021-08-10 오후 11 33 02" src="https://user-images.githubusercontent.com/60692335/128886612-c486cfca-e188-491c-9de6-56759a6e522f.png">
<img width=70% alt="스크린샷 2021-08-10 오후 11 33 10" src="https://user-images.githubusercontent.com/60692335/128886858-f1466dd8-17f0-4178-a5bb-193468a5b760.png">
<img width=70% alt="스크린샷 2021-08-10 오후 11 33 20" src="https://user-images.githubusercontent.com/60692335/128886932-c6ad5f0f-daa6-4442-9472-b5b8ade06815.png">

## 중복 순열과 중복 조합
<img width=70% alt="스크린샷 2021-08-10 오후 11 33 32" src="https://user-images.githubusercontent.com/60692335/128886991-470100ba-2f40-47c7-ab49-e708f4983d77.png">

## Counter
<img width=70% alt="스크린샷 2021-08-10 오후 11 34 04" src="https://user-images.githubusercontent.com/60692335/128887031-e2f954d5-b4c1-45ad-b97a-3365f4c99013.png">

## 최대 공약수와 최소 공배수
<img width=70% alt="스크린샷 2021-08-10 오후 11 35 13" src="https://user-images.githubusercontent.com/60692335/128887080-17383bb5-ad39-48e2-a2fd-aa5fef0237ba.png">



