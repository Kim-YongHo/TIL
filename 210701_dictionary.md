## Dictionary (딕셔너리)

- key와 value로 한 쌍의 item을 가지는 자료형
- 순서가 없어서 인덱스로 접근 X
- 중괄호 {} 사용해서 표현
- {key : value} -> key와 value을 합친 것이 item

---

## 딕셔너리 주요 함수

- keys()

  - 리스트 형태로 키 반환

- values()

  - 리스트 형태로 value 값 반환

- items()

  - keys와 value 동시에 반환

  ```
  member = {'name': '홍길동', 'phone' : '1234-1234', 'birth' : '10/15' }
  print(member.keys())
  print(member.values())
  print(member.items())
  ```

- 수정/추가/삭제

  ```
  #수정 (키 값 활용) 
  dict = { 'one' : 0, 'two' : 2 }
  dict['one'] = 1
  
  #추가
  dict = { 'one' : 1, 'two' : 2 }
  dict['three'] = 3
  
  #삭제 (키 값 활용)
  dict = { 'one' : 1, 'two' : 2, 'three' : 3 }
  del(dict['one'])
  dict.pop('one') # 삭제값 반환
  ```

---

## item 추가

```
d = {1:'a'}

print(d) # {1: 'a'}

d[2] = 'b'
print(d) # {1: 'a', 2: 'b'}

d['test'] = 'valueTest'
print(d) # {1: 'a', 2: 'b', 'test': 'valueTest'}
```

---

## 형변환

```
to_list = list(member.keys())
print(to_list)
print(type(to_list))

to_tuple = tuple(member.keys())
print(to_tuple)
print(type(to_tuple))
```

---

## for 문과 조합

~~~
member = {'name': '홍길동', 'phone' : '1234-1234', 'birth' : '10/15' }

for key in member.keys():
    print(key)

for value in member.values():
    print(value)

for item in member.items():
    print(item) ## 튜플 형태로 출력
~~~

---

## key로 value 값 찾기

- []로 사용 시 없을 경우 에러 발생
- get()로 사용 시 없을 경우 에러가 발생하지 않고 None 출력

~~~
member = {'name': '홍길동', 'phone': '1234-1234', 'birth': '10/15'}

print(member['name']) #홍길동
print(member.get('name')) #홍길동

print(member.get('names')) #None
print(member['names']) #에러 발생
~~~

---

## 관련 함수 찾기

```
my_list = []
print(dir(my_list))

my_tuple = ()
print(dir(my_tuple))

my_dictionary = {}
print(dir(my_dictionary))
```

---

