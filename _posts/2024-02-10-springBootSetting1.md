---
title: "STS로 Gradle 프로젝트 생성 가이드(1)"
date: 2024-02-10 01:24:00 +09:00
categories: 
    - java
    - spring boot
---
오늘은 스프링 부트에 대해 공부도 할겸 한번 프로젝트 세팅을 하는 것을 기록하려 적는다.  
STS는 설치가 되있기에 바로 프로젝트를 세팅해보겠다.

## 프로젝트 설치
<img src="/img/스크린샷 2024-02-10 175951.png" style="width:70%;">  
사진에 보이는 것 처럼 Spring starter Project를 클릭한다.

<img src="/img/스크린샷 2024-02-11 004524.png" style="width:70%;">
1. Name을 작성한다.
2. Type은 우리가 Gradle 프로젝트를 생성할거이기에 Gradle을 선택해 준다.
3. java Version을 설정해줄건데  버전은 스프링 부트 버전에 따라 고정이다
* 만약 스프링 부트 버전이 2.x.x면 자바 11, 8버전으로 실행이 가능하다.
* 스프링 부트 3.x.x부터는 17, 21고정이다.   
필자도 11을 고집했지만 17로 업그레이드 해버렸다.   
물론 스프링 부트 버전을 내리는 방법도 있겠지만 귀찮았다.  

<img src="/img/스크린샷 2024-02-11 004718.png" style="width:70%;">
여기서 이제 Dependecy를 설정한다.    
WEB안에 있는 Spring Web은 필수로 선택해야한다.  
여기안에는 Spring MVC, RestFul등 중요한 기능이 있어 필수로 선택해야 한다.
나머지 Dependecy는 추후에 정리해 보도록 하겠다.  

Finish 클릭  

<img src="/img/스크린샷 2024-02-11 025627.png" >  
프로젝트가 생성됐으면 끝난것이다

<img src="/img/스크린샷 2024-02-11 025746.png" style="width:70%;">  
프로젝트를 실행할때에는 Spring Boot App으로 시작하면 된다.  

<img src="/img/스크린샷 2024-02-11 030803.png" style="width:100%;">  
콘솔창이 이렇게 나오면 거의 다된것이다.

<img src="/img/스크린샷 2024-02-11 031414.png" style="width:100%;">  
이제 브라우저를 실행해 127.0.0.1:8080 주소를 입력했을때 이런 화면이 나오면 성공이다.  
err라고 나오는 것은 콘트롤러 및 세팅을 마저 안해서 그렇다.



## 설치하면서 만난 오류들
#### NomatchingGraphVariantsException
<img src="/img/스크린샷 2024-02-09 213541.png" style="width:100%;">
이오류는 봐서 알겠지만 필자는 11버전을 고집했기에 터진 오류이다.  17버전으로 올림으로 해결했다.

#### 8080포트 오류
<img src="/img/스크린샷 2024-02-09 220224.png" style="width:100%;">
이오류는 다른 프로세서가 8080포트를 사용중이여서 일어난 오류이다.  
cmd를 실행하고
```shell
netstat -ano | findstr 8080
taskkill /f /pid (포트번호)
```
강제로 8080포트를 삭제시키면 해결된다.