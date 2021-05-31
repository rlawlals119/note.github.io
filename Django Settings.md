# 오리엔테이션

##### 개발은 혼자하지 않는다

- 보안
- 개발자는 반드시 실수를 한다

# Windows 환경설정

git: 게임의 세이브 포인트



# 터미널 사용법1

터미널: CLI를 GUI 환경에서 사용할 수 있게 해주는 것

CLI: Command Line Interface

> 그래픽 없이 글자들로 구성, 명령어로 컴퓨터 조작

GUI: Graphic User Interface

> 1. 처음 지정된 기능 밖에 사용 불가
> 2. 조작 속도가 CLI에 비해 늦은 경우가 있음

~: 현재 작업중인 디렉토리의 위치

Home(~): 터미널 구동 시 처음 위치하는 디렉터리

Working directory(.): 작업중인 현재 위치

Root directory(/): 모든 디렉터리의 시작점

상위 디렉터리(..)

하위 디렉터리: 여러개가 존재할 수 있기 때문에 표현 방법이 없음

-> 상대적 위치의 디렉터리

##### 절대경로: 루트(/)에서부터 시작

-> 항상 표현방법이 같다

##### 상대경로: 현재(.)에서부터 시작

-> 현재 위치에 따라 다르다

# 터미널 사용법2

##### 명령어 [옵션] [인자]

##### 옵션

- "-"로 시작해서 영문 대소문자로 구성
- 명령어의 기능을 구체화
- 명령어에 따라 없을 수도 있음

##### 인자

- 명령어의 수행시 대상이 될 파일이나 디렉터리
- 명령어에 따라 필요 없을 수도 있고 필수일 수도 있음

pwd : Print Working Directory

- 현재 위치를 알려줌

man : manual

- 명령어 설명서

- man [알고싶은 명령어]

  > 설명 페이지에서 나오려면 q(quit)를 입력

ls : list

- 디렉터리의 목록 보여줌

- 옵션 a : 숨김파일까지 보여줌

- 옵션 l : 상세하게 보여줌

- 옵션 F: 파일인지 디렉터리인지 알려줌

  > 옵션은 한번에 여러개 사용 가능
  >
  > ex) ls -al

cd : Change Directory

- 현재 위치를 이동해줌
- cd [이동하고 싶은 위치]

clear

- 터미널 청소기

history

- 입력해온 명령어들 순차적으로 보여줌
- 화살표 위 아래로 확인 가능

tab

- 자동완성

# Django 시작하기



framework: 개발을 하는데 자주 사용하고 반복적으로 사용하는 기능들을 미리 만들어 놓아서 편리하게 함

- 라이브러리로 이루어진 라이브러리라고 보면 됨
- 개발속도가 빠름

가상환경

> python -m venv [가상환경명]

> source [가상환경이름]/Scripts/activate

> pip install django

> django-admin startproject [프로젝트이름]

> python manage.py runserver
