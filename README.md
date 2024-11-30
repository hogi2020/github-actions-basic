# github-actions-basic
Study github-actions for CI/CD

## 기본 문법
1. .github 폴더 생성
2. .github > workflow 폴더 생성
3. workflow > xxx.yml 파일 생성 및 작성
    - workflow 사용 시, Token 인증이 필요합니다.
    - git init 후, repo를 생성하고 push를 합니다.

4. .yml 코드 블럭 설명
```yml
# yml 파일은 하나의 Workflow를 의미합니다.
# name은 workflow의 이름입니다.
name: Github Actions 실행시켜보기

# Event : 언제 workflow를 실행시키고 싶은지 결정하는 부분
# 즉 master branch에 push가 되었을 때, 실행한다는 의미입니다.
on:
  push:
    branches:
      - master
      
# 어떤 실행을 할지 결정하는 부분
# 하나의 Workflow는 1개 이상의 Job으로 구성됩니다.
# 여러 Job은 기본적으로 병렬적으로 수행됩니다.
jobs:
  # My-Deploy-Job은 Job을 식별하기 위한 id
  My-Deploy-Job:
    # ubuntu 환경 / 가장 최신 버전(latest)
    runs-on: ubuntu-latest

    # Step : 특정 작업을 수행하는 가장 작은 단위
    # Job은 여러 Step들로 구성되어 있다.
    # Step 마다 name을 붙일 수 있고, 리눅스 명령어를 사용
    steps:
      - name: Hello World 찍기
        run: echo "Hello World"
```
