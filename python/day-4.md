# 모듈,패키지,프로그램
모듈은 단지 파이썬코드의 파일이다.<br>
import 파일명
```
#repory.py 파일
def get_description():
    """Return random weather, just like the pros"""
    from random import choice
    possibilties = ['rain','snow','sleet', 'fog', 'sun', 'who knows']
    return choice(possibilties) # 무작위로 보냄

# main.py 파일
import report as wr #as: 모듈이름을 똑같거나 더 짧게 쓰거나 할때 쓰면 된다 
description = wr.get_description()
print("Today's weather:", description)
#결과 Today's weather: sleet
#    Today's weather: snow


#필요한 모듈만 임포트 하는법
from report import get_description as doit
description = doit()
print("Today's weather:", description)
#결과 Today's weather: snow

#setdefault 딕셔너리에 키가 없는 경우 새 값에 사용된다
periodic_table = {'Hydrogen':1, 'Helium':2}
print(periodic_table)
carbon = periodic_table.setdefault('Carbon', 12)
print(periodic_table)
#결과 {'Hydrogen': 1, 'Helium': 2, 'Carbon': 12}

#defaultdict 값을 누락된 키에 할당하여 변환하는 함수다.
periodic_table = defaultdict(int)
periodic_table['Hydrogen'] = 1
periodic_table['Lead']
print(periodic_table)
#결과 defaultdict(<class 'int'>, {'Hydrogen': 1, 'Lead': 0})

#순서대로 키값을 반환한다.
from  collections import OrderedDict
quotes = OrderedDict([
    ('Moe','A wise guy, huh?'),
    ('Larry', 'Ow!'),
    ('Curly', 'Nyuk nyuk!')
])
for stooge in quotes:
    print(stooge)
#결과 Moe
#    Larry
#    Curly



```