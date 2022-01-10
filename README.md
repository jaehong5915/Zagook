# zagook

---

## 위치기반 SNS 서비스

1. 현재 위치를 받아와 내위치 마커가 찍힘
2. 현재위치를 기반으로 거리순으로 피드 정렬
3. 로그인이 되어 있지 않은 상태에서 피드 아래로 이동할 경우 로그인 창 띄움
4. 피드를 클릭 시 마커 위에 인포윈도우 창 생성
5. 마커 클릭 시 피드 위치로 이동
6. searching map 부분은 전국지도에서 전체공개된 마커들을 전부 조회가능
7. 댓글이나 피드/ 검색을 통해 아이디에 접근하면 friend 페이지로 이동하고 그 페이지를 통해 친구신청 가능
8. 친구는 상단의 친구관리 페이지에서 관리/처리 가능
9. 로그인은 현재 카카오/네이버 소셜 로그인 구현
10. 게시물 등록은 EXIF를 이용해 사진의 위치정보를 가져와 디비에 저장
11. 좋아요 기능
12. 댓글 기능
13. friend feed는 친구의 친구공개 게시물과 전체공개 게시물이 조회됨
14. 네이버 클로바AI를 이용한 챗봇(현재는 id가 만료되어 시현불가)
15. 우측 상단의 range를 변경을 통해 어느 거리의 게시물까지 조회할 것이지 지정 가능
16. 공지 기능 (어떤 기능을 업데이트할 것이지 등을 공지)
17. 검색은 #을 붙이고 검색할 경우 태그 검색, 안붙일 경우 유저 검색으로 자동 전환됨
17. 메신저 기능 (프로필을 통해 메세지를 보낼 수 있고 그 이후엔 top의 메신저를 통해 접근할 수 있음)

----

## 환경 및 스택

sts4, spring boot, mybatis, oracle, geolocation, exif, autocomplete, aws

---

## bug 및 개선사항

> 1. ~~home일 경우 range에 대한 값을 받아오지 못함.~~
>
>    ~~feed_scroll_event - 82 line~~
>
> 2. ~~sublist.size()가10 이후에 20보다 작을경우 다음 리스트를 가져오지 못하고 있음. -> 10개씩만 불러옴~~
>
>    ~~FeedRestController - 388 line~~
>
>    ~~다른 페이지의 경우 정상적으로 작동하는 것 확인. home일 경우에만 10개 이후의 데이터를 가져오지 못함. 위의 문제와 연관 있는 것으로 보임~~
>
> 3. 모바일 페이지를 구현하지 않음
>
> 4. 신고 기능(신고가 3~5개 이상이면 일시적으로 비공개 처리가 되고 관리자가 이후 처리하게)
>
> 5. 로그인 안되어 있을 때 스크롤 내렸을 때 로그인 모달창 안뜨는 문제 발생
>
>    scrollEventHandler가 제대로 작동하지 않음
