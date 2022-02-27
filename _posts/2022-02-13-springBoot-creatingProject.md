---
title:  intellij community로 SpringBoot 프로젝트 생성법
tags:
  - SpringBoot
  - Tedi
---

1.intellij 프로젝트 생성

새 프로젝트를 생성하는 창에서 gradle을 선택한 후 생성하면 프로젝트가 생성된다. 이 프로젝트가 열리면 가장 먼저 build.gardle이라는 파일이 열린다. 이 파일에

```java
buildscript {
    ext {
        springBootVersion = '2.1.7.RELEASE' // 2.1.7, 2.1.8, 2.1.9 다 괜찮습니다.
    }
    repositories {
        mavenCentral()
        jcenter()
    }
    dependencies {
        classpath("org.springframework.boot:spring-boot-gradle-plugin:${springBootVersion}")
    }
}

apply plugin: 'java'
apply plugin: 'eclipse'
apply plugin: 'org.springframework.boot'
apply plugin: 'io.spring.dependency-management'

group 'org.example'
version '1.0-SNAPSHOT'

repositories {
    mavenCentral()
    jcenter()
}

dependencies {
    compile('org.springframework.boot:spring-boot-starter-web')
    testCompile('org.springframework.boot:spring-boot-starter-test')
}
```

를 붙여 넣으면 된다.

2.Spring Boot 프로젝트 생성

[Spring Initializr](https://start.spring.io/)
images:
  -https://www.google.com/url?sa=i&url=https%3A%2F%2Fspring.io%2Fprojects%2Fspring-boot&psig=AOvVaw1YUl1RZEN1cvI3XLEmn0vi&ust=1646015159293000&source=images&cd=vfe&ved=0CAgQjRxqFwoTCNigwLvqnvYCFQAAAAAdAAAAABAI

이 사이트에 들어가면 Spring Initializr라는 창이 나온다. 이 창에서 몇 가지 옵션을 선택한 후 GENERATE라는 버튼을 누르면 스프링 부트 생성에 필요한 몇 가지 파일들을 zip파일로 묶어서 다운받을 수 있다. 나는 gardle을 사용하므로 gardle project를 선택했고, java를 주로 해 왔으므로 java를 선택했고, 버전은 2.5~6정도면 된다. 프로젝트명은 시험용이니 demo로 하고, java버전은 8을 사용하므로 8로 설정했다.

이제 다운받은 zip파일의 압축을 풀고 intellij로 열면 하나의 프로젝트가 나온다. 제대로 했는지 확인하는 방법은 src→main→java→com.example.프로젝트명→DemoApplication 을 실행하면 된다. 실행되었을 때 8080이 뜨면 제대로 된 것이고, 웹 브라우저에 localhost:8080을 입력했을 때 ‘404 에러’가 아니라 ‘빈 페이지’라고 뜨면 성공이다.

