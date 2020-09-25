0. Preliminaries
- git 설치
https://git-scm.com/
각자 운영체제에 맞는 git 

터미널 또는 CMD/PS 실행한 후  ```git --version``` 명령어를 입력하여 정상 설치여부 확인


1. clone
Repository를 현재 작업 중인 directory로 다운로드 하는 과정
다운로드 하는 내용에는 repository의 현재 소스내용 및 소스의 변화내역이 포함된다.
앞으로의 변화내역에 대해서 동기화를 시킬 레퍼런스도 포함

```
git clone https://github.com/fba-projects/docs
```

```git log```를 통해서 현재까지 변화가 있었던 내용을 확인할 수 있다. 현재 문서를 



마스터 브랜치에서 시작하는 작업을 한다면

```
git fetch
git pull
```

문서의 내용이 살짝 바뀌어 있을 것이다
2020.09.25일에 작성한 부분



2. branch

```
git branch tutorials/git-basics/<본인이름>
git checkout tutorials/git-basics/<본인이름>
```
또는
```
git checkout -b tutorials/git-basics/<본인이름>
```




3. add, commit 




4. push 
원격 저장소에 작업한 내용을 저장하도록 변경 내역을 "밀어 올리는" 작업


5. 


