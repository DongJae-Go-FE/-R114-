SmartManage CodingConvention
================
> - 최초작성 : 2023-11-14 (작성중)


개요
----
> 마크업 개발은 프런트 페이지의 기본 구조를 형성하기 때문에 디자인, 브라우저, 스크립트, 성능, 접근성 등과 깊은 연관성이 있으며, 
> 마크업 개발이 잘 구성되어야  모든 브라우저에서 콘텐츠의 손실 없이, 빠르고 쉽게 사용자에게 전달할 수 있다. 
> 가이드를 준수하여 프로젝트 멤버 간 원활한 코드 공유와 일관성 있는 기준으로 소스 코드를 작성하는 것이 중요하다.
> 최초 개발자가 아닌 사람도 코드를 빠르고 정확하게 이해할 수 있도록 작성하는 것은 코드의 유지보수와 업무 효율을 높이는 데 중요한 역할을 한다. 
> 위와 같이 코딩 컨벤션은 마크업 개발자가 지켜야 할 표준과 빠른 서비스 유지보수를 위해 통일된 코드 작성법을 제시한다.
 
* * *
 
React 환경 설정
--------------
> 신규 프로젝트 진행시 개발팀과 개발환경을 맞추기 위해 셋팅을 동일한 조건으로 한다.
> 프로젝트 개발 환경 셋팅은 개발팀의 가이드에 따른다.
> :warning: 현재 환경 설정은 기본적인 가이드이며 확정된 버전이 아님. (추후 프로젝트 진행 시 정의하여 가이드 작성 예정)

### 기본 개발언어
- React  
- @emotion-styled  
- TypeScript  
- Next.js  
- Chart.js


### React 설치 (설치 관련)
- node.js다운/설치 (https://nodejs.org/en/)
- 터미널에서 설치 버전 확인 <pre><code>npm -v</code></pre>
- 프로젝트 폴더에서 리액트설치 <pre><code>npx create-react-app .</code></pre>


### @emotion/styled 패키지 설치
<pre><code>yarn add @emotion/react @emotion/styled</code></pre>

* * *

React 가이드
--------------
### 기본규칙
> - 아토믹 디자인을 기반으로 구조를 설계한다.(기능에 따른 분류 or 유형에 따른 분류 등등)
> - 파일당 하나의 React 구성 요소만 포함한다.
> - 확장성있고 재사용성 있는 코드를 만들어야 한다.
> - 코드를 분리하고 단일 책임을 가지는 컴포넌트를 만들어야 한다.
> - 외부에 제어를 위임시키는 것을 고려 해야한다. (props)

### DTD문서형 선언 및 인코딩
- HTML5사용
<pre><code>&lt;!DOCTYPE html&gt;</code></pre>


### language TYPE 
<pre><code>&lt;html lang="ko"&gt;</code></pre>


### Encoding 선언
<pre><code>&lt;meta charset=utf-8" /&gt;</code></pre>


### 폴더구성 
> :warning: 프로젝트 진행에 따라 변경 될 예정이며 확정 후 다시 정리할 예정
- /public/ : 이미지,아이콘 등 관련 파일 저장 
- /src/ : 폴더 아래 구성 할 것
    + /components/  : 컴포넌트 파일을 저장(컴포넌트의 범위에 따라 아래 폴더별로 구분 저장)
        * /atoms/   
        * /molecules/  
        * /organisms/  
        * /templates/  

### 파일/폴더 네이밍 규칙
- 기본 네이밍은 카멜케이스를 기반으로 작성한다.
- 컨포넌트의 최종 폴더는 파스칼케이스 형식으로 네이밍을 작성한다. (예 - /SidePanelMenu/)
- 컨포넌트의 네이밍은 폴더명과 동일하게(파스칼케이스) 작성한다. (예 - /SidePanelMenu/SidePanelMenu.tsx)
- Styled 파일은 각 폴더에 styled.* 로 네이밍을 통일한다.
- 확장자는 Typescript를 사용함으로 *.tsx / *.ts 를 사용한다.
- 컨포넌트 외 파일의 네이밍은 카멜케이스로 작성한다. (예 - useDomainSelects.ts)


### 구조와 표현 분리 
- 문서의 마크업 언어(React)와 화면 표시(Styled)언어를 본래의 목적에 맞게 파일로 분리한다.
- Component 파일과 Styled 파일은 같은 폴더 내에 위치한다.
- 각 컨포넌트 폴더마다 index파일을 생성하여 import시 경로를 줄일 수 있도록 한다.
     예)
<pre><code>
import Layout from "./Layout";

export default Layout;
</code></pre>


### 온라인서식구성(Form)
- form, fieldset, legend, label, input, textarea, title 요소를 올바른 방법으로 사용한다.
   + 탭(tab)키를 이용하여 서식 제어 요소 간을 이동할 경우에 그 순서가 왼쪽 위에서 오른쪽 아래 부분으로 순차적인 이동이 가능하여야 한다
   + 서식제어 요소와 레이블 요소가 서로 매칭되어야 한다.
   + 추가 정보 필요시 경우 정확한 title 속성을 제공하여야 한다. 또한 label 요소가 사용되지 못하는 서식제어 요소에도 title 속성을 제공하여야 한다.
- 속성 선언
   + :keyboard: 작성중입니다.

### table요소 사용 방법
- 레이아웃을 표현하기 위하여 표를 사용하지 않는다.
- table 요소의 속성 지정 순서는 cellspacing, summay 이며 border 값은 클래스를 지정하여 사용한다.
- caption 요소는 표의 제목을 표현하며 표의 윗부분에 헤딩 요소로 표의 제목을 표시하면 생략가능하다.
- 디자인에 머리글이 제공되어 있지 않더라도 반드시 머리글을 제공한다.
- 행 제목과 열 제목이 있는 경우 이에 대한 scope 속성을 사용하여 행과 열의 범위를 적절히 구분하여 배치한다.
>  :keyboard: 작성중입니다.

### 시멘틱 마크업(Semantic Markup)
> 시멘틱 마크업은 종종 POSH(Plain Old Semantic HTML)라고도 불리는데, 단어 그대로 평범하고 오래된 의미론적인 HTML이라는 뜻이다. 
> 시멘틱은 즉, 기계(컴퓨터, 브라우저)가 잘 이해할 수 있도록 하는 것이며 프로그래밍 언어는 사람과 기계와의 정해진 약속이며 HTML 역시 마찬가지다.
> 시멘틱 마크업은 적절한 HTML 요소를 올바르게 사용하는 것에서 시작한다. 

- 시멘틱 마크업 태그 안내
   + &lt;article&gt; : 재사용할 수 있는 구획을 나타냄. 
      * 예) 게시판, 블로그 글, 뉴스 기사 등
   + &lt;aside&gt; : 문서의 주요 내용과 간접적으로 연관된 부분 
      * 예) 사이드바, 광고
   + &lt;details&gt; : '열림'상태일 때만 내부 정보를 보여주는 위젯 
      * 예) summary와 함께 쓰임
   + &lt;summary&gt; : 디테일 요소의 제목 역할 
      * 예) details 자식으로 상세요소가 열리기 위한 제목 역할
   + &lt;figcaption&gt; : 부모 요소 콘텐츠의 설명, 범례 
      * 예) 이미지에 대한 설명글
   + &lt;figure&gt; : 독립적인 콘텐츠 
      * 예) 이미지 등 설명을 위해 figcaption과 사용
   + &lt;footer&gt; : 작성자, 저작권 정보, 관련 문서 등의 내용을 담는 푸터 
      * 예) 사이트 푸터
   + &lt;header&gt; : 소개 및 탐색에 도움을 주는 콘텐츠 
      * 예) 로고, 제목, 검색폼, 작성자 이름 등이 있는 사이트 헤더
   + &lt;main&gt; : body의 주요 콘텐츠, 문서의 핵심 주제, 핵심 기능 
      * 예) hidden 속성을 이용해, 문서에 하나만 존재해야함.즉, 문서에서 유일한 내용이며 반복적이지 않은 콘텐츠
   + &lt;mark&gt; : 강조하고 싶은 부분 
      * 예) 하이라이트
   + &lt;nav&gt; : 또 다른 페이지로 이동하는 링크를 보여줌 
      * 예) 메뉴, 목차, 색인
   + &lt;section&gt; : 독립적인 구획을 나타내며, 더 적합한 의미를 가진 요소가 없을 때 사용. 해당 구획이 논리적인 구분을 나타냄 
      * 예) 단순 스타일링, 일반 컨테이너가 목적이라면 div를 사용할 것
   - &lt;time&gt; : 시간의 특정 지점, 구간 
      * 예) 기계가 읽을 수 있는 형태로 날짜와 시간을 표현할 때 사용
   
- 헤더/푸터에 &lt;header&gt;와 &lt;footer&gt; 사용
- 메인 컨텐츠에 &lt;main&gt;과 &lt;section&gt; 사용
- 독립적인 컨텐츠에 &lt;article&gt; 사용
- 최상위 제목으로 &lt;h1&gt; 사용
- 순서가 없는 목록으로 &lt;ul&gt;과 &lt;li&gt; 사용
- 내비게이션에 &lt;nav&gt;사용
- 
- [참고자료] 
   + https://developer.mozilla.org/en-US/docs/Glossary/Semantics
   + https://www.w3schools.com/htmL/html5_semantic_elements.asp
>  :keyboard: 작성중입니다.

### 스키마 마크업(SEO)
>  :keyboard: 작성중입니다.

### 들여쓰기 규칙
- 코드의 가독성을 높이고 전체 HTML 구조를 쉽게 파악하기 위하여 들여쓰기 규칙을 준수한다.
- 마크업의 중첩이 깊어질 때마다 자식 요소는 1탭 들여 쓰고, 1탭의 크기는 공백 4칸으로 설정한다.
>  :keyboard: 작성중입니다.

### 마크업 유의사항
- DTD 선언 앞에 주석 등의 내용이 없어야 한다.
- &lt;head&gt;태그의 내부와 &lt;body>태그의 내부 이외에 내용을 삽입하지 않는다.
- &lt;p&gt; 태그 안에는 &lt;p&gt;, &lt;div&gt;, &lt;ul&gt; 등 다른 블럭요소가 들어갈 수 없다. (display:inline 속성을 적용해도 소용없음)
   + &lt;p&gt; 태그는 문단을 구분하는 용도로만 사용하고 영역을 구분하는 용도로 사용하지 말 것.
- &lt;link&gt; 태그에 삽입된 &lt;img&gt; 태그에는 이미지맵을 사용할 수 없다.
- &lt;link&gt; 태그 안에는 &lt;link&gt; 태그가 들어갈 수 없다.
- &lt;form&gt; 태그 안에는 &lt;form&gt; 태그가 들어갈 수 없다.
- &lt;pre&gt; 태그 안에는 &lt;img&gt;, &lt;object&gt;, &lt;big&gt;, &lt;small&gt;, &lt;sub&gt;, &lt;sup&gt; 태그가 들어갈 수 없다.
- &lt;button&gt; 태그 안에는 &lt;input&gt;, &lt;select&gt;, &lt;textarea&gt;, &lt;label&gt;, &lt;button&gt;, &lt;form&gt;, &lt;fieldset&gt;, &lt;iframe&gt;, &lt;isindex&gt;태그가 들어갈 수 없다.
- &lt;button&gt; 태그의 type 속성을 지정하지 않았을 때 submit 기능으로 동작하므로 폼 값을 전송하는 용도로 사용하지 않을 경우 type="button"을 지정
- 태그의 중첩에 유의
   - &lt;em&gt;&lt;strong&gt;내용&lt;/em&gt;&lt;/strong&gt; (:x:)
   -  &lt;em&gt;&lt;strong&gt;내용&lt;/strong&gt;&lt;/em&gt; (:o:️)
- 하나의 ID는 페이지에서 한번만 사용할 것 (스타일은 적용되나 책갈피 기능이나 스크립트를 정상적으로 사용할 수 없음)
- :keyboard: 작성중입니다.

* * *

Styled Components 가이드
--------------------------
### 패키지 설치
<pre><code>yarn add @emotion/react @emotion/styled</code></pre>

### 기본구조
<pre><code>:keyboard: 작성중입니다.</code></pre>

### style기본 규칙
- 모든 속성은 영문 소문자로만 작성한다.
- 작은 따옴표('') 사용 범위 : 폰트의 선언, 배경 url, filter, content에 작은 따옴표('')를 사용한다. 그 외의 경우는 사용하지 않는다.
- 세미콜론(;) : 마지막 선언된 속성에도 세미콜론(;)을 사용한다.
- 공백의 사용 : 선택자 간, 중괄호간 한칸의 공백을 사용한다, 중괄호 안쪽 좌우에는 공백은 사용하지 않는다.(공백은 최소화 한다.)


### style작성 규칙
- 속성선언 순서 : 크기 - 형태 - 흐름 - 위치 - 박스모델 - 배경 - 글자 - 기타 순으로 지정 
- 네스팅 형식으로 작성하되 한줄에 하나의 속성만 작성한다.
- 관련된 속성은 붙여서 작성한다. (예 : text-align:center; font-size:12px; font-weight:bold; color:#000;) 
> 속성정보
> 1. 크기 : width height overflow
> 2. 형태 : display visibility
> 3. 흐름 : float clear
> 4. 위치 : position left right top bottom z-index
> 5. 박스 : margin padding border
> 6. 배경 : background
> 7. 글자 : text font color
> 8. 기타 : cursor transition transform 등 위에서 언급되지 않은 속성


### style파일구조
- 컴포넌트와 동일한 폴더에 동일한 파일 네임으로 존재할 것.
- :keyboard: 작성중입니다.

### Global CSS
- CSS 리셋 요소
- 공통 요소
- 저장위치 및 파일명 <pre><code>/app/global.css</code></pre>
- :keyboard: 작성중입니다.

### 네이밍 규칙
- 네이밍은 기본적으로 스네이크케이스 사용한다.
- 영문 대문자, 숫자, 특수문자로 시작할 수 없다
- :keyboard: 작성중입니다.

### 크로스브라우징
- 지원 브라우저
   + Microsoft Edge 최신버전
   + Chrome 최신버전
   + Safari 최신버전
   + Firefox 최신버전
   + Opera 최신버전
   + whale 최신버전
   + IE는... 포기하자 (크롬 설치 안내 팝업으로 대체)
> :scream: CSS핵의 사용은 최소화 하되 구버전 브라우저의 지원이 필요한 경우에만 CSS핵을 사용한다.

* * *

이미지 파일 네이밍 규칙
---------------------
- 네이밍 표기법 : 스네이크 케이스를 기반으로한다. (예. img_name_list.png)
- 네이밍 조합 : 종류_의미_순서_상태.확장자 (예. icon_arrow_up.png / but_bg_01_on.png)
- 이미지포맷 : gif / jpg / png / svg
- 금지조항 : 대문자. 공백, 특수기호는 사용 금지
- 네이밍 규칙 : 아이콘(icon_*) / 화살표(arrow_*) / 블릿(bull_*) / 배경(bg_*) / 비주얼(vi_*) / 일반(img_*) / 썸네일(thumb_*) / 임시(@*)

* * *

>  부동산R114 코딩 컨벤션은 계속 진행 진행중에 있습니다. 
>  추가 내용이 필요하거나 수정되어야 할 부분이 있으면 의견 전달 주시기 바랍니다.
