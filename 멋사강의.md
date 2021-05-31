# CSS 기초

##### Cascading Style Sheets

선택자: 스타일을 적용하고자 하는 html요소 선택

속성: 속성: 값;이 한 단위, 세미콜론으로 구분

값: 특정 단위를 이용하여 스타일 적용, 속성과 쌍을 이룸

> p{
>
> font-family: '맑은 고딕';
>
> font-size: 18px;
>
> }

CSS는 반드시 HTML에 적용시켜야 사용 가능

##### HTML에 CSS를 적용하는 방법

- Link style

  : HTML 외부에 있는 CSS 파일 불러옴

- Embedding style

  : <head>에 <style>을 이용하여 CSS 작성

- Inline style

  : HTML 요소에 직접 style 속성(Attributes)을 이용하여 작성



# 선택자

##### 일반적인 태그 (h1, p, span, div)

##### 콤마(,)를 이용하여 여러 개의 선택자 스타일을 한번에 지정 가능

> h1, p{
>
> color: red;
>
> }

#####  단순 선택자

<선택자>

- 타입 선택자

  > 해당 태그를 가지는 모든요소에 스타일 적용
  >
  > <style>

- 클래스 선택자

  - 클래스: 비슷한 요소들 묶음, 여러번 사용 가능

  > 같은 클래스 이름이면 모두 적용
  >
  > .main{color: red;}

  > <p class="main">

  

- 아이디 선택자

  > Id로 스타일 적용, 해당 Id 하나에 적용
  >
  > #main{color: red;}
  >
  > <p id="main">

- 전체 선택자

  > 모든 요소에 스타일 적용, 속도 저하 가능성 있음
  >
  > *{color: red;}

- 속성 선택자

  > 특정 속성을 소유하는 모든 요소에 스타일 적용
  >
  > 선택자[속성명="속성값"] {color: red;}

- 복합 선택자

  - 자식 선택자

    > 선택자A > 선택자B {color: red;} 

  - 후손 선택자 

    > 선택자A 선택자B {color: blue;}

- pseude 클래스

  > 요소의 특별한 상태를 지정할때 사용
  >
  > 선택자: pseudo-class{
  >
  > ​	속성: 속성 값;
  >
  > }

  - :link : 방문하지 않은 링크일 경우
  - :visited : 방문한 링크일 경우
  - hover : 요소에 마우스가 올라와 있을 경우



# 값과 단위

- 숫자값과 백분율

  - 숫자값

    - px

      - 화소단위

      - 절대 길이

    - em

      - 현재 스타일이 지정된 요소의 폰트 사이즈 기준

      - 상대적 길이

    - rem

      - 최상위 요소의 font-size 기준
      - 상대적 길이

      > 1em(1rem) 의 크기 = 기준 font-size*1em(1rem)

      

    - %(퍼센트)

      - 상대길이, 보통 이미지나 레이아웃의 너비나 높이를 지정할 때 씀

# 텍스트와 관련된 프로퍼티

#### 폰트와 관련된 프로퍼티

- font-size

  > font-size: 35px;

- font-family

  - 원하는 폰트 설정 가능

  - 한 단어로 구성된 폰트명은 상관없지만 여러  단어로 구성된 폰트명은 따옴표 필수

    > font-family: 'Cute Font', Arial, cursive;
    >
    > // 모든 이용자의 기기에 동일한 폰트가 있는 것이 아니기 때문에 여러개의 폰트 종류 정의
    >
    > // 앞에서 부터 차례로 폰트를 적용하고 없는 폰트일경우 그 다음 폰트 종류로 넘어감
    >
    > // 마지막에는 일반 글꼴인 cursive를 둔다

  - 웹폰트

    - Google Fonts 에서 원하는 글꼴의 STANDARD 링크를 복사하여 헤드부위에 링크태그를 이용하여 폰트 적용

- font-style

  - normal

  - italic

  - oblique: 기울임체

    > font-syle: oblique

- font-weight: bold

  - 100~900

  - normal: 400

  - bold: 700

    > font-weight: 900;

##### 폰트 프로퍼티

- font : (style) (bold) (size) (family);

- 띄어쓰기로 구분

  > font : oblique 900 35px 'Note Sans KR', sans-serif;

#### 텍스트 정렬과 관련된 속성

- text-align: 텍스트를 좌,우,중앙 정렬, 자기자신을 기준으로 정렬

- line-heigt: 문장사이의 간격을 조정

  > line-height: 24px;	
  >
  > // 단위없는 숫자값은 해당요소의 폰트사이즈를 기준으로 배로 만들어줌

- letter-spacing: 글자와 글자 사이의 간격을 조정, 자간

- text-indent: 문단부의 시작부에 들여쓰기를 함

# 박스모델

##### 박스 모델 개념

![image-20210510231546699](C:\Users\rlawlals119\AppData\Roaming\Typora\typora-user-images\image-20210510231546699.png)

- content(내용): 실제 내용

  +. overflow: fidden;

  +. overflow: scroll;

- border(경계선): content를 감싸는 테두리 선

  - border-style

    > border-style: dashed solid dotted double;	// 띄어쓰기로 구분
    >
    > - 1개: 전체
    >
    > - 2개(a, b): 상하는 a, 좌우는 b
    >
    > - 3개(a, b, c): 위는 a, 좌우는 b, 아래는 c
    >
    > - 4개(a, b, c, d): 시계 방향으로 a(위), b(오른쪽), c(아래), d(왼쪽)
    >
    >   -> width, color, margin, padding도 같은 방식으로 적용됨

    > border: 4px solid red;

    - border-radius: 둥근 모서리

      > border-radius: 12px;	// 반지름 12px
      >
      > -> 이것또한 네 방향으로 위와같이 적용

      - border-top-left-radius: 타원형 가능

        > border-top-left-radius: 30px 10px	// 두개의 숫자값, 타원의 가로 반지름, 세로 반지름
        >
        > border-radius: 30px 20px 10px 0 / 0 10px 20px 30px	// 나누기로 적용 가능

  - border-width

  - border-color

  - box-sizing

    - box-sizing: content-box;	// 콘텐트 박스의 크기를 기준

      > width(height)= content size

      - box-sizing: border-box;	// border의 두께까지 포함된 크기를 전체크기로 정함

        > width(height)= content size + padding + border

- padding: 보더 내부 여백

- margin: 보더 외부 여백

  - 마진 상쇄

    : 상하 요소사이의 마진은 상쇄가 된다. 그 기준은 큰 쪽을 따라간다

  > padding과 margin 모두 네 방향 따로 설정 가능

# 위치와 관련된 프로퍼티[1]

##### display

: 요소가 보여지는 방식을 지정

HTML 요소

- display: block;	// block element;

  : width, height, margin, padding 가능

- display: inline;    // inline element;

  : width, height, margin-top, margin-bottom 불가능

display: inline-block;

: width, height, margin-top, margin-bottom 가능

display: none;

: 브라우저에 해당요소가 출력이 되지 않음



##### position: 요소의 위치를 정의

- static

  : 기본값, 좌표 프로퍼티를 쓸 수 없음

  > position: static;
  >
  > top: 20px;
  >
  > left: 20px;

- relative

  : 상대 위치, 기본 위치를 기준으로 좌표를 사용

  > position: relative;

- absolute

  : 부모나 조상 중 relative, absolute, fixed가 선언된 곳을 기준으로 좌표 프로퍼티 적용

  > position: absolute;

- fixed

  : 보이는 화면을 기준으로 좌표 프로퍼티를 이용하여 위치를 고정

- z-index

  : 숫자를 지정하여 우선순위를 정할 수 있음(맨앞으로 보내기와 비슷), static을 제외한 요소에서 사용하여야 적용됨

# 위치와 관련된 프로퍼티[2]

##### flexbox

![image-20210510232541272](C:\Users\rlawlals119\AppData\Roaming\Typora\typora-user-images\image-20210510232541272.png)

flexbox를 사용하려면 정렬하고자하는 요소의 부모요소에 dispaly: flex; 추가

![image-20210510232800748](C:\Users\rlawlals119\AppData\Roaming\Typora\typora-user-images\image-20210510232800748.png)

##### 부모요소(flex Container)

- flex-direction: flex 컨테이너 안의 item들의 방향 정함

  > - flex-direction: rew;	// ->
  > - flex-direction: row-reverse;	// <-
  > - flex-direction: column;	// 아래로
  > - flex-direction: colume-reverse;	//위로

- flex-wrap: flex 아이템이 flex 컨테이너를 벗어났을때 줄을 바꾸는 속성

  > - flex-wrap: nowrap;	// 줄바꿈X
  > - flex-wrap: wrap;	// 줄바꿈O

- justify-content: flex-direction으로 정해진 방향을 기준으로 수평으로 item을 정렬하는 방법을 정함

  > - flex-direction: row;
  >
  > - flex-direction: column;
  >
  > - justify-content: flex-start;	// 기본값
  > - justify-contentd: center;	// 가운데 정렬
  > - justify-content: flex-end;	// 오른쪽 끝 정렬

  > - justify-content: space-around;	// 시작과 끝을 기준으로 동일 한 간격으로 아이템 배치
  > - justify-content: space-between;	// 시작과 끝에 아이템을 두고 그 사이에 남은 공간을 동일한 간격으로 아이템 배치

- align-items: flex-direction으로 정해진 방향을 기준으로 수직으로 item을 정렬하는 방법을 정함  

  > - align-items: stretch;(기본값)
  > - align-items: flex-start;
  > - align-items: flex-end;
  > - align-items: center;

  > - align-items: baseline;	// 글꼴의 기준선인 baseline을 기준으로 정렬

- align-content: flex-direction으로 정해진 방향을 기준으로 수직으로 여러 줄인 item을 정렬하는 방법을 정함

  > - align-content: stretch;(기본값)
  > - align-content: flex-start;
  > - align-content: flex-end;
  > - align-content: center;

  > - align-content: space-between;
  > - align-content: space-around;

##### 자식 요소(flex item)

- flex-grow

  : flex 아이템의 확장과 관련된 속성, 기본 0, 단위없는 숫자값 사용

  - 0인경우 콘테이너의 크기가 커져도 flex item 크기가 안커짐

  > 1. 두개 다 0인 경우 : 컨테이너에 맞춰 커지지 않음
  > 2. 0, 1인 경우 : 1인 부분이 컨테이너에 맞춰 커짐
  > 3. 1, 2인 경우 : 2인 부분이 컨테이너에 맞춰 커짐

- flex-shrink

  : flex 아이템의 축소와 관련된 속성, 기본 1, 단위없는 숫자값 사용

  - 0인 경우 콘테이너의 크기가 줄어도 flex item의 크기는 안줄음

    > 1. 0,0 : 안줄어듬
    > 2. 0,1 : 1쪽이 줄어듦 
    > 3. 1,2: 2쪽이 줄어듦

- flex-basis

  : flex 아이템의 기본 크기를 결정, 기본 auto

- flex

  : flex-grow, flex-shrink, flex-basis의 축약형

# 상속과 우선순위

##### 상속

모든 CSS 프로퍼티가 상속되는 것은 아님

+. inherit: 상속이 되지않는 프로퍼티를 상속에서 값을 상속받기 원하는 경우에 사용

> margin: inherit;

Casecading: css 적용 우선순위

##### 우선순위

1. 중요도: 어디에 선언되었는지에 따라 우선순위 달라짐

2. 명시도

   +. CSS 작성규칙_ ID 선택자를 쓰지말 것

   ​	-> class보다 id가 명시도가 더 높기 때문

3. 선언 순서: 나중에 선언된 스타일이 우선 적용

# Bootstrap

부트스트랩에서 정해둔 클래스 이름을 적으면 자동으로 CSS 적용됨

- 그리드 시스템
  - .container
    - .row
    - .col
      - col 12개를 나누어 가짐
      - ex) col-1(col 1개 크기), col-3(col 3개 크기)

> !important
>
> #id						<- 부트스트랩보다 상위 우선 순위
>
> div.class

> .class					<- 부트스트랩의 스타일 적용 방식

-> 부트스트랩은 클래스 기반이기 때문에 원하는 CSS 코드를 덮어주고 싶으면 부트스트랩보다 상위 우선 순위인것을 이용!

부트스트랩의 장점 -> 반응형 웹

![image-20210511194807178](C:\Users\rlawlals119\AppData\Roaming\Typora\typora-user-images\image-20210511194807178.png)

