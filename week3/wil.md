## DB 설계
ER Model : 문제 상황을 개체와 관계로 표현하는 방법
ERD : ER Model을 다이어그램으로 표현한 것
PK(Primary Key) : 하나의 개체를 식별할 수 있는 속성
- 개체 -> 테이블
- 관계 -> 테이블 or 왜래키
1:N 관계 (유저-할 일)
N:M 관계 (동아리-회원) : 중간 테이블 사용
- 속성 -> 테이블 컬럼
## 엔티티 클래스
- @Entity : 이 클래스가 엔티티라는 것을 명시
- @Id : PK필드에 이 필드가 PK라는 것을 명시(id 값은 데이터를 생성할 때마다 자동으로 1씩 증가)
- @GeneratedValue : id값을 자동으로 생성 (strategy는 IDENTITY로 설정)
- @Column : 이름과 타입 명시
# 엔티티 연관관계(왜래키 필드)
- @JoinColumn : FK 컬럼 정보 명시
- @ManyToOne/@OneToOnen: 왜래키로 생기는 연관관계 종류 나타냄
-> 연관 관계의 종류를 나타내는 fetch 속성 : 엔티티를 언제 가져올지 명시
-> EAGER : 객체의 모든 정보를 함꼐 한 번에 가져옴
-> LAZY : 객체의 정보를 필요할 때 가져옴
# 엔티티 생성자 (alt+insert)
id를 제외한 필드에 대한 생성자 추가
JPA는 엔티티 객체를 다룰 때 public 이나 protected의 인자 없는 생성자가 필요함
-> @NoArgsConstructor : 인자 없는 생성자를 만든다(access속성을 통해 접근 제한자 protected로 설정)
-> @Getter : 모든 필드에 getter를 만든다다