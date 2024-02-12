---
title: "STS로 Gradle 프로젝트 생성 가이드(2)"
date: 2024-02-11 17:17:00 +09:00
categories: 
    - java
    - spring boot
---
어제 기본적 세팅을 했다면 오늘은 컨트롤러와 뷰 연결까지 해볼려한다.  그리고 이작업을 하면서 배운것을 적어 남기려 한다.

## 1. 컨트롤러 세팅
<img src="/img/스크린샷 2024-02-12 160931.png" style="width:70%;">  
컨트롤러 클래스를 만드는데 어제 세팅할때 Packege명 뒤에 .controller를 붙여 패키지를 만든다.
그 패키지안에 클래스를 하나 만든다.

<img src="/img/스크린샷 2024-02-12 161432.png" style="width:70%;">  
사진처럼 세팅을 해주면 된다.  
여기서 보면 html파일을 쓰는것을 알 수 있는데 스프링 레거시는 jsp파일을 사용을 했는데 스프링 부트에서는 html파일을 사용한다고 한다.
jsp는 Java Server Page의 약자로 html파일에 자바 코드(서버 언어)를 곁들인 것 인데. 스프링 부트에서는 프론트와 백엔드의 완벽 분리를 지향한다고 한다.
그래서 html을 사용한다고 생각한다. 

## 2. HTML파일 세팅
<img src="/img/스크린샷 2024-02-12 162521.png" style="width:40%;">  
HTML파일을 세팅하기 전 이 두 파일을 알아가야한다.  
* templates = 동적 파일을 관리하는 디렉토리
* static = 정적 파일을 관리하는 디렉토리(ex : css, 이미지, 동영상 등등)  

<img src="/img/스크린샷 2024-02-12 163323.png" style="width:60%;">  
static에 html파일을 생성할 거다.  
그리고 127.0.0.1:8080으로 접속해 보겠다.

<img src="/img/스크린샷 2024-02-12 163649.png" style="width:60%;">  
잘연결이 된것을 확인할 수 있다. 보다 싶히 컨트롤러는 디폴트 경로가 static이란것을 확인 할 수 있다.

그럼 하나 의문점이 들 수 있다.  
우리는 데이터베이스 데이터를 받아 동적 페이지를 만들 것인데 static은 정적 파일인데?  
맞다 우리가 동적 페이지를 만들려면 추가 Dependecy를 받아야한다.

## 3. Dependecy 추가/삭제
<img src="/img/스크린샷 2024-02-12 165518.png" style="width:40%;">  
프로젝트를 우클릭 후 Spring > Add Starters  

<img src="/img/스크린샷 2024-02-12 170110.png" style="width:40%;">  
이런 화면이 뜰 것인데 처음엔 아무것도 선택이 안돼었다. 그렇다고 Spring Web을 선택을 안하면 삭제가 된다.  
그러니 Spring Web추가 하고 다음으로 Template Engines > Thymeleaf를 추가한다.
그리고 넥스트 후에 gradle이란 .md파일 둘다 클릭후 Finish하면 된다.
이렇게 한 후 서버를 재실행해서 페이지를 다시 가보면 에러가 뜨는 것을 확인 할 수 있다.

<img src="/img/스크린샷 2024-02-12 174702.png" style="width:40%;">  
이제 home.html파일을 template 파일로 옮기고 재실행하면 다시 연결 돼 었다. 이제 컨트롤러 디폴트 경로는 tamplate란 것을 확인 한것이다.
  
이렇게 오늘 추가 한 Tymeleaf는 동적 서버를 만들어주는 Dependecy라는 것을 알 수 있다.





