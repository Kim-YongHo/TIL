## Function (함수)

- 특정 작업을 수행하는 코드 집합

---

## 함수 장점

- 코드 재사용 가능
- 중복된 코드 제거
- 작업 분해
  - 기능별로 분리해서 작업이 가능

---

## 함수 종류

- 내장함수
  - 파이썬 내부에 미리 제작한 함수
  - 특정 객체를 통해 사용 가능한 함수 (메소드)

- 사용자 정의 함수
  - 사용자 제작한 함수

---

## 함수 구조

~~~
def 함수명 (매개변수1, 매개변수2):
	수행 문장1
	수행 문장2
	
	return 반환값


def Function_name (argument1, argument2):
	temp = argument1 + argument2
	
	return temp
~~~

---

## 함수 이름 설정

- 함수의 목적을 알 수 있게 함수 이름 설정
- 영문 소문자 위주로 사용할 것을 추천

---

## 함수 리턴

- 파이썬은 하나의 함수에서 여러 개의 반환값을 가질 수 있음

~~~
def multi_return():
    return 1, 2, 3

a, b, c =multi_return()

print(type(a))
print (a, b, c)
print(multi_return())
print(type(multi_return())) ## 동시에 return 할 경우 data type은 tuple
~~~

- 튜플, 리스트, 딕셔너리 반환 가능
- 반환값이 없는 함수를 강제로 대입 할 경우 None 값으로 인식
  - None을 NULL이랑 비슷한 개념으로 생각하면 됨

---

## argument (인수/인자)

- 함수에 실제로 전달되는 값 (호출할 때 전달되는 값)

  ```
  print("hello") # hello가 인자
  ```

![image-20210701153431229](C:\Users\USER-PC\Desktop\Study\Daily\TIL\TIL_picture\image-20210701153431229.png)

## parameter (매개변수)

- 함수를 호출할 때 전달되는 실제 값을 받아 저장하는 변수

  ```
  def print(data) # data가 매개변수에 해당됨
  ```

---

## default parameter

- 인수가 없어도 기본적으로 적용하는 매개변수

- `매개변수 =` 로 default 매개변수를 선언

  - default 매개변수는 마지막에 배치

  ```
  def greet(name, msg='안녕^^'):
  
      print(name + ', ' + msg)
      #name 인수가 꼭 전달되어야 하는 매개면수
      #msg - 매개변수는 인수가 전달되면 사용하고, 없을 경우 기본값 '안녕^^' 사용
  
  
  if __name__ == '__main__':
      greet('홍길동', '잘 지내시죠???')
      greet('김철수')
      greet('이철수')
  ```

  ```
  def show_info(name, year=4, age=23):
  
      print(name, year, age)
  
  
  if __name__ == '__main__':
      show_info('홍길동') #홍길동 4 23
      show_info('홍길동', 3) #홍길동 3 23
      show_info('홍길동', 1, 20) #홍길동 1 20
  ```

---

## 가변 길이 매개변수 (*args / **kwargs)

- 가변 길이 매개변수 (Variadic Parameter)

  - 1개의 매개변수로 개수가 정해지지 않은 여러 개의 값을 전달 받을 때 사용하는 매개변수
  - return 받은 값은 튜플

- *args

  - arguments의 약자

  - 인수값을 받음

    ```
    def show_players(*players):
        print(players)
        print(type(players))
        for player in players:
            print(player)
    
    if __name__ == '__main__':
    
        show_players('손흥민', '기성용')
        show_players('박지성', '황의조', '배다영')
    ```

- **kwargs

  - KeyWord arguments의 약자
  
  - key=value 값을 받음
  
    ```
    def info(**kesthd):
    
    
    info(id = 'abcd', name = 'kim') ##인수2개 딕셔너리
    info(id = 'abcd', name = 'lee', age = 30) ##인수3개 딕셔너리
    #info(1='abc') 
    #에러 발생 손으로 딕셔너리를 만들 때 key값으로 정수를 사용가능 하지만 함수에서 불가능
    ```

---

## 위치 인수 (position arguments)

- 함수 호출 시 위치에 의하여 구별하는 방식

- 매개변수의 순서대로 인수를 전달하는 방식

  ```
  def student_info(name, age, gender):
      student = {
          'name' : name,
          'age' : age,
          'gender' : gender
      }
      return student
  
  temp = student_info('다혜', 30, 'w')
  print(temp)
  
  temp = student_info(name='다영', age=30, gender='w')
  print(temp)
  
  temp = student_info('다혜', gender='w', age=28)
  print(temp)
  
  #temp = student_info(name='다호', 25, gender=27) ##에러 발생 위치 인수를 먼저 써야함
  #print(temp)
  ```

---

## 딕셔너리와 함께 사용한 예시

~~~

students = [
    {"name":"홍길동","korean":87, "math":98,"english":88, "science":95},
    {"name":"이몽룡","korean":92, "math":98,"english":96, "science":98},
    { "name":"성춘향","korean":76, "math":96,"english":94, "science":90},
    { "name":"변학도","korean":98, "math":92,"english":96, "science":92},
    {"name":"박지성","korean":95, "math":98,"english":98, "science":98},
    {"name":"류현진","korean":94, "math":88,"english":92, "science":92}
] ### 딕셔너리를 리스트로 묶음 형태

def get_student_subinfo(std_list):
    name = std_list['name']
    korean = std_list['korean']

    return {'name':name, 'korean':korean}


std_sublist = []

for s in students:
    #print(s)
    std_info = get_student_subinfo(s)
    std_sublist.append(std_info)

    #print(std_info)

print(std_sublist)
~~~

