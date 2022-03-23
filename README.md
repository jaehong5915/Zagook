# 위치기반 SNS 서비스 - Zagook 👣 

게시물이 시간 순 정렬을 보이는 기존의 SNS와 달리 거리 순 정렬을 통해,  
위치를 기반으로 추억을 기록하고 주변사람과 공유하는 SNS 서비스
  
---


### 🔖 프로젝트 주요기능
- Interceptor 사용하여 특정 페이지 관리자 권한부여  
  (공지 등록, 수정, 삭제)
- 사진으로부터 불러온 위치정보를 지도에 매핑
- 로그인(Zagook 가입, 소셜을 통한 가입[카카오, 네이버])
- 피드 (게시글 모아보기, 정렬(시간 순, 거리 순), 좋아요, 댓글)
- 사진 업로드, 게시글 (CRUD)
- 친구 신청 및 관리, 게시글 공개 범위 설정
- 챗봇 서비스

---

### 📌 프로젝트 목적
- 내 주변 아름다운 곳의 위치를 사진과 함께 공유하고 싶은 이들을 위한 SNS 구현
- 낯선 곳에서 주변의 다양한 장소를 알고 싶은 사람들을 위해
- 지인들과의 추억을 기록하고 공유하고 싶은 사람들을 위해
---


### 🛠 환경 및 스택
- Java, HTML, JS, css
- Springboot
- JQuery, mybatis, geolocation, SocialLogin, Kakao map
- sts4
- Oracle, aws 
<br>
---

### ⚙️ 프로젝트 설계
<br>

웹 페이지 계층 구조
![](img/계층구조1.png)

<br>

ERD 설계
![](img/erd.png)

---

## 개발 상세내용
1. 피드 (메인페이지)
- 위치정보가 담긴 이미지를 통해 지도 내 해당 위치 마커 표시
- 마커 클릭 시 해당하는 피드 게시물로 이동
- Searching map / 현재 위치에 관계 없이 원하는 위치의 마커 열람 기능
- 게시글 태그 등록 기능 (검색 가능)
- 좋아요, 댓글 (댓글 아이디 클릭 시 유저의 피드 페이지로 이동)
<br>

![](img/feed.png)
<br>



2. 회원 관리 페이지
- 모달을 통한 로그인, 회원 가입 경로(웹, 소셜)
- OAuth2 인증 방식을 통한 소셜 로그인 회원가입
- 이메일 인증 기능 (인증버튼 클릭 시 해당 이메일로 랜덤번호 발송)
- 마이페이지 구현(회원 상세정보, 프로필 소개)
<br>

![](img/login.png)
<br>

3. 게시물 등록
- 모달을 통해 글 등록, 수정, 삭제
- 사진 업로드 시 미리보기 기능 구현
- 업로드 시 위치 정보 추출해 데이터베이스에 저장
- 공개 범위 설정 (0: 비공개/ 1: 친구/ 2: 전체)
<br>

![](img/insert.png)
<br>

4. 친구 관리
- 유저의 피드 페이지에서 친구 신청
- 친구 관리 페이지를 통해 친구 수락 혹은 삭제 가능
<br>

![](img/friend.png)
<br>

5. 챗봇 서비스
- 네이버 Chatbot API 활용
- 아이콘 클릭 시 챗봇 모달 생성
- 모달 ON/OFF 토글을 통해 챗봇 ON/OFF 기능 구현

<p align="left"><img width="400" height="350"  src="img/chat.png"></p>

