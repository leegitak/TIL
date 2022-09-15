# 파이 크러스트: 코드 구조

---
 
 ```
 
==    (같다)
 !=     (다르디)
 <      (보다 작다)
 <=    (보다 작거나 같다)
 >       (보다 크다)
 >=     (보다 크거나 같다)
in       (멤버십)


 # 주석이다.
#  🚫 한글로 변수명을 달지 마시오 🚫
#라인 유지
name = 'my '\
       'name '\
       'is '\
       'leegitak'

print(name)
#결과 my name is leegitak

# 비교하는 법
돈 = True
if 돈:
    print('true')
else:
    print('false')
#결과 true
#돈에다가 false를 넣으면 당연하게도 false가 출력됨

빵 = True
우유 = False

if 빵:
    if 우유:
        print("다음에도 부탁해")
    else:
        print("난 초코우유가 좋아! 다시사와")
else:
    if 우유:
        print("다음애도 부탁해")
    else:
        print("난 초코우유가 좋아! 다시사와")
#결과 난 초코우유가 좋아! 다시사와

소시지빵 = "소시지빵"
if 소시지빵 == "소시지빵":
    print("소시지빵 합격")
elif 소시빵 == "초코빵":
    print("초코빵 싫다고 했지")
#결과 소시지빵 합격

# 반복하기
빵셔틀 = 1
while 빵셔틀 <= 5:
    print(빵셔틀, "명")
    빵셔틀 += 1
#결과 1 명
#    2 명
#    3 명
#    4 명
#    5 명


빵셔틀_목록 = ["진구","훈이","범진"]
while count < len(빵셔틀_목록):
    print(빵셔틀_목록[count])
    count +=1
#결과 진구
#    훈이
#    범진

#조금더 우아하게 출력하기
for 빵셔틀_목록_복사 in 빵셔틀_목록:
    print(빵셔틀_목록_복사)
#결과 진구
#    훈이
#    범진

빵셔틀_목록 = ["진구","훈이","범진"]
빵셔틀_주문 = ["빵","우유","핫바"]
list_ = list(zip(빵셔틀_목록, 빵셔틀_주문))
print(list_)
dict_ = dict(zip(빵셔틀_목록, 빵셔틀_주문))
print(dict_)
#결과 [('진구', '빵'), ('훈이', '우유'), ('범진', '핫바')]
#결과 {'진구': '빵', '훈이': '우유', '범진': '핫바'}


# 함수
def LeeMoonse(music1,music2):
    return music1 + ", " + music2
print(LeeMoonse('붉은노을','깊은밤을날아'))
#결과 붉은노을, 깊은밤을날아

#클로져
#클로져는 다른 함수에 동적으로 생성된다. 그리고 바깥 함수로부터 생성된 변수값은 변경하고, 저장할수있다.
def knighrts(saying):
    def inner():
        return "We are the knigts who say: '%s'" %saying
    return inner
a = knighrts("miss")
b = knighrts("sam")
print(a())
print(b())
#결과 We are the knigts who say: 'miss'
#결과 We are the knigts who say: 'sam'

#제너레이터
# 일반 함수는 return 으로 반환하지만 yield문으로 반환한다
def my_ranger(frist=0, last=10, step = 1):
    number = frist
    while number < last:
        yield number
        number += step

ranger = my_ranger(1,5)
for x in ranger:
    print(x)

#네임스페이스(전역변수)
#locals() 함수는 로컬 네임스페이스의 내용이 담긴 딕셔너리를 반환한다.
#global() 함수는 글로벌 네임스페이스의 내용이 담긴 딕셔너리를 반환한다.
animal = '시고르자브종'
print(animal)
def change_animal():
    animal = '포메라니안'
    print("change_anmal: " + animal)
change_animal()
print(animal)
#결과 시고르자브종
#    change_anmal: 포메라니안
#    포메라니안
```