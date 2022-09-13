# 파이썬 1일차
---
## 파이썬 데이터 타입

bool: True와 False값만 가질수 있다. True는 1 False는 0의 값을 가진다<br>
int: 숫자이다 (30, 69)<br>
char: 문자 (’문’ , ’자’)<br>
float: 소수점이 있는 숫자 (3.14, 5,924)<br>
string: 문자열 (”문자열")
---
## 숫자 연산자
```
# + 더하기
# - 빼기
# * 곱하기
# / 나누기: 예) 7 // 2 = 3.5
# // 나누기:(소수점 버림) 예) 7 // 2 = 3
# % 나머지: 예) 7 % 3 = 1
# ** 지수: 예) 3 ** 4 = 81
# divmod(9, 5): 몫과 나머지를 동시에 얻음: 출) (1,4)
```
---
## 문자

```
print('ab\tcd')#\tab
#결과 ab	cd
print("hi "*5)
#결과 hi hi hi hi hi

#문자 추출
#[start:end:스텝]
letters = '가나다라마바사아자차카타파하'
print(letters[0])
#결과 가
print(letters[4])
#결과 마
print(letters[0:4])
#결과 가나다라
print(letters[1:4])
#결과 나다라
print(letters[0:-1])
#결과 가나다라마바사아자차카타파
print(letters[0::2])
#결과 가다마사자카파
print(letters[::-1])
#결과 하파타카차자아사바마라다나가



#문자 바꿔치기
name = 'Leegitak'
name = name.replace('L', 'P')
print(name)
#결과 Peegitak
name = 'Leegitak'
name = 'P' + name[1:] # name = 'P' + name[0:]하면 PLeegitak됨
print(name)
#결과 Peegitak
name = 'Leegitak'
name = name.replace('Lee', "Pack")
print(name)
#Packgitak

#문자열 길이 구하기
letters = '가나다라마바사아자차카타파하'
a = len(letters)
print(a)
#결과 14

#문자열 결합
string_list = ['a','b','c','d']
total_string = ', '.join(string_list)
print(total_string)
#결과 a, b, c, d

#문자열 찾기
letters = '가나다라마바사아자차카타파하'
print(letters.find('다'))
#결과 2

#문자열 대문자 소문자로 바꾸기
setup = 'im iron man'
print(setup.capitalize())#첫번째 단어만 대문자
print(setup.title())#모든 단어의 첫번째만 대문자
print(setup.upper())#모든걸 대문자로
print(setup.lower())#모든걸 소문자로
print(setup.swapcase())#대문자는 소문자로 소문자는 대문자로
# 출력
# Im iron man
# Im Iron Man
# IM IRON MAN
# im iron man
# IM IRON MAN

```