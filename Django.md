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

