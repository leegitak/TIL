# 5일차

# 객체와 클래스

```python

class person():
    def __init__(self, name):  # __init__ 객체를 초기화하는 메서드이다.
        self.name = name

hunter = person('leegitak')
print('The hunter name: ' + hunter.name)
#결과 The hunter name: leegitak
```

### 상속이란 기존 클래스의 기능을 쓸 수 있다.
필요한것을 추가/변경 할수 있다.
기존 클래스의 추가/변경을 오버라이드라고 한다.
기존 클래스는 부모 클래스, 슈퍼 클래스, 슈퍼 클래스, 베이스 클래스라고 부른다.
새 클래스는 자식클래스, 서브 클래스, 파생된 클래스라고 한다.

```python
#상속
class Car():
    def exclaim(self):
        print("I'm a Car")

class Yugo(Car):
    pass
give_me_a_car = Car()
give_me_a_yugo = Yugo()

give_me_a_car.exclaim()
give_me_a_yugo.exclaim()
#결과 **I'm a Car
#    I'm a Car

#오버라이드 
class Person():
    def __init__(self, name):#self는 자신을 가리킴
        self.name = name

class MDPerson():
    def __init__(self, name):
        self.name = "Doctor " + name
class JDPerson():
    def __init__(self, name):
        self.name = name + ", Esquire"
person = Person('Fudd')
doctor = MDPerson('Fudd')
lawyer = JDPerson("Fudd")

print(person.name)
print(doctor.name)
print(lawyer.name)

#결과 Fudd
#    Doctor Fudd
#    Fudd, Esquire

class Car():
    def exclaim(self):
        print("I'm a Car")

class Yugo(Car):
    def exclaim(self):
        print("I'm a Yugo! Much like a Car, but more Yugo-ish")
    def need_a_push(self):
        print("A little help here?")
give_me_a_car = Car()
give_me_a_yugo = Yugo()

give_me_a_car.exclaim()
		give_me_a_yugo.exclaim()
#결과 Doctor Fudd
#    Fudd, Esquire

#super
class EmailPerson(Person):
    def __init__(self, name, email):
        super().__init__(name)
        self.email = email

bob = EmailPerson('Bob Frapples', 'bob@gmail.com')
print(bob.name)
print(bob.email)
#결과 Bob Frapples
#    bob@gmail.com

# get/set
class Duck():
    def __init__(self, input_name):
        self.hidden_name = input_name
    @property
    def name(self):
        print('inside the getter')
        return self.hidden_name
    @name.setter
    def name(self, input_name):
        print('inside the setter')
        self.hidden_name = input_name
fowl = Duck('Howard')
print(fowl.name)
fowl.name = 'Daffy'
print(fowl.name)
fowl.set_name
#결과 inside the getter
#    Howard
#    inside the setter
#    inside the getter
#    Daffy

class Circle():
    def __init__(self, radius):
        self.radius = radius
    @property
    def diameter(self):
        return 2 * self.radius

class Circle():
   def __init__(self, radius):
       self.radius = radius
   @property
   def diameter(self):
       return 2 * self.radius

c = Circle(5)
print(c.radius)
print(c.diameter)
#결과 5
#    10
#변경도 가능
c.radius = 7
print(c.diameter)
#결과 14

#__는 파이썬 클래스 정의 외부에서 벌 수 없도록 하는 속성에 대한 네이밍 컨벤션
class Duck():
    def __init__(self, input_name):
        self.__name = input_name
    @property
    def name(self):
        print('inside the getter')
        return self.__name
    @name.setter
    def name(self, input_name):
        print('inside the setter')
        self.__name = input_name
fowl = Duck('Howard')
print(fowl.name)
fowl.name = 'Daffy'
print(fowl.name)
fowl = Duck('Donald')
print(fowl._Duck__name)
#결과 inside the getter
#    Howard
#    inside the setter
#    inside the getter
#    Daffy
#    Donald

#classmethod는 클래스 전체 영향을 미친다.
class A():
    count = 0
    def __init__(self):
        A.count += 1
    def exclaim(self):
        print("I'm an A")
    @classmethod
    def kids(cls):
        print("A has", cls.count, "little objects.")

easy_a = A()
breezy_a = A()
wheezy_a = A()
A.kids()
#결과 A has 3 little objects.

#정적 메소드
#편의상 존재하는 @staticmethod, self나 cls가 필요없다 
class CoyoteWeapon():
    @staticmethod
    def commercial():
        print("This COyoteWeapone has been brought to you by Acme")
CoyoteWeapon.commercial()
#결과 This COyoteWeapone has been brought to you by Acme

#덕타이핑
#클래스와 상관없이 같은 동작을 다른 객체에 적용할 수 있다는 것을 의미한다.
class Quote():
    def __init__(self, person, word):
        self.person = person
        self.word = word

    def who(self):
        return self.person
    def says(self):
        return self.word + '.'
class QuestionQuote(Quote):
    def says(self):
        return self.word+'?'
class ExclamationQuote(Quote):
    def says(self):
        return self.word+"!"
hunter = Quote("Elmer Fudd", "I'm hunting wabbits")
print(hunter.who(), 'says: ',hunter.says())
hunted1 = QuestionQuote("Bugs Bunny", "What's up doc")
print(hunted1.who(), 'says: ',hunted1.says())
hunted2 = ExclamationQuote("Daffy Duck", "It's rabbit season")
print(hunted2.who(), 'says: ',hunted2.says())
#결과 Elmer Fudd says:  I'm hunting wabbits.
#    Bugs Bunny says:  What's up doc?
#    Daffy Duck says:  It's rabbit season!

def who_says(obj):
    print(obj.who(), 'says', obj.says())
who_says(hunter)
who_says(hunted1)
who_says(hunted2)

#결과 Elmer Fudd says I'm hunting wabbits.
#    Bugs Bunny says What's up doc?
#    Daffy Duck says It's rabbit season!

class Bill():
    def __init__(self, description):
        self.description = description
class Tail():
    def __init__(self, length):
        self.length = length
class Duck2():
    def __init__(self, bill,tail):
        self.bill = bill
        self.tail = tail
    def about(self):
        print('This duck has a', self.bill.description,
							"bill and a", self.tail.length, 'tall')

tall = Tail('long')
bill = Bill('wide orange')
duck = Duck2(bill, tall)
duck.about()
#결과 This duck has a wide orange bill and a long tall

#네임드 튜플
from collections import namedtuple
Duck = namedtuple('bill', 'bill tail')
duck = Duck('wide orange', 'long')
print(duck.bill)
print(duck.tail)
#결과 wide orange
#    long

#딕셔너리 네임드 튜플
parts = {'bill':'wide orange','tail': 'long'}
duck2 = Duck(**parts)
print(duck2)
#결과 bill(bill='wide orange', tail='long')

#또 다른 네임드 튜플로 반환
duck3 = duck2._replace(tail='magnificent',bill='crushing')
print(duck3)

duck_dict = {'bill':'wide orange','tail':'long'}
print(duck_dict)
duck_dict['color'] = 'green'
print(duck_dict)
#결과 {'bill': 'wide orange', 'tail': 'long'}
#    {'bill': 'wide orange', 'tail': 'long', 'color': 'green'}
class person():
    def __init__(self, name):  # __init__ 객체를 초기화하는 메서드이다.
        self.name = name

hunter = person('leegitak')
print('The hunter name: ' + hunter.name)class person():
    def __init__(self, name):  # __init__ 객체를 초기화하는 메서드이다.
        self.name = name

hunter = person('leegitak')
print('The hunter name: ' + hunter.name)class person():
    def __init__(self, name):  # __init__ 객체를 초기화하는 메서드이다.
        self.name = name

hunter = person('leegitak')
print('The hunter name: ' + hunter.name)**
```

****