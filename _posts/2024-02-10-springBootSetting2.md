---
title: "STS로 Gradle 프로젝트 생성 가이드(2)"
date: 2024-02-11 17:17:00 +09:00
categories: 
    - java
    - spring boot
---
어제 기본적 세팅을 했다면 오늘은 컨트롤러와 뷰 연결까지 해볼려한다.  그리고 이작업을 하면서 배운것을 적어 남기려 한다.

## 1. 컨트롤러 설정
<img src="/img/스크린샷 2024-02-11 172249.png" style="width:30%;">  
컨트롤러 클래스를 만드는데 어제 세팅할때 Packege명 뒤에 .controller를 붙여 패키지를 만든다. (ex: com.increpas.bootTest.controller)  
그 패키지안에 클래스를 하나 만든다.