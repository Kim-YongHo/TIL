## Buit-in-Functions (내장 함수)

- 파이썬에 미리 제작한 함수

---

## 주요 내장 함수

- abs(x) - x의 절대값 반환

- all(iterable) - 모든 요소가 참이면 True 아니면 False 반환 (0이 아니면 참)

  ~~~python
  	print(all([1,2,3,4])) #true
  	print(all([0, 1,2,3,4])) #false
  ~~~
  -  0이 하나라도존재하면 False 반환
  - iterable : 각각의 요소를 반환할 수 있는 형태 (for문으로 반복해서 출력 가능한 자료)

- any(iterable) - 하나라도 참이면 True , 모두 거짓이면 False

  ~~~python
      print(any([0,0,0])) #false
      print(any([0,1,2,3,4])) #true
      print(any([0,'',[]])) #false
  ~~~

- chi(i) - 아스키(ASCII)코드 값에 해당하는 문자 반환

  ~~~python
  	print(chr(65)) #A
      print(chr(97)) #a
      print(chr(98)) #b
      print(chr(13)) #enter
      
      for i in range(65,97):
      print(chr(i))
  ~~~

- ord(c) - chr과 반대로 문자에 해당되는 아스키코드 값 반환

  ~~~python
      print(ord('a'))
      print(ord('0'))
      print(ord('\n'))
      print(ord('\r'))
  ~~~

- divmod(a,b) - a를 b로 나눈 몫과 나머지를 튜플 형태로 반환

  ~~~python
      print(divmod(7,3))
  	#(2, 1) 튜플 형태
  ~~~

- enumerate(iterable, start=0) - 시퀀스 형태의 값을 넘겨주면 index 값을 포함하는 enumerate 객체로 반환

  - 객체가 현재 어느 위치에 있는 알려주는 인덱스가 필요할 때 사용

  ```python
  	print(enumerate(['Kim', 'Lee', 'Park']))
  	#<enumerate object at 0x00000206335770C0>
  
  	for i, name in enumerate(['Kim', 'Lee', 'Park']):
      	print(i, name)
      #0 Kim
  	#1 Lee
  	#2 Park
  ```

- eval(expression) - 표현식의 연산 결과 반환

  ```python
      print(type(eval('10'))) #<class 'int'>
      print(type(eval('10.5'))) #<class 'float'>
  
      print(eval('1+2')) # 3
  ```

- filte() - 여러 개 데이터에서 참만 걸러낼 때 사용

  ```python
  def even_number(x):
      if x%2 == 0:
          return x
  
  
  print(list(filter(even_number, [1,2,3,4,5,6,7,8,9])))
  #값이 없을 경우 리턴 시 None 넘어오는 것을 막아줌
  ```

- help() - 내장 도움말 시스템 호출

  ~~~python
  help(print)
  ################################################################
  Help on built-in function print in module builtins:
  
  print(...)
      print(value, ..., sep=' ', end='\n', file=sys.stdout, flush=False)
      
      Prints the values to a stream, or to sys.stdout by default.
      Optional keyword arguments:
      file:  a file-like object (stream); defaults to the current sys.stdout.
      sep:   string inserted between values, default a space.
      end:   string appended after the last value, default a newline.
      flush: whether to forcibly flush the stream.
  ###################################
  ~~~

- hex() - 정수를 '0x'접두사가 붙은 소문자 16진수 문자열로 반환

  ```python
  print(hex(7))
  print(hex(10))
  ```

- map(function 이름, iterable) - iterable 각 요소가 함수 function에 의해 수행된 결과 반환

  ~~~python
  def increase(x):
      return x+1
  
  print(map(increase,[1,2,3,4,5])) ###map 객체로 반환
  print(list(map(increase,[1,2,3,4,5])))
  ~~~

- open() - 외부 파일을 사용하기 위해 접근 경로를 생성하는 함수(파일없을 경우 해당 파일을 만들고 열어줌)

  ~~~python
  file_write = open('my_file.txt','w')
  ~~~

- round(number[.ndigits]) - 반올림 함수 ndigits : 소수 이하 자리수 

  ~~~python
  print(round(3.141592,3))
  #3.142
  ~~~

- zip(iterable, iterable1.....) : 각 iterable에서 동일한 인덱스의 요소를 추출하여 튜플 형태로 묶어서 반환

  ```python
  print(zip([1,2,3],[4,5,6]))
  print(list(zip([1,2,3],[4,5,6]))) #[(1, 4), (2, 5), (3, 6)]
  print(list(zip('123','abc'))) #[('1', 'a'), ('2', 'b'), ('3', 'c')]
  
  
  #zip 함수를 사용해서 튜플로부터 딕셔너리 생성하는 예제
  keys = ('apple', 'pear', 'peach')
  vals = (300, 250, 400)
  
  result = dict(zip(keys, vals))
  print(result) #{'apple': 300, 'pear': 250, 'peach': 400}
  ```

- sum(iterable) - iterable의 모든 요소의 합 반환

  ```python
  print(sum([1,2,3,4,5])) #1
  ```

---

## lambda 식

-  실행 시(런타임) 생성해서 사용할 수 있는 익명의 함수 (단, 하나의 파일에서만 사용)

  - 익명함수 : 이름이 없는 함수

- 입력과 출력이 있는 간단한 한 행짜리 함수를 만들 때 사용 가능 

  - 같은 함수를  def  문으로 정의할 때보다 간결하게  사용 가능

- 형식 : lambda  매개변수 : 표현식(lambda  매개변수 : 리턴값)

  ~~~
  ## 2개의 정수를 인수로 받아 더한 결과를 출력하는 함수
  
  def add(a, b):
      return a+b
  
  print(add(3,5)) # 8
  
  ## 람다식 표현
  print((lambda a,b:a+b)(3,5)) #8
  
  ## 람다식 실사용 재사용 유의 (변수에 저장해서 사용)
  lambda_add = lambda a,b:a+b
  
  print(lambda_add(3,5)) #8
  print(lambda_add(10,20)) #30
  ~~~

  
