## BFS 문제 분석

- [이코테] p152 미로탈출

~~~python
from collections import deque

def bfs(x, y):
    
    queue = deque() # 큐 기능
    queue.append((x, y)) # 튜플 형태 초기값 셋팅
    
    while queue: # queue 값 존재하지 않으면 종료
        x, y = queue.popleft() # 먼저 입력된 값을 popleft 기능으로 가져오고 삭제

        for i in range(4): # for문을 통해 행과 열로 옮길 수 있는 모든 경우의 표현
            nx = x + dx[i]
            ny = y + dy[i]

            if nx < 0 or nx >= n or ny < 0 or ny >= m: # 표현 불가능한 범위 
                continue # 아래 조건을 무시하고 다시 for문으로

            if graph[nx][ny] == 0: # 몬스터가 존재하는 위치 (갈 수 없는 곳)
                continue # 아래 조건을 무시하고 다시 for문으로

            if graph[nx][ny] == 1: #(갈 수 있는 곳)
                graph[nx][ny] = graph[x][y] + 1 # 해당 좌표에 값을 변경시켜 다시 해당 길을 생략
                queue.append((nx, ny)) # deque 추가
                
    return graph[n - 1][m - 1] # (n,m)의 좌표 실제로는 -1 필요(0,0) 부터 존재해서


if __name__ == '__main__':

    n, m = map(int, input().split()) # n*m 행렬 값

    graph = []
    dx = [-1, 1, 0, 0] # x 방향 값(행)
    dy = [0, 0, -1, 1] # y 방향 값 (열)

    for i in range(n): # 한 행씩 리스트 형태로 값을 가지고 옴
        graph.append(list(map(int, input())))
        
    print(bfs(0, 0))
~~~

