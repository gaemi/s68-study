# 넷째날

## position model

* NormalFlow 를 참조하지 않는 모델

### relative

* NormalFlow 에서 일어난 일은 그대로!
* 그 상태에서 위치만 이동한다.
* 하지만 크기는 늘어난다. 스크롤바는 생긴다.
* enable offset parent
* undefined - table elements
* http://www.bsidesoft.com/hika/s68/4_1.html

### absolute

* NormalFlow 로 그리지 않는 녀석 (out of normal flow)
* relative to nearest positioned ancestor 
  * positioned ancestor = static 이 아닌 녀석
  * 즉 static 이 아닌 부모가 하나라도 발견되면 그녀석을 기준으로 계산한다
* 또는 initial container (브라우저에선 주로 body)

### fixed

* relative to viewport bound
  * viewport = 화면에 표시할 수 있는 공간. display area
  * viewport 는 body. iframe 등이 가질 수 있다.
* effect only z-index from positioned ancestor
* http://www.bsidesoft.com/hika/s68/4_2.html

### sticky

* https://drafts.csswg.org/css-position-3/relative + fixed
* 부모 컨테이너가 화면에 보일때까지 살아있을 수 있다. (부모와 공동 운명체)
* 본인이 스크롤 한계에 도달하지 않으면 relative, 또는 fixed 로 움직인다
* http://www.bsidesoft.com/hika/s68/4_3.html

## relative bridge

* absolute in normal flow
* normal flow 중간에 굉장히 자연스럽게 배치하는 공간을 만들고 싶다.
* 이때 relative bridge 를 사용해서 normal flow 안에 relative 공간을 만든다.

## 책

### p.63

* scope, isolate (격리) 이야기가 나옴. 하단의 h1, p 를 div 로 감싸서 한정하였음.
* 여파가 외부로 퍼져나가지 않게 하기 위한 기법.
* 변경가능성에 얼마나 내성이 있는가... 
* html4 에서는 `<h1>` 은 문서에 한번만 나올 수 있다.
* html5 에서는 컨텍스트가 다르면 `<h1>` 이 또 나올 수 있다
* 그렇다면 컨텍스트의 경계면을 결정하는 건?? section, article

### p.67

* html4 에선 li 의 부모가 될 수 있는건 ul, ol 이었음.
* html5 에선 li 의 부모가 될 수 있는건 menu 가 생겼음. 여기선 원래 이걸 써야 함...
* ul 에 list-style 에 none 처리를 해서 normalize 라고 한다.

### p.72

* 스캐폴딩 (scaffolding) : 공통적으로 준비하는걸 준비하는 행위. 뼈대.

### p.73

* DOCTYPE 이 있는 이유는, 최초에는 하나의 파일에 여러개의 각기 다른 DOCTYPE 을 문서가 연속적으로 있을것이라고 예상했음.
  * 그래서 지금 DOCTYPE 이 무의미..
  * html4에선 DTD 라는게 있었음. (파서한테 주는 정보. 이 DTD 를 사용해서 파싱해)
  * html5에선 표준파서를 사용한다. DTD 없음.
* 언어종류 즉 lang 이라는 속성은 html 말고도 모든 태그에 (아마도?) 다 들어갈 수 있다.
* head 의 meta 태그. charset 은 파일 인코딩.  
  * 실제로는 파일 인코딩값이랑 meta 태그에 지정된 charset 이랑 다를 수 있자나?? 왜 쓸까?
  * 이게 안써있으면 웹서버가 결정을 한다.
  * 웹서버가 제대로 response head 에 encoding 정보를 표시하지 못한다면? 웹브라우저는 head 의 meta 정보의 도움을 받는다.

## 번외

### encode, decode

* 비슷한 말 encrypt, decrypt (암호화, 복호화)
* encode 는 암호화가 아니라 단순히 표현을 바꿔주는 것. 누구나 보면 원래 모양을 복원 (decode) 할 수 있다.
* 압축 - 압축해제로 쓰이기도 한다.
* encode 에서 쓰인 charset 이란? 코드집.
* utf-8 은 유니코드를 사용한 코드집
* 문자 > 유니코드 > 숫자 > 인코딩(utf-8, 16, 32) 
* 즉 utf-8 이라는건 유니코드로 숫자화 시킨걸 인코딩 시켰다.

