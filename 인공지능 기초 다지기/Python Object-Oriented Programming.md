# Python Object-Oriented Programming

---
## 학습 날짜
> 2022-06-23

## 학습 시간
> PM 4:13 ~ 

---

### 객체 지향 프로그래밍
- 객체: 실생활에서 일종의 물건
- 속성과 행동을 가짐.
- Attribute, Action

### OOP는 객체 개념을 프로그램으로 표현
- 속성은 변수, 행동은 함수
- attribute: variable
- action: method

### Class 선언
- python3 에서 object는 자동 상속
```python
class SoccerPlayer(object):
```
> 함수와 변수명은 snake_case\
> Class는 CamelCase

### 파이썬에서 __ 의미 *magic method*
- __는 특수한 예약 함수나 변수 그리고 함수명 변경(맨글링)으로 사용
- __main__, __add__, __str__, __eq__, __init__ 등

### self?
- 생성된 인스턴스(객체)를 뜻함
- 코드 안에서는 self로 사용되고, 밖에서(선언부)에서는 객체명으로 사용됨

### 속성을 바꾸기
- apple.back_number = 10 <-- 권장하지 않음
- apple.change_back_number(10)

### Note 프로그램 작성
| | NoteBook | Note |
|:---:|:---:|:---:|
|method|add_note|write_content|
|      |remove_note|remove_all|
|      |get_number_of_pages|  |
|variable|title|content|
|        |page_number|        |
|        |notes|              |

### 필요한 세가지
- 상속, 다형성, 가시성
- Inheritance, Polymorphism, Visibility

### Inheritance 상속
- 부모클래스의 속성과 메소드를 자식클래스가 물려받아 생성하는것
```python
class Person(object):
  def __init__(self, name, age):
    self.name = name
    self.age = age

class Korean(Person):
  # Person 부모클래스
  # Korean 자식클래스
  pass

first_korean = Korean('Jo', 25)
print(first_korean.name)
```

### Polymorphism 다형성
- 같은 이름의 메소드를 *내부 로직을 다르게 작성*하는 것
- Dynamic Typing 특성으로 인해 파이썬에서는 같은 부모클래스의 상속에서 주로 발생함
- 중요한 OOP의 개념 그러나 너무 깊이 알 필요는 없다

```python
class Animal:
  def __init__(self, name):
    self.name = name
  
  def talk(self):
    raise NotImplementedError("Subclass must implement abstract method")
    
class Cat(Animal):
  def talk(self):
    return "Meow"

class Dog(Animal):
  def talk(self):
    return "Woof"
    
animals = [
  Cat('navi'),
  Cat('tom'),
  Dog('dodo')
]

for animal in animals:
  print(animal.name + ': ' + animal.talk())
```

### Visibility 가시성
- 객체의 정보를 볼 수 있는 레벨을 조절하는 것
- 누구나 객체 안에 모든 변수를 볼 필요가 없음
- private, protect, public
- 캡슐화 또는 정보 은닉 (Information Hiding)
- Class를 설계할 때, 클래스 간 간섭/정보공유의 최소화 목적
- __item 처럼 __ 를 붙여 private 변수로 생성

> private 속성에 접근이 가능해야 할 때가 있음\
> @property 사용 <-- 데코레이터라 부름

