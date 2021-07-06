## Error (에러)

- 문법적 오류, 실행 시간 에 잘못된 메모리 접근 오류, 논리 오류, 사용자 잘못된 입력 오류 등
- 오류가 발생하면 프로그램 중단되고 에러 메세지 출력



---

## 예외 처리 방법

- try...except 문 사용

  ![image-20210706141857608](C:\Users\USER-PC\Desktop\Study\Daily\TIL\TIL_picture\image-20210706141857608.png)

---

## 예시

~~~python
try:
    print(10/0) ## 에러가 발생하면 무조건 except 처리
except: #Exception 클래스를 포함하고 있어서 모든 에러를 처리
    print('오류 발생')
~~~

```python
try:
    #print(10/0) 
    print('나이' + 23 + '살')

except ZeroDivisionError: ##제로 디비전 에러만 처리
    print('오류 발생')
```

```python
try:
    print(10/0) ## 에러가 발생하면 무조건 except 구문으로 넘어간 후 프로그램 종료
    print('나이' + 23 + '살')

except ZeroDivisionError:
    print('오류 발생')
```

```python
try:
    print('나이' + 23 + '살')
    print(10/0) ## 에러가 발생하면 무조건 except 처리
    print('나이' + 23 + '살')

except ZeroDivisionError:
    print('오류 발생')
```

```python
try:
    num = int(input('숫자를 입력하세요 : '))

except ValueError:
    print('숫자가 아닙니다')
```

```python
## 에러 종류 명시 : as 에러 메세지 변수
try:
    num = int(input('숫자를 입력하세요 : '))

except ValueError as e:
    print('숫자가 아닙니다', e)
    
#숫자를 입력하세요 : 가나다
#숫자가 아닙니다 invalid literal for int() with base 10: '가나다'
```

```python
### 먼저 발생한 에로만 처리하는 문제가 있음

a = [1, 2, 3]

try:
    print(a[4])
    print(10/0)

except ZeroDivisionError as e:
    print('0으로 나눌 수 없습니다!')
except IndexError as e:
    print(e)

#### 괄호치고 에러 동시 기입 가능 위와 동일하게 먼저 인식되는 에러를 먼저 처리
a = [1, 2, 3]

try:

    print(10/0)
    print(a[4])

except (ZeroDivisionError, IndexError) as e:
    print('0으로 나눌 수 없습니다!')
    print(e)
```

```python
#### else
try:
    num = int(input('숫자입력 : '))
    print(num)

except ValueError:
    print('숫자가 아닙니다')

else: #에러가 없는 경우
    print(num)

#### pass    
try:
    num = int(input('숫자입력 : '))
    print(num)

except ValueError:
    pass

print('종료')


### finally else 추가
try:
    num = int(input('숫자입력 : '))

except ValueError:
    print('숫자가 아닙니다')

else:
    print(num)

finally:
    print('종료')

```

