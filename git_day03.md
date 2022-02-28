# 3일차

**Time-line **

- 2일차 복습 & 코드 예시
- TIL repository, README.md 실습
- branch 명령어 (1)
- branch 명령어 (2)
- branch 실습
- branch merge , conflict 실습 
- git workflow
- git workflow 실습

---

## Branch란?

**Branch는 나뭇가지라는 의미를 가지고 있고 뜻과 같이 나뭇가지처럼 여러 갈래로 나뉘어진 작업 공간을 의미한다.**

![branch 사진](git_day03.assets/git-branches-merge.png)

- branch 사용 이유: 동시다발적으로 업무를 하는 경우 서로 다른 작업 공간을 마련해 서로 영향을 받지 않는다. 그리고 마지막에 서로 다른 변경 사항을 적용할 수 있어 협업하는데 최적이다.

---

### Branch 기본 명령어

1. 조회, 생성, 삭제, 브랜치 목록 확인 git 명령어

```bash
# 브랜치 생성
git branch 브랜치이름

# 특정 커밋 기준으로 브랜치 생성
git branch 브랜치이름 커밋이름

# 브랜치 목록 확인
git branch

# 원격 저장소 (TIL) 브랜치 목록 확인
git branch -r

# 브랜치 삭제
git branch -d 브랜치이름 # 병합된 브랜치만 삭제 가능
git branch -D 브랜치이름 # 강제 삭제 기능
```

2. 브랜치 이동 git 명령어

```bash
# 브랜치 이동
git switch 다른브랜치이름

# 브랜치 생성 및 이동
git switch -c 브랜치이름

# 특정 커밋 기준으로 브랜치 생성 및 이동
git switch -c 브랜치이름 커밋이름
```

3. 브랜치를 포함한 그래프 형성 명령어

```bash
# 모든 브랜치 로그 보기
git log --oneline --all

# 그래프와 함께 보기
git log --oneline --all --graph
```

4. 브랜치 병합 명령어
   - Branch Merge는 master에 반영하는 즉 병합하는 역할을 한다. 독립적 공간인 각 브랜치에서 작업을 완료한 후에 merge를 사용해 합쳐야할 경우 사용한다. 

```bash
# kim와 mini 브랜치가 있고, HEAD (현재 위치)가 알려주는 것은 kim 브랜치.
git branch
* kim
  mini
  
# kim에 mini를 합치기
git merge mini

# mini에 kim 합치기
git switch mini
git merge kim
```

---

### Branch Conflict

직접 해보면서 익혀나가는게 중요할 것 같아 보류

---

## Git Workflow

**branch를 이용해 협업하는 두 가지 방법**

1. 원격 저장소 소유권이 있는 경우 (Shared repository model)

 - 개념

     - 자신이 소유한 원격 저장소 혹은 소유권이 등록되어 있는 경우 (collaborator)에 가능

     - master에 개발하는 것이 아니라 맡은 업무별 브랜치를 별도로 생성해 개발

     - Pull request를 사용해 협업자들과 변경 사항에 대해 소통

- Workflow

```bash
# clone 실행 - 소유권을 가지고 있는 원격 저장소를 로컬 저장소로 변경
git clone URL

# branch 생성 및 작업 실행
git switch -c login

# 작업 완료 후 원격 저장소로 push (branch - 원격)
git push origin login

# 원격 저장소에는 master와 각 작업의 브랜치들이 반영 되있음

# pull request를 통해 master에 반영

# 병합이 완료되면 각 작업 브랜치 삭제 - 불필요하기 때문 (원격저장소에서)

# master 병합 후 각 개발자들은 master 브랜치로 이동
git switch master

# 병합된 내용 (master)를 로컬에 저장
git pull origin master

# 기존 로컬 작업 브랜치 삭제 - 불필요하기 때문
git branch -d login
```

2. 원격 저장소 소유권이 없는 경우 (Fork & Pull Model)

- 개념
  - 자신이 소유권이 없는 원격 저장소 => 오픈소스
  - 타 원격 저장소를 내 원격 저장소에 복제 => **fork**
  - 작업 완료 후에 push하여 내 원격 저장소에 저장
  - pull request를 통해 타 원격 저장소에 반영이 될 수 있도록 요청

- Workflow

```bash
# 타 원격 저장소를 fork를 사용해 복제

# 복제된 것을 clone을 통해 내 로컬 저장소에 복제
git clone URL

# 타 원격 저장소와 로컬 저장소를 동기화 위해 연결
git remote add upstream 타원격저장소링크

# 작업할 브랜치 생성
git branch -c login

# 작업 완료 후 복제한 원격 저장소에 push
git push origin login (branch - 복제 원격 저장소)

# 복제 원격 저장소에 master와 브랜치 반영 완료

# 복제 원격 저장소를 타 원격 저장소에 반영해 달라는 pull request 사용 

# 타 원격 저장소 master에 병합이 되면 복제 원격 저장소 브랜치 삭제

# 개발자는 로컬 저장소에서 master로 이동
git switch master

# 병합된 내용이 반영된 타 원격 저장소 내용을 로컬 저장소에 받기 위해 pull
git pull upstream master
git branch -d login
```





