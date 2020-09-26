### 0. Preliminaries

- https://git-scm.com 에서 각자 운영체제에 맞는 git 설치
- 터미널/명령프롬프트/powershell을 실행한 후  ```git --version``` 명령어를 입력하여 정상 설치여부 확인

### 1. clone

Repository를 현재 작업 중인 directory로 다운로드 하는 과정. 다운로드 하는 내용에는 repository의 현재 소스 내용 뿐만 아니라 소스의 변화내역, 앞으로의 변화내역에 대해서 동기화를 시킬 레퍼런스가 포함된다.
```
git clone https://github.com/fba-projects/docs
```

```git log```를 통해서 현재까지 있었던 변화를 확인할 수 있다.

### 2. fetch, pull
``` ```
내가 작업하지 않는 동안 다른 사람이 같은 repository에 작업을 해서 수정을 했다면, 내가 만든 변경사항을 반영시키지 전에 해당 내용을 나의 환경에서 확인해서 점검할 필요가 있다. ```git fetch``` 명령어는 원격 repository에 반영된 모든 변경내역을 나의 환경에서도 사용 가능하도록 동기화 한다. ```git pull``` 명령어는 현재 작업 중인 branch에 

예를 들어, 현재 사용 중인 branch(=master)에 변경내역이 생겼다면, 다음의 명령어를 수행할 때 본 문서의 내용이 바뀌어 있을 것이다.

```
git fetch
git pull
```
> 2020.09.26일에 작성한 부분

### 2. branch

git을 사용하는 가장 큰 이유는 여러 명이 동시에 서로 다른 작업을 하면서도, 소스코드의 형상을 관리하기 용
이를 위해서는 전체 변경내용이 취합되는 repository의 본체, 즉 master branch에 영향을 주지 않으면서도 변경내역들을 저장할 수 있는 환경이 필요하다. 이를 branch라고 부른다. branch를 생성해서 기존의 변경내역과는 다르게 뻗어나가는 새로운 변경내역을 만들 수 있다. 생성한 branch들 간에는 checkout을 통해서 전환이 가능하다.

```bash
git branch tutorials/git-basics/<본인이름>
git checkout tutorials/git-basics/<본인이름>
# git checkout -b tutorials/git-basics/<본인이름> # 또는 이렇게 입력하여 두 개 명령어를 한 번에 수행할 수 있다.
```
이제 변경내역을 만들더라도 프로젝트의 본체에는 영향을 주지 않는 환경을 구성하였다.

### 3. add, commit 
디스크에서 일어난 변경사항을 git repository에 반영시키는 것. 방금 만든 branch에서 

```
git add <파일경로>
# git add --all # 또는 프로젝트 repository에 포함되는 모든 파일의 변경사항을 ```--all```플래그를 사용하여 한번에 적용할 수 있다.
```


```
git commit -m "added contents"
```
여기서 commit을 실행하면 현재 선택 된 branch에 현재 디스크 상에 저장된 
commit을 수행할 때에는 항상 메시지를 입력해야 한다.

checkout을 통해서 master branch 이동


### 4. push 
로컬 repository에서 변경한 내용을 원격(remote) repository에 반영하도록 변경 내역을 "밀어 올리는" 작업이다.

원격 repository는 햣 
어디로 밀어올릴지에 대해서 설정을 해 줘야 한다
```
git push --set-upstream origin tutorials/git-basics/<본인이름>
```

origin이라는 repository의 tutorials/git-basics/<본인이름>라는 branch에 변경내역을 반영한다는 듯이다.

upstream 설정은 branch 별로 설정한다. 한 번 upstream을 설정하고 나면 그 다음부터는 ```git push```명령어만 입력하더라고 commit을 push할 때마다 같은 upstream 설정을 사용하여 push가 실행된다.

(tip. upstream설정 없이 git push명령어를 입력하면, 에러메시지에서 적절한 명령어를 제안한다. 제안받은 명령어를 그대로 다시 활용하면 쉽게 push할 수 있다.)

여기까지 완료되었으면 remote repository(=https://github.com/fba-projects/docs)의 각자 생성한 branch에 변경내역이 반영되어 있다.

### 5. pull request
어디로 밀어올릴지에 대해서 설정을 해 줘야 한다
    git push --set-upstream origin tutorials/git-basics

5. pull request


6.

branch에 반영된 내용은 전체 프로젝트에 반영되기 적절한지 여부를 검토한 후 검토를 통과한다면, 프로젝트 전체에 변경내역을 반영할 수 있다. 이 검토 및 병합요청을 보내는 것을 pull request (PR이라고도 함)라고 한다.

merge pull request를 가진 사람이 pull request를 수락하면, 각자의 branch의 내용이 master branch의 내용으로 병합이 된다. 병합된 이후 master의 내용을 사용하게 되는 사람은 병합된 내용을 포함한 소스코드를 사용하게 된다.
