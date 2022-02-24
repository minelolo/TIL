# 2일차 정리

- 2일차에 배운 내용 정리하기 
- Vscode 상에 `git add -> commit -> push` 하는 과정까지 완료!

---

## GitHub

1. GitHub 가입 (Sign-Up)

- user name: minelolo
- user email : secret

2.  GitHub 상에서 TIL Repository 생성 (remote)
3. TIL Repository와 Local 연결 - TIL 저장소 주소를 복사해서
4. README.md : README.md 파일을 생성해 나만의 Today I Learned 내용 구성 (with 마크다운)

---

## Git 명령어

1. 파일 혹은 기록물 변경 이력 저장하기

```bash
# 일반 폴더 (TIL)을 로컬 저장소 (TIL)로 올려놓기
git init

# working directory에 있는 md 파일을 stagin area ()로 옮기기
git add . or git add "file_name.md"

# commit 하기 
git commit -m "add file_name.md"

# 현재 프로세스 상황 파악하고 싶으면
git status

# 현재 사용중인 저장소 변경 이력 출력하기
git log --oneline
```

2. Push : GitHub 에 올리기

```bash
# GitHub 연결을 위한 길 만들기
git remote add origin [github 저장소 URL]

# GitHub에 반영이 되기 위해 push 하기
git push origin master

# GitHub에 로그인하기

# 홈페이지에 정상 반영 확인하기
```

3. Gitignore : 특정 파일, 확장자, 혹은 폴더 등 필요없거나 민감한 정보를 담고 있는 것들에 대해 git이 관여하지 못하게 하는 목록 지정

```bash
# .gitignore 파일 생성
touch .igitignore 

# https://gitignore.io/에서 해당되는 단어 검색 및 vscode에 복붙하기
# command + s (저장)

# GitHub에 push하기
git add ".gitignore"
git commit -m "add .gitignore"
git log --oneline

# 정상 반영 확인하기
```

4. Clone : 원격 저장소 (TIL) 복제하기

```bash
# GitHub에 반영된 TIL 복제하기
## git init과 remote add는 별도로 수행할 필요 없음
git clone [github 저장소 url] TIL-class -> 새로 지정할 이름
```

5. Pull : 원격 저장소 (TIL)의 변경 사항을 local에 저장하기

```bash
# TIL의 변경사항을 local 저장소에 가져오기
git pull origin master
```

---

## 주의 사항

- 절대로 github상에서 edit 하지 말기
  - push 할 때 reject 오류가 나옴. 
    - 해결 방안 작성은 Later...
- 파일을 github에 드래그 하지 말기 
