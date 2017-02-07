# 첫째날

## 스터디 목적

### Dick bruna

* 미피 캐릭터만든 할아버지
* 미피 캐릭터 3장씩 그린다. (많이 그리면 가치가 떨어짐)
* 그렇지만 유니세프에는 매년 하나씩 납품

## Graphics System, Rendering System

### Graphics System

* *표시된것이 스터디에서 배울거임

#### Fixed Number System

* layer0
* 시각적인 시스템
* Computer Graphics 의 기본은 점을 찍는거
* x, y, width, height, color...
* 총괄해서 Fixed Number System (확정된 수치를 기반으로 한 시스템)
* 가장 기본적인 시스템
* update 가 어렵다

#### Abstract Calculator *

* layer1
* 여러 시스템, 여러 디스플레이에서 동일한 컨텍스트를 유지하고 싶다.
* 컨텍스트(context)는 한국어로 표시할 수 없다. 문맥X
* %, left, top, block, inline, float...
* screen size, chrome size, hierarchy calculator 등을 알아야 한다.

#### Components *

* layer2
* Button, Checkbox, RadioButton, Slide...
* Component, 목적만을 기술
* Html 에선 textarea, input, button, img...

#### Frameworks

* layer3

### Rendering System

* 실제로 구현하는거...
* Rendering 이란 시각화되지 않은 데이터를 기반으로 시각화하는거.

#### Geometry calculate

* 영역, 공간을 잡는 행위
* Layout = Geometry
* 채우는건 채우는거고, 먼저 공간계획을 세우는 연습을 하자.

#### Fragment Fill

* 공간을 나눴으면 색칠 연습
* Fragment = 조각 = 셀
* 채울수 있는건 굉장히 많다.

### Html 특징

* 텍스트 최적화
  * 물론 더 강력해지고 있다. hint 라던지...
* Form 이 강력하다.
* Image는 느리다. (타 시스템에 비해서)

## 책으로 넘어가서

### Computer Science

* 추상화에 대한 이야기.
* A>B, B>C 면 A>C 가 성립. 이걸 F 라고 하자 (이것이 추상화) 오! 뭔가 명쾌한 설명

### Html 다시.. (p23)

* 원고지에 v 표시가 markup 의 꺽쇠 원조. 레알?
* SGML > 웹으로 옮긴게 HTML
* 즉 HTML 은 최초 인쇄를 목적으로 한 언어
* 4.0 이후 태그에 의미를 부여
* 디지털 문서에서 유의미한 데이터를 추출하기 힘들다. 그래서 태그를 사용. MS의 힘.
* `<b>` 가 의미를 가지는 `<strong>` 으로 바뀌었다.
* 태그가 어떤식으로 표현될지... Opera 의 창립자가 CSS 라는걸 고민.
* Html 은 의미만 있어야 한다. (이론적으로는...)
* 예외는 있어요. `<audio>`, `<vidoe>`, `<img>` 완전 기능적인 태그
* 또 `<span>`, `<div>` 등... 모양만 입히기 위해서 사용. `<nav>`, `<footer>` 등도 태어남.

### class (p23)

* 스타일을 적용하기 위해 사용
* 스타일만 Html 을 알고 있다. Html 은 스타일을 모름.
* 스타일이 Html 을 찾기 위한 방법 = selector
* 빨간색(스타일) + selector...  = 이런걸 Rule 이라고 한다.
* Rule 이 모여있는걸 RuleSet
* RuleSet 이 모여서 Sheet. 이래서 이걸 Style Sheet 라고 부른다.
* Html 은 기본 Sheet 가 있다. 각 태그별 기본 모양을 가지고 있음.
* Sheet 가 여러개 있으면, 이전 Sheet 를 덮어쓰기가 가능함. 마지막놈이 이김.
* selector 방법
  * 번호를 지정하는 방법 (몇번째 child 이런식...)
  * hint 지정하는 방법 (span 태그 이런식...)
  * 직접적인 이름으로 부르면 대체하기 어렵다. 예를들면 index. 그래서 되도록 사용 안하려고 한다.
  * 그러니 공통점을 찾아 그룹화하자. class! (왜 group 을 안쓰고...)
  * 고유한건 id!
* class spec
  * 스페이스로 여러가지 지정 가능
  * 뒤에거가 이긴다.
* 왜 id 를 안쓰고 class 를 쓰는가. 
  * id 가 고유하다고 보장하기 힘들다.
  * 왜냐면 여러 작업물이 합쳐질 수 있는걸...

### css (p24)

* 자식은 부모의 속성을 상속 받는다. 
* 그래서 cascading style sheet
* 자기 스타일이 우선시된다. 이 경우는 cascading 무시.
* 몇가지 특징
  * 뒷놈이 이긴다.
  * 긴놈이 이긴다. `.boxA .box2` 는 `.box2` 를 이긴다. (길다 = 구체적이다)

### display (p24)

#### block

* 부모가 허락하는 한 가로를 다 차지한다.
* `<div>` 의 기본 속성은 block 이다. 그러니 가로를 다 차지함

#### inline

* 가장 큰 녀석이 inline 의 크기를 결정
* 앞의 영역의 baseline 을 따라가고 전요소 옆에 다음요소가 붙는다.
* 부모의 남은 공간에 다음 요소가 들어갈 수 있으면 집어 넣는다. 아니면 다음줄 baseline 잡는다.

#### float

* 현업 퍼블리셔들도 설명하기 힘들다.
* 어려운 속성
* 화면 크기에 대응하는 유동적인 레이아웃을 작성하는데 유용하게 사용할 수 있다.
* 의미는 둥둥 떠 있다.
* 안떠있는 애들은 block, inline.
  * 이걸 실체라고 부른다. 공간을 차지하는 애들.
* float 은 대표적인 실체가 없는 요소
  * 공간을 점유할 수 없으므로, 이걸로만 속성을 지정하면 사이즈가 (자동으로) 안늘어난다.
  * 별도 레이어가 있다고 생각해보자.
* float 이 block 과 inline 에 주는 영향이 다르다.
  * float 이 어려운 이유.
* float 는 block 에 영향을 끼칠 수 없다. (block은 float을 인식할 수 없다. 모른다. p24 가장 아래 이미지에서 box4 크기는 가로 꽉 차지한다.)
* inline은 float을 가드, 가이드로 생각한다. (block 요소 안의 텍스트는 float 영역을 가이드로 잡는다. p24 가장 아래 이미지)
* float 끼리는 inline 처럼 움직인다. 순서대로... left, right...



