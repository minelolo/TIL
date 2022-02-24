# CLI

- CLI VS GUL

- 커멘드라인 명령어

  ```bash
  # 디렉토리 생성
  mkdir
  # 디렉토리 이동
  cd
  # 파일을 생성
  touch
  # 디렉토리 안 리스트를 확인
  ls
  # 제거
  rm
  ## -r 옵션: 재귀적
  ## -rf 옵셥: 강제 삭제
  # 이동/이름변경
  mv
  #현재의 경로를 보여줌
  pwd
  # 화면 깨끗이/스크롤 올리기
  clear
  command + l
  ```

  

# 마크다운

- 마크다운과 마크업

  - 마크 업 : HTML -> 개발자 도구로 확인 (태그)
  - 마크다운 : 경량화된 마크업 언어

- 마크다운 역할

- 마크다운 문법

  ```markdown
  1. 제목 : # ~ ######
  2. 목록 : \-, \*, \+ / 들여쓰기와 내어쓰기 (tab, shift + tab)
  3. 강조 : 
  	- 기울임 : *글자* 
  	- 굵게 : **굵게**
  	- 기울이고 굵게 : ***글자***
  4. 코드
  	- 인라인 : `한줄코드` 백틱으로 묶어주기
  	- 코드블럭 : 여러줄 코드를 백틱 3개로 묶어주기
  	- 하이라이트 : 마크다운에서 코드블럭 형성시 알맞은 걸 사용하면 자동으로 하이라이트가 된다. 
  5. 링크 : [표시하고 싶은 텍스트](연결하고 싶은 url)
  6. 이미지 : 
  	- url로 연결할 때 : ![표시텍스트](이미지 주소 url)
  7. 구분선 : ---
  8. 표 : command(ctrl) + t  
  9. 인용문 : > 뒤 인용문구 작성, 중첩 가능
  ```

  

# git 기초

- git의 3공간

  - 분장실, 무대, 사진 촬영본
  - Working Directory, Stage Area, Commits

- Git 명령

  - git init
    - 유의 사항 : 맨처음1회, 절대 홈폴더에서 하지 않는다.
    - git init한 폴더의 하위 폴더에서 절대 git init하지 않는다.
  - git add
  - git commit -m "message"
  - git status : 파일 상태를 확인
  - git log : 커밋 내역 확인
    - --oneline : 한줄 출력

- git 초기 설정

  - git config

    ```bash
    git config --global user.name "id"
    git config --global user.email "my email" # git hub에서 사용
    ```

    

---

# TIL

`Today I Learned` : 하루하루 배웠던 내용을 기록하는 repository