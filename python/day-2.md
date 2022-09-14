# 리스트, 튜플, 딕셔너리, 셋
---

## 리스트
```
# 리스트는 값을 변경을 하거나 삭제 할수가 있다.
a = () #튜플 생성
a = [] #리스트 생성 

birthday = '1/9/1972'
print(birthday.split('/'))
#결과 ['1','9','1972']

#리스트안에 리스트
a = ['1','2','3']
b = ['a','b','c']
ab = [a,b]
print(ab)
#결과 [['1', '2', '3'], ['a', 'b', 'c']]

#꺼내 먹는법
print(ab[0][1]) 
#결과 2
print(ab[1][2])
#결과 c

#오프셋으로 항목 바꾸기
politics = ['red','yello', 'black']
politics[2] = 'blue'
print(politics)
#결과 ['red', 'yello', 'blue']

#리스트 추가하기
politics.append('mint')
print(politics)
#결과 ['red', 'yello', 'blue', 'mint']
politics.insert(2, 'black')
print(politics)
#결과 ['red', 'yello', 'black', 'blue', 'mint']

#병합하기
red1 = ['yun']
red2 = ['ahn']
red1 += red2
print(red1)
#결과 ['yun', 'ahn']

#삭제
del politics[2]
print(politics)
#결과 ['red', 'yello', 'blue', 'mint']
politics.remove('blue')
print(politics)
#['red', 'yello', 'blue', 'mint']

#바꿔치기
politics = ['red','yello', 'blue','black'] #재설정
politics.pop()
print(politics)
politics.pop(1)
#결과 ['red', 'blue','blue']
print(politics)
#결과 ['red', 'blue']

#항목 오프셋 찾기
red = ['yun', 'kim','ahn']
#결과 2

#존재여부
print('yun' in red)
#결과 True
print('hong' in red)
#결과 False

#값 세기
red.count('ahn')
#결과 1
red.count('sim')
#결과 0

#문자열로 변환
print('/'.join(red))
#결과 yun/ahn/kim

#정렬
sort() #리스트 자체를 내부적으로 정렬한다
soted() #리스트의 정렬된 복사본을 정렬한다
print(sorted(red))
#결과 ['ahn', 'kim', 'yun']
#내림차순으로 하고 싶으면 reverse=True
len(red)
#결과 3

#복사
yello1 = ['sim', 'lee', 'kim']
yello2 = yello1.copy()
print(yello1)
print(yello2)
#결과 ['sim', 'lee', 'kim']
#    ['sim', 'lee', 'kim']
```
---
## 튜플
```
# 튜플의 값은 변하지 않는다
#쓰는 이유: (1) 적은 공간을 사용한다 (2)손상될 걱정이 없다 (3)튜플을 딕셔너리 키로 사용할 수 있다/
a = () #튜플 생성
#()를 꼭 쓸필요는 없는데 구별하기 쉽게하기 위해서 쓴다.
#튜플은 한번에 여러 변수를 쓸수있다.
a = ('1','2','3')
b, c, d = a
print(b)
print(c)
print(d)
#결과 1
#    2
#    3
```
---
## 딕셔너리
```
#딕셔너리
empty_dict = {
	"year":"2022"
	"month":"9"
	"Work":"14"
}
print(empty_dict)
#결과 {'year': '2022', 'month': '9', 'Work': '14'}
empty_dict['month'] = '8'
print(empty_dict)
#결과 {'year': '2022', 'month': '8', 'work': '14'}
empty_dict['month'] = '9'
print(empty_dict)
#결과 {'year': '2022', 'month': '9', 'work': '14'}

#결합
empty_dict.update(empty_update)
print(empty_dict)
#결과 {'year': '2022', 'month': '9', 'work': '14', 'h': '10', 'm': '04'}

#있는지 없는지 확인하는법
print('month' in empty_dict)
#결과 True

#모든값 구하기
print('month' in empty_dict)
#결과 dict_values(['2022', '9', '14', '10', '04'])
#초기화
empty_dict.clear()
print(empty_dict)
#결과 {}




#딕셔너리 변환
lol = [['a', 'b'], ['c', 'd'],['e','f']]
print(dict(lol))
#결과 {'a': 'b', 'c': 'd', 'e': 'f'}
```
---
## 셋
```
#셋은 딕셔너리에서 키만 남은 느낌이다.
empty_set = {1,2,3,4,5}
print(empty_set)
#결과 {1, 2, 3, 4, 5}

print(set("leegitak"))
#결과 {'l', 'e', 'g', 'a', 'k', 't', 'i'}

#set으로 변환
#리스트
a = set(['1','2','3'])
print(a)
#결과 {'1', '2', '3'}

#튜플
a = set(('1','2','3'))
print(a)
#결과 {'1', '2', '3'}

#딕셔너리
a = set({'1':'2','3':'4','5':'6'})
print(a)
#결과 {'1', '5', '3'}
```