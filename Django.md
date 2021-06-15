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