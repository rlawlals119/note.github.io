# 웹기초

# LEC1-1. Web & Web Service

클라이언트: 요청(request)

서버: 응답(response)

웹서비스를 만든다 = 서버를 만든다

클라이언트 -> 갖다줘(get), 처리해줘(post) -> 서버

이때 html 파일이 오간다

P2P(peer to peer): 모두가 서버이자 클라이언트

Web browser : 다른 서버 또는 P2P와 연결해주는 통로



# LEC1-2. 웹 서버를 만드는 방법

- 서버 컴퓨터

  - 빠른 컴퓨팅 능력
  - 24시간 켜 있어야 함 (무한루프)
  - 발열 냉각 장치
  - 클라이언트 수 고려
  - 보안

- 서버가 되기 위한 방법

  1. 내 컴퓨터 = 서버 컴퓨터화 (로컬환경 세팅)

     > apache, iis

  2. 웹호스팅

     > cloud9, github

     + 클라이언트 수 고려 안해도 됨





# LEC1-3. HTML[1]

HTML: Hyper Text Markup Language

1. 글
2. 태그
3. 속성

> www,codecademy. com
>
> -Introduction to html
>
> > ```html
> > <body>
> >   <h1>The Brown Bear</h1>
> >   <div id="introduction">
> >     <h2>About Brown Bears</h2>
> >     <p>The brown bear (<em>Ursus arctos</em>) is native to parts of northern Eurasia and North America. Its conservation status is currently <strong>Least Concern</strong>.<br /><br /> There are many subspecies within the brown bear species, including the Atlas bear and the Himalayan brown bear.</p>
> >     <h3>Species</h3>
> >     <ul>
> >       <li>Arctos</li>
> >       <li>Collarus</li>
> >       <li>Horribilis</li>
> >       <li>Nelsoni (extinct)</li>
> >     </ul>
> >     <h3>Features</h3>
> >     <p>Brown bears are not always completely brown. Some can be reddish or yellowish. They have very large, curved claws and huge paws. Male brown bears are often 30% larger than female brown bears. They can range from 5 feet to 9 feet from head to toe.</p>
> >   </div>
> >   <div id="habitat">
> >     <h2>Habitat</h2>
> >     <h3>Countries with Large Brown Bear Populations</h3>
> >     <ol>
> >       <li>Russia</li>
> >       <li>United States</li>
> >       <li>Canada</li>
> >     </ol>
> >     <h3>Countries with Small Brown Bear Populations</h3>
> >     <p>Some countries with smaller brown bear populations include Armenia, Belarus, Bulgaria, China, Finland, France, Greece, India, Japan, Nepal, Poland, Romania, Slovenia, Turkmenistan, and Uzbekistan.</p>
> >   </div>
> >   <div id="media">
> >     <h2>Media</h2>
> >     <img src="https://content.codecademy.com/courses/web-101/web101-image_brownbear.jpg" alt="A Brown Bear"/>
> >     <video src="https://content.codecademy.com/courses/freelance-1/unit-1/lesson-2/htmlcss1-vid_brown-bear.mp4" width="320" height="240" controls>
> >     Video not supported
> >     </video>
> >   </div>
> > </body>
> > ```



# LEC1-4. HTML[2]

HTML은 꾸미는 언어가 아니다

- HTML 코드

  1. HTML로 작성된 문서임을 알려주는 태그

     - <html lang="ko"> -> 문서가 한국말로 작성되었음을 알려줌
     - <html>

  2. 화면에 등장하지는 않지만 문서를 설명하는 태그

     - <head>

     > 'Title', 인코딩 방식(utf-8) 등등

  3. 직접적으로 화면에 등장하는, 문서에 보이는 태그

     > h1, p, li

인코딩 uft-8 설정

live server 사용

!tab : 기본세팅 단축키

- form

  > 사용자 -<form>-> HTML -<form action="전송받을 대상"> -> 전송받을 대상





# LEC1-5. HTML[3]

이미지 파일은 html 파일과 같은 폴더에 있어야 함

많은 내용을 입력하고 싶은 경우, <input type="type">이 아닌 <textarea> 이용

textarea는 행렬을 이용해 크기 설정

> ex) <textarea cols="30" rows="20"> </textarea>



- ol>li*(원하는 리스트 갯수) <tab>

- ul>li*(원하는 리스트 갯수) <tab>

  -> 입력한 숫자만큼의 리스트가 만들어짐



- 글자에 링크걸기

  <a href="1.html"> 

  > 링크로 걸고자 하는 파일은 html 파일과 같은 폴더에 있어야함



페이지 소스 보기 or f12



# LEC1-6. Bootstrap

- CDN

  CDN 링크를 <head> 태그 안에 넣음

- jquery

  코드를 <head> 태그 안에 넣음



# LEC1-7. Github 배포

### Github : 3+1가지의 기능

1. Code 저장 기능
2. Undo 기능
3. 협업기능

+. Web Hosting 기능



