# MTV패턴

##### 가상환경

python -m venv [가상환경명]	// 가상환경 만드는 명령어

source [가상환경명]/bin/activate	// 가상환경 실행

source [가상환경명]/script/activate	// 가상환경 실행

##### django 설치

pip install django	// 장고 다운

django-admin startproject [프로젝트 이름]	// 프로젝트 만들기

python manage.py runserver	// 서버 기동



#### MTV

- Model : Back end

  > DataBase(DB)

- Template : Front end

  > 사용자가 보이는 영역
  >
  > HTML, CSS, 템플릿 언어

- View : Back end

  > 데이터를 처리하는 곳
  >
  > MTV중에서 핵심



# Django 실습[1]

##### App 

> Django 프로젝트를 이루는 작은 단위

##### 웹사이트 구동 순서

1. 사용자가 서버에 요청
2. 서버의 view 는 model에게 요청에 필요한 데이터를 받음
3. view는 받은 데이터를 적절하게 처리해서 template으로 넘ㄱ미
4. template은 받은 정보를 사용자에게 보여줌

##### 정리

1. App을 생성
2. Template 제작
3. View 제작
4. URL 연결



# Django 실습[2]

##### 템플릿 언어

> html에서 파이썬 변수와 문법을 사용하게 해주는 언어

{% for word in wordDict %}

...

{% endfor %}



# Git 사용법

git : 자신이 작업한 코드 공유

echo "# firstproject" >> README.md	// README.md 파일을 만들고 그 안에 firstproject 라고 내용을 입력

git init	

git add origin [레퍼지토리 주소]	// 파일을 저장하고 기록

1. 저장할 파일 선택
2. 선택한 파일 저장

git commit -m "first commit"

git branch -M main	// 마스터 branch의 이름을 main으로 바꾼다

> git branch "브랜치 이름"	// 새로운 브랜치 만듦

git push -u origin main	// 파일 업로드

##### 정리

- 새로 만듦

  > git init
  >
  > git add
  >
  > git commit -m "message"
  >
  > git remote add [remote 이름] [repository 주소]
  >
  > git push [remote 이름] [branch 이름]

- 코드 수정

  > git add
  >
  > git commit -m "message"
  >
  > git push [remote 이름] [branch 이름]



# Django와 데이터 베이스

##### Wordcount

1. 클라이언트가 서버에 워드카운트 페이지를 보여주라고 요청을 보내는 것
2. 렌더링, 요청에 대한 서버의 응답으로 home.html을 보여준다
3. 클라이언트 이용자가 데이터를 적고 submit을 누르는 행위는 내용을 result url과 data 요청을 보내는 것이다
4. result url로 보낸 데이터를 views.py에서 세주는 로직을 통해 다시 클라이언트에게 result.html과 workdcount data로 응답을 해준다

- ORM: Object Relation Mapping

- models.py

- Python 객체지향
- class



# Model 실습

![image-20210615224528595](C:\Users\rlawlals119\AppData\Roaming\Typora\typora-user-images\image-20210615224528595.png)

##### 필드 옵션

- blank : validation 시에 empty 허용하는지
- null : null 값 허용하는지
- db_index : 인덱스 필드인지
- default : 디폴드 값이나 함수를 지정해줌
- unique : 현재 테이블 내 유일한 값인지
- makemigrations : 앱 내의 migration 폴더를 만들어서 models.py의 변경사항 저장
- migrate : Migration 폴더를 실행시켜 데이터베이스에 적용



# CRUD

Create Read Update Delte

데이터 베이스 정보를 CRUD

## Read

Path-converter : 디테일 페이지

Primary Key : 기본키, 데이터 베이스에서 ID 값을 pk라고 함

## Create

new : new.html 보여줌

create : 데이터베이스에 저장

##### GET vs POST

GET

- 데이터를 얻기 위한 요청
- 데이터가 url에 보임

POST

- 데이터를 생성하기 위한 요청
- 데이터 url 안보임
- Csrf 공격 방지

## Update

edit : edit.html 보여줌

update : 데이터베이스에 적용

create와 차이점: 수정할 데이터의 id값을 받아야함

## Delete

삭제하기 링크를 만들고 요청을 보내 보내준 id값에 맞는 데이터 하나를 삭제해주면 끝

# Templete 상속

##### Templete 상속

중복되는 코드를 중복작성하지 않기 위해  base.html을 만들어 상속을 시킴



# Static

##### 장고에서 다루는 파일

-> 정적파일 vs 동적파일

##### 정적파일: 미리 서버에 저장되어 있는 파일, 서버에 저장된 그대로를 서비스해주는 파일

- Static: 개발자가 서버를 개발할 때 미리 넣어놓은 정적파일(lmg, js, css)
- media: 사용자가 업로드 할 수 있는 파일



##### 동적파일: 서버의 데이터들이 어느정도 가공된다음 보여지는 파일(상황에 따라 달라질 수 있음)



# Media

1. static

서버에 사진 보여주라고 요청 -> 서버는 사용자에게 사진을 보여줌

2. madia

사용자가 사진 업로드 -> 서버는 사신 저장 -> 서버에 사진 보여주라고 요청 ->  서버가 사용자에게 사진을 보여줌(서버에서 사용자에게 사진의 url을 보냄)

서버는 사진을 보여줄 뿐이지 사진의 원본 형태를 보여주지는 않음

웹통신방식: url



# Form

Form: 입력 공간

클라이언트가 데이터베이스에 데이터베이스 형식에 맞게 정보를 보낼 수 있도록 함

장고에서는 forms.py 클래스로, 객체지향적으로 만들 수 있도록 제공

장점: 유효성 검사 편하게 사용가능



# User 확장과 인증

예시)

A <-- a -- 서버

B <-- b -- 서버

사용자에 따라 페이지에 보여지는게 다른데 이것을 서버에서 구별하기 위해 usertable이 필요



- 장고에서제공해주는 User, 이것만으로는 부족하기 때문에 {User를 대체할 테이블을 만들자!}

- 장고에서 제공해주는 auth
  - Authentication : 인증
  - 클라이언트가 서버에 회원가입 요청 -> 서버에서 유저 테이블에 회원정보 저장 -> 클라이언트가 서버에 로그인 요청 -> 유저 테이블에 로그인 정보가 맞는지 확인(authenticate) -> 맞다면 서버가 클라이언트에게 token(중요한 정보)를 줌(login) -> 클라이언트가 token을 가지고 서버에 요청을 보내면 -> 서버는 해당 user에 대한 응답

장고에서는 token을 발급하는 기능을 만들지 않고 {authenticate, login, logout} 함수 사용



# Paginator

{ 이용자가 많아지고 글이 많아진다 }

{ 블로그 객체를 잘라서 보내주는 paginator }

{ http://127.0.0.1:8000/?page=1 }	// 첫번째 페이지

{ <a href="?page=1"> }	// html에서 a태그로

{  /?page = paginator.어떤페이지 }	// 페이지 관련 정보도 있음


  # 배포 사전준비

{ 환경 변수, requirements.txt, AWS }



##### 환경 변수

- 시스템에 저장되어 있는 변수
- 보통 비밀키 등 유출되면 안되는 정보
- 환경 차이를 둘 때 사용 (테스트/프로덕션 구별 등)
- os.environ 에서 dict 형식으로 불러올 수 있음
- os.environ.get('변수명','기본값)으로 사용



##### requirements

- 파이썬(장고)앱을 실행하기 위해 우선 설치되어야 하는 패키지들(Django, Pillow 등)
- 패키지명 == 버전 으로 저장
- 보통 requirements.txt 파일에 저장
- pip freeze 명령어는 해당 환경에 설치된 모든 패키지를 보여줌
- ' > '는 프로그램의 출력을 파일에 저장한다는 뜻
- pip freeze > requirements.txt로 생성



##### IAM

- Identity and Access Management의 줄임말
- IAM에서 계정을 만든 후 해당 계정 로그인 정보 (엑세스 키 & 시크릿 키)를 이용하여 AWS의 API 활용
- 보안을 위해 권한을 최대한 보수적으로 잡음



##### S3

- Simple Storage Service 의 줄임말
- AWS에서 제공하는 구글드라이브 정도로 생각할 수 있음
- 최초 용량 지정 없이 사용한 만큼만 과금되므로 용량 예측 필요 X
- 여러 서버에서 동시에 접속 가능 (부하 분산 유리)



# Heroku 배포하기

1. Heroku 회원가입

2. Hereko CLI 설치

3. 환경 변수 적용

   1. Debug 는 아래 값 사용
      1. DBUG = (os.environ.get('DEBUG', 'TRUE') != 'False')

4. .gitignore 파일 적용

   1. gitignore.io에서 Django 선택 후 '생성' 클릭
   2. 페이지에서 나온 텍스트를 모두 복사후 .gitignore 파일로 저장

5. Heroku 용 파일 작성

   1. Procfile 이라는 파일을 만들어 아래 내용 작성
      1. web: gunicorn 프로젝트명.wsgi --log-file -
   2. runtime.txt 파일에 아래 내용 작성
      1. python-3.9.1

6. 필요한 Dependency 설치

   1. pip install gunicorn whitenoise df-database-url psycopg2-binary

7. settings.py 수정

   1. Whitenoise 설치

      1. MIDDLEWARE 에서 제일 SecurityMiddleware 바로 아래 내용 추가
         1. 'whitenoise.middleware.WhileNoiseMiddleware'.

   2. ALLOWED_HOSTS 수정

      1. ALLOWED_HOSTS = [] 를 ALLOWED_HOSTS = [ ' * ' ]로 수정

   3. DB 관련 코드 수정

      1. settings.py 제일 밑에 아래 내용 추가

      > import dj_database_url
      >
      > db_from_env = dj_database_url.config(conn_max_age=500)
      >
      > DATABASES['default'].update(db_from_env)

1. requirements. txt 생성

   1. pip freeze > requirements.txt

2. git에 수정된 파일들 추가

   1. git add -A
   2. git commit -m "add files for deploying to heroku"

3. Heroku 관련 명령어들 실행

   1. heroku login
   2. heroku create
   3. git push heroku main
   4. heroku run python manage.py migrate
   5. heroku run python manage.py createsuperuser
   6. heroku open

4. Heroku 에서 환경 변수 설정

   1. https://dashboard.heroku.com 에서 앱 선택
   2. Settings
   3. Config Vars > Reveal Config Vars
   4. KEY VALUE 값에 입력후 저장

   

   # Docker

https://www.yalco.kr/08_docker/           // 참고하기



##### Docker 이미지 생성

준비사항

- Gitpod.io 계정 (Free or Student)

- Gitpod 설정 수정

  - Feature Preview > Enable Feature Preview 체크
  - Default IDE 선택
    1. Theia : Eclipse 팀이 만든 IDE / 강의에서 사용
    2. Code : VSCode 의 웹버전 IDE / 호환성 이슈 있음
  - Gitpod 인스턴스 새성
    1. 본인의 GitHub 레포지토리로 이동
    2. 레포지토리 주소 앞에 gotpod.io/#을 붙임
    3. 예)gitpod.io/#https://github.com/username/repo
  - DockerHub 계정 생성

  

  

  

