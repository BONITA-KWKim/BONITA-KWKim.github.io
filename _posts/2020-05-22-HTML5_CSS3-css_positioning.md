---

title: "HTML5 & CSS3; CSS Positioning"
date: 2020-05-22
categories: ['web']
tags: ['frontend', 'web', 'html5', 'css3']

---

# 9장 CSS 포지셔닝

## CSS 포지셔닝과 주요 속성들

* 포지셔닝
  - 브라우저 화면 안에 각 콘텐츠 영역을 어떻게 배치할지를 결정하는 것
  - box-sizing 속성: 박스 너비 기준 설정
  - float 속성과 position 속성
  - visibility: 요소를 보이거나 보이지 않게 함
  - z-index: 요소를 쌓는 순서 정하기

||float 속성|position 속성|
|---|---|---|
|정의|왼쪽이나 오른쪽 구석으로 요소가 배치<br>clear 속성으로 해제|웹 문서 안에서 요소들을 자유자재로 배치|
|속성 값|left: 왼쪽 부터 채움<br>right: 오른쪽부터 채움<br>none|static: 흐름에 맞추어 배치<br>relative: static과 같지만 좌푯값을 사용해 위치 지정 가능<br>absolute: 원하는 위치에 배치<br>fixed: 브라우저 창을 기준으로 배치|


> 로렘 입숨(Lorem Ipsum)
> - 의미 없이 내용을 채워주는 것
> - 참고 사이트: <http://guny.kr/stuff/klorem/>


## 다단으로 편집하기

* 웹 문서를 다단으로 편집
* 브라우저 별 접두사를 붙여 사용해야함

## 표 스타일

* 표와 관련된 속성
  - 제목 위치
  - 테두리 스타일
  - 테두리 통합 및 분리
  - 인접한 셀의 테두리 사이 거리
  - 빈 셀의 표시 여부
  - 너비와 높이
  - 셀 안에서 수평 정렬 및 수직 정렬
