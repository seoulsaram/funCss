# 최신 CSS기법을 모아둔 곳입니다.

### scss 컴파일 방법

1. `npm install sass`

2. 터미널에 `npx sass --watch [scss파일명] [컴파일할 css파일명]` 실행
   - example
     `npx sass --watch style.scss style.css `

### [FunCss 1편 보러가기](/css1/README.md)

- 목차

  1.  transition으로 step별 움직임 효과 주기
  2.  쉬운 탭 디자인 만들기
  3.  글자에 그라디언트 넣기
  4.  textarea 리사이즈 none
  5.  화면 사이즈 넘어가는 텍스트를 알아서 줄바꿈

  6.  문자열 첫글자만 스타일주기 + 첫번째 라인만 스타일 주기

  7.  글자를 넣지 않은 빈 div에만 따로 스타일을 줄 수 있음.

  8.  firt-of-type 연습! content 밑에 p타입의 첫번째 아이에게 스타일주기

  9.  text-shadow 주기

  10. list 스타일 포지션 + 마커 스타일

  11. 문장 들여쓰기

  12. 글자 뒤집기

  13. zoom으로 요소 확대하기

  14. 애니메이션

  15. scss의 extend기능을 사용하여 스타일 주기

  16. @supports 사용해보기

  17. scroll-snap-type 사용해보기

  - 한 화면에 꽉 차는 div가 세로 또는 가로로 여러개 있을 때,
  - 스크롤 했을 시 div가 잘리지 않고 바로 다음 div로 깔끔하게 스크롤링 되도록 하는 기능.

  18. is seudo selector 사용해보기

  19. 이미지나 비디오의 비율을 정할 수 있는 aspect-ratio 사용해보기

  20. sticky 활용해서 유저의 스크롤을 따라다니는 header 만들기

### [2022 new css 소개](/css2/README.md)

- 목차

  1. `color-mix`

  - 명시한 컬러들을 섞어주는 기능.

  2. `accent-color`

  - hover, focus, checked 등 특수한 상황의 포인트 컬러를 한 번에 명시 가능하다.

  3. `color-contrast()`

  - 배경색 대비하여 잘 보이는 색을 직접 고르는 대신 브라우저가 적절한 색을 골라주는 기능.

  4. `inert`

  - focus, click 등 유저와의 상호작용을 막을 때 유용한 어트리뷰트 소개.

  5. `has() `

  - 부모 요소에 특정 자식이 있는지 여부에 따라 부모 요소의 스타일을 할 수 있음

  6. `dvh, lvh, svh`

  - 윈도우 사이즈를 조절할 수 없는 mobile을 위한 프로퍼티들 소개.

  7. `@nest`

  - 중첩 스타일 적용

  8. `@scope`

  - 스타일의 범위를 지정하거나 자신만의 버블로 지정할 수 있다.
  - theme을 줄 때 유용하다.

  9. `@container`

  - 반응형을 구현할 때 이젠 넓이 뿐만 아니라 그 부모 요소에 대응할 수 있다.

  10. `custom-media`

  - 미디어 쿼리 변수를 만들고 재사용할 수 있다.
