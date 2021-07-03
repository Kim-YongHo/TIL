## Buit-in-Functions (내장 함수)

- 파이썬에 미리 제작한 함수

---

## 주요 내장 함수

- abs(x) - x의 절대값 반환

- all(iterable) - 모든 요소가 참이면 True 아니면 False 반환

  ~~~
  	print(all([1,2,3,4])) #true
  	print(all([0, 1,2,3,4])) #false
  ~~~
  -  0이 하나라도존재하면 False 반환
  - iterable : 각각의 요소를 반환할 수 있는 형태 (for문으로 반복해서 출력 가능한 자료)

- any(iterable) - 하나라도 참이면 True , 모두 거짓이면 False

  ~~~
      print(any([0,0,0])) #false
      print(any([0,1,2,3,4])) #true
      print(any([0,'',[]])) #false
  ~~~

- chi(i) - 아스키(ASCII)코드 값에 해당하는 문자 반환

  ~~~
  	print(chr(65)) #A
      print(chr(97)) #a
      print(chr(98)) #b
      print(chr(13)) #enter
      
      for i in range(65,97):
      print(chr(i))
  ~~~

- ord(c) - chr과 반대로 문자에 해당되는 아스키코드 값 반환

  ~~~
      print(ord('a'))
      print(ord('0'))
      print(ord('\n'))
      print(ord('\r'))
  ~~~

- divmod(a,b) - a를 b로 나눈 몫과 나머지를 튜플 형태로 반환

  ~~~
      print(divmod(7,3))
  	#(2, 1) 튜플 형태
  ~~~

  