# springboot-jpa-aws
스프링부트와 jpa로 구현한 웹서비스를 aws를 사용해 배포해본다
# 필기
## entitiy annotation
* 클래스에 붙이며 테이블과 링크될 클래스임을 나타낸다.
* 카멜케이스이름이 db에는 언더바로 매칭된다 ex) newTable.java -> create table new_table
* 필드가 컬럼이 되며 id,column어노테이션등을 추가해 추가될 컬럼에 제약조건을 넣을 수 있다.
* 생성자를 통해 데이터를 삽입한다
* setter는 선언하지 않고 필요 할 때 값을 수정하는 메소드를 작성한다.  
->(값 수정이 필요한 경우 어떤 이벤트에 사용하는지 나타내는 메소드를 정의해 거기서 수정하게 되므로 값의 수정이 필요한 경우는 모두 엔티티 클래스 안에서만 할 수 있다.)  

## 생성자 패턴과 빌더패턴
생성자 패턴
```java
    new Example(a,b);//타입이 같으면 뭐가 어느필드에 들어가는지 알기 힘듬
```
빌더 패턴
```java
    Example.builder()
    .a(a)
    .b(b)
    .build();//어느 필드에 뭐가 들어가는지 명확함
```
## Repository
* jpa에서 DAO역할을 하는 것. JPARepository<Entity,PK_CLASSTYPE>를 상속하면 알아서 crud 메소드가 등록됨  
    *save(extends Entity s) -> s를 update 하거나 insert함 id가있으면 update,없으면 insert
    *findAll()-> 모든 데이터 리스팅
* entity클래스와 기본 repository인터페이스는 같은 위치에 있어야함
* 
