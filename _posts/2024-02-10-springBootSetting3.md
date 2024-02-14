---
title: "STS로 Gradle 프로젝트 생성 가이드(3) 스프링 부트로 오라클 DB를 연동해 Mytais로 데이터 CRUD"
date: 2024-02-11 17:17:00 +09:00
categories: 
    - java
    - spring boot
---
오늘은 스프링 부트에서 오라클 db연동을 해보려 한다. 필자는 단순히 오라클로 연동해서 데이터 CRUD 그런걸 찾고 싶었지만 JPA 등 너무 많은 지식의 저주로 인해 4~5시간 정도를 쏫은 거 같다.   
이글을 작성하므로서 되게 단간히 정리하려고 한다.

## 1. 초기 설정
일단 Dependecy를 추가햐여야 한다. SQL안에 Mybatis와 Oracle Driver을 추가하면 된다.
그러고 application.properties안에 Oracle계정및 Mybatis의 xml파일 경로를 설정을 해야한다.   

Oracle Setting
```properties
spring.datasource.driver-class-name=oracle.jdbc.driver.OracleDriver
spring.datasource.url=jdbc:oracle:thin:@localhost:1521/xe
spring.datasource.username=youId
spring.datasource.password=youPassword
```
오라클은 계정 정보를 적어주면된다.


Mybatis Setting
```properties
#Mybatis Setting
mybatis.mapper-locations=classpath:mybatis/*.xml
```
마이바티스는 xml파일이 저장된 위치를 표시하면 된다.  
classpath는 src/main/resources의 경로를 가진다.  
이제 그럼 표기한 위치에 xml파일을 만들어주면된다.

<img src="/img/스크린샷 2024-02-14 125210.png" style="width: 40%;">  
resources안에 mybatis패키지 생성후 .xml로 끝나는 파일을 생성하면된다.

xml안에는 아래코드를 추가해주면 된다.
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE mapper
PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"
"http://mybatis.org/dtd/mybatis-3-mapper.dtd">
<mapper namespace="namespace는 좀 이따 설명해 주겠다. 일단은 다음으로 넘어가자">
	<!-- SQL문들을 작성하는 파일 -->
	
</mapper>
```

<img src="/img/스크린샷 2024-02-14 131654.png" style="width: 40%;">
위 사진처럼 패키지안에 mapper패키지를 생성해주고 안에 class가 아닌 interface파일을 생성해준다.

<img src="/img/스크린샷 2024-02-14 132226.png" style="width: 70%;">












