# 셋째날

## MediaQuery

### MediaType

* 어떤 목적으로 사용될 문서인것인지를 표시하기 위해 사용
* all, aural, braille, embossed, handheld, print, projection, screen, speech, tty, tv (+sound)...
* css 에서는 all, print, screen, speech 정도만 남음. 나머지는 deprecate
* MediaQuery 기본은 MediaType 을 지정하는 것.
* css 가 적용될 대상을 지정하는 일

### Display Area vs Device

* Display Area 는 표시되는 영역. 웹브라우저 내부. 가로 세로 크기 등.. 변경 될 수 있다.
* Device 디바이스 화면. 모니터. 흑백이냐 컬러냐.. orientation 등..

### Media feature 1

* MediaQuery 에서 사용되는 속성
* width, height : (max-, min-) + (device-) + (width, height)
  * min-device-height = 300px;
* aspect-ratio : (max-, min-) + (device-) + (aspect-ratio)
  * 화면의 비율을 뜻함.
  * width / height
  * 소수로 기술 할 수 있고, 분수로도 기술할 수 있다.
  * min-aspect-ratio : 5/4, 가로로 더 커지도록 허용할 수 있다. 6/4, 7/4...
* orientation : portrait, landscape
  * 꼭 ratio 랑 일치하지 않다. 디바이스가 결정하는 것.

### Media feature 2 (덜 사용되는 속성)

* color : (min-, max-) + (color) + (-index)
  * color 값이 8 이면 8bit 컬러라는 이야기.
  * color-index 이면 실제로 표현이 가능한 색상 수.
* monochrome : (min-, max-) + (monochrome)
  * 값을 안주면 흑백장치
  * 값일 주면 흑백 색상수.
* scan : progressive | interlace
  * 거의 안쓰는 속성
* grid : 0 | 1
  * 고정 폭 글꼴을 사용한다던지... pixel 기반으로 그림을 그리는게 아닐때...

### MediaQuery 적용하는 방법

* link tag
  * `<link rel="stylesheet" media="query" href="css" />`
* @media
  * `@media query{rules}`
* @import
  * `@import url(xx.css) query`
* MediaType 과 feature 를 사용하여 질의(Query)를 만든다.
  * and, or 를 사용한다.
* or == ,
  * screen, print == screen or print
* and
  * screen and resolution > 90dpi
* print, screen and resolution > 90dpi (섞여있으면??)
  * (print, screen) and resolution > 90dpi : X
  * print, (screen and resolution > 90dpi) : O
  * 컴퓨터는 좌측부터 해석하는데... print, 먼저 해석하다보니 이후건 하나로 묶어서 처리
  * 우선순위에 휘둘리지 말고 괄호로 묶어서 처리하자.

### MediaQuery Template

* 업계에서 공공연하게 사용하고 있다...
* mobile 은 일반적으로 지정하지 않는다.
  * mobile 먼저 대응하고 크면 더 보여주도록 한다.

```
/*all*/

/*mobile*/

@media (max-width:768px) {
  /*tablet portrait*/
}

@media (min-width:768px) and (max-width:1024px) {
  /*tablet landscape & desktop*/
}

@media (min-width:1025px) {
  /*desktop*/
}
```

## 책에서...

### p.47

* clear-fix
  * wrapping 되는 태그를 씌우고, 그 안에 float 속성을 가진 엘리먼트를 배치하여 clear-fix 해라

### p.48

* 메인콘텐츠
  * flexible 하게 크기 변경될 수 있는 영역
  
### p.50 ~ p.51

* 어떻게 뭉텅이를 나눌것인가... 중요한 스킬
* 뭉텅이간의 관계를 정한다.
* 큰 레이아웃을 먼저 본다.
