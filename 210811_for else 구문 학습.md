~~~python
def solution(nums):
    
    import itertools #조합 기능을 사용하기 위해
    answer = 0
    datas = itertools.combinations(nums,3) ## nums라는 리스트에 3개를 골라서 data 리스트로 저장
    
    for data in datas:
        temp = sum(data)
        
        for i in range(2, temp):
            if temp%i == 0:
                break #break로 나가면 else 동작을 안함
        else:
            answer += 1
    
    return answer
~~~

