<h1>🌱TIL (Today I Learned)</h1>

## git 기초

### 깃 구성요소1

![깃 구성요소](git.assets/깃 구성요소.png)

---



### 깃 구성요소2

![깃 구성요소2(staging_area)](git.assets/깃 구성요소2(staging_area).png)

---



### 깃 구성요소3

![깃 구성요소3](git.assets/깃 구성요소3.png)

---

* `init` 명령어

1. `git`은 초기 init 명령으로 working directory 폴더를 만들 수 있습니다. 해당  폴더를 생성하면서 untracked(관리 되고 있는 파일/폴더가 아니다.) or tracked(관리되고 있는 대상) 으로 나뉩니다.
2. 만약 관리되고 있는 대상의 내용이 변경 되었다면 modified로 표시되게 되며 혹은 새로 만들어진 대상이라면 untracked로 빨간색으로 표시되게 됩니다.

* `add` 명령어

1. add 명령을 이용 해 새로생기거나 변경된 파일을 staging area 로 이동하게 되는데 staging area로 이동시킴으로 써 모든 파일을 tracked 즉, 관리대상파일로 변경하며 이미 관리대상인 파일일 경우 modified로 변경된 내용을 관리합니다. 
2. 해당 단계에서 commit 하기 전에 로컬 리파지터리로 옮기고 싶지 않은 파일을 관리할 수 있습니다.  

* `commit` 명령어
  1. commit 명령어를 통해 local repository 로 바뀐 파일/폴더를 다 저장합니다. 이로써 버젼이 만들어 지게 되고 해당 버젼을 통으로 관리하게 됩니다.

### ### 아래부터는 원격 저장소(git hub) 로 추가하는 작업입니다.

1. 원격 저장소 정보 등록(url)

   > git remote add remote별명 remote주소 <- 주로 사용하는 remote별명은 origin이름으로 사용한다. (해당 작업은 주소 등록이므로 한번만 등록해주면 됩니다.)

2. 그 후에 저장된 주소로 push 해준다.

   > git push -u origin master

5. 그 후에 실제 repository에 올라갔는지 깃허브에서 직접 확인.
