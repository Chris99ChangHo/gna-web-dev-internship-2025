# ✨ HTML: Basic Concepts and Applications

## 1. What is HTML? (Introduction) 💡

**HTML (HyperText Markup Language)** is a **markup language** used to create web pages. It defines how web browsers should structure and display web content. Think of it like building the **framework and structure** of a building. It's responsible for the **logical structure and meaning** of all the elements we see on a web page, including text, images, links, buttons, input forms, and videos.

HTML doesn't directly perform complex calculations or implement dynamic features like a programming language. Instead, it provides the **fundamental blueprint and semantic information** for web content. On top of this blueprint, **CSS** is used to apply visual styling, and **JavaScript** is added to incorporate interactive functionalities, completing a full web page. HTML is the most basic and essential component of all web development.

**Key Features of HTML:**

* **Markup Language:** Uses predefined symbols called tags (e.g., `<tag>`) to display and describe data. These tags tell the browser the type and role of the content.
* **Defines Web Page Structure:** Organizes web content (text paragraphs, headings, lists, images, tables, etc.) in a meaningful and hierarchical way, clarifying the relationships and flow of content.
* **Tag-Based:** Uses various tags like `<p>`, `<h1>`, `<img>`, `<a>` to represent the role and meaning of each element. Most tags consist of an opening tag and a closing tag.
* **Hyperlinks:** Creates **hyperlinks** using the `<a>` (anchor) tag, connecting to other web pages, specific parts of a document, or external resources. This implements the core web functionality of inter-connectivity.
* **Platform-Independent:** Can be written using any plain text editor (e.g., Visual Studio Code, Sublime Text) without special software or compilation processes, and is interpreted and displayed consistently by all major web browsers (Chrome, Firefox, Safari, Edge, etc.) according to web standards.

## 2. Basic HTML Syntax 📝

HTML documents are written using tags and attributes. Most HTML tags consist of an opening tag (`<html>`) and a closing tag (`</html>`), with content placed in between. Some tags are empty or used stand-alone (e.g., `<br>`, `<img>`).

* **Basic Document Structure:** Every HTML document has a standard structure to ensure web browsers can interpret and render it correctly.

    ```html
    <!DOCTYPE html>  <html lang="en"> <head>           <meta charset="UTF-8"> <meta name="viewport" content="width=device-width, initial-scale=1.0"> <title>Document Title</title> <link rel="stylesheet" href="style.css"> </head>
    <body>           <h1>Hello there!</h1>
        <p>This is the first paragraph.</p>
        <script src="script.js"></script> </body>
    </html>
    ```

* **Key Tags and Attributes:**

    * **Heading Tags (`<h1>` ~ `<h6>`):** Define titles or subtitles for the document. `<h1>` is the most important (top-level) heading, with importance decreasing down to `<h6>`.
        ```html
        <h1>Largest Heading</h1>
        <h2>Second Largest Heading</h2>
        <h3>Third Important Heading</h3>
        ```

    * **Paragraph Tag (`<p>`):** Defines a general text paragraph. Browsers automatically add margins before and after `<p>` tags.
        ```html
        <p>This is a paragraph on a web page. It can contain multiple lines of text.</p>
        <p>A new paragraph always starts on a new line.</p>
        ```

    * **Link Tag (`<a>`):** Creates **hyperlinks** that connect to other web pages, documents, or specific parts within the same document. The `href` (Hypertext REFerence) attribute specifies the URL (address) of the target.
        ```html
        <a href="[https://www.google.com](https://www.google.com)" target="_blank">Go to Google (new tab)</a>
        <a href="#section2">Jump to another section on this page</a>
        ```

    * **Image Tag (`<img>`):** Embeds an image into a web page. It's a self-closing tag, meaning it doesn't have a separate closing tag.
        * `src` (Source) attribute: Specifies the path (URL) to the image file.
        * `alt` (Alternative text) attribute: Provides text that is displayed when the image cannot be shown (e.g., broken path, image load failure) or read by screen readers for visually impaired users. **Its use is mandatory for web accessibility.**
        ```html
        <img src="flower.jpg" alt="A beautiful blooming flower">
        <img src="[https://example.com/logo.png](https://example.com/logo.png)" alt="Company Logo">
        ```

    * **List Tags (`<ul>`, `<ol>`, `<li>`):** Used to present information in a structured list format.
        * `<ul>`: Represents an **Unordered List**, where each item is typically preceded by a bullet point or similar marker.
        * `<ol>`: Represents an **Ordered List**, where each item is numbered or lettered sequentially.
        * `<li>`: Defines each **List Item**. It must be used as a child of either a `<ul>` or `<ol>` tag.
        ```html
        <h3>Favorite Fruits</h3>
        <ul>
            <li>Apple</li>
            <li>Banana</li>
            <li>Cherry</li>
        </ul>

        <h3>Ranking</h3>
        <ol>
            <li>Gold Medal</li>
            <li>Silver Medal</li>
            <li>Bronze Medal</li>
        </ol>
        ```

    * **Container Tags (`<div>`, `<span>`):** Generic container tags used to group other HTML elements without special semantic meaning, primarily for applying layout or styles.
        * `<div>`: A **block-level element**. It typically starts on a new line and takes up the full width available. Primarily used for defining large sections or layout divisions of a web page.
        * `<span>`: An **inline-level element**. It doesn't start on a new line and only takes up as much width as its content. Used to apply styles to a specific part of text or to control it with JavaScript without breaking the flow.
        ```html
        <div class="header-section">
            <p>This is a paragraph within the header section.</p>
            <span>This part of the text will be highlighted.</span>
        </div>
        ```

    * **Form Tags (`<form>`, `<input>`, `<textarea>`, `<button>`, `<label>` etc.):** Define elements for receiving user input or facilitating interaction.
        ```html
        <form action="/submit-form" method="post">
            <label for="username">Username:</label>
            <input type="text" id="username" name="username" placeholder="Enter your name">
            <br>
            <label for="message">Message:</label>
            <textarea id="message" name="message" rows="4" cols="50"></textarea>
            <br>
            <button type="submit">Submit Information</button>
        </form>
        ```

* **Attributes:** Used to provide additional information or define behavior for tags. They are written within the opening tag in the format `attribute="value"`.
    * `id`: A unique identifier for an element within the document. It must be unique across the entire web page. Primarily used by CSS to apply specific styles to a single element or by JavaScript to precisely control that element.
    * `class`: Used to apply the **same styles to multiple elements** or to control **groups of elements with JavaScript**. An element can have multiple classes.
    * `style`: Used to apply inline styles directly to an element. While convenient for simple styling, **using external CSS files is highly recommended** for better code readability and maintainability.

## 3. Where is HTML Used? (Key Applications) 🌐

HTML is the foundational language of the web, used to display virtually all digital content through web browsers. Its applications are incredibly vast and it remains a core, indispensable technology in the modern web environment.

* **Structuring and Displaying Web Page Content:**
    * Its most fundamental use is to logically arrange and display all content (text, images, videos, audio, etc.) on a website. It provides the basic framework for all types of informational websites, including blog posts, news articles, product detail pages, and company profiles.
* **Building Web Application Frontends:**
    * It forms the **User Interface (UI)** of all web applications that users directly see and interact with. It serves as the visual component for dynamic and interactive web services such as complex dashboards, online e-commerce platforms (e.g., **WooCommerce**), social media feeds, and online games.
* **Forms and User Input:**
    * Creates various **form elements** (`input`, `textarea`, `select`, `button`, etc.) for receiving data and feedback from users, such as for registration, login, search, inquiries, and orders. This enables interaction between the user and the web page.
* **SEO (Search Engine Optimization):**
    * By using **semantic HTML tags** (e.g., `header`, `nav`, `main`, `article`, `section`, `aside`, `footer`) introduced in HTML5, the meaning of content is clearly conveyed. This helps search engines like Google better understand and index the content of web pages, positively impacting search rankings.
* **Enhancing Web Accessibility:**
    * Aims to ensure that all users can equally access and utilize web content. Proper use of HTML, such as providing descriptive `alt` text for images, using logical heading structures, and employing ARIA (Accessible Rich Internet Applications) attributes, is crucial for assistive technologies like screen readers to effectively deliver web content to all users.
* **Email Template Creation:**
    * HTML is used to create visually rich and structured email newsletters or marketing email templates that maintain compatibility across various email clients (e.g., Outlook, Gmail).
* **E-book and Digital Document Formats:**
    * E-book formats like EPUB internally use HTML and CSS to structure content, including text, images, and layout. This enables efficient distribution of digital documents based on web standards.

HTML is the core language of the web, serving as the most fundamental and essential underlying technology for building all types of web-based content and applications.

---

# ✨ HTML: 기본 개념과 활용

## 1. HTML이란 무엇인가? (소개) 💡

**HTML (HyperText Markup Language)**은 웹 페이지를 만들 때 사용하는 **마크업 언어**입니다. 웹 브라우저가 웹 콘텐츠를 어떻게 구조화하고 표시해야 하는지를 정의하죠. 마치 건물을 지을 때 **뼈대와 구조**를 세우는 것과 같습니다. 텍스트, 이미지, 링크, 버튼, 입력 폼, 동영상 등 우리가 웹 페이지에서 보는 모든 요소의 **논리적인 구조와 의미**를 담당합니다.

HTML은 프로그래밍 언어처럼 복잡한 계산이나 동적인 기능을 직접 수행하지는 않습니다. 대신, 웹 콘텐츠의 **기본적인 틀과 의미론적인 정보**를 제공합니다. 이 틀 위에 **CSS**로 시각적인 디자인을 입히고, **JavaScript**로 상호작용적인 기능을 추가하여 완전한 웹 페이지를 완성하게 됩니다. HTML은 이 모든 웹 개발의 가장 기초이자 필수적인 구성 요소입니다.

**HTML의 주요 특징:**

* **마크업 언어:** 데이터를 표시하고 설명하기 위해 `<태그>`와 같은 미리 정의된 기호(태그)를 사용합니다. 이 태그들이 콘텐츠의 종류와 역할을 브라우저에 알려줍니다.
* **웹 페이지의 구조 정의:** 웹 콘텐츠(텍스트 단락, 제목, 목록, 이미지, 테이블 등)를 의미 있고 계층적으로 조직하여, 콘텐츠의 관계와 흐름을 명확하게 합니다.
* **태그 기반:** `<p>`, `<h1>`, `<img>`, `<a>` 등 다양한 태그를 사용하여 각 요소의 역할과 의미를 나타냅니다. 대부분의 태그는 시작 태그와 종료 태그로 구성됩니다.
* **하이퍼링크:** `<a>` (앵커) 태그를 통해 다른 웹 페이지나 문서의 특정 부분, 또는 외부 리소스로 연결되는 **하이퍼링크**를 생성합니다. 이는 웹의 핵심 기능인 정보 간의 연결성을 구현합니다.
* **플랫폼 독립적:** 특별한 소프트웨어나 컴파일 과정 없이 일반 텍스트 편집기(예: Visual Studio Code, Sublime Text)로 작성할 수 있으며, 모든 주요 웹 브라우저(Chrome, Firefox, Safari, Edge 등)에서 웹 표준에 따라 동일하게 해석되고 표시됩니다.

## 2. HTML의 기본 문법 📝

HTML 문서는 태그와 속성을 사용하여 작성됩니다. 대부분의 HTML 태그는 시작 태그(`<html>`)와 종료 태그(`</html>`)로 이루어지며, 그 사이에 콘텐츠가 들어갑니다. 일부 태그는 내용이 없거나 단독으로 사용됩니다(예: `<br>`, `<img>`).

* **기본 문서 구조:** 모든 HTML 문서는 웹 브라우저가 올바르게 해석하고 렌더링할 수 있도록 다음과 같은 표준 구조를 가집니다.

    ```html
    <!DOCTYPE html>  <html lang="ko"> <head>           <meta charset="UTF-8"> <meta name="viewport" content="width=device-width, initial-scale=1.0"> <title>문서 제목</title> <link rel="stylesheet" href="style.css"> </head>
    <body>           <h1>안녕하세요!</h1>
        <p>이것은 첫 번째 문단입니다.</p>
        <script src="script.js"></script> </body>
    </html>
    ```

* **주요 태그와 속성:**

    * **제목 태그 (`<h1>` ~ `<h6>`):** 문서의 제목이나 소제목을 정의합니다. `<h1>`이 가장 중요한 최상위 제목이며, `<h6>`으로 갈수록 중요도가 낮아집니다.
        ```html
        <h1>가장 큰 제목</h1>
        <h2>두 번째 큰 제목</h2>
        <h3>세 번째 중요 제목</h3>
        ```

    * **문단 태그 (`<p>`):** 일반적인 텍스트 문단을 정의합니다. 브라우저는 `<p>` 태그 전후로 자동으로 여백을 추가합니다.
        ```html
        <p>이것은 웹 페이지의 한 문단입니다. 여러 줄의 텍스트를 포함할 수 있습니다.</p>
        <p>새로운 문단은 항상 새로운 줄에서 시작됩니다.</p>
        ```

    * **링크 태그 (`<a>`):** 다른 웹 페이지나 문서, 또는 문서의 특정 부분으로 연결되는 **하이퍼링크**를 만듭니다. `href` (Hypertext REFerence) 속성으로 연결할 대상의 URL(주소)을 지정합니다.
        ```html
        <a href="[https://www.google.com](https://www.google.com)" target="_blank">Google로 이동 (새 탭)</a>
        <a href="#section2">페이지 내 다른 섹션으로 이동</a>
        ```

    * **이미지 태그 (`<img>`):** 웹 페이지에 이미지를 삽입합니다. 단독 태그로 종료 태그가 없습니다.
        * `src` (Source) 속성: 이미지 파일의 경로(URL)를 지정합니다.
        * `alt` (Alternative text) 속성: 이미지를 표시할 수 없을 때(경로 오류, 이미지 로드 실패 등) 대신 표시될 텍스트나 시각 장애인용 스크린 리더가 읽어줄 텍스트를 지정합니다. **웹 접근성을 위해 필수로 사용해야 합니다.**
        ```html
        <img src="flower.jpg" alt="활짝 핀 아름다운 꽃">
        <img src="[https://example.com/logo.png](https://example.com/logo.png)" alt="회사 로고">
        ```

    * **목록 태그 (`<ul>`, `<ol>`, `<li>`):** 정보를 구조화된 목록 형태로 표현할 때 사용됩니다.
        * `<ul>`: **순서 없는 목록 (Unordered List)**을 나타내며, 각 항목 앞에 기호(점, 원 등)가 붙습니다.
        * `<ol>`: **순서 있는 목록 (Ordered List)**을 나타내며, 각 항목 앞에 숫자나 문자가 순서대로 붙습니다.
        * `<li>`: 목록의 **각 항목 (List Item)**을 정의합니다. `<ul>` 또는 `<ol>` 태그의 자식으로 사용됩니다.
        ```html
        <h3>좋아하는 과일</h3>
        <ul>
            <li>사과</li>
            <li>바나나</li>
            <li>체리</li>
        </ul>

        <h3>순위</h3>
        <ol>
            <li>금메달</li>
            <li>은메달</li>
            <li>동메달</li>
        </ol>
        ```

    * **컨테이너 태그 (`<div>`, `<span>`):** 특별한 의미 없이 다른 HTML 요소들을 그룹화하여 레이아웃이나 스타일에 영향을 주기 위해 사용되는 일반적인 컨테이너 태그입니다.
        * `<div>`: **블록 레벨 요소**입니다. 내용의 앞뒤로 줄 바꿈이 일어나며, 주로 웹 페이지의 큰 구역이나 레이아웃을 나눌 때 사용됩니다.
        * `<span>`: **인라인 레벨 요소**입니다. 내용의 흐름을 방해하지 않고 텍스트의 특정 부분에 스타일을 적용하거나 JavaScript로 제어할 때 사용됩니다.
        ```html
        <div class="header-section">
            <p>이것은 헤더 섹션에 속한 문단입니다.</p>
            <span>이 부분은 강조될 텍스트입니다.</span>
        </div>
        ```

    * **폼 태그 (`<form>`, `<input>`, `<textarea>`, `<button>`, `<label>` 등):** 사용자로부터 데이터를 입력받거나 상호작용하기 위한 요소를 정의합니다.
        ```html
        <form action="/submit-form" method="post">
            <label for="username">사용자 이름:</label>
            <input type="text" id="username" name="username" placeholder="이름을 입력하세요">
            <br>
            <label for="message">메시지:</label>
            <textarea id="message" name="message" rows="4" cols="50"></textarea>
            <br>
            <button type="submit">정보 제출</button>
        </form>
        ```

* **속성 (Attributes):** 태그에 추가적인 정보나 동작을 정의하기 위해 사용됩니다. 시작 태그 내에 `속성="값"` 형태로 작성됩니다.
    * `id`: 문서 내에서 요소를 **고유하게 식별**하는 이름입니다. 웹 페이지 내에서 단 하나만 존재해야 하며, CSS에서 특정 요소에 고유한 스타일을 적용하거나 JavaScript로 해당 요소를 정밀하게 제어할 때 주로 사용됩니다.
    * `class`: 여러 요소에 동일한 스타일을 적용하거나 **JavaScript로 특정 요소 그룹을 제어**할 때 사용됩니다. 하나의 요소에 여러 클래스를 적용할 수 있습니다.
    * `style`: 요소에 직접 인라인 스타일을 적용할 때 사용합니다. 간단한 스타일링에는 편리하지만, 코드의 가독성과 유지보수성을 위해 **외부 CSS 사용이 권장**됩니다.

## 3. HTML은 어디에 사용되나요? (주요 활용 분야) 🌐

HTML은 웹의 근간을 이루는 언어로서, 거의 모든 디지털 콘텐츠가 웹 브라우저를 통해 표시되는 데 사용됩니다. 그 활용 분야는 매우 광범위하며, 현대 웹 환경에서 없어서는 안 될 핵심 기술입니다.

* **웹 페이지 콘텐츠 구조화 및 표시:**
    * 가장 기본적인 용도로, 웹사이트의 모든 텍스트, 이미지, 비디오, 오디오 등의 콘텐츠를 **논리적인 구조**로 배열하고 브라우저에 표시합니다. 블로그 게시글, 뉴스 기사, 제품 상세 페이지, 회사 소개 페이지 등 모든 유형의 정보성 웹사이트의 기본 틀을 제공합니다.
* **웹 애플리케이션 프론트엔드 구축:**
    * 사용자가 직접 보고 상호작용하는 모든 웹 애플리케이션의 **사용자 인터페이스(UI)**를 구성합니다. 복잡한 대시보드, 온라인 쇼핑몰(예: **WooCommerce**), 소셜 미디어 플랫폼, 온라인 게임 등 동적이고 상호작용적인 웹 서비스의 시각적인 구성 요소가 됩니다.
* **사용자 입력 폼 및 상호작용:**
    * 회원가입, 로그인, 검색, 문의하기, 주문 등 사용자로부터 정보를 입력받고 피드백을 제공하기 위한 다양한 **폼 요소**(`input`, `textarea`, `select`, `button` 등)를 만듭니다. 이를 통해 사용자와 웹 페이지 간의 상호작용을 가능하게 합니다.
* **SEO (검색 엔진 최적화):**
    * HTML5에서 도입된 **시맨틱 HTML 태그**(`header`, `nav`, `main`, `article`, `section`, `aside`, `footer` 등)를 사용하여 콘텐츠의 의미를 명확하게 전달합니다. 이는 Google과 같은 검색 엔진이 웹 페이지의 내용을 더 정확하게 이해하고 색인하는 데 도움을 주어 검색 결과 순위에 긍정적인 영향을 미칩니다.
* **웹 접근성 (Web Accessibility) 향상:**
    * 모든 사용자가 웹 콘텐츠에 동등하게 접근하고 이용할 수 있도록 하는 것을 목표로 합니다. `alt` 속성으로 이미지에 대한 설명을 제공하거나, 논리적인 헤딩 구조를 사용하고, ARIA(Accessible Rich Internet Applications) 속성을 활용하는 등 HTML의 올바른 사용은 시각 장애인용 스크린 리더와 같은 보조 기술이 웹 콘텐츠를 모든 사용자에게 효과적으로 전달하는 데 필수적입니다.
* **이메일 템플릿 제작:**
    * 다양한 이메일 클라이언트(Outlook, Gmail 등)에서 호환성을 유지하며 시각적으로 풍부하고 구조화된 이메일 뉴스레터나 마케팅 이메일 템플릿을 만드는 데 HTML이 사용됩니다.
* **전자책 및 디지털 문서 형식:**
    * EPUB과 같은 전자책 형식은 내부적으로 HTML과 CSS를 사용하여 텍스트, 이미지, 레이아웃 등 콘텐츠를 구성합니다. 이는 웹 표준을 기반으로 한 디지털 문서의 효율적인 배포를 가능하게 합니다.

HTML은 웹의 핵심 언어로서, 모든 종류의 웹 기반 콘텐츠 및 애플리케이션을 구축하는 데 없어서는 안 될 가장 기본적이고 필수적인 기반 기술입니다.

