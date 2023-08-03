# 변수

---

## 변수란?

"변수란, 변하는 수(값) 이라고 한다."  
응? 뭔소리인가 하니...  

우리가 잔이 하나 있다고 생각하자. 그 잔에는 물도 담을수 있고 술도 담을 수 있다. 프로그램에서는 값을 담을 수 있는 것이 필요하다.  
그게 바로 **변수** 이다. 

변수는 정수, 소수, 문자열 그리고 True / False 를 구분하는 boolean 형으로 되어 있다.  
이건 또 무슨 소리?

위의 잔을 예를 들어 잔에도 종유가 있다. 커피를 담는 커피잔, 소주를 담는 소주잔, 물을 담는 물컵... 등등 여러 값을 잔에 담을 수 있고, 그 용도가 있다.
소주 잔에 가령 맥주를 담아 먹는다고 하면... 먹을 수는 있겠지만 맥주의 그 시원함을 느끼지 못할 것이고, 유리잔에 뜨거운 물을 담아 먹는다 하면 잔을 잡는 순간 너무 뜨거울 것이다.

이처럼 각 내용물에 맞는 그릇이 있듯 변수에도 여러 그릇이 존재 한다. 

### 변수의 종류 

* 정수 : 숫자의 기본값이다. 0 과 1, 2, 3 같은 자연수 혹은 -1, -2, -3 음수도 담을 수 있는 그릇이다. 
* 소수 : 소수점 값을 포함한 값을 담는다. 0.1, 1.3 같은 소수를 담는다. 참고로 1.0 도 소수다. 컴퓨터는 그렇게 본다.
* 문자 : 글자는 'a', 'b' 와 같은 1개의 문자를 의미 한다. 
* 문자열 : 문자열은 글자 모음이다.
* Boolean : True 혹은 False 값을 가진다. 계산기는 어차리 1 아니면 0 값을 연산 하기에 1은 보통 True, 0 은 False를 표시하지만 사람 눈으로 보기 힘드니 따로 형태를 지원한다.

끝이다. 이 외 배열이라 던가 좀더 개념적인 내용은 나중에 차차 알아가고 정말 이게 끝이다.  
어느 프로그램 언어를 가도 변수의 개념과 종류는 이게 끝이나. 단순 하지?


---

## 숫자를 담는 방법

사용법:
```python
>>> a = 10
>>> b = 20
>>> c = a + b
>>> print(s); print(b); print(c)
```

결과 : 
```shell
10
10
20
```

~~개쉽네...~~ 그냥 **'변수명 = 값'** 하면 된다. 정수든 소수든 그냥 이런식으로 쓰면 된다. 


## 문자/문자열을 담는 방법

문자도 변수에 담아 사용하지만 위의 숫자의 방법과 크게 다르지 않다. 숫자나 문자나 결국 변수니깐.  
하지만 연산을 할때는 숫자 형들과는 조금 다른 형태를 취한다.  
사칙연산이 정해진 숫자의 경우는 그냥 계산하고 결과를 반환 하면 된다. 그러나, 문자는 사칙연산? 그런거 없다.  
문자는 일부분의 내용을 수정 한다거나, 어디에 그 문자가 있는지 찾는다거나 더 손이 많이 간다. 
그래서 많은 프로그래밍 언어에서는 그런 기능을 제공해 주고 그를 활용해서 사용하면 된다. ~~맨땅에서 하나하나 다 만들면 끝도 없기에...~~


사용법:
```python
>>> str01 = 'abcdefg'
>>> str02 = 'hijklmnop'
>>> print(str01 + str02)
```
이 또한 간단하다~ ~~날로 먹는데 속도도 빨라 졌네...~~  

결과:
```python
abcdefghijklmnop
```

하지만 문자열의 경우 **문자**의 **배열**로 인식 하기 때문에 이에 따른 여러 부가적인 방법이 필요 하다 가령...

### 문자를 잘라서 가져오기

```python

# 한개만 가져오기
>>> str01[0]
'a'

# 영역 지정 해서 가져오기
>>> str01[:]
'abcdefg'
>>> str01[1:]
'bcdefg'
>>> str01[2:4]
'cd'
>>> str01[::2]
'aceg'
>>> str01[1::2]
'bdf'

# 건너 뛰고 가져오기
>>> str01[::2]
'aceg'
>>> str01[1::2]
'bdf'


```
배열 안에 무언가 들어간다. 일반적으로 배열에 단일 index 숫자만 넣게 되는데 파이썬은 무언가를 더 넣는다.

```
[start:end:step]
```

- **start** : 시작 index, 0부터 시작                              | 
- **end** : 끝나는 값, count 값이기 때문에 이 값의 -1 의 index 까지 가져온다. 
 str[2:4] 라면 2번 index 의 문자 'c' 와 4번째 문자 (3번째 index)의 'd'를 가져온다. 
 결국 2번째 문자부터 시작해서 4-2(e-s) 갯수 만큼의 문자를 가져온다고 보면 된다.
- **step** : 건너 뛰는 문자 갯수이다.


### 뒤에서 부터는 못가져와?

파이썬은 인덱스에 음수를 넣을 수 있다. 

```python
>>> str01[-1]
'g'
```
캬아~ -1 인덱스, 고로 0에서 한칸 뒤의 문자를 가져오는데... ~~이러면 index out bount exception 같은건... 안녕...~~  

```python
# 이건 안된다?
>>> str01[-1:2]
''

# 이건 된다???
>>> str01[1:-2]
'bcde'
```

- **str01[-1:2]** : 시작점은 언제나 끝나는 곳보다 뒤에 있어야 한다. -1 은 'g'의 index 를 가르키기 때문에  
6번째 index 로 인식 하기 때문이다. 결국 str01[6:2] 를 하라고 한것이니 당연히 '' 빈 문자열을 돌려 준다.  
~~이것도 이렇게 처리 되네... null 반환 하거나 error 반환 하는거 아닌거 뭐임?~~

이렇게 활용 할 수 있는 점이 참 편리 하긴 한데 오류 생기면 어떻게 되지? 찾기 조금 귀찮아 질 수 있는 부분 이다.  
그래도 편한 것이 더 많으니 좋다. 귀찮게 길이를 구해서 -1 을 해서 하는 코드가 줄어들 것 같다.  

### 문자열 합치기 

```python
>>> str1 = "hello"
>>> str2 = "lazy matin"
>>> str1 + " " + str2
```
+ 를 사용해서 문자를 합친다. 

### 문자 복제 하기

```python
>>> start = "NA" * 4
>>> start
'NANANANA'
```
이 쯤 편해지면 나 좀 무서워... 그냥 문자도 한개의 값으로 보고 확 곱해 버리는 저 클라스  
곱샘은 본디 덧샘의 연속이라 하지 않던가... 2*3 = 4 라는게 2 + 2 + 2 니깐... 문자따위 예외 없다. 

### 문자 관련 함수들



### 문자열 길이 : len()

```python
>>> len(str1)
5
```

### 문자열 나누기 : split()

```python
>>> wish_list = "sail yacht,cyber truck,a lot of meet,a lot of soju"
>>> wish_list.split(",")
['sail yacht', 'cyber truck', 'a lot of meet', 'a lot of soju']

>>> wish_list.split()
['sail', 'yacht,cyber', 'truck,a', 'lot', 'of', 'meet,a', 'lot', 'of', 'soju']
```

문자를 잘라서 배열로 반환 한다. 
split 함수의 전달인자가 없으면 ' ' 문자를 기준으로 잘라 버린다.0


### 문자열로 합치기 : join()

위의 + 연산자는 문자열과 문자열을 합친 새로운 문자열을 반환 한다면, join() 은 위의 split() 한 배열을 한 문자열로 합쳐 준다. 

```python
>>> splited_wish = wish_list.split(',')
>>> splited_wish
['sail yacht', 'cyber truck', 'a lot of meet', 'a lot of soju']
>>> ','.join(splited_wish)
'sail yacht,cyber truck,a lot of meet,a lot of soju'
```

~~쪼개진 나의 꿈이 다시....~~ split() 를 이용해 배열로 나누어진 것을 다시 한 문자열로 만들어 주는 기능이다. 
만약 + 연산자를 사용하게 된다면  

> splited_wish[0]+","+splited_wish[1]+","splited_wish[2]+","... 

이런 행위를 했어야 할 것 이다.

### 문자 관련 검색

문자열을 다루다 보면 시작 되는 문자, 이 문자는 몇번째에 있는지 등등 몇몇 검색이 필요한 경우가 있다.

```python
# 'of' 라는 문자가 처음 시작 하는 곳을 찾는다. 
>>> wish_list.find("of")
29
# 'of' 라는 문자가 마지막에 있는 곳에서 시작점을 찾는다. 
>>> wish_list.rfind("of")
43
# 'z' 라는 문자는 없기 떄문에 -1 을 return 한다.
>>> wish_list.find("z")
-1
# 'of" 가 몇번이나 나오는지 count 한다.
>>> wish_list.count("of")
2
```

find 는 정말 많이 쓰인다. 약속해둔 문자열을 찾기 위함 같은 거다.   
가령 중괄호 {} 안의 문자를 찾으려 할 때 예를 들어 보자. 

 

```python
# 우선 { 시작 부분을 찾아야 할 것이다.
>>> str = "Hi, My name is {your_name}. Nice to meet you."
>>> str.find("{")
15

# 그럼 이제 닫는 문자도 찾아야 할 것이다.(여기서는 예제를 위해 rfind 를 그냥 사용 하겠다.)
>>> str.rfind("}")
25

# 이제 { 와 } 의 위치를 알았으니 그 사이 값만 가져와 보자
>>> str[15+1:25]
'your_name'
```
짜잔~ 중괄호 사이의 값만 쏙~ 가져올 수 있다. 만약 문자열에서 markup 을 해야하는 상황은 수도 없이 많이 일어나고,  
이에 따른 문자열을 찾을 때는 이런 방식이 가능 하다. 저 your_name 의 문구만 다른 이름으로 replace 한다면 문장을 템플렛으로 만들 수 있다.  
(**주의** : { 를 찾을 값에서 +1을 해줘야 한다. 15는 { 문자의 시작 index 값이기 때문이다.) 

```python
# 문자열 시작이 meet 로 하는가?
>>> wish_list.startswith("meet")
False
# 문자열 마지막이 soju 인가?
>>> wish_list.endswith("soju")
True
# 문자열이 모두 숫자로 이루어져 있는가?
>>> wish_list.isalnum()
False
```

### 문자열 대체하기 : replace()

```python
>>> wish_list.replace("soju", "money")
'sail yacht,cyber truck,a lot of meet,a lot of money'

>>> wish_list.replace("a lot of", "many", 1)
'sail yacht,cyber truck,many meet,a lot of soju'

```


### 문자열 대소문자 변환
```python

>>> wish_list.capitalize()
'Sail yacht,cyber truck,a lot of meet,a lot of soju'
>>> wish_list.title()
'Sail Yacht,Cyber Truck,A Lot Of Meet,A Lot Of Soju'
>>> wish_list.upper()
'SAIL YACHT,CYBER TRUCK,A LOT OF MEET,A LOT OF SOJU'
>>> wish_list.lower()
'sail yacht,cyber truck,a lot of meet,a lot of soju'

```

### 문자열 정렬

```python

>>> wish_list.center(80)
'               sail yacht,cyber truck,a lot of meet,a lot of soju               '
>>> wish_list.ljust(80)
'sail yacht,cyber truck,a lot of meet,a lot of soju                              '
>>> wish_list.rjust(80)
'                              sail yacht,cyber truck,a lot of meet,a lot of soju'
```
---
 
# 후기...

새로운 프로그램 언어를 공부하는건 어렵진 않지만 귀찮은 일이다.  
마음 잡고 하면 1주 정도면 간단한 게시판 같은 것도 만들수 있지만... 그게 참 귀찮다. 난 게으르니깐.  
언제든 할 수 있기 때문에 더 미루는 경향이 있는거 같다. 그래도 툴도 있고, 대세가 대세니...  
