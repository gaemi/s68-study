# 둘째날

## 인사말

* 1장에 많은 내용이 있어요.
* 기초가 탄탄해야함. 아니면 나아가기 어려움.
* 저번에 이야기했던 Graphics System 은 굉장히 일반적인 내용. 모든 시스템이 그렇습니다.
* HTML 이 그림이 그리는 방법은 CSS스펙문서를 참고하면 된다.
  * 하지만 스펙문서는 굉장히 딱딱하고 개발자도 잘 안본다.
  * 그래도 보려는 노력은 해야 한다.
  * 개발자적인 사고 = 남이 만들어 놓은게 무언지 정확하게 이해하는 것.
  * 코끼리 전체(스펙문서)를 봐야하지 다리, 몸통 등 부분부분 필요할때만 봐서 이해하려하면 안된다.
* 각 시스템이 (Html, iOS, Android...) 고유의 Graphics System 이 있다.

## Box Model

* 하나의 엘리먼트들이 그릴때 아래와 같은 박스모델로 공간을 차지
  * margin : 외각선 바깥의 공간
  * border : 외각선
  * padding : 외각선을 기준으로 contents 까지의 공간
  * contents : margin, border, padding 빼고 나머지 공간
* 위와 같을때 width, height 는 contents 영역의 크기를 의미한다.
  * 문제점은 width, height 를 100% 로 주고 별도의 margin, border, padding 있으면 화면을 넘어간다. (스크롤바가 생긴다.) 
* 그래서 CSS3 는 width, height 가 어느박스를 기준으로할지 설정할 수 있다. (기본은 contents)
  * box-sizing:contents-box - contents-box 까지 포함 (이게 기본값)
  * box-sizing:padding-box - padding-box 까지 포함 (현재 Firefox 만 지원)
  * box-sizing:border-box - border-box 까지 포함
* 지식의 붕괴
  * 여러 지식들이 부딪혀서 뭐가 뭔지 더더욱 모르게 되는 상태.
  * 체계성 있는 지식을 차곡 차곡 외우는게 필요.

## Normal Flow

* HTML 이 렌더링을 할 때 static 포지션 모델에서 사용하는 것.
* 엘리먼트의 포지션이란...
  * static : 컴퓨터가 알아서
  * releative...
* 세로로 배치하는 행위 block
* 가로로 배치하는 행위 inline 
* BFC (Block Formatting Context)
  * 이 동네는 내가 다 세로로 배치할꺼야 하는 컨텍스트.
  * 그 안에 엘리먼트들은 세로로 배치된다.
  * 블럭요소를 담을수 있는 일종의 컨테이너
* IFC (Inline Formatting Context)
  * 이 동네는 내가 다 가로로 배치할꺼야 하는 컨텍스트.
  * 그 안에 엘리먼트들은 가로로 배치된다.
  * 일반적으로 IFC 는 BFC 안에서 발동된다.
* (어떠한 이유로) BFC 가 발동되고 그 안에서 새로운 BFC 가 발동되고 그 안에서 IFC 가 발동되고...
* 컴퓨터는 이걸로 그림을 그린다. 엘리먼트로 그림을 그리는게 아니다!
  * 엘리먼트는 데이터적인 관점. 컴퓨터가 그림 그리는것과 무관한다.
  * 각각의 레이어는 서로 관심이 없다. DOM 과 그림그리는건 별개다.
  * BFC + IFC 의 조합으로 그림을 그린다고 보면 됩니다.
* BFC 가 언제 만들어지나
  * root
  * float != none
  * display == inline-block, table-cell, table-caption
  * overflow != visible
  * flex box
* BFC 는 안에 포함된 엘리먼트를 포함하지만, 안에 포함된 BFC가 포함하는 엘리먼트는 포함하지 않는다.
* 예제 : http://www.bsidesoft.com/hika/s68/2.html

## Display & Float

### display

* display-outside
  * block, inline, inline-block
  * 내가 바깥쪽에 (부모입장에서 봤을때) 어떤식으로 공간을 차지해야 할까??
  * inline 요소는 Wrap Content 에 따라 width, height 가 결정. 
  * 따라서 width, height 를 유지하려면 inline-block 사용
* display-inside
  * table, flex, grid
  * 내 안에 어떤식으로 표시되었으면 좋겠다.
* display-internal
  * table-cell
  * display-inside 안에 있다.

### float

* BFC 박스 마지막 엘리먼트 다음의 좌상단을 기준으로 float 박스가 생성된다.
* 따라서 어디가 BFC 의 시작이야? 가 float 한테 매우 중요하다.
