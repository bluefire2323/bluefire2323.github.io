---
title:  SQL Select
tags:
  - DB
---

1.SQL의 정의

SQL은 관계형 데이터베이스 관리 시스템을 조작할 때 사용하는 언어이다.

2.데이터 조회
명색이 데이터베이스인데 데이터를 조회하지 못하면 사용할 이유가 없어진다. 그래서 조회는 중요한 명령 중 하나다.

```SQL
SELECT * FROM [Customers]
```
이건 가장 기본적인 SELECT 명령어이다. Customers 라는 데이터에서 모든 항목을 조회하는 명령어이다. 하지만 이렇게 하면 무조건 모든 자료의 모든 데이터가 나오기 때문에 불편하다.

```SQL
SELECT * FROM [Customers] WHERE Country = "Germany"
```
이는 특정한 조건을 만족하는 자료에서만 데이터를 나오게 하는 명령어이다. 위의 코드는 Country가 Germany인 자료의 모든 데이터를 출력하는 명령어이다. 이렇게 하면 특정한 지역, 특정한 연령대의 사용자를 조회하는 데에도 사용할 수 있다.

```SQL
SELECT * FROM [Customers] WHERE Country = "Germany" AND City = "Berlin"
```
하지만 조건이 하나일 필요는 없다. AND를 이용하면 조건이 두 개 이상이어도 된다. 여기서는 Germany에 살고 도시가 Berlin인 모든 데이터를 조회한 것이다.
![](\image\sql_image.png){: width="100%" height="100%"}
연습용 사이트에 실행하면 이와 같이 조건에 만족하는 자료만 잘 나오는 것을 확인할 수 있다.

```SQL
SELECT Address FROM [Customers]
```
이는 모든 자료에서 Address만 조회하는 명령어이다. 이도 마찬가지로 조건을 이용해서 특정한 조건을 만족하는 자료의 Adress만 조회할 수 있다.

```SQL
SELECT Address,Country FROM [Customers]
```
여기서도 한 자료의 데이터를 두 가지 이상씩 조회할수도 있다. 이 경우에는 모든 자료의 Address와 Country를 조회했다.
