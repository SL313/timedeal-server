# [넘블 챌린지] 타임딜 서버 구축하기
https://www.numble.it/b1f4ecbb-67b7-488a-b7dc-ca8824f43a60

## 목록
1. [시스템 아키텍쳐](#-시스템-아키텍쳐)
2. [API 목록](#-API-목록)
3. [기능 상세 목록](#-기능-상세-목록)
4. [클래스 설계](#-클래스-설계)
5. [와이어 프레임](#-와이어-프레임)
6. [ERD](#-ERD)
7. [성능측정 및 개선 내용](#-성능측정-및-개선-내용)
8. [회고록 URL](#-회고록-URL)

<br>

---

<br>

### 📌 시스템 아키텍쳐

(추후에 구조도 이미지 업로드 예정)
- Java
- Spring Boot, Spring Data JPA
- AWS RDS, EC2, CodeDeploy
- GitHub Actions CI/CD
- MySQL
- Intellij
- nGrinder
- pinpoint

### 📌 API 목록

- [ ] 회원 가입 API
- [ ] 로그인 아이디 중복 체크 API
- [ ] 닉네임 중복 체크 API
- [ ] 로그인 API
- [ ] 회원 탈퇴 API
- [ ] 회원 조회 (로그인 아이디) API
- [ ] 회원 조회 (닉네임) API
- [ ] admin 계정 확인 API
- [ ] 상품 등록 API
- [ ] 상품 수정 API
- [ ] 상품 삭제 API
- [ ] 상품 목록 조회 API
- [ ] 상품 상세 조회 API
- [ ] 구매 API

### 📌 기능 상세 목록

- [ ] ✔️회원 가입
  - [ ] 로그인 아이디 (중복 X)
  - [ ] 로그인 패스워드
  - [ ] 닉네임 (중복 X)
  - [ ] admin 계정 분리
- [ ] ✔️회원 탈퇴
  - [ ] status 변환 처리
  - [ ] 구매 table의 해당 회원 목록 status 변환 처리
- [ ] ✔️회원 조회
  - [ ] 로그인 아이디를 통해 조회 가능
  - [ ] 닉네임을 통해 조회 가능
  - [ ] status 확인
- [ ] ✔️상품 등록
  - [ ] 상품 이름
  - [ ] 상품 사진 (보류)
  - [ ] 상품 마감 시간
  - [ ] 상품 재고수량
  - [ ] 상품 가격 (보류)
  - [ ] status는 마감 시간 및 재고수량에 따라 변동
- [ ] ✔️상품 수정
  - [ ] 상품 이름 변경 불가
    - 구매한 상품에 변경을 줄 수 없음
  - [ ] 상품 마감 시간
    - 현재 시간 ~ 기존 마감 시간 사이 조정 가능
  - [ ] 상품 재고수량
    - API 호출되는 순간의 재고수량보다 적게 가능
- [ ] ✔️상품 삭제
  - [ ] status 변환 처리
  - [ ] 이미 구매한 목록에 대해서는 변경사항 X
- [ ] ✔️상품 목록
  - [ ] 남은 시간 순으로 목록 정렬
  - [ ] 목록 총 개수 반환
  - [ ] status 확인
- [ ] ✔️상품 상세조회
  - [ ] 상품 이름
  - [ ] 상품 사진 (보류)
  - [ ] 상품 마감 시간
  - [ ] 상품 재고수량
  - [ ] 상품 가격 (보류)
- [ ] ✔️구매
  - [ ] 회원 고유 ID
  - [ ] 상품 고유 ID
  - [ ] 수량
  - [ ] status
    - 취소 여부
    - 해당 상품의 status 확인

<br>

### 📌 클래스 설계

```
└── timedeal
    ├── TimedealApplication.java
    ├── domain
    │   ├── UserDomain.java
    │   ├── ProductDomain.java
    │   └── PurchaseDomain.java
    ├── dto
    │   ├── UserDto.java
    │   ├── ProductRegisterDto.java
    │   ├── ProductModifyDto.java
    │   └── PurchaseDto.java
    ├── repository
    │   ├── UserRepository.java
    │   ├── ProductRepository.java
    │   └── PurchaseRepository.java
    ├── service
    │   ├── UserService.java
    │   ├── ProductService.java
    │   └── PurchaseService.java
    ├── controller
    │   ├── UserController.java
    │   ├── ProductController.java
    │   └── PurchaseController.java
    └── utils
        ├── s3Image
        │   ├── AmazonS3config
        │   ├── AwsS3Service
        │   └── CommonUtils
        └── session
```

### 📌 와이어 프레임

<br>

### 📌 ERD

<br>

### 📌 성능측정 및 개선 내용

<br>

### 📌 회고록 URL

<br>