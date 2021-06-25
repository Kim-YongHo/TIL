##  **발생 이슈**

![img](210624_GiHub_push_issue.assets/Untitled.png)

- git push를 하면 아무 일도 일어나지 않고 진행되지 않는 현상

- 현재 2.3.2 버전의 git credential manager가 에러가 있기 때문에 발생한 이슈



## **해결책**

- CTRL + ALT + DELETE 누르셔서 작업 관리자로 이동 후에 쭉  git-credential-manager-core 프로세스가 떠있을 강제로 작업 종료 누르면 로그인 창이 나옴

![img](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F515e8ad1-76fe-4b23-99f0-f3f3a151aef0%2FUntitled.png?table=block&id=d561c138-d2df-4b8c-ae5b-2e4f080f8c26&spaceId=daa2d103-3ecd-4519-8c30-4f55e74c7ef4&width=1590&userId=a2faf281-5047-4da0-aa28-a265725d18ac&cache=v2)

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/515e8ad1-76fe-4b23-99f0-f3f3a151aef0/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/515e8ad1-76fe-4b23-99f0-f3f3a151aef0/Untitled.png)

## **해결책 2**

[git-2.30.2.windows](http://git-2.30.2.windows) 버전으로 재설치



## **해결책 3**

github의 레포지토리는 권한이 있는 사용자만 push 할 수 있습니다. 따라서 로그인을 해줘야하는데요. 로그인을 하는 프로그램이 여러개 있는데, 그걸 변경하는 명령어 입니다.

```python
git config --global credential.git.example.com.provider generic
```