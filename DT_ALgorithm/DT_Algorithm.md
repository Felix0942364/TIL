# 2023 Jan 12

> TIL
> 
> > Today I Learned

## GIT

> 잘하면 되지 않을까요?
> 
> > 흔히 알듯 협업용 툴이다~~
> > 
> > 분산시스템으로 백업이 용이해서 손실의 위험을 줄일수가 있다~~

##

## MARKDOWN

> 공통적으로 어느정도의 기능을 가지는지 배워봅시다

### 기본적인 기능

#### 리스트에 대해서 더 알아볼까요?

우선은 리스트를 생성해 봅시다!

- abc
  
- cde
  
- 123
  
  1. 456
    
  2. 789
    

- 세개까지
  - 각각의 앞쪽 문양이
    - 다른걸 확인할수 있습니다.
      - 4번째부턴 동일해요

#### 코드블럭 작성을 알아볼까요?

문장 중에 코드블럭을 설명하자면? `python -V` 을 입력해서 확인해볼수가 있습니다

세따옴표 입력을 통해 코드블럭을 입력할수가 있습니다
세따옴표 옆에 활용 언어를 입력해주면 기능별 색상을 입혀 언어별 가독성을 높입니다.

```python
import abc
d = abc.split()
print(e==d)
```

#### 귀여운 고양이를 드릴게요

동일한 레포지토리 내의 문서로 이동하거나 외부 URL을 불러올수가 있습니다. [네이버](https://www.naver.com)

- 이미지를 가져와볼까요?![고양이](https://github.com/Felix0942364/TIL/blob/main/image_assets/Cat_August_2010-4.jpg)

- 다만 마크다운 문법 내에서 고양이의 높이 및 너비를 조절할수 없으므로
  
  - - 추후 HTML을 통해 추가는 가능합니다.

#### 글짜 꾸미기 기능을 써볼까요?

- **굵게** *꺾게* ~~취소선~~ ***굵고 꺾게*** ~~***굵꺾취***~~
- 또 10을 꾸며볼까요?
- superscript : 10<sup>2</sup>
- subscript : 10<sub>2</sub>
- in mathematical form : $10$
긴 가로선 작성은 한 행에 하이픈만을 세개 이상 입력함으로서 출력할수가 있습니다
---

#### Make Table

| 2   | 1   | 3   |
| --- | --- | --- |
| a   |     | b   |
| hungry |     | superhungry |

## CLI : Git Client

### git 문법
- Start git
  - 초기화 : `git init` : git local repository 초기화 
    - 로컬 레포지토리 생성 후 버전으로 관리할 파일을 `git add`로 단 한번이라도 staging area에 옮겨줘야 함 
      > 왜? : `git init`을 실행해도, git은 어떤 파일의 버전을 관리해야하는지 모른다. 
    - 파일의 상태 
      - 최초 생성시 : untracked
      - git add 후 : staged 상태
      - git commit 후 : tracked 상태
      - 파일의 수정이 있을 때 : modified
      - 최신이면 : up-to-date
  - `git add` : staging area 로 버전관리 할 파일 옮기기
    - git add .: 현재 위치한 w.d(working directory)에 생긴 모든 변화사항을 stage
    - git add {file name} : file를 지정해서 stage
  - `git commit -m '{commit msg}'`.
    - commit message : 해당 버전이 어떤 목적에서 생성 됐는지 입력 
      > 이유는 길이 제한이 있기 때문

**여기가지가 Local Repository에서 발생한 일들**
---
### Remote Repository (원격 레포지토리 / 깃허브)
> github는 결국에 온라인에서 원격 레포지토리를 제공해주는 웹서비스
- repository 연결 : `git remote add origin {remote_repo URL}`
- `git push origin master` : local -> remote upload
  > 최초 실행 시 인증 : remote repository에 push 할 권한 확인
- add -> commit -> push
# Jan 17

Control Statement
- 순차, 선택, 반복
- 파이썬은 기본적으로 위에서부터 아래로 차례대로 명령을 수행
- 특정 상황에 따라 코드를 선택적으로 실행(분기/조건)하거나 계속하여 실행(반복)하는 제어가 필요함
- 제어문은 순서도(flowchart)로 표현이 가능

## Code Style Guide

- 코드를 '어떻 작성할지'에 대한 가이드라인
- 파이썬에서 제안하는 스타일 가이드(강의에서 사용)
  - PEP8(https://www.python.org/dev/peps/pep-0008/)
- 각 회사/프로젝트마다 따로 스타일 가이드를 설정하기도 함
  - Google Style Guide(https://google.github.io/styleguide/pyguide.html) 등

틀린 예
```python
print('hello')
print("world")
a = 'apple'
if True:
  print(True)
else:
        print(False)
b='banana' 
```
옳은 예
```python
print('hello')
print('world')
a = 'apple'
if True:
  print(True)
else:
  print(False)
b = 'banana'
```
### 들여쓰기
- Space Sensitive
  - 문장을 구분할 때, 중괄호({,}) 대신 들여쓰기(indentation)을 사용
  - 들여쓰기를 할 때는 4칸(space 4번) 혹은 1탭(Tab키 1번)을 입력
    - 주의! 한 코드 안에서는 반드시 한 종류의 들여쓰기를 사용
    > !혼용 금지!
    - Tab으로 들여쓰면 계속 탭으로 들여써야 함
    > 그러나 tab은 경우에 따라 길이가 다름
    > 따라서 vscode에서는 tab을 space 4칸으로 자동적으로 변환해줌
    - 원칙적으로는 공백(빈칸, space) 사용을 권장 *PEP8 권장사항

## 조건문(Conditional Statement)
### 조건문 기본
조건문은 참/거짓을 판달할 수 있는 조건식과 함께 사용
> Flowchart를 활용하여 가시화하여 코드 작성 효율을 높일수 있음

#### 기본 형식
- 조건에는 참/거짓에 대한 조건식
  - 조건이 참인 경우 이후 들여쓰기 되어있는 코드 블록을 실행
  - 이외의 경우 else 이후 들여쓰기 되어있는 코드 블록을 실행
    - else는 선택적으로 활용할 수 있음
```python
if 조건 == True:
  # Run This Code Block
else:
  # Run this Code Block
```
#### 조건문 예시
```python
a = 5
if a > 5:
  print('5 초과')
else:
  print('5 이하')
print(a)
```
#### 조건문 실습 문제
- 조건문을 통해 변수 num의 값의 홀수/짝수 여부를 출력하시오.
  - 이때 num은 input을 통해 사용자로부터 입력을 받으시오.
```python
num = int(input('숫자 입력 : '))
if num % 2:
  print('홀수입니다')
else:
  print('짝수입니다')
```

### 복수 조건문
- 복수의 조건식을 활용할 경우 elif를 활용하여 표현함
```python
if 조건:
  # Code Block
elif 조건:
  # Code Block
elif 조건:
  # Code Block
else:
  # Code Block
```

#### 복수 조건문 실습 문제
- 미세먼지 농도에 따른 위험 등급이 다음과 같을때, dust 값에 따라 등급을 출력하는 조건식을 작성하시오
```python
dust = int(input('미세먼지 농도 입력 : '))
if dust > 150:
  print('미세먼지 농도 : 매우나쁨')
elif dust > 80:
  print('미세먼지 농도 : 나쁨')
elif dust > 30:
  print('미세먼지 농도 : 보통')
elif dust >= 0:
  print('미세먼지 농도 : 좋음')
else:
  print('미세먼지 농도 입력값을 확인해주세요.')
```

### 중첩 조건문
- 조건문은 다른 조건문에 중첩되어 사용될 수 있음
  > 들여쓰기에 유의하여 작성할 것!
```python
if 조건1 :
  # Codeblock
  if 조건2 :
    # Codeblock
else:
  # Codeblock
```
- 기존 미세먼지 코드에 300이 넘는 경우 '실외 활동을 자제하세요'를 추가로 출력
```python
dust = int(input('미세먼지 농도 입력 : '))
if dust > 150:
  print('매우나쁨')
  if dust > 300:
    print('실외활동을 자제하세요')
elif dust > 80:
  print('나쁨')
elif dust > 30:
  print('보통')
elif dust >= 0:
  print('미세먼지 농도 : 좋음')
else:
  print('미세먼지 농도 입력값을 확인해주세요.')
```

## 조건 표현식
- 조건 표현식(Conditional Expression)이란?
> 간단한 조건문을 한줄로 간결하기 표현하기 활용한다 할수 있음
  - 조건 표현식을 일반적으로 조건에 따라 값을 정할 때 활용
  - 삼항 연산자(Ternary Operator)로 부르기도함
  > true이 경우 값 if 조건 else false인 경우 값

### 조건 표현식 실습 문제
- value = num if num >= 0 else -num
  > 절대값을 저장하기 위한 코드

- 다음의 코드와 동일한 조건 표현식을 작성해볼까요?
```python
num = int(input('숫자 입력 : '))
if num % 2:
  print('홀수입니다')
else:
  print('짝수입니다')
```
```python
num = 3
value = '홀수입니다' if num % 2 else '짝수입니다' 
print(value)
```

- 다음의 코드와 동일한 조건 표현식을 작성해볼까요?
```python
num = -5
value = num if num>=0 else 0
print(value)
```
```python
num = -5
if num<0:
  num = 0
value = num
print(value)
```

## 반복문
- 특정 조건을 만족할 때까지 같은 동작을 계속 반복하고 싶을 때 사용
- 반복문의 종류
  - while 문
    - 해당 조건에 해당하는 코드를 통해 반복문을 종료시켜야함
  - for 문
    - 반복가능한 객체를 모두 순회하면 종료(별도의 종료 조건이 필요 없음)
  - 반복 제어
    - break, condition, for-else
### while문
- while 문은 조건식이 참인 경우 반복적으로 코드를 실행
  - 조건이 참인 경우 들여쓰기 되어 있는 코드 블록이 실행됨
  - 코드 블록이 모두 실행되고, 다시 조건식을 검사하며 반복저긍로 실행됨
  - while문은 무한 루프를 하지 않도록 종료 조건이 반드시 필요
```python
while 조건:
  # Code block
```
#### while문 예시
- 복합 연산자(In-Place Operator)
  - 복합 연산자는 연산과 할당을 합쳐 놓은 것
    - 예시) 반복문을 통해서 개수를 카운트 하는 경우
```python
a = 0
while a<5:
  print(a)
  a += 1
print('끝')
```

### for문
- for문은 시퀀스(string, tuple, list, range)를 포함한 순회 가능한 객체(iterable)의 요소를 모두 순회
> 종료문이 별도로 필요하지 않음
- iterable
  - 순회할 수 있는 자료형(string, list, dict, tuple, range, set 등)
  - 순회형 함수(range, enumerate)
```python
for 변수명 in iterable:
  #Codeblock
```
#### for문 예시
- list
```python
fruits = ['apple', 'mango', 'banana']
for fruit in fruits:
  print(fruit)
```
- string
```python
chars = str(input())
for idx in range(len(chars)):
  print(chars[idx])
```
- dictionary
```python
grades = {'john' : 80, 'eric' : 90}
for student in grades:
  print(student, grades([student]))
```
  - 추가적인 매서드를 활용한 dictionary 순회
  ```python
  grades = {'john' : 80, 'eric' : 90}
  for student, grade in grades.items():
    print(student, grade)
  ```
- enumerate()
  - 인덱스와 객체를 쌍으로 담은 열거형(enumerate) 객체 반환
    - (index, value) 형태의 tuple로 구성된 열거 객체를 반환
```python
members = ['민수', '영희', '철수']
for idx, number in enumerate(members):
  print(idx, number)
```
> enumberate(iterable, start=0)
```python
seasons = ['Spring', 'Summer', 'Fall', 'Winter']
list(enumerate(seasons))
list(enumerate(seasons, start = 1))
```
- enumerate의 함수를 들여다보면 다음과 같다
```python
def enumerate(sequence, start = 0):
  n = start
  for elem in sequence:
    yield n, elem
    n+=1
```

#### List Comprehension
- 표현식과 제어문을 통해 특정한 값을 가진 리스트를 간결하게 생성하는 방법
> [code for 변수 in iterable]
> [code for 변수 in iterable if 조건식]
```python
cubic_list = []
for number in range(1,4):
  cubic_list.append(number ** 3)
print(cubic_list)
```
```python
cubic_list = [number ** 3 for number in range(1,4)]
print(cubic_list)
```
#### Dictionary Comprehension
- 표현식과 제어문을 통해 특정한 값을 가진 dictionary를 간결하게 생성하는 방법
> {key : value for 변수 in iterable}
> {key : value for 변수 in iterable if 조건식}
```python
cubic_dict = {}
for number in range(1,4):
  cubic_dict[number] = number ** 3
print(cubic_dict)
```
```python
cubic_dict = {number : number ** 3 for number in range(1,4)}
print(cubic_dict)
```

### 반복문 제어
- break
  - 반복문을 종료
- continue
  - continue이후의 코드 블록은 수행하지 않고, 다음 반복을 수행
- for-else
  - 끝가지 반복문을 실행한 이후에 else 문 실행
    - break를 통해 중간에 종료되는 경우 else 문은 실행되지 않음
- pass
  - 아무것도 하지 않음(문법적으로 필요하지만, 할 일이 없을 때 사용)
  > 다음의 예시에서 pass문을 사용하지 않았을 경우에는 if문에서 `IndentationError: expected an indented block` 에러가 발생
  ```python
  def class:
    pass
  n = 10
  if n >10:
    pass
    # write code later
  ```
#### break
- break문을 만나면 반복문은 종료됨
```python
n = 0
while True:
  if n == 3:
    break
  print(n)
  n += 1
```
```python
for i in range(10):
  if i > 1:
    print('only 0 & 1 is needed')
    break
  print(i)
```
#### continue
- continue 이후의 코드 블록은 수행하지 않고, 다음 반복을 수행
```python
for i in range(6):
  if i % 2 == 0:
    continue
  print(i)
```
#### else
- 끝까지 반복문을 실행한 이후에 else문 실행
```python
for char in 'apple':
  if char == 'b':
    print('b!')
    break
else:
  print('b가 없습니다.')
```
```
b가 없습니다.
```
```python
for char in 'apple':
  if char == 'b':
    print('b!')
    break
else:
  print('b가 없습니다.')
```
```
b!
```
# Jan 18
## Function
### Function Intro
Why use Functions? Functions are used mainly for the sake of 2 reasons
1. Decomposition(분해)
> 기능을 분해하고 재사용 가능하게 만듦
2. Abstraction(추상화)
> 복잡한 내용을 모르더라도 사용할수 있도록 재사용성과 가독성, 생산성을 높임

#### Decomposition

`len([1,2,3])`를 구현하면 아래와 같이 됨.

```python
numbers = [1,2,3]
count = 0
for i in numbers:
  count += 1
return count
```

`sum([1,2,3])`를 구현하면 아래와 같이 됨
```python
numbers = [1,2,3]
sum = 0
for i in numbers:
  sum += i
return sum
```

#### Abstraction
- 자주 사용하는 `print('hello')는 어떻게 구현할 수 있을까요?
- 내부 구조를 변경할게 아니라면 함수 내부가 어떻게 생겼는지 몰라도 무방
> 스마트폰의 원리를 몰라도 우리는 사용할 수 있음

### 함수의 종류
- 함수는 크게 3가지로 분류
  - 내장 함수(built-in function)
    - 파이썬에 기본적으로 포함된 함수
    > https://docs.python.org/3/library/functions.html
  - 외장 함수(External Functions)
    - import 문을 통해 사용하며, 외부라이브러리에서 제공하는 함수
    > sys, pickle, Os, shutil, Glob, Tempfile, Time, Calendar, Random ......
  - 사용자 정의 함수
    - 사용자 정의 함수

- 함수의 정의
  - 특정 기능을 하는 코드의 조각(묶음)
  - 특정 코드를 매번 다시 작성하지 않고, 필요시에만 호출하여 간편히 사용

### 함수 기본 구조
- 선언과 호출(define & call)
- 입력(Input)
- 문서화(Docstring)
- 범위(Scope)
- 결과값(Output)

#### 선언과 호출(define & call)
- 함수의 선언은 def 키워드를 활용함
- 들여쓰기를 통해 Function Body(실행된 코드 블록)을 작성함
  - Docstring은 함수 body 아에 선택적으로 작성 가능
  > 작성시에 첫번째 문장에 문장열 '''''' 사용
- 함수 parameter을 넘겨줄수 있음
- 함수는 동작 후에 return을 통해 결괏값을 전달함

### Function 결과값의 종류
1. Void function
  - 명시적인 return 값이 없는 경우, None을 반한하고 종료
2. Value returning function
  - 함수실행 후, return문을 통해 값 반환
  - return을 하게 되면, 값 반환 후 함수가 바로 종료
```python
a = print('hello world')
b = float('3.14')

print(a) # None
print(b) # 3.14
```
> ex
```python
def void_product(x,y):
  print(f'{x} x {y} = {x * y}')

void_product(4,5) # 4 x 5 = 20
ans = void_product(4,5) # 4 x 5 = 20
print(ans) #
```
```python
def value_returning_product(x,y):
  return x * y
value_returning_product(4,5) #
ans = value_returning_product(4,5) #
print(ans) # 20
```
#### 두 개 이상의 반환값 받기
다음 코드의 문제점은?
```python
def minus_and_product(x,y):
  return x - y
  return x * y

y = minus_and_product(4, 5)
print(y)
```
오로지 x - y 값만을 반환하는 것을 볼수 있다.
이는 함수 내부에서 첫번째 return 값만을 반환하고 함수를 종료하기 때문이다.
두가지의 값을 반환하고자 한다면 다음과 같이 작성하여야 한다.
```python
def minus_and_product(x,y):
  return x - y, x * y

y = minus_and_product(4, 5)
print(y) # (-1, 20)
print(type(y)) # <class 'tuple'>
```
> 튜플로 묶인 반환값을 받을 수가 있다.

#### 함수 반환 정리
- return X => None
- return O => 값 하나를 반환
- 여러 개의 반환을 원한다면 컨테이너를 활용한다
```python
word_list = ['우영우', '기러기', '별똥별', '파이썬']
def is_palindrome(word_list):
  palindrome_list = []
  for word in wordlist:
    if word == word[::-1]:
      palindrome_list.append(word)
  return palindrome_list
print(is_palindrome(word_list))
```

### Parameter & Argument
- Parameter : 함수를 정의할 때, 함수 내부에서 사용되는 변수
- Argument : 함수를 호출 할 때, 넣어주는 값
```python
def function(ham): # parameter: ham
  return ham
function('spam') # argument : 'spam'
#함수 return 값 : spam
```
#### Argument
- Argument란?
  - 함수 호출 시 함수의 parameter을 통해 전달되는 값
    - Argument는 소괄호 안에 할당 func_name(argument)
      - 필수 Argument : 반드시 전달되어야 하는 argument
      - 선택 Argument : 값을 전달하지 않아도 되는 경우는 기본값이 전달
> https://binaryworld.tistory.com/18

##### Positional Arguments
- 기본적으로 함수 호출 시 Argument는 위치에 따라 함수 내에 전달됨
```python
def add(x,y)
  return x + y
add(2,3)
#=>
#def add(x, y):
  # x = 2 y = 3
  # return x + y
```
##### Keyword Arguments
- 직접 변수의 이름으로 특정 Argument를 전달할 수 있음
- Keyword Argument 다음에 Positional Argument를 활용할 수 없음
```python
def add(x, y):
  return x + y
add(x = 2, y = 5)
add(2, y = 5)
add(x = 2, 5) # ERROR 발생
```
##### Default Arguments Values
- 기본값을 지정하여 함수 호출 시 argument 값을 설정하지 않도록 함
  - 정의된 것보다 더 적은 개수의 argument 들로 호출될 수 있음
```python
def add(x, y = 0):
  return x + y
add(2)
# def add(x, y=0):
#   x = 2, y = 0
#   return x + y
```

### Python의 범위(Scope)
- 함수는 코드 내부에 local scope를 생성하며, 그 외의 공간인 global scope로 구분
- scope
  - global scope : 코드 어디에든 참조할 수 있는 공간
  - local scope : 함수가 만든 scope. 함수 내부에서만 참조 가능
- variable
  - global variable : global scope에 정의된 변수
  - local variable : local scope에 정의된 변수
- global과 local에 정의돼 있는 변수를 호출하고자 한다면?
> print(globals())
> print(locals())
> 함수 내에서 탐색 가능한 모든 전역변수 혹은 지역변수를 출력해준다

#### 변수 수명주기(lifecycle)
- 변수는 각자의 수명주기(lifecycle)가 존재
  - built-in scope
    - 파이썬이 실행된 이후부터 영원히 유지
    > 예를들면 time과 같은 built in 함수 내부에 존재하는 변수
  - global scope
    - 모듈이 호출된 시점 이후 혹은 인터프리터가 끝날 때까지 유지
  - local scope
    - 함수가 호출될 때 생성되고, 함수가 종료될 때까지 유지
- 함수에서 변수를 통해 값을 불러올 경우 해당 local 내에 새롭게 값을 정의함

```python
def func():
  a = 20
  print('local', a) # local 20

func()
print('global', a) # NameError : name 'a' is not defined
```
> a는 local scope에서만 존재

#### 이름 검색 규칙(Name Resolution)
- 파이썬에서 사용되는 이름(식별자)들은 이름공간(namespace)에 저장돼 있음
- 아래와 같은 순서로 이름을 찾아나가며, LEGB Rule이라고 부름
  - Local scope : 지역 범위(현재 작업 중인 범위)
  - Enclosed scope : 지역 범위 한 단계 위 범위
  > 함수 내 함수의 경우 enclosed scope으로 구분함
  - Global scope : 최상단에 위치한 범위
  - Built-In scope : 모든 것을 담고 있는 범위(정의하지 않고 사용할 수 있는 모든 것)
  > ex) print()
- 함수 내에서는 바깥 Scope의 변수에 접근 가능하나 수정은 할 수 없음

##### 예시1
```python
print(sum) # <built-in function sum>
print(sum(range(2))) # 1
sum = 5
print(sum) #5
print(sum(range(2))) # TypeError : 'int' object is not callable
```
> Global Scope 이름공간의 sum 변수에 값 5가 할당
> 이후 global scope에서 sum은 LEGB에 의해 Built-in scope의 내장 함수보다 5가 먼저 탐색

##### 예시2
```python
a = 0 # a에 0 할당
b = 1 # b에 1 할당
def enclosed(): # enclosed 함수 정의
  a = 10 # enclosed 내 a = 10 할당
  c = 3 # enclosed 내 c = 3 할당
  def local(c): # enclosed 함수 내 local 함수 정의
    print(a,b,c) # local scope에서는 외부 scope의 변수를 읽어오는 것이 가능하다
    # ex) 우리는 global scope에서 built-in scope의 함수들을 호출할 수가 있다 
  local(300) # 10, 1, 300
  print(a,b,c) # 10, 1, 3
enclosed() # enclosed 함수 호출
print(a,b) # 0, 1
```

##### 예시3
```python
my_list = [1,2,3,4]

def func1():
  my_list[1] = 5554

func1()
print(my_list)
# [1, 5554, 3, 4]
```
> func1 내에 my_list[1]가 정의되지 않으므로 global의 my_list를 가져온다
> 이후 global의 my_list[1]을 5554로 변환했기 때문에 [1, 5554, 3, 4]가 출력됨

##### 예시4
```python
my_list = [1, 2, 3, 4]

def func1():
  my_list = [5, 6, 7]
  print(my_list) # [5, 6, 7] 
func1()
print(my_list)
# [1, 2, 3, 4]
```

##### 예시4
```python
x = 3
def func1():
  x = 2
  def func2():
    global x
    x = 3
    print(x)
  func2()
  print(X)

func1()
print(x)
```
> '3\n2\n3' 출력

#### Global 문
- 현재 코드 블록 전체에 적용되며, 나열된 식별자(이름)이 global variable임을 나타냄
  - global에 나열된 이름은 같은 코드 블록에서 global 앞에 등장할 수 없음
  - global에 나열된 이름은 parameter, for 루프대상, 클래스/함수 정의 등으로 정의되지 않아야 함
```python
# 함수 내에서 글로벌 변수 변경하기
a = 10
def func1():
  global a
  a = 3

print(a) # 10
func1()
print(a) #3
```
> Local scope에서 global 변수 값의 변경
> Global 키워드를 사용하지 않으면, Local scope에 a 변수가 생성됨

##### Global 관련 에러
global 변수 사용 제한 예시
1. 예시
```python
# global 주의 사항
a = 10
def func1():
  print(a) # global a 선언 전에 사용
  global a
  a = 3

print(3) # 10
func1()
print(a) 
# SyntaxError:name 'a' is used prior to global declaration 
```
2. 예시
```python
# global 주의 사항
a = 10
def func1(a):
  global a # parameter에 global 사용 불가
  a = 3

print(a) # 10
func1()
print(a) 
# SyntaxError:name 'a' is parameter and global 
```

#### nonlocal
- global을 제외하고 가장 가까운 (둘러싸고 있는) scope의 변수를 연결하도록 함
  - nonlocal에 나열된 이름은 같은 코드 블록에서 nonlocal 앞에 등장할 수 없음
  - nonlocal에 나열된 이름은 parameter, for 루프 대상, 클래스/함수 정의 등으로 정의되지 않아야 함
- global과는 달리 이미 존재하는 이름과의 연결만 가능함

##### nonlocal 예시
```python
x = 0
def func1():
  x = 1
  def func2():
    nonlocal x
    x = 2
  func2()
  print(x) # 2

func1()
print(x) # 0
```

##### nonlocal 예시 2
```python
def func1():
  x = 10
  def func2():
    nonlocal x
    x = 20
  func2()
  print(x) # 20

func1()
print(x) # NameError : name 'x' is not defined
```

#### nonlocal, global 비교
nonlocal은 이름공간(namespace)상에 존재하는 변수만 가능함
```python
# 선언된 적 없는 변수의 활용
def func1():
  global out
  out = 3

func1()
print(out)
```
```python
# 선언된 적 없는 변수의 활용
def func1():
  def func2():
    nonlocal y
    y = 2
  func2()
  print(y)

func1()
# SyntaxError: no binding for nonlocal 'y' found
```

#### ***함수의 범위 주의***
- 기본적으로 함수에서 선언된 변수는 Local scope에 생성되며, 함수 종료 시 사라짐
- 해당 scope에 변수가 없는 경우 LEGB rule에 의해 이름을 검색함
  - 변수에 접근은 가능하지만, 해당 변수를 수정할 수 없음
  - 값을 할당하는 경우 해당 scope의 이름공간에 새롭게 생성되기 때문
  - ***단, 함수 내에서 필요한 상위 scope 변수는 argument로 넘겨서 활용할 것***
- 상위 scope에 있는 변수를 수정하고 싶다면 global, nonlocal 키워드를 활용 가능
  - 단, 코드가 복잡해지면서 변수의 변경을 추적하기 어렵고, 예기치 못한 오류가 발생
  - 가급적 사용하지 않는 것을 권장하며, ***함수로 값을 바꾸고자 한다면 항상 argument로 넘기고 리턴 값을 사용하는 것을 추천***
# Jan 26
데이터 구조란?
- 여러 데이터를 효과적으로 사용, 관리하기 위한 구조
- 파이썬에는 대표적으로 List, Tuple, Dict, Set 등의 데이터 구조가 있음
## 순서가 없는 데이터 구조
### 셋(set)
- Set이란 중복되는 요소가 없이, 순서에 상관없는 데이터들의 묶음
  - 데이터의 중복을 허용하지 않기 때문에 중복되는 원소가 있다면 하나만 저장
  - 순서가 없기 때문에 인덱스를 이용한 접근이 불가능
- 수학에서의 집합을 표현한 컨테이너
  - 집합 연산이 가능(여집합을 표현하는 연산자는 별도로 존재 X)
  - 중복되는 값이 존재하지 않음
- 담고 있는 요소를 삽입 변경, 삭제 가능 -> 가변 자료형 (mutable)

#### Set Method
> [https://docs.python.org/ko/3/tutorial/datastructures.html](https://docs.python.org/ko/3/tutorial/datastructures.html)
- set.add(element)
> set에 값을 추가
- set.update(*others)
> set에 *others에 없는 값을 추가합니다. update는 return 값이 없으며, set을 변형시키기 때문에, set.union가 상이함
- set.remove(element)
> set에서 삭제하고, 없으면 ***KeyError*** 발생
- set.dicard(element)
> element 항목 제거
- set.pop()
> 임의의 원소를 제거해서 반환하지만, set의 경우 원소들의 ascii 코드에 따른 배열을 차용하고 있다
> 따라서 pop을 하게 될 경우 ascii 코드의 마지막에 해당되는 값을 반환하며 제거한다
- set.clear()
> 모든 항목 제거
- set.isdisjoint(t)
> set과 t 가 서로소일 시 True 반환
- set.issubset(t)
> set 이 t의 부분집합일 경우 True 반환
- set.issuperset(t)
> set이 t의 모집합일 경우 True 반환

### 딕녀너리
딕셔너리란?
- 키-값(key-value) 쌍으로 이뤄진 자료형(3.7 초과 버전은 순서 존재, 3.7이하는 순서 없음)
- Dictionary의 키
  - key는 변형이 불가능한 데이터(immutable)만 활용 가능
    - string, integer, float, boolean, tuple, range
- 각 키의 값(values)
  - 형태 : Any

#### Dictionary Method
|문법|설명|
|---|---|
|d.clear()|모든 항목을 제거|
|d.copy()|딕셔너리의 d의 얕은 복사본을 반환|
|d.keys()|딕셔너리 d의 모든 키를 담은 뷰를 반환|
|d.values()|딕셔너리 d의 모든 값을 담은 뷰를 반환|
|d.items()|딕셔너리 d의 모든 키-값의 쌍을 담은 뷰를 반환|
|d.get(k)|k의 값을 반환하는데, k가 d에 없을 경우 None 반환|
|d.get(k,v)|k의 값을 반환하는데, k가 d에 없을 경우 v을 반환|
|d.pop(k)|k의 값을 반환하고, k의 항목을 d에서 삭제, k가 없을 경우 ***KeyError***|
|d.pop(k,v)|k의 값을 반환하고, k의 항목을 d에서 삭제, k가 없을 경우 v반환|
|d.update(other)|딕셔너리 d의 값을 매핑하여 업데이트|

#### d.get(key[,default])
- key를 통해 value를 가져옴
- ***KeyError***가 발생하지 않으며, default 값을 설정할 수 있음(기본 : None)
```python
my_dict = {'apple' : 사과, 'banana' : '바나나'}
my_dict['pineapple'] # KeyError: 'pineapple'

my_dict = {'apple' : 사과, 'banana' : '바나나'}
print(my_dict.get('pineapple')) # None
print(my_dict.get('apple')) # 사과
print(my_dict.get('pineapple', 0)) # 0
```

#### d.pop(key[,default])
- key가 dictionary에 있으면 제거하고 해당 값을 반환
- 그렇지 않으면 default를 반환
- default 값이 없으면 ***KeyError***
```python
my_dict = {'apple' : '사과', 'banana' : '바나나', 'coconut' : '코코넛'}
data = my_dict.pop('apple')
print(data, my_dict) # 사과 {'banana' : '바나나', 'coconut' : '코코넛'}

data = my_dict.pop('pineapple', 0) # 0
data = my_dict.pop('pineapple') # KeyError : 'pineapple'
```

#### d.update()
- 값을 제공하는 key,value로 덮어씁니다.
```python
my_dict = {'apple':'사과', 'banana':'바나나'}
my_dict.update('apple' = '사과')
print(my_dict)
```

## 얕은 복사와 깊은 복사(Shallow Copy & Deep Copy)
### 자료형과 메모리
데이터 10을 컴퓨터가 기억하는 과정
  1. 10을 저장할 공간을 메모리에 만들고
  2. 저장할 공간에 대한 주소를 할당받는다
  3. 할당 받은 주소를 기억했다가
  4. 10이라는 데이터를 해당 주소로 찾아가서 저장한다.
  5. 이후에 10이 필요해지면 해당 주소로 가서 읽어온다

### 기존 변수 사용 과정에서의 문제점?
하나의 기억에, 하나의 주소가 필요 
- 100개의 의변수를 저장하려면 주소 100개가 필요함
- 여러 기억을 하나의 주소로 찾아갈 수 있도록 할 수 없나?
  - 연속적인 공간에 데이터를 저장되도록 함
  - 예시로 list와 같은 자료형의 경우 맨 처음 기억의 주소만 가지고 있음 나머지 정보에 접근이 가능함

- 하지만 동일한 변수를 저장하고자 하다면 추가적인 메모리를 할당해줄 필요가 있음
```python
a = [10, 20, 45]
b = a
b[0] = 99
print(a) # [99, 20, 45]
```
> a와 b의 object가 동일한 상황이기 때문에, b라는 변수를 변형할 경우, a에도 변형이 발생하는 것을 볼수 있음.
> b에 추가적인 list를 할당하고자 한다면? *Deep Copy*

### 복사 방법
- 할당 (Assignment)
- 얕은 복사 (Shallow copy)
- 깊은 복사 (Deep copy)

#### 할당(assignment)
- 대입 연산자 (=)
  - List 복사 확인하기
```python
original_list = [1,2,3]
copy_list = original_list
print(original_list, copy_list)

copy_list[0] = 'hello'
print(original_list, copy_list) # ['hello', 2, 3] ['hello', 2, 3]
```
> 대입 연산자(=)를 통한 복사는 해당 객체에 대한 객체 참조를 복사
> 동일한 객체를 참조했기 때문에 해당 주소의 값을 변형할 경우 할당한 모든 변수에 영향을 미침

#### 얕은 복사(shallow copy)
Slice 연산자 활용하여 같은 원소를 가진 리스트지만 연산된 결과를 복사 (다른 주소)
```python
a = [1,2,3]
b = a[:]
print(a, b) # [1,2,3] [1,2,3]
b[0] = 5
print(a, b) # [1,2,3] [5,2,3]
```

##### 얕은 복사(shallow copy) 주의사항
- 복사하는 리스트의 원소가 주소를 참조하는 경우
```python
a = [1,2, ['a', 'b']]
b = [:]
print(a,b) # [1, 2, ['a', 'b']] [1, 2, ['a', 'b']] 
b[0] = 5
b[2][0] = 0
print(a,b) # [1, 2, [0, 'b']] [5, 2, [0, 'b']] 
```

#### 깊은 복사(Deep Copy)
```python
import copy
a = [1,2, ['a', 'b']]
b = copy.deepcopy(a)
print(a,b) # [1, 2, ['a', 'b']] [1, 2, ['a', 'b']] 
b[0] = 5
b[2][0] = 0
print(a,b) # [1, 2, ['a', 'b']] [5, 2, [0, 'b']] 
```

### 결론
- 리스트를 복사하고 싶다는 욕망이 든다면 리스트 변화를 확인할 것
- 그렇다면 copy.deepcopy()만 쓰면 되는가?
  > 메모리 용량 증가, 무거운 프로그램
# Jan 30
객체지향 프로그래밍(Object-Oriented Programming, OOP)은 컴퓨터 프로그래밍의 패러다임 중 하나
객체 지향 프로그래밍은 컴퓨터 프로그램을 명령어의 목록으로 보는 시각에서 벗어나 여러개의 도립된 단위, 즉 "객체"들의 모임으로 파악하고자 하는것.
각각의 메시지를 주고받고, 데이터를 처리할 수 있음.
## 절차 지향 프로그래밍
하드웨어가 발전함에 따라 소프트웨어도 점점 커지고 복잡한 설계가 요구됨
하드웨어의 발전 속도를 소프트웨어의 발전 속도가 따라가지 못함

절차지향 방법론은 생산성이 너무 낮다! 어떻게 하지?
'절차'대신 핵심이 되는 '데이터'를 중심으로 생각하기

데이터를 중심으로 절차를 도입해서, 현실의 사물을 나타내고,
이런 것들을 조립하는 방식으로 개발하자 == OOP

## 객체지향 프로그래밍
개체지향 프로그래밍이란?
- 프로그램을 여러 개의 독립된 객체들과 그 객체 간의 상호작용으로 파악하는 프로그래밍 방법
- 예시
  - 콘서트
    * 가수 객체
    * 감독 객체
    * 관객 객체

```python
class Person:
  def __init__(self, name, gender):
    self.name = name
    self.gender = gender

  def greeting(self):
    print(f"안녕하세요, {self.name}입니다")

jimin = Person('지민', '남')
jimin.greeting() # 안녕하세요, 지민입니다.

jieun = Person('아이유', '여')
jieun.greeint() # 안녕하세요, 아이유입니다.
```

### 객체 지향의 장점 / 단점
장점
- 객체는 잘 만들어놓으면 계속해서 재사용이 가능!
- 객체는 그 자체로 데이터와 행동이 정의됨(독립적) == 개발자가 내부 구조를 몰라도 그냥 가져다가 다른 객체와 조립하면서 개발이 가능
- 객체 단위로 모듈화시켜 개발할 수 있으므로 많은 인원이 참여하는 대규모 소프트웨어 개발 가능
- 개발 용이성, 유지 보수 편의성, 신뢰성을 바탕으로 생산성이 대폭 증가

단점
- 설계 시 많은 노력과 시간이 필요함
  - 다양한 객체들의 상호 작용 구조를 만들기 위해 많은 시간과 노력이 필요
- 실행 속도가 상대적으로 느림
  - 절차 지향 프로그래밍이 컴퓨터의 처리구조와 비슷해서 실행 속도가 빠름

## 객체
컴퓨터 과학에서 객체 또는 오브젝트는 클래스에서 정의한 것을 토대로 메로리(실제 저장공간)에 할당된 것으로 프로그램에서 사용되는 데이터 또는 식별자에 의햇 참조되는 공간을 의미하녀, 변수, 자료 구조, 함수 또는 메서드가 될 수 있음

객체
속성과 행동으로 구성된 모든 것
# Jan 31
객체지향의 핵심 4가지
1. 추상화 : 핵심이 되는 부분만 추리기
2. 상속 : 코드의 재사용성을 높이고 기능을 향상
3. 다형성 : 각자의 속성에 따라 다른 결과 만들기
4. 캡슐화 : 데이터 보호하기

## 추상화
현실 세계를 프로그램 설계에 반영
- 복잡한 것은 숨기고, 필요한 것만 드러내기
```python
class Student:
  def __init__(self, name, age, gpa):
    self.name = name
    self.age = age
    self.gpa = gpa

  def talk(self):
    print(f'반갑습니다. {self.name}입니다.')

  def study(self):
    self.gpa += 1
    

```

## and, or 비교연산자

a and b
|a|b|result|
|---|---|---|
|F|F|a|
|F|T|a|
|T|T|b|
|T|F|b|

a or b
|a|b|result|
|---|---|---|
|F|F|b|
|F|T|b|
|T|T|a|
|T|F|a|

and 와 or 연산자의 반환값은 최종적으로 판별한 구문을 반환합니다.

ex)
and의 경우
if a:
  if b:
    pass
  return b
return a

or 의 경우
if a:
  return a
return b
# Feb 9
String Searching Algorithms.
[https://en.wikipedia.org/wiki/String-searching_algorithm](https://en.wikipedia.org/wiki/String-searching_algorithm)

## Introduction
In computer science, string-searching algorithms, sometimes called string-matching algorithms are an important clss of string algorithms that try to find a place where one or several strings(also called patterns) are found within a larger string or text.
A basic example of string searching is when the pattern and searched text are arrays of elements of an alphabet (finite set) Σ.  Σ may be a human language alphabet, for example, the letters A~Z and other applications may use a binary alphabet(Σ={0,1}) or as DNA alphabet(Σ={A,C,G,T}) in bioinformatics.
In practice, the method of feasible string-search algorithm amy be affected by the string encoding. In particular, if a variable-width encoding is in use, then it may be slower to find the Nth character, perhaps requiring time proportional to N. this may significantly slow some search algorithms. one of many possible solutions is to search for the sequence of code units instead, but doing so may produce false matches unless the encoding is specifically designed to avoid it.

## Overview
The most basic case of string seraching involves on(often very long) string, sometimes called the haystack, and one (often very short) string, sometimes called the needle. The goal is to find one or more occurrences of the needle within the haystack. For example, one might search for to within:
```
Some books are to be tasted, others to be swallowed, and some to be chewed and digested.
```
One might request the first occurrence of "to", which is the fourth word; or all occurrences, of which there are 3; or the last, which is the fifth word from the end.
Very commonly, however, various constraints are added. For example, one might want to match the "needle" only where in consists of one(or more) complete words -- perhaps defined as not having other letters immediately adjacent on either sid. In that case a search for "hew" or "low" should fail for the example sentence above, even though those literal strings do occur.
Another common example involves "normalization". For many purposes, a search for a phrase such as "to be" shoud succeed even in places where there is something else intervening between the "to" and the "be"
- More than one space
- Other "whitespace" characters such as tabs, non-breaking spaces, line-breaks, etc.
- Less commonly, a hyphen or soft hyphen
- In structured texts, tags or even arbitrarily large but "parenthetical" things such as footnotes, list-nubers or other marker, embedded images, and so on.

Many symbol systems include characters that are synonymous(at least for some purposes):
- Latin-based  alphabets distinguis lower-case from upper-case, but for many purposes string search is expected to ignore the distiction.
- Many languages include ligatures, where one composite character is equivalent to two or more other characters.
- Many writing systems involve diacritical marks such as accents or vowel points, which may vary in their usage, or be of varying importance in matching.
- DNA swequences can invove non-coding segments which may be ignored for some purposes, or polymorphisms that lead to no chagne in the encoded proteins, which may not count as a true difference for some other purposes.
- Some languages have rules where a different character or form of character must be used at the star, middle, or end of words.
Finally for strings that represent natural language, aspects of the language itself become invovled. For example one mgith wish to find all occurrences of a "word" despite it having alternate spellings, prefixes or suffixes, etc.
Another more complex type of search is regular expression searching, where the user constructs a pattern of characters or other symbols, and any match to the patter should fulfill the serach. For example, to catch both the Amercian English word "color" and the British equivalent "colour", instead of search for two different literal strings, one might use a regular expression such as:
```
colou?r
```
where the "?" conventionally makes the rpeceding character ("u") optional.
This article mainly discusses algorithms for the simpler kinds of string searching.
A similar problem in the field of bioinformatics and genomics is the maximal exact matching(MEM). Given two strings, MEMs are common substrings that cannot be extended left or right without causing a mismatch.

## Examples of search algorithms
### Naive string serach
A simple and inefficient way to see where one string occurs inside another is to check at each index, one by one. First, we see if there's a copy of the needle starting at the first character of the haystackk; if not, we look to see if there's a copy of the needle starting at the second character of the haystack, and so forth. In the normal case, we only have to look at one or two characters for each wrogn position to see that is a wrong position, so in the average case, this takes O(n+m) steps, where n is the length of the haystack and m is the length of the needle; but in the worst case, each for a string like "aaaab" in a string like "aaaaaaaaaaaaaaab", it takes O(nm)

### Finite-state-automaton-based search
In this approach backtracking is avoided by constructing a deterministic finite automato(DFA) that recognizes stored search string. These are expenseive to construct --- they are usually created using the powerset construction -- but are very quick to use for [example](https://en.wikipedia.org/wiki/File:DFA_search_mommy.svg), the DFA shown to the right recognizes the word "MOMMY". This approach is frequently generalized in parctice to search for arbitrary regular expressions.

### Stubs
Knuth-Morris-Pratt(KMP) computes a DFA that recognizes inputs with the string to search for as a suffix, Boyer-Moore starts searching from the end of the neelde, so it can usually jum ahead a whole needle-length at each step. Baeza-Yates keeps track of whether the previous *j* characters were a prefix of the serach string, and is therefore adaptable to [fuzzy string searching](https://en.wikipedia.org/wiki/Approximate_string_matching). The [bitap algorithm](https://en.wikipedia.org/wiki/Bitap_algorithm) is an application of Baeza-Yates approach.

### Index methods
Faster serach algorithms preprocess the text. After building a substring index, for example a suffix tree or suffix array, the occurrences of a pattern can be found quickly. As an example, a suffix tree can be built in O(n) time, and all *z* occurrences of a pattern can be found in underneath them. The latter can be accompished by running a DFS algorithm form the root of the suffix tree.

### Other variants
Some search methods, for instance [trigram search](https://en.wikipedia.org/wiki/Trigram_search)

## Classification of serach algorithms
### Classification by a number of patterns
The various algorithms can be classified by the number of patterns each used

#### Single-pattern algorithms
In the following compiation, *m* is the length of the pattern, *n* the length of the serachable text, and *k* = |Σ| is the size of the alphabet.

|Algorithms|Preprocessing time|Matching time|Space|
|---|---|---|---|
|Naive Algorithm|none|Θ(mn)|none|
|Knuth-Morris-Pratt|Θ(m)|Θ(n)|Θ(m)|
|Boyer-Moore|Θ(m+k)|Ω(n/m) at best, O(mn) at worst|Θ(k)|
|Two-way algorithm|Θ(m)|O(n)|O(1)|
|Backward Non-Deterministic DAWG Matching(BNDM)|O(m)|Ω(n/m) at best, O(mn) at worst|---|
|Backward Oracle Matching(BOM)|O(m)|O(mn)|---|
The [Boyer-Moore](https://en.wikipedia.org/wiki/Boyer%E2%80%93Moore_string-search_algorithm) string-searching algorithm has been the standard benchmark for the practical string-serach literature.


#### Algorithms using a finite set of patterns
In the following compiation, *m* is the length of the pattern, *n* the length of the serachable text, and *k* = |Σ| is the size of the alphabet.

|Algorithms|Preprocessing time|Matching time|Space|
|---|---|---|---|
|Naive Algorithm|none|Θ(mn)|none|
|Knuth-Morris-Pratt|Θ(m)|Θ(n)|Θ(m)|
|Boyer-Moore|Θ(m+k)|Ω(n/m) at best, O(mn) at worst|Θ(k)|
|Two-way algorithm|Θ(m)|O(n)|O(1)|
|Backward Non-Deterministic DAWG Matching(BNDM)|O(m)|Ω(n/m) at best, O(mn) at worst|---|
|Backward Oracle Matching(BOM)|O(m)|O(mn)|---|


Algorithm	Extension of	Preprocessing time	Matching time[4]	Space
Aho–Corasick	Knuth–Morris–Pratt	Θ(m)	Θ(n + o)	Θ(m)
Commentz-Walter	Boyer-Moore	Θ(m)	Θ(M * n) worst case
sublinear in average[9]	Θ(m)
Set-BOM	Backward Oracle Matching			
Algorithms using an infinite number of patterns
Naturally, the patterns can not be enumerated finitely in this case. They are represented usually by a regular grammar or regular expression.

Classification by the use of preprocessing programs
Other classification approaches are possible. One of the most common uses preprocessing as main criteria.

Classes of string searching algorithms[10]
Text not preprocessed	Text preprocessed
Patterns not preprocessed	Elementary algorithms	Index methods
Patterns preprocessed	Constructed search engines	Signature methods :[11]
Classification by matching strategies
Another one classifies the algorithms by their matching strategy:[12]

- Match the prefix first (Knuth–Morris–Pratt, Shift-And, Aho–Corasick)
- Match the suffix first (Boyer–Moore and variants, Commentz-Walter)
- Match the best factor first (BNDM, BOM, Set-BOM)
- Other strategy (Naïve, Rabin–Karp)
# Feb 13
## 스택
### 스택의 특성
- 물건을 쌓아 올리듯 자료를 쌓아 올린 형태의 자료구조이다.
- 스택에 저장된 자료는 선형 구조를 갖는다.
  - 선형 구조: 자료 간의 관계가 1대1의 관계를 갖는다.
  - 비선형 구조 : 자료 간의 관계가 1대N의 관계를 갖는다.(예: 트리)
- 스택에 자료를 삽입하거나 스택에서 자료를 꺼낼 수 있다.
- 마지막에 삽입한 자료를 가장 먼저 꺼낸다. 후입선출(LIFO, Last-In-First-Out)이라고 부른다.
  - 예를 들어 스택에 1,2,3, 순으로 자료를 삽입한 후 꺼내면 역순으로 즉 3,2,1순으로 꺼낼 수 있다.

스택을 프로그램에서 구현하기 위해서 필요한 자료구조와 연산
- 자료구조 : 자료를 선형으로 저장할 저장수
  - 배열을 사용할 수 있다.
  - 저장소 자체를 스택이라 부르기도 한다.
  - 스택에서 마지막 삽입된 원소의 위치를 top이라 부른다.
  > 스택 pointer라고도 부른다.


## 스택의 구현
### 연산
- 삽입(push) : 저장소에 자료를 저장한다
- 삭제(pop) : 저장소에서 삽입한 자료의 역순으로 자료를 꺼낸다 
- isEmpty : 스택이 공백인지 아닌지를 확인하는 연산
- peek : 스택의 top에 있는 item(원소)을 반환하는 연산

### 스택의 삽입/삭제 과정
- 빈 스택에 원소 A,B,C를 차례로 삽입 후 한번 삭제하는 연산과정
```python
stack = []    # stack = [],      top = None
stack.push(A) # stack = [A],     top = A
stack.push(B) # stack = [A,B],   top = B
stack.push(C) # stack = [A,B,C], top = C
stack.pop()   # stack = [A,B],   top = B
```

### 스택의 push 구현
- 스택의 push 알고리즘
  - append 메소드를 통해 리스트의 마지막에 데이터를 삽입
```python
def push(item) :
  s. append(item)  # 단점 : append가 느림

s = []
s.push(0)
```
참고
```python
def push(item, size):
  global top
  top += 1
  if top == size:
    print('overflow!')
  else:
    stack[top] = item
  
size = 10
stack = [0] * size
top = -1

push(10, size)
top += 1          # push(20)
stack[top] = 20   # 
```

### 스택의 pop 구현
```python
def pop():
  if len(s) == 0 :
    # underflow
    return
  else :
    return s.pop()
```
```python
def pop():
  global top
  if top == -1:
    print('underflow')
    return 0
  else:
    top -= 1
    return stack[top+1]

print(pop())

if top > -1:     # pop()
  top -= 1
  print(stack[top+1])
```

### 스택 구현 고려 사항
- 1차원 배열을 사용하여 구현할 경우 구현이 용이하다는 장점이 있지만 스택의 크기를 변경하기가 어렵다는 단점이 있다.
- 이를 해결하기 위한 방법으로 저장소를 동적으로 할당하여 스택을 구현하는 방법이 있다.
  - "동적 연결리스트"를 이용하여 구현하는 방법을 의미한다.
  - 구현이 복잡하다는 단점이 있지만 메모리를 효율적으로 사용한다는 장점을 가진다.
  > 스택의 동적 구현은 생략

### 스택의 응용 1 : 괄호검사
- 괄호의 종류 : 대괄호 ('[',']'), 중괄호 ('{}','}'), 소괄호 ('()',')')
- 조건
1. 왼쪽 괄호의 개수ㅗ아 오른쪽 괄호의 개수가 같아야 한다.
2. 같은 괄호에서 왼쪽 괄호는 오른쪽 괄호보다 먼저 나와야 한다.
3. 괄호 사이에는 포함 관계만 존재한다.

- 잘못된 괄호 사용의 예
  (a(b)
  a(b)c)
  a{b(c[d]e}f)

#### 괄호를 조사하는 알고리즘 개요
- 문자열에 있는 괄호를 차례대로 조사하면서 왼쪽 괄호를 만나면 스택에 삽입하고, 오른쪽 괄호를 만나면 스택에서 top 괄호를 삭제한 후 오른쪽 괄호와 짝이 맞는지를 검사한다.

- 이 때, 스택이 비어 있으면 조건 1 또는 조건 2에 위배되고 괄호의 짝이 맞지 않으면 조건 3에 위배된다.

- 마지막 괄호까지를 조사한 후에도 스택에 괄호가 남아 있으면 조건 1에 위배된다.

##### 괄호 조사 알고리즘
```python
def parenthesis(string):
    stack = []
    for c in string:
        if c in ['[', '{', '(']:
            print(stack, c)
            stack.append(c)
        elif c in [']','}', ')']:
            print(stack, c)
            if not stack:
                return 'error'
            elif stack[-1] != dictionary[c]:
                return 'error'
            else:
                stack.pop()
    else:
        if stack:
            return 'error'
        else:
            return 'success'


dictionary = {
            ']' : '[',
            '}' : '{',
            ')' : '('
            }

data_set = ['a{b(c[d]e}f)', '(a(b)', 'a(b)c)', '(a{b[c(d{e}f)g]h}i)']

for data in data_set:
    parenthesis(data)
```

### 스택의 응용 2 : function call
- Function call
- 프로그램에서 함수 호출과 복귀에 따른 수행 순서를 관리
  - 가장 마지막에 호출된 함수가 가장 먼저 실행을 완료하고 복귀하는 후입선출 구조이므로, 후입 선출 구조의 스택을 이요하여 수행순서 관리
  - 함수 호출이 발생하면 호출한 함수 수행에 필요한 지역변수, 매개변수 및 수행 후 복귀할 주소 등의 정보를 스택 프레이(stack frame)에 저장하여 시스템 스택에 삽입
  - 함수의 실행이 끝나면 시스템 스택의 top 원소(스택 프레임)를 삭제(pop)하면서 프레임에 저장되어 있던 복귀주소를 확인하고 복귀
  - 함수 호출과 복귀에 따라 이 과정을 반복하여 전체 프로그램 수행이 종료되면 시스템 스택은 공백 스택이 된다.

- 함수 호출과 복귀에 따른 전체 프로그램의 수행 순서

|stack|비고|
|---|---|
|---|---|
|---|---|
|stack_Frame(F_2)|F_2() 함수 실행 관련 정보|
|stack_Frame(F_1)|F_1() 함수 실행 관련 정보|
|stack_Frame(main)|main() 함수 실행 관련 정보|
# Feb 14
## 스택2
### 재귀 호출
- 자기 자신을 호출하여 순환 수행되는 것
-  함수에서 실행해야 하는 작업의 특성에 따라 일반적인 호출방식보다 재귀호출방식을 사용하여 함수를 만들면 프로그램의 크기를 줄이고 간단하게 작성
   - 재귀 호출의 예) factorial, fibonacci

문제점 : 엄청난 중복 호출이 존재함
> python의 경우 1000회의 중복 호출을 하게 되면 문제가 발생함
피보나치 수열을 자귀함수로 구할 경우 Θ(2^n)이라고 할수 있을정도로 연산속도는 최악


## 메모이제이션
메모이제이션(memoization)은 컴퓨터 프로그램을 실행할 때 이전에 계산한 값을 메모리에 저장해서 매번 다시 계산하지 않도록 하여 전체적인 실행속도를 빠르게 하는 기술이다. 동적 계획법의 핵심이 되는 기술이다.

- 'memoization'은 글자 그대로 해석하면 '메모리에 넣기(to put in memory)'라는 의미이며 '기엉되어야 할 것' 이라는 뜻의 라틴어 memorandum에서 파생되었다. 흔히 '기억하기', '암기하기'라는 뜻의 memorization과 혼동하지만, 정확한 단어는 memoization이다. 동사형은 memoize이다.

### 피보나치 수를 구하기
앞의 예에서 피보나치 수를 구하는 알고리즘에서 fibo(n)의 값을 계산하자마자 저장하면(memoize), 실행시간을 Θ(n)으로 줄일 수가 있음.

- Memoization을 적용할 경우
```python
# memo를 위한 배열을 할당하고, 모두 0으로 초기화한다;
# memo[0]을 0으로 memo[1]는 1로 초기화 한다;

def fibo1(n):
  global memo
  if n>=2 and memo[n] == 0:
    memo[n] = fibo(fibo(n-1)+fibo1(n-2))
    return memo[n]

memo = [0] * (n+1)
memo[0] = 0
memo[1] = 1
```
## DP(Dynamic Prgroamming)
- 동적 계획(Dynamic Programming) 알고리즘은 그리디 알고리즘과 같이 최적화 문제를 해결하는 알고리즘이다.

- 동적 계획 알고리즘은 먼저 입력 크기가 작은 부분 문제들을 모두 해결한 후에 그 해들을 이용하여 보다 큰 크기의 부분 문제들을 해결하여, 최종적으로 원래 주어진 입력의 문제를 해결하는 알고리즘이다.

- 피보나치 수 DP 적용
  - 피보나치 수는 부분 문제의 답으로부터 본 문제의 답을 얻을 수 있으므로 최적 부분 구조로 이루어져 있다.
  
1. 문제를 부분 문제로 분할한다.
  - Fibonacci(n) 함수는 Fibonacci(n-1) + Fibonacci(n-2)의 합
  - ...
  - Fibonacci(n)은 Fibonacci(n-1), Fibonacci(n-2), ..., Fibonacci(1), Fibonacci(0)의 부분집합으로 나뉜다.
2. 부분 문제로 나누는 일을 끝냈으면 가장 작은 부분 문제부터 해를 구한다.
3. 그 결과는 테이블에 저장하고 테이블에 저장된 문제의 해를 이용하여 상위 문제의 해를 구한다.
   |테이블 인덱스|저장되어 있는 값|
   |---|---|
   |[0]|0|
   |[1]|1|
   |[2]|1|
   |[3]|2|
   |...|...|
   |[n]|fibo(n)|

피보나치 수 DP 적용 알고리즘
```python
def fibo2(n):
  f = [0] * (n+1)
  f[0] = 0
  f[1] = 1
  for i in range(2, n+1):
    f[i] = f[i-1] + f[i-2]
  
  return f[n]
```

### DP의 구현 방식
- recursive 방식 : fib1()
- iterative ㅂ아식 : fib2()

- memoization을 재귀적 구조에 사용하는 것보다 반복적 구조로 DP를 구현한 것이 성능 면에서 보다 효율적이다.
- 재귀적 구조는 내부에 시스템 호출 스택을 사용하는 오버헤드가 발생하기 때문이다.
  
## DFS(깊이 우선 탐색)
- 비선형구조인 그래프 구조는 그래프로 표현된 모든 자료를 빠짐없이 검색하는 것이 중요함.
- 두 가지 방법
  - 깊이 우선 탐색(Depth First Search, DFS)
  - 너비 우선 탐색(Breadth First Search, BFS)

- 시작 정점의 한 방향으로 갈 수 있는 경로가 있는 곳까지 깊이 탐색해 가다가 더 이상 갈 곳이 없게 되면, 가장 마지막에 만았던 갈림길 간선이 있는 정점으로 되돌아와서 다른 방향의 정점으로 탐색을 계속 반복하여 결국 모든 정점을 방문하는 순회방법
  
- 가장 마지막에 만났던 갈림길의 정점으로 되돌아가서 다시 깊이 우선 탐색을 반복해야 하므로 후입선출 구조의 스택 사용

### DFS 알고리즘
1. 시작 정점 v를 결정하여 방문한다.
2. 정점 v에 인접한 정점 중에서
   - 방문하지 않은 정점 w가 있으면, 정점 v를 스택에 push하고 정점 w를 방문한다. 그리고 w를 v로 다시 2.를 반복한다.
   - 방문하지 않은 정점이 없으면, 탐색의 방향을 바꾸기 위해서 스택을 pop하여 받은 가장 마지막 방문 정점을 v로 하여 다시 2.를 반복한다.
3. 스택이 공백이 될 때까지 2.를 반복한다.

pseudo code
```python
DFS(v)
  시작점 v 방문;
  visited[v] <- true:
  while{
    if (v의 인접 정점 중 방문 안 한 정점 w가 있으면)
      push(v);
      v <- w: (w에 방문)
      visited[w] <- true:
    else
      if (스택이 비어 있지 않으면)
        v <- pop(stack);
      else
        break
  }
end DFS()
```
# Feb 15
## 스택2
APS(Algorithm Problem Solving) 기본
- 계산기1
- 계산기2
- 백트래킹
- [참고] 부분집합, 순열
- 분할정복
  
### 계산기
문자열로 된 계산식이 주어질 때, 스택을 이용하여 이 계산식의 값을 계산할 수 있음
문자열 수식 계산의 일반적 방법
- step1. 중위 표기법의 수식을 후위 표기법으로 변경한다. (스택 이용)
- step2. 후위 표기법의 수식을 스택을 이용하여 계산한다.
> 중위 표기법(infix notation) : A + B
> 후위 표기법(postfix notation) : AB+

#### 계산기 1
step1. 중위 표기식의 후위표기식 변환 방법1
- 수식의 각 연산자에 대해서 우선순위에 따라 괄호를 사용하여 다시 표현한다.
- 각 연산자를 그에 대응하는 오른쪽 괄호의 뒤로 이동시킨다.
- 괄호를 제거한다.
> A*B-C/D
  1. ((A*B)-(C/D))
  2. (AB)*(CD)/-
  3. AB*CD/-

1. 입력 받은 중위 표기식에서 토큰을 읽는다.
2. 토큰이 피연산자이면 토큰을 출력한다
3. 토큰이 연산자(괄호포함)일 때, 이 토큰이 스택의 top에 저장되어 있는 연산자보다 우선순위가 높으면 스택에 push하고, 그렇지 않으면 스택 top의 연산자의 우선순위가 토큰의 우선순위보다 작을때까지 스택에서 pop한 후 토큰의 연산자를 push한다. 만약 top에 연산자가 없으면 push 한다.
4. 토큰이 오른쪽 괄호')'이면 스택 top에 왼쪽 괄호 '('가 올 때까지 스택에 pop연산을 수행하고 pop한 연산자르 출력한다. 왼쪽 괄호를 만나면 pop만 하고 출력하지는 않는다.
5. 중위 표기식에 더 읽을 것이 없다면 중지하고, 더 읽을 것이 있다면 1부터 다식 반복한다.
6. 스택에 남아 있는 연산자를 모두 pop하여 출력한다.
   - 스택에 남아 있는 연산자를 모두 pop하여 출력한다.
    - 스택 밖의 왼쪽 괄호는 우선순위가 가장 높으며, 스택 안의 왼쪽 괄호는 우선순위가 가장 낮음

수식연산자를 읽어서 피연산자는 바로 출력하고 연산자는 스택에 push하여 수식이 끝나면 스택의 남아있는 연산자를 모두 pop하여 출력하시오. 연산자는 사칙 연산만 사용하시오.

예를 들어 2+3*4/5인 수식인 경우
> 2345/*+ 가 출력될 것이다.

```python
string = input()
operator = ['-', '+', '/', '*', '(', ')']
answer = []
stack = []
for c in string:
    if answer[-1] not in operator and c not in operator:
        answer[-1] = c + answer[-1]
        continue
    elif answer[-1] in operator and c in operator:
        answer[-1] = c + answer[-1]
    else:
        if c == ')':
            while stack[-1] != '(':
                answer.append(stack.pop())
            else:
                stack.pop()
        else:
            stack.append(c)
else:
    while stack:
        answer.append(stack.pop())
print(''.join(answer))
```

#### 계산기 2
step2. 후위 표기법의 수식을 스택을 이용하여 계산
1. 피연산자를 만나면 스택에 push 한다.
2. 연산자를 만나면 필요한 만큼의 피연산자를 스택에서 pop하여 연산하고, 연산결과를 다시 스택에 push 한다.
3. 수식이 끝나면, 마지막으로 스택을 pop하여 출력한다.

```python
string = input()
operator = ['-', '+', '/', '*']
answer = int()
stack = list()
for c in string:
    if c not in operator:
        stack.append(c)
    else:
        right = int(stack.pop())
        left = int(stack.pop())
        if c == '+':
            stack.append(left+right)
        elif c == '-':
            stack.append(left-right)
        elif c == '*':
            stack.append(left*right)
        elif c == '/':
            stack.append(left/right)
else:
    answer = stack.pop()
print(answer)
```

### 백트래킹
백트래킹 (Backtracking) 기법은 해를 찾는 도중에 '막히면' (즉, 해가 아니면) 되돌아가서 다시 해를 찾아 가는 기법이다.
백트래킹 기법은 최적화(optimization) 문제와 결정 (decision) 문제를 해결할 수 있다.
결정 문제 : 문제의 조건을 만족하는 해가 존재하는지의 여부를 'yes'또는 'no'가 답하는 문제
- 미로 찾기
- n-Queen 문제
- Map coloring 문제
- 부분 집합의 합(Subset Sum) 문제 등

#### 백트래킹과 깊이 우선 탐색과의 차이
- 어떤 노드에서 출발하는 경로가 해결책으로 이어질 것 같지 않으면 더 이상 그 경로를 따라가지 않음으로써 시도의 횟수를 줄임.(prunning 가지치기)
- 깊이우선탐색이 모든 경로를 추적하는데 비해 백트래킹은 불필요한 경로를 조기에 차단.
- 깊이우선탐색을 가하기에는 경우의 수가 너무나 많음. 즉, N! 가지의 경우의 수를 가진 문제에 대해 깊이 우선 탐색을 가하면 당엲 ㅣ처리 불가능한 문제.
- 백트래킹 알고리즘을 적용하면 일반적으로 경우의 수가 줄어들지만 이 역시 최악의 경우에는 여전히 지수함수 시간(Exponential Time)을 요하므로 처리 불가능

백트래킹 기법
- 어떤 노드의 유망성을 점검한 후에 유망(promising)하지 않다고 결정되면 그 노드의 부모로 되돌아가(backtracking) 다음 자식 노드로 감
- 어떤 노드를 방문하였을 때 그 노드를 포함한 경로가 해답이 될수 없으면 그 녿느느 유망하지 않다고 하며, 반대로 해답의 가능성이 있으면 유망하다고 한다.
- 가지치기(pruning) : 유망하지 않는 노드가 포함되는 경로는 더 이상 고려하지 않는다.
 
백트래킹 알고리즘은 다음의 절차로 진행됨
1. 상태 공간 트리의 깊이 우선 검색을 실시
2. 각 노드가 유망한지를 점검
3. 만일 그 노드가 유망하지 않으면, 그 노드의 부모 노드로 돌아가서 검색을 계속한다.

#### 일반 백트래킹 알고리즘
```python
def checknode (v) : # node
  if promising(v) :
    if there is a solution at v:
      write the solution
    else:
      for u in each childe of v:
        checknode(u)
```
깊이 우선 탐색 vs. 백트래킹
- 순수한 깊이 우선 검색 = 155노드
- 백틀캐이 = 27노드

#### 미로찾기
- 입구와 출구가 주어진 미로에서 입구부터 출구까지의 경로를 찾는 문제이다.
- 이동할 수 있는 방향은 4방향으로 제한한다.

#### 부분집합 구하기
어떤 집합의 공집합과 자기자신을 포함한 모든 부분집합을 powerset이라고 하며 구하고자 하는 어떤 집합의 원소 개수가 n일 경우 부분집합의 개수는 2^n개 이다

백 트래킹 기법으로 powerset을 구해보자
- 앞에서 설명한 일반적인 백트래킹 접근 방법을 이용한다.
- n개의 원소가 들어있는 집합의 2^n개의 부분집합을 만들 때는, true 또는 false값을 가지는 항목들로 구성된 n개의 배열을 만드는 방법을 이용.
- 여기서 배열의 i번째 항목은 i번째 원속 ㅏ부분집합의 값인지 아닌지를 나타내는 값 이다.

각 원소가 부분집합에 포함되었는지를 loop 이용하여 확인하고 부분집합을 생성하는 방법
```python
bit = [0,0,0,0]
for i in range(2):
  bit[0] = i
  for j in range(2):
    bit[1] = j
    for k in range(2):
      bit[2] = k
      for l in range(2):
        bit[3] = 1
        print(bit)
```

powerset을 구하는 backtracking algorithm
```python
def backtrack(a,k,input) :
  global MAXCANDIDATES
  c = [0] * MAXCANDIDATES

  if k == input:
    process_solution(a,k) # 답이면 원하는 작업을 한다
  else :
    k += 1
    ncandidates = construct_candidates(a,k,input, c)
    for i in range(ncandidates):
      a[k] = c[i]
      backtrack(a,k,input)

def construct_candidates(a,k,input,c):
  c[0] = True
  c[1] = False
  return 2


MAXCANDIDATES = 2
NMAX = 4
a = [0] * NMAX
backtrack(a,0,3)
```

ex) {1,2,3}을 포함하는 모든 순열을 생성하는 함수
- 동일한 숫자가 포함되지 않았을 때, 각 자리 수 별로 loop을 이용해 아래와 같이 구현할 수 있음
```python
for i1 in range(1,4):
  for i2 in range(1,4):
    if i2 != i1:
      for i3 in range(1,4):
        if i3!=i1 and i3!=i2:
          print(i1, i2, i3)
```

순열 구하기
```python
def backtrack(a,k,input) :
  global MAXCANDIDATES
  c = [0] * MAXCANDIDATES

  if k == input:
    for i in range(1, k+1):
      print(a[i], end = ' ')
    print()
  else :
    k += 1
    ncandidates = construct_candidates(a,k,input, c)
    for i in range(ncandidates):
      a[k] = c[i]
      backtrack(a,k,input)

def construct_candidates(a,k,input,c):
  in_perm = [FALSE] * NMAX

  for i in range(1, k):
    in_per[a[i]] = True

  ncandidates = 0
  for i in range(1, input+1):
    if in_perm[i] == False:
      c[ncandidates] = i
      ncandidates += 1
  return ncandidates


MAXCANDIDATES = 2
NMAX = 4
a = [0] * NMAX
backtrack(a,0,3)
```
# Feb 16
## 부분집합의 합
집합 {1,2,3}의 원소에 대해 각 부분집합에서의 포함 여부를 트리로 표현

- i원소의 포함 여부를 결정 하면 i까지의 부분 집합의 합 s_i를 결정할 수 있음
- si_1이 찾고자 하는 부분집합의 합보다 크면 남은 원소를 고려할 필요가 없음
- A[i] 원소를 부분 집합의 원소로 고려하는 재귀 함수(A는 서로 다른 자연수의 집합)
  
```python
# i-1원소까지 고려한 합 s, 찾으려는 합 t
f(i, N, s, t)
  if s == t
  elif i ==N
  elif s > t
  else
    subset[i] = 1
    f(i+1, N, s+A[i], t)
    subset[i] = 0
    f(i+1, N, s, t)
```

- 추가 고려 사항
고려한 구간의 합 S
S>T이면 중단
남은 구간의 합 RS
S + RS < T 남은 원소의 합을 다 더해도 찾는 값 T 미만인 경우 중단

### A[1,2,3]의 모든 원소를 사용한 순열
- 123, 132, 213, 231, 312, 321
- 총 6가지 경우
|---|---|---|
|---|---|---|
|1|2|3|
|---|3|2|
|2|1|3|
|---|3|1|
|3|2|1|
|---|1|2|

```python
f(i,N)
  if i == N
  else
    for j:i -> N-1
      P[i] <-> P[j]
      f(i+1, N)
      P[i] <-> P[j]
```

## 분할 정복 알고리즘
유래
- 1805년 12월 2일 아우스터리츠 전투에서 나폴레옹이 사용한 전략
- 전력이 우세한 연합군을 공격하기 위해 나폴레옹은 연합군으 ㅣ중앙부로 쳐들어가 연합군을 둘로 나눔
- 둘로 나뉜 연합군을 한 부분씩 격파함
  
설계 전략
- 분할(Divide) : 해결한 문제를 여러 개의 작은 부분으로 나누다.
- 정복(Conquer) : 나눈 작은 문제를 각각 해결한다.
- 통합(Combine) : (필요하다면) 해결된 해답을 모은다.
  
### 분할 정복 예제
#### 거듭 제곱(Exponentiation)
- O(n)
```python
def Power(Base, Exponenet) :
  if Base == 0:
    return 1
  result = 1
  for  i in range(Exponent) :
    result *= Base
  return result
```

분할 정복 기반의 알고리즘
- O(log_2(n))
C^n
if n % 2 == 0 : C = C^(n/2)*C(n/2)
else : C = C^(n-1)/2 * C^(n-1)/2 * C
```python
def Power(Base, Exponent) :
  if Exponent == 0 or Base == 0:
    return 1
  if Exponent % 2 == 0:
    NewBase = Power(Base, Exponent/2)
    return NewBase * NewBase
  else:
    NewBase = Power(Base, (Exponenet-1)/2)
    return NewBase * Newbase * Base
```

#### 퀵 정렬
주어진 배열을 두 개로 분할하고, 각각을 정렬한다.
> 합병정렬과 동일?
다른점 1: 합병정렬은 그냥 두 부분으로 나누는 반면에, 퀵정렬은 분할할 때, 기준 아이템(pivot item) 중심으로, 이보다 작은 것은 왼편, 큰 것은 오른편에 위치시킨다.
다른점 2: 각 부분 정렬이 끝난 후, 합병정렬은 "합병"이란 후처리 작업이 필요하나, 퀵정렬은 필요로 하지 않는다.

```python
def quickSort(a, begin, end) :
  if begin < end :
    p = partition(a, begin, end)
    quickSort(a, begin, p-1)
    quickSort(a, p+1, end)

def partition(a, begin, end):
  pivot = (begin+end) // 2
  L = begin
  R = end
  while L < R :
    while(L<R and A[L] < a[pivot]) : L += 1
    while(L<R and a[R] >= a[pivot]) : R -= 1
    if L < R :
      if L == pivot: pivot = R
      a[L], a[R] = a[R], a[L]
  a[pivot], a[R] = a[R], a[pivot]
  return R
```

##### 구현
{69, 10 30 2 16 8 31 22}
1. 원소 2를 피봇으로 선택하고 퀵 정렬 시작
  - L이 오른쪽으로 이동하면서 피봇보다 크거나 같은 원소를 찾고, R은 왼쪽으로 이동하면서 피봇보다 작은 원소를 찾는다.
  - L은 원소 69를 찾았지만, R은 피봇보다 작은 원소를 찾지 못한 채로 원소 69에서 L과 만나게 된다.
  - L과 R이 만났으므로, 원소 69를 피봇과 교환하여 피봇 원소 2의 위치를 확정한다.
2. 피봇 2의 왼쪽 부분 집합은 공집합이므로 퀵 정렬을 수행하지 않고, 오른쪽 부분 집합에 대해서 퀵 정렬 수행.
  - 오른쪽 부분 집합의 원소가 7개 이므로 가운데 있는 원소 16을 피봇으로 선택.
  - L이 찾은 30과 R이 찾은 8을 서로 교환한다.
  - 현태 위치에서 L과 R의 작업을 반복한다.
  - L은 원소 69를 찾았지만, R은 피봇보다 작은 원소를 찾지 못한 채로 원소 69에서 L과 만나게 된다.
  - L과 R이 만났으므로, 원소 69를 피봇과 교환하여 피봇 원소 16의 위치를 확정한다.
3. 피봇 16의 왼쪽 부분 집합에서 원소 10을 피봇으로 선택하여 퀵 정렬 수행.
  - L의 원소 10과 R의 원소 8을 교환하는데, L의 원소가 피봇이므로 피봇원소에 대한 자리교환이 발생한 것이므로 교환한 자리 피봇 원소 10의 위치로 확정한다.
4. 피봇 10의 확정된 위치에서의 왼쪽 부분 집합은 원소가 한개이므로 퀵 정렬을 수행하지 않고, 오른쪽 부분 집합은 공집합이므로 역시 퀵 정렬을 수행하지 않는다.
  - 이제 1단계의 피봇이었던 원소 16에 대한 오른쪽 부분 집합에 대해 퀵 정렬을 수행한다.
  오른쪽 부분집합의 원소가 4개이므로 두번째 원소 30을 피봇으로 선택한다.
  - L이 찾은 69와 R이 찾은 22를 서로 교환한다.

- 현재 위치에서 L과 R의 작업을 반복한다. L은 오른쪽으로 이동하면서 피봇보다 크거나 같은 원소인 30을 찾고, R은 왼쪽으로 이동하면서 피봇보다 작은 원소를 찾다가 못 찾고 원소 30에서 L과 만난다.
- L과 R이 만났으므로 피봇과 교환한다. 이 경우는 R의 원소가 피봇이므로 피봇에 대한 자리교환이 발생한 것이므로 교환한 자리를 피봇의 자리로 확정한다.
  
5. 피봇 30의 확정된 위치에서의 왼쪽 부분 집합의 원소가 한 개 이므로 퀵 정렬을 수행하지 않고, 오른족 부분 집합에 대해서 퀵 정렬 수행.
  - 오른쪽 부분 집합의 원소 2개 중에서 원소 31을 피봇으로 선택한다.
  - L은 오른쪽으로 이동하면서 원소 31을 찾고, R은 왼쪽으로 이동하면서 피봇 보다 작은 원소를 찾다가 못 찾은 채로 원소 31에서 L과 만난다. L과 R이 만났으므로 피봇과 교환하는데 R의 원소가 피봇이므로 결국 제자리가 확정된다.
- 피봇 31의 오른쪽 부분 집합의 원소가 한 개 이므로 퀵 정렬을 수행하지 않는다. 이것으로 전체 퀵 정렬 완성


##### 퀵 정렬 특성
퀵 정렬의 최악의 시간 복잡도는 O(n^2)로, 합병정렬(merge sort)에 비해 좋지 못하다.
그런데, 왜 "빠른" 정렬이라고 했을까?
이는 퀵정렬의 평균 복잡도는 nlogn 이기 때문이다.

|알고리즘|평균 수행시간|최악 수행시간|알고리즘 기법|비고|
|---|---|---|---|---|
|버블 정렬|O(n^2)|O(n^2)|비교와 교환|코딩이 가장 손쉬움|
|카운팅 정렬|O(n+k)|O(n+k)|비교환 방식|n이 비교적 작을 때만 가능|
|선택 정렬|O(n^2)|O(n^2)|비교와 교환|교환의 회수가 버블, 삽입정렬보다 작음|
|퀵 정렬|O(n log n)|O(n^2)|분할 정복|최악의 경우 O(n^2) 이지만, 평균적으로는 가장 빠름|
|삽입 정렬|O(n^2)|O(n^2)|비교와 교환|n의 개수가 작을 때 효과적|
|병합 정렬|O(n log n)|O(n log n)|분할 정복|연결리스트의 경우 가장 효율적인 방식|

## quick sort
```python
def quicksort(lst, a, b):
    if a < b:
        p = partition(lst, a, b)
        quicksort(lst, a, p-1)
        quicksort(lst, p+1, b)
        
def partition(lst, a, b):
    pivot = (a+b)//2
    l = a
    r = b
    while l < r:
        while(l < r and lst[l] < lst[pivot]) :
            l += 1
        while(l < r and lst[r] >= lst[pivot]) :
            r += 1
        if l < r :
            if l == pivot:
                pivot = r
            lst[l], lst[r] = lst[r], lst[l]
    lst[pivot], lst[r] = lst[r], lst[pivot]
    return r
```

```python
def quicksort(lst, a, b):
    if a < b:
        p = partition(lst, a, b)
        quicksort(lst, a, p-1)
        quicksort(lst, p+1, b)
        
def partition(lst, a, b):
    pivot = (a+b)//2
    l = a
    r = b
    while l < r:
        while(l < r and lst[l] < lst[pivot]) :
            l += 1
        while(l < r and lst[pivot] <= lst[r]) :
            r -= 1
        if l < r :
            if l == pivot:
                pivot = r
            lst[l], lst[r] = lst[r], lst[l]
    lst[pivot], lst[r] = lst[r], lst[pivot]
    return r


qs = [69, 10, 30, 2, 16, 8, 31, 22]
quicksort(qs, 0, len(qs)-1)
```
# Feb 20
## Queue
- 선형큐
- 원형큐
- 우선순위 큐
- 큐의 활용 : 버퍼
- BFS
- BFS 예제

## 큐의 특성
- 스택과 마찬가지로 삽입과 삭제의 위치가 제한적인 자료구조
  > 큐의 뒤에서는 삽입만 하고, 큐의 앞에서는 삭제만 이루어지는 구조

- 선입선출구조(FIFO : First in First Out)
  > 큐에 삽입한 순서대로 원소가 저장되어, 가장 먼저 삽입(First In)된 원소는 가장 먼저 삭제(First Out) 된다.

## 큐의 구조 및 기본 연산
큐의 선입선출 구조
머리(Front) : 저장된 원소 중 첫 번째 원소(또는 삭제될 위치)
꼬리(Rear) : 저장된 원소 중 마지막 원소

큐의 기본 연산
- 삽입 : enQueue
- 삭제 : deQueue

### 큐의 주요 연산
큐의 사용을 윟 ㅐ필요한 주요 연산은 다음과 같음
|연산|기능|
|---|---|
|enQueue(item)|큐의 뒤쪽(rear 다음)에 원소를 삽입하는 연산|
|deQueue()|큐의 앞쪽(front) 원소를 삭제하고 반환하는 연산|
|createQueue()|공백 상태의 큐를 생성하는 연산|
|isEmpty()|큐가 공백상태인지를 확인하는 연산|
|isFull()|큐가 포화상태인지를 확인하는 연산|
|Qpeek()|큐의 앞쪽(front)에서 원소를 삭제 없이 반환하는 연산|

### 큐의 구현
선형큐
- 1차원 배열을 이용한 큐
  - 큐의 크기 = 배열 크기
  - front : 저장된 첫 번째 원소의 인덱스
  - rear : 저장된 마지막 원소의 인덱스

- 상태 표현
  - 초기 상태 : front = rear = -1
  - 공백 상태 : front == rear
  - 포화 상태 : rear = n-1 (n : 배열의 크기, n-1 : 배열의 마지막 인덱스)

- 초기 공백 큐 생성
  - 크기 n인 1차원 배열 생성
  - front와 rear를 -1로 초기화
  
삽입 : enQueue(item)
- 마지막 원소 뒤에 새로운 원소를 삽입하기 위해
  1. rear 값을 하나 증가시켜 새로운 원소를 삽입할 자리를 마련
  2. 그 인덱스에 해당하는 배열 원소 Q[rear]에 item을 저장
  ```python
  def enQueue(item):
    global rear
    if isFull() : print("Queue_Full")
    else:
      rear <- rear + 1;
      Q[rear] <- item;
  ```

삭제 : deQueue()
- 가장 앞에 있는 원소를 삭제하기 위해
  1. front 값을 하나 증가시켜 큐에 남아있게 될 첫 번째 원소 이동
  2. 새로운 첫 번째 원소를 리턴 함으로써 삭제와 동일한 기능함
  ```python
  def deQueue():
    if(isEmpty()) then Queue_Empty();
    else{
      front <- front + 1;
      return Q[front]
    }
  ```

공백 상태 및 포화상태 검사 : isEmpty(), isFull()
- 공백상태 : front == rear
- 포화상태 : rear == n-1(n:배열의 크기, n-1:배열의 마지막 인덱스)
  ```python
  def isEmpty() :
    return front == rear
  
  def Full() :
    return rear  == len(Q) - 1
  ```

검색 : Qpeek()
- 가장 앞에 있는 원소를 검색하여 반환하는 연산
- 현재 front의 한자리 뒤(front+1)에 있는 원소, 즉 큐의 첫 번째에 있는 원소를 반환
  ```python
  def Qpeek():
    if isEmpty() : print("Queue_Empty")
    else: return Q[front+1]
  ```

#### 예제 1
큐를 구현하여 다음 동작을 확인해 봅시다.
- 세 개의 데이터 1, 2, 3을 차례로 큐에 삽입하고
- 큐에 세 개의 데이터를 차례로 꺼내서 출력한다.  # 1, 2, 3이 출력


#### 선형 큐 이용시의 문제점
잘못된 포화상태 인식
- 선형 큐를 이용하여 원소의 삽입과 삭제를 계속할 경우, 배열의 앞부분에 활요할 수 있는 공간이 있음에도 불구하고, rear = n-1잍 상태 즉, 포화 상태로 인식하여 더 이상의 삽입을 수행하지 않게 됨
  
해결방법 1
- 매 연산이 이루어질 때마다 저장된 원소들을 배열의 앞부분으로 모두 이동시킴
- 원소 이동에 많은 시간이 소요되어 큐의 효율성이 급격히 떨어짐

해결방법 2
- 1차원 배열을 사용하되, 논리적으로는 배열의 처음과 끝이 연결되어 원형 형태의 큐를 이룬다고 가정하고 사용

### 원형 큐(Circular Queue)
#### 원형 큐의 구조
초기 상태 공백
- front = rear = 0
  
Index의 순환
- front와 rear의 위치가 배열의 마지막 인덱스인 n-1를 가리킨 후, 그 다음에는 논리적 순환을 이루어 배열의 처음 인덱스인 0으로 이동해야 함
- 이를 위해 나머지 연산자 mod를 사용함

front 변수
- 공백 상태와 포화 상태 구분을 쉽게 하기 위해 front가 있는 자리는 사용하지 않고 항상 빈자리로 둠

삽입 위치 및 삭제 위치
|구분|삽입 위치|삭제 위치|
|---|---|---|
|선형큐|rear = rear + 1|front = front + 1|
|원형큐|rear = (rear + 1) mod n|front = (front + 1) mod n|


#### 원형 큐의 구현
초기 공백 큐 생성
- 크기 n인 1차원 배열 생성
- front와 rear을 0으로 초기화

공백 상태 및 포화 : isEmpty(), isFull()
- 공백상태 : front == rear
- 포화상태 : 삽입할 rear의 다음 위치 == 현재 front
  - (rear + 1)mod n == front
  ```python
  def isEmpty():
    return front == rear

  def isFull():
    return (rear+1) % len(cQ) == front
  ```

삽입 : enQueue(item)
- 마지막 원소 뒤에 새로운 원소를 삽입하기 위해
  1. rear 값을 조정하여 새로운 원소를 삽입할 자리를 마련함 :
    rear <- (rear+1) mod n
  2. 그 인덱스에 해당하는 배열 원소 cQ[rear]에 item을 저장
  ```python
  def enQueue(item):
    global rear
    if isFull():
      print("Queue_Full")
    else:
      rear = (rear+1)%len(cQ)
      cQ[rear] = item
  ```

삭제 : deQueue(), delete()
- 가장 앞에 있는 원소를 삭제하기 위해
  1. front 값을 조정하여 삭제할 자리를 준비함
  2. 새로운 front 원소를 리턴 함으로써 삭제와 동일한 기능함
  ```python
  def deQueue():
    global front
    if isEmpty():
      print("Queue_Empty")
    else:
      front = (front + 1) % len(cQ)
      return cQ[front]
  ```

```python
def isEmpty() :
  return front == rear

def isFull() :
  return (rear + 1) % len(cQ) == front
```

### 우선순위 큐(Priority Queue)
우선순위 큐의 특성
- 우선순위를 가진 항목들을 저장하는 큐
- FIFO 순서가 아니라 우선순위가 높은 순서대로 먼저 나가게 된다.

우선순위 큐의 적용 분야
- 시뮬레이션 시스템
- 네트워크 트래픽 제어
- 운영체제의 테스크 스케줄링

우선순위 큐의 구현
- 배열을 이용한 우선순위 큐
- 리스트를 이용한 우선순위 큐

우선순위 큐의 기본 연산
- 삽입 : enQueue
- 삭제 : deQueue

배열을 이용하여 우선순위 큐 구현
- 배열을 이용하여 자료 저장
- 원소를 삽입하는 과정에서 우선순위를 비교하여 적절한 위치에 삽입하는 구조
- 가장 앞에 최고 우선순위의 원소가 위치하게 됨

문제점
- 배열을 사용하므로, 삽입이나 삭제 연산이 일어날 때 원소의 재배치가 발생함
- 이에 소요되는 시간이나 메모리 낭비가 큼
# Feb 21
## 큐의 활용
버퍼
- 데이터를 한 곳에서 다른 한 곳으로 전송하는 동안 일시적으로 그 데이터를 보관하는 메모리의 영역
- 버퍼링 : 버퍼를 활용하는 방식 또는 버퍼를 채우는 동작을 의미한다.

버퍼의 자료 구조
- 버퍼는 일반적으로 입출력 및 네트워크와 관련된 기능에서 이용된다.
- 순서대로 입력/출력/전달되어야 하므로 FIFO방식의 자료구조인 큐가 활용된다.

ex)
```python
버퍼 = []
if callback:
  peak(buffer)
  if peak(buffer) == input_within_cpu:
    buffer.dequeue
```
키보드 버퍼는 아래와 같이 수행된다.
```python
human_input = [A, P, S, ent]
keyboard_queue = [A, P, S, ent]
program_stack = [ent, S, P, A]  # -> process
```

### 연습문제 2
1. 마이쮸 시뮬레이션 구현

2. 엔터릴 칠 대마다 다음 정보를 화면에 출력해 보자.
  - 큐에 있는 사람 수
  - 현재 일인당 나눠주는 사탕의 수
  - 현재까지 나눠준 사탕의 수

```python
n = 20
front = 0
rear = 0
lst = [0]*20**2
lst[rear] = (1, 1)
id = 2
while n > 0:
    lst[rear+1] = (lst[front][0], lst[front][1]+1)
    lst[rear+2] = (id, 1)
    n -= lst[front][1]
    if n < 0:
        break
    id += 1
    front += 1
    rear += 2
print(lst[front][0])
```

```python
while True:
    queue = input()
    for c in queue:
        print(c)
```

## BFS(Breadth First Search)
그래프를 탐색하는 방법에는 크게 두 가지가 있음
- 깊이 우선 탐색(Depth First Search, DFS)
- 너비 우선 탐색(Breadth First Search, BFS)

너비우선탐색은 탐색 시작점의 인접한 정점들을 먼저 모두 차례로 방문한 후에, 방문했던 정점을 시작점으로 하여 다시 인접한 정점들을 차례로 방문하는 방식

인접한 정점들에 대해 탐색을 한 후, 차례로 다시 너비우선탐색을 진행해야 하므로, 선입선출 형태의 자료구조인 큐를 활용함

### BFS 알고리즘
입력 파라미터 : 그래프 G와 탐색 시작점 v
```python
def BFS(G, v) :
  visited = [0] * (n+1)           # n : 정점의 개수
  queue = []                      # 큐 생성
  queue.append(v)                 # 시작점 v를 큐에 삽입
  while queue :                   # 큐가 비어있지 않은 경우
    t = queue.pop(0)              # 큐의 첫번째 원소 반환
    if not visited[t] :           # 방문되지 않은 곳이라면
      visited[t] = True           # 방문한 것으로 표시
      visit(t)                    # 정점 t에서 할 일
      for i in G[t]:              # t와 연결된 모든 
        if not visited[i]:        # 방문되지 않은 곳이라면
          queue.append(i)         # 큐에 넣기
```

### 연습문제 3
다음은 연결되어 있는 두 개의 정점 사이의 간선을 순서대로 나열 해 놓은 것이다. 모든 정점을 너비우선탐색 하여 경로를 출력하시오. 시작 정점을 1로 시작하시오.
- 1, 2, 1, 3, 2, 4, 2, 5, 4, 6, 5, 6, 6, 7, 3, 7
- 추력 결과의 예는 다음과 같다. : -1-2-3-4-5-7-6
```python
from collections import deque

string = '1 2 1 3 2 4 2 5 4 6 5 6 6 7 3 7'
lst = list(map(int, string.split()))
node = 7
edge = len(lst)//2
graph = [list() for _ in range(node)]
for i in range(edge):
    graph[lst[2*i]-1].append(lst[2*i+1]-1)
    graph[lst[2*i+1]-1].append(lst[2*i]-1)

visited = [False] * node
start = 0
queue = deque()
queue.append(start)
visited[start] = True
answer = list()

while queue:
    tmp = queue.popleft()
    answer.append(tmp)
    for neighbor in graph[tmp]:
        if not visited[neighbor]:
            queue.append(neighbor)
            visited[neighbor] = True
print('-'.join(map(lambda x: str(x+1), answer)))
```
# Feb 22
## 트리
- 트리
- 이진 트리
- 이진 트리의 표현
- [참고] 이진 트리의 저장
- 연습 문제
- 이진탐색 트리
- 힙

## 트리의 개념
- 비선형 구조
- 원소들 간에 1:n 관계를 가지는 자료 구조
- 원소들 간에 계층 관계를 가지는 계층형 자료구조
- 상위 원소엣 하위 원소로 내려가면서 확장되는 트리(나무)모양의 구조

## 트리의 정의
한개 이상의 노드로 이루어진 유한 집합이며 다음 조건을 만족함
- 노드 중 최상위 노드를 루트(root)라 함
- 나머지 노드들은 n(>=0)개의 분리 집합 T1, ..., TN으로 분리될 수 있다.

이들 T1, ..., TN은 각각 하나의 트리가 되며(재귀적 정의) 루트의 부 트리(subtree)라 한다.

## 트리 용어
노드(node) - 트리의 원소
- 트리 T의 노드 - A, B, C, D, E, F, G, H, I, J, K
간선(edge) - 노드를 연결하는 선. 부모 노드와 자식 노드를 연결
루트 노드(root node) - 트리의 시작 노드
- 트리 T의 루트노드 - A
형제 노드(sibling node) - 같은 부모 노드의 자식 노드들
- B,C,D는 형제 노드
조상 노드 - 간선을 따라 루트 노드까지 이르는 경로에 있는 모든 노드들
- K의 조상 노드 : F, B, A
서브 트리(subtree) - 부모 노드와 연결된 간선을 끊었을 때 생성되는 트리
자손 노드 - 서브 트리에 있는 하위 레벨의 노드들
- B의 자손 노드 - E, F, K

차수(degree)  ```dictionary = {A: [B,C,D], B: [E, F], C: [G], D:[H,I,J]}```
- 노드의 차수 : 노드에 연결된 자식 노드의 수.
  - B의 차수 = 2, C의 차수 = 1
- 트리의 차수 : 트리에 있는 노드의 차수 중에서 가장 큰 값
  - 트리 T의 차수 = 3
- 단말 노드(리프 노드) : 차수가 0인 노드. 자식 노드가 없는 노드

높이
- 노드의 높이 : 루트에서 노드에 이르는 간선의 수. 노드의 레벨
  - B의 높이=1, F의 높이 =2
- 트리의 높이 : 트리에 있는 노드의 높이 중에서 가장 큰 값. 최대 레벨
  - 트리 T의 높이=3

## 이진트리
모든 노드들이 2개의 서브트리를 갖는 특별한 형태의 트리
각 노드가 자식 노드를 최대한 2개 까지만 가질 수 있는 트리
- 왼쪽 노드(left child node)
- 오른쪽 노드(right child node)

### 이진트리의 특성
레벨 i에서 노드의 최대 개수는 2^i개
높이가 h인 이진 트리가 가질 수 있는 노드의 최소 개수는 (h+1)개가 되며, 최대 개수는 (2^(h+1)-1)개가 된다
 
### 이진트리의 종류
포화 이진 트리(Full Binary Tree)
- 모든 레벨에 노드가 포화상태로 차 있는 이진 트리
- 높이가 h일 때, 최대의 노드 개수인(2^(h+1)-1)의 노드를 가진 이진 트리
  - 높이 3일 때 2(3+1)-1 = 15개의 노드
- 루트를 1번으로 하여 2^(h+1)-1까지 정해진 위치에 대한 노드 번호를 가짐

완전 이진트리(Complete Binary Tree)
- 높이가 h이고 노드 수가 n개일 때(단, h+1 <= n < 2^(h+1)-1), 포화 이진 트리의 노드 번호 1번부터 n번까지 빈 자리가 없는 이진 트리

편향 이진 트리(Skewed Binary Tree)
- 높이 h에 대한 최소 개수의 노드를 가지면서 한쪽 방향의 자식 노드만을 가진 이진 트리
  - 왼쪽 편향 이진트리
  - 오른쪽 편향 이진트리

### 이진트리 - 순회(traveral)
순회(traversal)란 트리의 각 노드를 중복되지 않게 전부 방문(visit)하는 것을 말하는데 트리는 비 선형 구조이기 때문에 선형구조에서와 같이 선후 연결 관계를 알 수 없다.
따라서 특별한 방법이 필요하다

순회(traversal): 트리의 노드들을 체계적으로 방문하는 것

3가지의 기본적인 순회방법
- 전위순회(preorder traversal) : VLR
  - 부모노드 방문 후, 자식노드를 좌,우 순서로 방문한다.
- 중위순회(inorder traversal) : LVR
  - 왼쪽 자식노드, 부모노드, 오른쪽 자식노드 순으로 방문한다.
- 후위순회(postorder traversal) : LRV
  - 자식노드를 좌우 순서로 방문한 후, 부모노드로 방문한다.

#### 전위 순회(preorder traversal)
- 수행 방법
  1. 현재 노드 n을 방문하여 처리한다 -> V
  2. 현재 노드 n의 왼쪽 서브트리로 이동한다. -> L
  3. 현재 노드 n의 오른쪽 서버트리로 이동한다. -> R
- 전위 순회 알고리즘
```python
def preorder_traverse(T):  # 전위 순회
  if T:
    visit(T)
    preorder_traverse(T.left)
    preorder_traverse(T.right)
```

#### 중위 순회(preorder traversal)
- 수행 방법
  1. 현재 노드 n의 왼쪽 서브트리로 이동한다. -> L
  2. 현재 노드 n을 방문하여 처리한다 -> V
  3. 현재 노드 n의 오른쪽 서버트리로 이동한다. -> R
- 전위 순회 알고리즘
```python
def preorder_traverse(T):  # 전위 순회
  if T:
    preorder_traverse(T.left)
    visit(T)
    preorder_traverse(T.right)
```

#### 전위 순회(preorder traversal)
- 수행 방법
  1. 현재 노드 n의 왼쪽 서브트리로 이동한다. -> L
  2. 현재 노드 n의 오른쪽 서버트리로 이동한다. -> R
  3. 현재 노드 n을 방문하여 처리한다 -> V
- 전위 순회 알고리즘
```python
def preorder_traverse(T):  # 전위 순회
  if T:
    preorder_traverse(T.left)
    preorder_traverse(T.right)
    visit(T)
```

## 이진트리의 표현
배열을 이용한 이진 트리의 표현
- 이진 트리에 각 노드 번호를 다음과 같이 부여
- 루트의 번호를 1로 함
- 레벨 n에 있는 노드에 대하여 왼쪽부터 오른쪽으로 2^n 부터 2^(n+1)-1까지 차례로 부여

### 배열
배열을 이용한 이진 트리의 표현
노드 번호의 성질
- 노드 번호가 i인 노드의 부모 노드 번호? : i//2
- 노드 번호가 i인 노드의 왼쪽 자식 노드 번호? : 2*i
- 노드 번호가 i인 노드의 오른쪽 자식 노드 번호? : 2*i + 1
- 레벨 n의 노드 번호 시작 번호는? 2^n

배열을 이용한 이진 트리의 표현
- 노드 번호를 배열의 인덱스로 사용
- 높이가 h인 이진 트리를 위한 배열의 크기는?
  - 최대 i의 최대 노드 수는? 2^i
  - 따라서 1+2+4+8 ... + 2^i = sum(2^i) = 2^(h+1) - 1

> by chat gpt
> When representing a tree, using a list has several limitations. Lists can only represent linear structures, which makes it difficult to represent a hierarchical structure like a tree. Traversal can be complex, search can be slow and inefficient, and the functionality and flexibility may be limited. Instead, a tree class is a better option as it is designed specifically for trees and provides a more intuitive and natural way to work with trees. Although using a tree class can take more processing time, it is more powerful and flexible, and there are ways to optimize the processing time. The choice of data structure depends on the specific requirements of the application, and whether processing time or ease of use is the priority.
# Feb 23
## 수식을 표현하는 이진트리
- 수식 이진 트리(Expression Binary Tree)라고 부르기도 함.
- 연산자는 루트 노드이거나 가지 노드
- 피연산자는 모두 잎 노드

중위 순회 : A / B * C * D + E
후위 순회 : A B / C * D * E +
전위 순회 : + * * / A B C D E

## 이진 탐색 트리
탐색작업을 효율적으로 하기 위한 자료 구조
모든 원소는 서로 다른 유일한 키를 갖는다.
key(왼쪽 서브트리) < key(루트 노드) < key(오른쪽 서브트리)
왼쪽 서브트리와 오른쪽 서브트리도 이진 탐색 트리다.
중위 순회하면 오름차순으로 정렬된 값을 얻을 수 있다.

### 탐색연산
- 루트에서 시작한다.
- 탐색할 키 값 x를 루트 노드의 키 값과 비교한다.
  - (키 값 x = 루트노드의 키 값)인 경우 : 원하는 원소를 찾았으므로 탐색연산 성공
  - (키 값 x < 루트노드의 키 값)인 경우 : 루트노드의 왼쪽 서브트리에 대해서 탐색연산 수행
  - (키 값 x > 루트노드의 키 값)인 경우 : 루트노드의 오른쪽 서브트리에 대해서 탐색연산 수행
- 서브트리에 대해서 수환적으로 탐색 연산을 반복한다.

### 연산
1. 먼저 탐색 연산을 수행
  - 삽입할 원소와 같은 원소가 트리에 있으면 삽입할 수 없으므로, 같은 원소가 있는지 탐색하여 확인한다.
  - 탐색에서 탐색 실패가 결정되는 위치가 삽입 위치가 된다.
2. 탐색 실패한 위치에 원소를 삽입한다.

### 성능
탐색(searching), 삽입(insertion), 삭제(deletion) 시간은 트리의 높이 만큼 시간이 걸린다.
- O(h), h : BST의 깊이 (height)
평균의 경우
- 이진 트리가 균형적으로 생성되어 있는 경우
- O(log n)
최악의 경우
- 한쪽으로 치우친 경사 이진트리의 경우
- O(n)
- 순차탐색과 시간복잡도가 같다.

#### 검색 알고리즘의 비교
- 배열에서의 순차 검색 : O(N)
- 정렬된 배열에서의 순차 검색 : O(N)
- 정렬된 배열에서의 이진탐색 : O(logN)
  - 고정 배열 크기와 삽입, 삭제 시 추가 연산 필요
- 이진 탐색트리에서의 평균 : O(logN)
  - 최악의 경우 : O(N)
  - 완전 이진 트리 또는 균형트리로 바꿀 수 있다면 최악의 경우를 없앨 수 있다.
    - 새로운 원소를 삽입할 때 삽입 시간을 줄인다.
    - 평균과 최악의 시간이 같다.O(logn)
  - 해쉬 검색 : O(1)
    - 추가 저장 공간이 필요

#### 상용에서 검색을 위한 어떤 알고리즘을 사용할까?
- Crawling and indexing algorithms
  - These algorithms are used to crawl the web and index the content of websites. They help search engines to understand the content of web pages and make it searchable.

- Ranking algorithms
  - These algorithms are used to determine the relevance and importance of a webpage in response to a user's search query. Ranking algorithms typically use factors such as keyword frequency, page authority, backlinks, and user behavior to determine which pages to show in search results.

- Natural language processing (NLP) algorithms
  - These algorithms are used to help search engines understand the intent behind a user's search query. NLP algorithms can help search engines interpret ambiguous or complex queries and provide more accurate results.

- Machine learning algorithms
  - These algorithms are used to improve the relevance and accuracy of search results over time. Machine learning algorithms can help search engines learn from user behavior and feedback to improve their results.

## 힙(heap)
완전 이진 트리에 있는 노드 중에서 키값이 가장 큰 노드나 키 값이 가장 작은 노드를 찾기 위해 만든 자료 구조

최대 힙(max heap)
- 키값이 가장 큰 노드르 찾기 위한 완전 이진 트리
- {부모 노드의 키값 > 자식 노드의 키값}
- 루트 노드 : 키값이 가장 큰 노드

최소 힙(min heap)
- 키값이 가장 작은 노드를 찾기 위한 완전 이진 트리
- {부모 노드의 키값 < 자식 노드의 키값}
- 루트 노드 : 키값이 가장 작은 노드

### 힙 연산
#### 삽입
1. 삽입 전의 힙
2. 삽입할 자리 확장
3. 확장한 자리에 삽입할 원소 저장

1. (삽입한 노드 23 > 부모 노드 19) : 자리바꾸기
2. (삽입 노드 23 > 부모 노드 20) : 자리 바꾸기
3. 비교할 부모 노드가 없으므로 자리 확정

#### 삭제
- 힙에서는 루트 노드의 원소만을 삭제 할 수 있다.
- 루트 노드의 원소를 삭제하여 반환한다.
- 힙의 종류에 따라 최대값 또는 최소값을 구할 수 있다.

힙 삭제의 예
1. 루트 노드의 원소 삭제
2. 마지막 노드 삭제
3. (삽입노드 10 < 자식 노드 19) : 자리바꾸기
4. 자리 확정

### 힙을 이용한 우선순위 큐
- 완전 이진 트리로 구현된 자료구조로서, 키값이 가장 큰 노드나 작은 노드를 찾기에 용한 자료구조
- 아래의 예는 최소 힙(Min heap)으로서, 가장 작은 키값을 노드가 항상 루트에 위치한다.
- 힙의 키를 우선순위로 활용하여 우선순위 큐를 구현할 수 있다.
- 관령 링크 : [http://pages.cs.wisc.edu/~vernon/cs367/notes/11.PRIORITY-Q.html](http://pages.cs.wisc.edu/~vernon/cs367/notes/11.PRIORITY-Q.html)
# Feb 27
## Start
- SW 문제 해결
- 복잡도 분석
- 표준 입출력 방법
- 비트 연산
- 진수
- 실수

SW 문제 해결 역량이란 무엇인가를 이해하고 역량을 강화하는 방법을 이해한다.
효율적인 알고리즘의 필요성을 이해하고 알고리즘의 성능 측정 방법 중 하나인 시간복잡도에 대해 이해한다.
프로그램을 작성하기 위한 기본 중 표준 입출력 방법에 대해 이해한다.
비트 수준의 연산과 알고리즘에 대해 이해한다.
컴퓨터에서의 실수 표현 방법에 대해 이해한다.

프로그래밍 ... "잘하는 사람과 못하는 사람의 생산성 차이가 스무 배" ... [thinking in java]의 저자 브루스 에켈
프로그래밍하기 위한 제약 조건과 요구사항
- 프로그래밍 언어의 특성
- 프로그램이 동작할 HW와 OS에 관한 지식
- 라이브러리들의 유의 사항들
- 프로그램이 사용할 수 있는 최대 메모리
- 사용자 대응 시간 제한
- 재사용성이 높은 간결한 코드
- ...

### SW 문제 해결 역량이란 무엇인가?
- 프로그램을 하기 위한 많은 제약 조건과 요구사항을 이해하고 외선의 방법을 찾아내는 능력
- 프로그래머가 사용하는 언어나 라이브러리, 자료구조, 알고리즘에 대한 지식을 절재적소에 퍼즐을 배치하듯 이들을 연결하여 큰 그림을 만드는 능력이라 할 수 있다.
- 문제 해결 역량은 추상적인 기술이다.
  - 프로그래밍 언어, 알고리즘처럼 명확히 정의된 실체가 없다.
  - 무작정 알고리즘을 암기하고 문제를 풀어본다고 향상되지 않는다.
- 문제 해결 역량을 향상시키기 위한 훈련이 필요하다.

문제해결 능력을 훈련하기 위해서는?
- 일부 새로운 언어, 프레임워크, 개발 방법론만을 배워나가는 것만으로 충분하지 않다.
  이들을 조합해 나가는 방법을 배워야 하지만 쉽지 않다.
- 경험을 통해서 나아지리라 막연히 짐작만 한다.
  그러나 경험에서는 문제 해결 능력을 개발 할 수 있는 상황이 주어지는 것이 아니며 또한 그런 상황에서 자기 개발을 하기는 쉽지 않다.
- 상황을 인위적으로 만들어 훈련해야 한다.
  즉 잘 정제된 추상적인 문제를 제시하고 이를 해결해 가면서 문제 해결 능력을 향상 시킬 수 있는 훈련이 필요하다.

문제 해결 과정
1. 문제를 읽고 이해한다.
2. 문제를 익숙한 용어로 재정의한다.
3. 어떻게 해결할지 계획을 세운다.
4. 계획을 검증한다.
5. 프로그램으로 구현한다.
6. 어떻게 풀었는지 돌아보고, 개선할 방법이 있는지 찾아본다.

문제 해결 전략
- 직관과 체계적인 접근
체계적인 접근을 위한 질문들
- 비슷한 문제를 풀어본 적이 있던가?
- 단순한 방법에서 시작할 수 있을까?
- 문제를 단순화 할 수 있을까?
- 그림으로 그려 볼 수 있을까?
- 수식으로 표현할 수 있을까?
- 문제를 분해 할 수 있을까?
- 뒤에서부터 생각해서 문제를 풀 수 있을까?
- 특정 형태의 답만을 고려할 수 있을까?

## 복잡도 분석
### 알고리즘?
- (명) 알고리즘 : 유한한 단계를 통해 문제를 해결하기 위한 절차나 방법이다.
  주로 컴퓨터용어로 쓰이며, 컴퓨터가 어떤 일을 수행하기 위한 단계적 방법을 말한다.
- 간단하게 다시 말하면 어떠한 문제를 해결하기 위한 절차라고 볼 수 있다.
- 예를 들어 1부터 100까지의 합을 구하는 문제를 생각해 보자

### 알고리즘의 효율
- 공간적 효율성과 시간적 효율성
  - 공간적 효율성은 연산량 대비 얼마나 적은 메모리 공간을 요하는 가를 말한다.
  - 시간적 효율성은 연산량 대비 얼마나 적은 시간을 요하는 가를 말한다.
  - 효율성을 뒤집어 표현하면 복잡도(Complexity)가 된다. 복잡도가 높을수록 효율성은 저하된다.

알고리즘의 효율
- 시간적 복잡도 분석
  - 하드웨어 환경에 따라 처리시간이 달라진다.
    - 부동소수 처리 프로세서 존재유무, 나눗셈 가속기능 유무
    - 입출력 장비의 성능, 공유여부
  - 소프트웨어 환경에 따라 처리시간이 달라진다.
    - 프로그램 언어의 종류
    - 운영체제, 컴파일러의 종류
  - 이러한 환경적 차이로 인해 분석이 어렵다.

복잡도의 점근적 표기
- 시간 (또는 공간)복잡도는 입력 크기에 대한 함수로 표기하는데, 이 함수는 주로 여러 개의 항을 가지는 다항식이다.
- 이를 단순한 함수로 표현하기 위한 점근적 표기 (Asymptotic Notation)를 사용한다.
- 입력 크기 n이 무한대로 커질 때의 복잡도를 간단히 표현하기 위해 사용하는 표기법이다.
  - O(Big-Oh) - 표기
  - Ω(Big-Omega) - 표기
  - Θ(Big-Theta) - 표기

O(Big-Oh) - 표기
- O-표기는 복잡도의 점근적 상한을 나타낸다.
- 복잡도가 f(n) = 2n2-7n+4이라면, f(n)의 O- 표기는 O(n2)이다.
- 먼저 f(n)의 단순화된 표현은 n2이다.
- 단순화된 함수 n2에 임의의 상수 c를 곱한 cn2이 n이 증가함에 따라 f(n)의 상한이 된다.
  (단, c>0.)
> 단순히 "실행시간이 n<sup>2</sup>에 비례"하는 알고리즘이라고 말함.

복잡도 f(n)과 O-표기를 그래프로 나타내고 있다.
n이 증가함에 따라 O(g(n))이 점근적 상한이라는 것을 보여 준다.
(즉, g(n)이 n0보다 큰 모든 n에 대해서 항상 f(n)보다 크다는 것)

Ω(Big-Omega) - 표기
- 복잡도의 점근적 하한을 의미한다.
- f(n) = 2n2-7n+4의 Ω-표기는 Ω(n2)이다.
- f(n) = Ω(n2)은 "n이 증가함에 따라 2n2-7n이 cn2보다 작을 수 없다"라는 의미이다.
  이때 상수 c=1로 놓으면 된다.
- O-표기 때와 마찬가지로 Ω-표기도 복잡도 다항식의 최고차항만 계수 없이 취하면 된다.
- **"최소한 이만한 시간은 걸린다"**

Θ(Big-Theta) - 표기
- O-표기와 Ω-표기가 같은 경우에 사용한다.
- f(n) = 2n<sup>2</sup> + 8n + 3 = O(n<sup>2</sup>)이므로, f(n) = Θ(n<sup>2</sup>)이다.
- **"f(n)은 n이 증가함에 따라 n<sup>2</sup>과 동일한 증가율을 가진다"** 라는 의미이다.

자주 사용하는 O-표기
|표기|의미|
|---|---|
|O(1)|상수 시간(Constant time)|
|O(logn)|로그(대수) 시간(Logarithmic time)|
|O(n)|선형 시간(Linear time)|
|O(nlogn)|로그 선형 시간(Log-Linear time)|
|O(n<sup>2</sup>)|제곱 시간(Quadratic time)|
|O(n<sup>3</sup>)|세제곱 시간(Cubic time)|
|O(2n)|지수 시간(Exponenetial time)|

왜 효율적인 알고리즘이 필요한가?
- 10억 개의 숫자를 정렬하는데 PC에서 O(n<sup>2</sup>) 알고리즘은 300여 년이 걸리는 반면에 O(nlogn) 알고리즘은 5분 만에 정렬한다.
  |O(n<sup>2</sup>)|10<sup>3</sup>|10<sup>6</sup>|10<sup>9</sup>|
  |PC|<1second|2hours|300years|
  |SuperComputer|<1second|<1second|1week|
  |O(nlogn)|10<sup>3</sup>|10<sup>6</sup>|10<sup>9</sup>|
  |PC|<1second|<1second|5minutes|
  |SuperComputer|<1second|<1second|<1second|
- 효율적인 알고리즘은 슈퍼컴퓨터보다 더 큰 가치가 있다.
- 값 비싼 H/W의 기술 개발보다 효율적인 알고리즘 개발이 훨씬 더 경제적이다.


## 표준 입출력 방법
Python 3 표준입출력
- 입력
  - Raw 값의 입력 : input()
    - 받은 입력값을 문자열로 취급
  - Evaluated된 값 입력 : eval(input())
    - 받은 입력값을 평가된 데이터 형으로 취급
- 출력
  - print()
    - 표준 출력 함수, 출력값의 마지막에 개행 문자 ㄹ포함
  - print('text', end='')
    - 출력 시 마지막에 개행문자 제외할 시
  - print('%d' % number)
    - Formatting 된 출력

파일의 내용을 표준 입력으로 읽어오는 방법
- import sys
- sys.stding = open('a.txt', 'r')

### 비트 연산자
|연산자|연산자의 기능|
|---|---|
|&|비트단위로 AND 연산을 한다.|
|\||비트단위로 OR 연산을 한다.|
|^|비트단위로 XOR 연산을 한다.|
|~|단항 연산자로서 피연산자의 모든 비트를 반전시킨다.|
|<<|피연산자의 비트 열을 왼쪽으로 이동시킨다.|
|>>|피연산자의 비트 열을 오른쪽으로 이동시킨다.|

1<<n
- 2n의 값을 갖는다.
- 원소가 n개일 경우의 모든 부분집합의 수를 의미한다.
- Power set (모든 부분집합)
  - 공집합과 자기 자신을 포함한 모든 부분집합
  - 각 원소가 포함되거나 포함되질 않는 2가지 경우의 수를 계산하면 모든 부분집합의 수가 계산된다.
i & (1<<j)
- 계산 결과는 i의 j번째 비트가 1인지 아닌지를 의미한다.

### 엔디안(Endianness)
- 컴퓨터의 메모리와 같은 1차원의 공간에 여러 개의 연속된 대상을 배열하는 방법을 의미하며 HW 아키텍처마다 다르다.
- 주의 : 속도 향상을 위해 바이트 단위와 워드 단위를 변환하여 연산 할 때 올바로 이해하지 않으면 오류를 발생 시킬 수 있다.
- 엔디안은 크게 두가지로 나뉨
  - 빅 엔디안(Big-Endian): 보통 큰 단위가 앞에 나옴. 네트워크
  - 리틀 엔디안(little-endian): 보통 작은 단위가 앞에 나옴. 대다수 데스크탑 컴퓨터
  |종류|0x1234의 표현|0x12345678의 표현|
  |---|---|---|
  |빅 엔디안|12 34|12 34 56 78|
  |리틀 엔디안|34 12|78 56 34 12|

엔디안 확인 코드
```python
import sys
print(sys.byteorder)
```

#### 예제3
```python
def ce(n): # change endian
  p = []
  for i in range(0,4):
    p.append((n>>(24-i*8)) &0xff)
  return p

x = 0x01020304
p = []
for i in range(0, 4):
  p.append((x>>(i*8)) & 0xff)

print('x = %d%d%d%d' % (p[0], p[1], p[2], p[3]))
print = ce(x)
print('x = %d%d%d%d' % (p[0], p[1], p[2], p[3]))
```

#### 예제4
```python
def ce1(n):
  return(n<<24 & 0xff000000 | (n << 8 & 0xff0000) | (n >> 8 & 0xff00) | (n >> 24 & 0xff))
```

#### 예제5
- 비트 연산자 ^를 두번 연산하면 처음 값을 반환한다.
```python
def Bbit_print(i):
  output = ""
  for j in range(7, -1, -1):
    output += "1" if i & (1 << j) else "0"
  print(output)

a = 0x86
key = 0xAA

print("a        ==> ", end = '')
Bbit_print(a)

print("a^=key   ==> ", end = '')
a ^= key
Bbit_print(a)

print("a^=key   ==> ", end = '')
a ^= key
Bbit_print(a)
```
# Feb 28
## 진수
2 진수, 8진수, 10진수, 16진수
10진수 -> 원하는 타 진수로 변환
- 원하는 타진법의 수로 나눈 뒤 나머지를 거꾸로 읽는다.
- 예제) 149)<sub>10</sub> = (10010101)<sub>2</sub>
                       = (225)<sub>8</sub>
                       = (95)<sub>16</sub>

타 진수 -> 10진수로 변환
- 예) (135)<sub>8</sub> = 1\*8<sup>2</sup> + 3\*8<sup>2</sup> + 5\*8<sup>0</sup> = 93<sub>10</sub>
- 소수점이 있을 때의 예)
  - (135.12)<sub>8</sub> = 1\*8<sup>2</sup> + 3\*8<sup>2</sup> + 5\*8<sup>0</sup> + 1\*8<sup>-1</sup> + 2\*8<sup>-2</sup> = 93.15625<sub>10</sub>

2진수, 8진수, 16진수간 변환
- 2진법 -> 8진법 : 3자리씩 묶음
- 8진법 -> 2진법 : 3자리씩 나열
- 2진법 -> 16진법 : 4자리씩 묶음
- 16진법 -> 2진법 : 4자리씩 나열

컴퓨터에서의 음의 정수 표현 방법
- 1의 보수: 부호와 절대값으로 표현된 값을 부호 비트를 제외한 나머지 비트들을 0은 1로 1은 0으로 변환한다.
- 2의 보수: 1의 보수방법으로 표현된 값의 최하위 비트에 1을 더한다.

## 실수
실수의 표현
- 컴퓨터는 실수를 표현하기 위해 부동 소수점(floating-point) 표기법을 사용한다
- 부동 소수점 표기 방법은 소수점의 위치를 고정시켜 표현하는 방식이다.
  - 소수점의 위치를 왼쪽의 가장 유효한 숫자 다음으로 고정시키고 밑수의 지수승으로 표현

실수를 저장하기 위한 형식
- 단정도 실수(32비트)
- 배정도 실수(64비트)
|단정도 실수|부호 1비트|지수 8비트|가수 23비트|
|---|---|---|---|
|배정도 실수|부호 1비트|지수 11비트|가수 52비트|
  - 가수부(mantissa) : 실수의 유효 자릿수들을 부호화된 고정 소수점으로 표현한 것
  - 지수부(exponent) : 실제 소수점의 위치를 지수 승으로 표현한 것

단정도 실수의 가수 부분을 만드는 방법
- 예 : 1001.0011
	- 정수부의 첫 번째 자리가 1이 되도록 오른쪽으로 시프트
	- 소수점 이하를 23비트로 만든다
	- 소수점 이하만을 가수 부분에 저장
	- 지수 부분은 시프트 한 자릿수 만큼 증가 또는 감소
단정도 실수의 지수 부분을 만드는 방법
- 지수부에는 8비트가 배정(256개의 상태를 나타낼 수 있음)
- 숫자로는 0-255까지 나타낼수 있지만, 음수 값을 나타낼 수 있어야 하므로 excess 표현법을 사용
	- 익세스 표현법 : 지수부의 값을 반으로 나누어 그 값을 0으로 간주하여 음수지수와 양수지수를 표현하는 방법

컴퓨터는 실수를 근사적으로 표현한다.
- 이진법으로 표현할 수 없는 형태의 실수는 정확한 값이 아니라 근사 값으로 저장되는데 이때 생기는 작은 오차가 계산 과정에서 다른 결과를 가져옴
실수 자료형의 유효 자릿수를 알아 두자.
- 32비트 실수형 유효자릿수 (십진수) -> 6
- 64비트 실수형 유효자릿수 (십진수) -> 15

파이썬에서의 실수 표현 범위를 알아보자
- 파이썬에서는 내부적으로 더 많은 비트를 사용해서 후러씬 넓은 실수를 표현할 수 있다.
- 최대로 표현할 수 있는 값은 약 1.8 \* 10<sup>308</sup>이고 이 이상은 inf로 표현
- 최소로 표현할 수 있는 값은 약 5.0 \* 10<sup>-324</sup>이며, 이 이하는 0으로 표현
