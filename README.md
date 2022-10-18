# Animall
파이어베이스 연동 crud 프로젝트

https://velog.io/@chchaeun/Firebase%EC%99%80-Javascript%EB%A1%9C-To-do-list-%EB%A7%8C%EB%93%A4%EA%B8%B0

참고.

## 22/10/05
forEach를 사용하여 데이터를 배열에 담아서 table에 출력하려는데 쉽지가 않다.
공부가 더욱 필요할 것으로 보인다.

## 22/10/11
- 전체적인 구상은 다음과 같다.

- 메인페이지
ㄴ메뉴, 배너, 타이틀, 섹션, 푸터

- 회원가입/로그인

- 게시판
ㄴ질문게시판(질문게시판/사진가능/글로만 제목보임)
ㄴ중고장터(일반리스트게시판/썸네일목록/사진가능)/신상품 판매에 주력.
ㄴSNS(제목없음 어그로방지 무한스크롤,글쓰기,글수정,글삭제 /해시태그 구현) - 강아지 사진 올리는 게시판. 추천 수 많으면 그 주의 메인화면에 걸림. 강아지가 아닌 사진은 선정되지 않음. 한 번 올리면 일주일간 지울 수 없음. / 메인에 올라가기 싫어요 체크박스 있음.

- 쇼핑몰(개발 3순위/훈련사 장터와 통합.)
ㄴ훈련사장터(결제시스템 구현 필요)
ㄴ카테고리
ㄴ훈련사목록
ㄴ훈련사

- 여행지(동반가능한곳)
지도api 활용 / 프론트로 그려야할듯? 백엔드 구현 시 같이 사용해야하나..

★짜임새보다는 기능구현에 초점을 맞추자★

## 2022 이내 구현할 것.
- SNS(인스타그램형식)
- 무한스크롤
- CRUD
- 클라우드 사진저장
- #해시태그 - 검색에도움될듯

## 그 다음 수순(2023 이내 구현할 것.)
- 질문/중고 게시판
- 회원가입/로그인
=================================================취업절취선기대
## 그 다음 수순
- 백엔드 구현
- 쇼핑몰 구현
- 결제시스템 구현
- 여행지 지도 API


# 22/10/11
- Mypage삽입 및 모달창으로 로그인, 회원가입 구현 중. firebase 인증 유지 기능 구현 필요.

- 10/12~15 / 제주도 여행 갔다와서 나머지 구현해봅시다.

- 휴가기간동안 개인프로젝트를 다듬을 수 있어서 행복했다.

# 22/10/17
- 휴가에서 복귀했다. 휴가 가기 전, 오늘 해야할 것들을 적어놓아서 과거의 나에게 너무 고맙다.

- https://mateeth.tistory.com/m/6 firebase와 세션

# 22/10/18
- 오늘은 세션에 대해 공부하고 적용해야한다.

-https://beomseok95.tistory.com/m/108 회원정보 관련 메소드 

- 파이어베이스에 의존하여 백엔드 서버 없이 구축하다보니 애로사항이 꽃 핀다.
- 세션 유지 메소드 활용법을 아무리 찾아도 모르겠다.
- 처음 로그인 시 세션에 회원 id값을 대입하고, 서버로부터 전체 회원 id값과 세션에 저장된 id값을 대조하는 식으로 하는 방법이 있겠지만 보안상 분명 문제가 있을 것이다.

-https://firebase.google.com/docs/auth/web/manage-users?hl=ko Firebase에서 사용자 관리하기

- 커스텀 토큰을 만드는 방법이 있다 JWT 그러나 그것까지 공부하면 나는 백엔드 개발자(?)
- 집에 가서 todolist 최고의 예제를 참고해봐야겠다.

- https://firebase.google.com/docs/auth/admin/verify-id-tokens?hl=ko#web 이건가

- https://codingapple.com/unit/firebase-authentication-register/?id=9822 코딩애플강의 돈주고 

- https://ldevlog.tistory.com/m/28 간편하게 구현하려면 이걸 보자. 이후에 리팩토링 해도 되잖아~

# 파이어베이스 로그아웃은 왜 있지?

## https://mateeth.tistory.com/m/6 돌고 돌아 이것이 근본

- firebase 토큰에 대해서도 찾아보자

- https://firebase.google.com/docs/auth/web/manage-users?hl=ko 로그인한 유저 있는지 확인가능

### 로그인 버튼 누르는 순간 이미 세션에는 임의의 세션값이 입력돼있다. 크롬 개발자 도구로 보면 됨.
- 고로 이제 페이지가 열렸을 때 세션이 있는지 확인하면 될 듯?

일단은 간편하게 세션이 있으면 그냥 로그인된걸로 치게 할까?

- 회원가입시 개인정보를 추가로 DB에 작성하게 하는게 나을듯. 글 작성 시 닉네임 등 개인정보도 로딩을 해야함;

- displayName:null
- email:"yjhws2011@naver.com"
- phoneNumber: null
- photoURL:null
- providerId:"password"
- uid:"yjhws2011@naver.com"

- 세션에는 위와 같은 값이 들어간다.

https://firebase.google.com/docs/auth/web/manage-users#web-version-8_2
- 위 주소를 통해 프로필 업데이트가 가능하다.
