# JDBC, ORM, JPA, persistance

## 영속성 (persistance) 이란?
영구히 저장되는 것, 비휘발성

## JDBC
- Java JDBC

## SQLMAPPER
객체의 필드와 DB 데이터를 매핑시켜 데이터를 관리함  
SQL를 명시해줘야 한다.
- Mybatis (XML에 따로 SQL 명시)
- Spring JDBC

## ORM
객체 관계 매핑  
SQL 중심이 아닌 객체 중심으로 구현  
└> SQL을 직접 관리 x, 메소드로 조작 (SQL을 자동생성)

- JPA
- Hibernate

## JPA (Java Persistance Api)
### EntityManager

### 영속성 Context
Entity 를 영구히 저장하는 환경
jpa 에서 바로 DB에 저장하는게 아닌, persist() 에서 영속성 컨텍스트에 저장되는 것이다.
commit이 되면 비로소 db에 저장됨

굳이 application과 db 사이에 영속성(persistance) 레이어를 둔 이유?
버퍼링, 캐싱

### lazy loading  
### dirty checking (변경 감지)  
- persistance layer 와 db가 동기화될 때 entity 의 상태가 변경되었다면 그걸 감지하고 update 해줌  
└> 그래서 entityManager에서는 update() 가 없다!
### 쓰기 지연 (버퍼링)  
- 영속성 컨텍스트 내의 쿼리 저장소에 insert 를 저장하고 있다가 commit이 되면 한꺼번에 db에 쿼리문을 보낸다
### 캐싱 caching  
- 엔티티를 조회할 때 1차 캐시에 데이터 내역이 있으면 캐싱 데이터를 들고옴 -> 성능 향상 굳

### spring-data-jpa  
repository 내부에 Entitymanager 동작



※ 참조 
- https://www.youtube.com/watch?v=mezbxKGu68Y&ab_channel=%EC%9A%B0%EC%95%84%ED%95%9CTech
- https://velog.io/@adam2/JPA%EB%8A%94-%EB%8F%84%EB%8D%B0%EC%B2%B4-%EB%AD%98%EA%B9%8C-orm-%EC%98%81%EC%86%8D%EC%84%B1-hibernate-spring-data-jpa#orm%EC%9D%B4-%EB%AD%90%EC%A3%A0-sql-mapper%EC%99%80-orm