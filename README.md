# 화면 템플릿 적용 가이드

화면 템플릿엔진은 Thymeleaf를 활용하였습니다.

bootstrap4, sb-admin2, dataTable.js 를 활용해서 구성하였습니다.

## 0. gradle dependency

```groovy
...
    implementation 'org.springframework.boot:spring-boot-starter-thymeleaf'
    implementation('nz.net.ultraq.thymeleaf:thymeleaf-layout-dialect')
    implementation 'org.springframework.boot:spring-boot-starter-web'
...
```



## 1. 화면 템플릿 구조

본 템플릿은 thymeleaf-layout-dialect를 활용하여 공통 화면과 컨텐츠 화면을 분리하여 구성하였습니다.

resources/templates 아래에 html 파일들이 존재하며, 공통 화면은 아래 목록이 존재합니다.

| html files             | description                                                  |
| ---------------------- | ------------------------------------------------------------ |
| fragments/head.html    | html head 에 들어갈 공통 정의                                |
| fragments/footer.html  | html footer 정의                                             |
| fragments/sidebar.html | 화면 상 사이드바 정의. 사이드바 수정이 필요하다면 본 파일 수정할 것 |
| fragments/top.html     | 검색바 등이 포함되어있는 화면 상 상단 정의. 수정이 필요하다면 본 파일 수정할 것. |
| layout.html            | 화면의 전체 레이아웃의 구조를 잡아놓은 템플릿 html           |
| sample.html            | 화면 추가 구현 필요 시 활용할 수 있는 컨텐츠 화면 샘플       |

실제로 화면 추가 구현 필요시 sample.html 을 복사하여 필요한 화면 내용에 대해 작성하시면 됩니다.



## 2. 기 구현 화면 별 URL

URL : http://localhost:8181

| URL        | Description                                       |
| ---------- | ------------------------------------------------- |
| /          | /login 으로 redirection                           |
| /login     | 로그인 화면 접속                                  |
| /main      | 메인 화면 접속                                    |
| /openings  | 청약 관리 화면 접속 (CR 참조)                     |
| /customers | 고객 관리 화면 접속 (CRUD 참조)                   |
| /users     | 직원 정보 화면 접속 (미구현 상태. 직접 구현 요망) |

