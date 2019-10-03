# CSS/CSS를 HTML에 적용시키는 방법
* Inline Style Sheet : HTML 태그의 style 속성에 CSS 코드를 넣는 방법
* Internal Style Sheet : HTML 문서 안의 <style>과 </style> 안에 CSS 코드를 넣는 방법
* Linking Style Sheet : 별도의 CSS 파일을 만들고 HTML 문서와 연결하는 방법

* Inline Style Sheet
  * <p style="color: blue">Lorem ipsum dolor.</p>
    * 해당 태그(위 코드에서는 p)가 선택자(selector)가 되고, CSS 코드에는 속성(property)과 값(value)만 들어감 
  
* Internal Style Sheet
  * <style>
    h1 {
      color: blue;
      }
    </style>
    * <style> 태그는 보통 <head>와 </head> 사이에 넣으나, HTML 문서의 어디에 넣어도 잘 적용
  
* Linking Style Sheet
  * h1 {
   color: red;
  }


# CSS / 기초 / 문법
  * h1 { color: red } : h1, color, red 세 개의 단어가 있는데 각각 선택자, 속성, 값
   * 선택자(selector) : 무엇을 꾸밀지 정합니다. h1은 h1 요소를 꾸미겠다는 뜻
   * 속성(property) : 어떤 모양을 꾸밀지 정합니다. color는 색을 꾸미겠다는 뜻
   * 값(value) : 어떻게 꾸밀지 정합니다. red는 빨간색으로 만들겠다는 뜻
* 여러 개의 선언 
  * h1 {
  color: red;
  font-size: 20px;
} -> h1 요소의 색을 빨간색으로 하고 글자 크기를 20px로 만들겠다는 뜻

* 값(value)에 공백이 있는 경우
  * p {
  font-family: 'Times New Roman';
} -> 값(value)에 공백이 있다면 작은 따옴표 또는 큰 따옴표로 감쌈
* 공백 
  * selector { property: value; property: value; } -> 여러 개의 연속한 공백이나 줄바꿈은 하나의 공백으로 인식
* 주석
  * /* Comment */
  
  
# CSS / 선택자(Selector) / 전체 선택자, 타입 선택자, 속성 선택자
* 전체 선택자(Universal Selector)는 모든 HTML 요소를 선택합니다. 별표(* ) 로 나타냄
  * * {
     color: blue;
      } -> 모든 요소의 색을 파란색으로 만듬
* 타입 선택자
  * h1, p, div, span 등 HTML 요소(Element)를 선택하는 선택자
    * p {   color: blue; } -> HTML 문서 안에 있는 모든 p 요소의 내용을 파란색으로 만듬
* 속성 선택자
  * 특정 속성(attribute)을 갖고 있거나 특정 속성이 특정 값 등을 갖고 있는 요소(element)를 선택
    * [attribute] ex) h1[title] -> title 속성을 가진 h1 요소를 선택
    * [attribute="value"] ex) h1[title="abc"] -> title 속성의 값이 abc인 h1 요소를 선택
    * [attribute~="value"] ex) h1[title~="abc"] -> title 속성의 값이 abc를 포함한 h1 요소를 선택. 포함 여부는 단어 기준으로 판단
    * [attribute|="value"] ex) h1[title|="abc"] -> title 속성의 값이 abc이거나 abc-로 시작하는 h1 요소를 선택
    * [attribute^="value"] ex) h1[title^="abc"] -> title 속성의 값이 abc로 시작하는 h1 요소를 선택합니다. 단어 기준이 아니라 문자열 기준
    * [attribute$="value"] ex) h1[title$="abc"] -> title 속성의 값이 abc로 끝나는 h1 요소를 선택. 단어 기준이 아니라 문자열 기준
    * [attribute*="value"] ex) h1[title*="abc"] -> title 속성의 값이 abc를 포함한 h1 요소를 선택. 포함 여부는 문자열 기준으로 판단
    
    
# CSS / 선택자(Selector) / 아이디 선택자, 클래스 선택자
* 아이디 선택자
  * 특정 값을 id 속성(attribute)의 값으로 갖는 요소(element)를 선택. 속성값 앞에 #을 붙여 아이디임을 나타냄 
    * #abc {   color: red; }
* 클래스 선택자
  * 특정 값을 class 속성(attribute)의 값으로 갖는 요소(element)를 선택, 속성값 앞에 .을 붙여 클래스임을 나타냄
    * .abc -> class 속성값으로 abc를 갖는 요소를 선택
    * 클래스 선택자 앞에 아무 것도 없으면 그 값을 갖는 모든 요소를 선택
    * 선택자 앞에 무언가 있으면 모두 만족하는 요소를 선택 (p.abc -> class 값으로 abc를 갖는 p 요소를 선택클래스)
    
    
# CSS / 선택자(Selector) / 하위 선택자, 자식 선택자, 형제 선택자, 인접 형제 선택자
* 하위 선택자
  * 특정 요소의 하위에 있는 요소를 선택
    * div blockquote -> div 요소의 하위에 있는 blockqoute 요소를 선택합니다. 이때 div와 blockquote 사이에 요소가 더 있어도 선택됨
* 자식 선택자 
  * 특정 요소의 자식 요소를 선택
    * div > blockquote -> div 요소의 자식 요소 중 blockqoute를 선택. 주의할 점은 한단계 아래에 있는 요소만 선택한다는 것
* 형제 선택자
  *  어떤 요소의 형제 요소를 선택하는 선택자
    * h1 ~ p -> h1 요소의 형제 요소 중 p 요소를 선택
* 입접 형제 선택자
  * 어떤 요소의 형제 요소 중 첫번째 요소를 선택
    * h1 + p -> h1 요소의 형제 요소 중 첫번째 p 요소를 선택
   
# CSS / 선택자(Selector) / 가상 요소
* 가상 요소
  * 가상 요소(Pseudo-elements)는 요소의 특정 부분을 선택
  * 가상 클래스는 콜론을 한 개(:), 가상 요소는 콜론을 두 개(::) 씀. 하지만 콜론을 한 개(:)만 써도 대부분의 브라우저에서 제대로 작동
    * ::first-line : 첫번째 줄을 선택 ex) p::first-line { color: red; } -> p 요소의 첫번째 줄의 글자색을 빨간색
    * ::first-letter : 요소의 첫번째 문자를 선택 ex) p::first-letter { color: red; } -> p 요소의 첫번째 문자의 색을 빨간색 
    * ::before :요소의 앞을 선택 ex) p::before { content: "xyz"; color: red; } -> p 요소 앞에 xyz라는 단어를 넣고 색을 빨간색
    * ::after : 요소의 뒤를 선택 ex) p::after {content: "xyz"; color: red;} -> p 요소 뒤에 xyz라는 단어를 넣고 색을 빨간색
    * ::selection : 마우스 드래그 등으로 선택한 텍스트를 선택
    
    
# CSS / 선택자(Selector) / 가상 클래스
* :empty
  * 내용이 없는 비어있는 요소를 선택
    *  li:empty -> li 요소 중 내용이 없는 것을 선택
* :first-child 
  * 형제 요소 중 첫번째 요소를 선택
* :hover
  * 요소에 마우스를 올린 상태를 선택
    * p:hover {color: red;} -> p 요소에 마우스를 올렸을 때 글자색을 빨간색


# CSS / 선택자(Selector) / :nth-child(), :nth-last-child()
* :nth-child(), :nth-last-child()
  * 특정 순서에 있는 요소를 선택할 때 사용하는 선택자
  * :nth-child()는 앞에서부터 세고, :nth-last-child()는 뒤에서부터 셈
  
* :nth-child()
  * 형제 요소 중에서 특정 순서에 있는 요소를 선택할 때 사용
    * :nth-child( an+b )
    * a와 b는 정수입니다. 0과 음수도 가능
    * n에는 음이 아닌 정수, 즉 0, 1, 2, 3, …이 차례대로 대입
    * an+b 대신에 even, odd를 넣을 수도 있음
 * :nth-last-child()
   * 형제 요소 중에서 특정 순서에 있는 요소를 선택할 때 사용. 뒤에서 부터 센다는 것
     * :nth-last-child( an + b )
     * a와 b는 정수입니다. 0과 음수도 가능
     * n에는 음이 아닌 정수, 즉 0, 1, 2, 3, …이 차례대로 대입
     * an+b 대신에 even, odd를 넣을 수도 있음
     

# CSS / 상속(inheritance)
* 상속
  * 상속하는 속성과 상속하지 않는 속성이 있음. 상속하는 속성은 자식 요소에 영향을 미침. 상속하지 않는 속성은 자식 요소에 영향을 미치지 않음
    * 상속하는 속성 : color는 상속하는 속성. 부모 요소에서 정한 색이 자식 요소에도 적용
    * 속하지 않는 속성 : 부모 요소에서 padding을 정의해도 자식 요소에 적용되지 않음
   
