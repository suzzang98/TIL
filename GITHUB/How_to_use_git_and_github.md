# Git의 사용방법

### git이란?
분산형 버젼 관리 시스템

### git의 장점 
* 기능을 개발하면서 코드의 변경점을 기록할 수 있다.
* 특정 지점으로 돌아가기 쉬운 구조로 되어있다.

### git으로 저장하는 법
1. 작업 폴더를 열고 터미널이 작업 폴더에서 열려있는지 확인한다.
2. 파일을 작성한 후 저장을 해준다.
3. 터미널에 `git init`을 입력함으로 해당 폴더에 .git의 폴더를 생성한다.
4. `git add <파일명>`으로 저장하고 싶은 코드를 지정하고, `git commit -m <메세지>`를 통해서 저장해준다. (파일명 대신 "."을 사용하면 전체를 지정해 주는 것이다)
5. `git status`로 현재 상태를 파악해 준다.

이러한 방식으로 간단하게 git으로 코드를 관리할 수 있다.

### 이외의 다른 유용한 기능들
* `git log`<br>
&nbsp;&nbsp;&nbsp;&nbsp; 이전에 입력한 커밋의 내역이 나온다. 이것을 통해서 과거 시점으로 돌아갈 수도 있다.
* <strong>`git branch <브랜치명>`</strong><br>
&nbsp;&nbsp;&nbsp;&nbsp; 통째로 복사본을 만들 수 있는 브랜치를 만들어준다.
* `git switch <브랜치명>` or `git checkout <브랜치명>`<br>
&nbsp;&nbsp;&nbsp;&nbsp; 작성한 브랜치로 이동할 수 있다.
* `git merge`<br>
&nbsp;&nbsp;&nbsp;&nbsp; 다른 브랜치에 있는 코드를 가져와 합쳐주는 역할을 한다.


<br><br><br>

# Github 사용방법

### github란?
협업을 가능하게 하는 대표적인 무료 git 저장소

### github의 장점
* 팀원들과 효율적으로 협업할 수 있다.
* 코드를 온라인에 백업해 놓을 수 있다.

### github에 코드를 업로드 하는 법
1. 레포지토리를 생성해준다.
2. 하단의 push existing repository ~ 내의 코드를 복사해서 터미널에 붙여넣는다.

### github로 협력하는 방법
1. 대표자의 github에서 팀원을 collaborator로 등록한다.
2. 팀원들은 `git clone <링크>`를 통해서 github의 코드를 가져온다.
3. 브랜치를 새로 만들고 코드를 작성한다.
4. `git add`와 `git commit`을 통해서 커밋한다.
5. `git push origin <브랜치명>`을 통해서 github에 업로드한다.
6. Pull request를 만들어서 코드를 합칠 수 있다.

