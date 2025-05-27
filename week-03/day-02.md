# 📅 Day 02 (2025-05-27, Tue)

## 🎓 What I Did Today

**📌 Attended the 9 AM Daily Development Meeting.**  
**📌 Understood and practically applied the CSS-first approach for WooCommerce page design customization.**  
**📌 Explored how to use the `Simple Custom CSS and JS` plugin and gained experience in styling key WooCommerce pages with CSS.**  
**📌 Gained an initial understanding of JavaScript's role and PHP hooks for future learning.**  

### Detailed Activities

* **Attended the 9 AM Daily Development Meeting:**
    * During today's meeting, I received advice to **prioritize CSS for design customization before attempting PHP template overrides.** I understood that this is a practical approach for safely and quickly modifying designs without risking the site's structure or functionality.

* **WooCommerce CSS Customization Practical Learning & Application:**
    * Following the development meeting's advice, I focused on hands-on CSS customization.
    * **Utilized the `Simple Custom CSS and JS` plugin:** I used this plugin to directly add and manage custom CSS code within the WordPress admin dashboard, confirming immediate application of the code. I experienced the benefit of maintaining changes during updates by not directly modifying original theme or plugin files.
    * **Leveraged Chrome Developer Tools (F12)**: I actively used the developer tools to find precise CSS selectors (class names, IDs) for various elements on WooCommerce pages. I realized this is an essential process for accurately targeting desired elements within the complex WooCommerce DOM structure.

    * **Key WooCommerce Page CSS Styling Experience (Core Examples):**
        * **My Account Page:** Adjusted bullets, spacing, row dividers, backgrounds, and `hover` effects for navigation (sidebar) to improve visibility. Standardized the overall box style (size, padding, shadow) for login/registration forms, and unified the design of input fields and buttons (border-radius, padding, background, font-size). Applied `border` and `box-shadow` for visual separation of Billing/Shipping address boxes, and considered responsive design using `@media` queries for mobile readability.
        * **Cart/Checkout Pages:** Applied consistent colors, font weights, and border-radii to WooCommerce block-based buttons (`wc-block-components-button`) and general buttons (`woocommerce-button`) using `!important`.
        * **Single Product Page:** Applied styles to `th` and `tr` of the Attributes (Additional Information) table. Crucially, I learned that to style the actual attribute values, I had to use developer tools to find and target specific class names like `.woocommerce-product-attributes-item__value`.

* **Initial Understanding of JavaScript's Role and PHP Hooks for Future Learning:**
    * I recognized that the `Simple Custom CSS and JS` plugin also supports JavaScript, and gained a brief understanding of JavaScript's role in WooCommerce for future learning. I understood that JavaScript is used for dynamic UI, event handling, and especially AJAX for asynchronous communication.
    * Furthermore, I grasped the **concept of WordPress and WooCommerce PHP Hooks (Actions and Filters)**, which were recommended as the next step after CSS customization. I understood that PHP hooks are essential for manipulating and extending core WooCommerce functionalities (e.g., price calculation, payment logic, order processing) beyond design. I will explore how these are implemented using `add_action()` and `add_filter()` functions via the `functions.php` file.

### 🧠 Key Concepts Learned

* **'CSS-First' Principle for WooCommerce Customization**: I realized that most design and layout changes can be handled safely and efficiently with CSS, and PHP template overrides should only be used carefully when structural changes are necessary.
* **Importance of Chrome Developer Tools**: I mastered the essential use of developer tools to accurately find CSS selectors for specific elements in complex systems like WooCommerce.
* **Initial Grasp of JavaScript's Role**: I understood that JavaScript plays a key role in client-side interaction in the WooCommerce environment, handling dynamic UI, event handling, and especially asynchronous communication via AJAX, which I **plan to explore further.**
* **Initial Grasp of PHP Hook Concepts**: I recognized that in-depth learning of PHP hooks is essential for extending WooCommerce logic and backend functionalities that cannot be resolved with CSS and JavaScript, and that this is a **key area for future study.**

### 💡 Practical Trial & Error and Tips

* **Accurate CSS Selector Targeting**: General tag selectors like `td`, `th`, `tr` **often may not apply desired styles**, which is why it's crucial to use developer tools to find and precisely target actual class names such as `wc-block-components-button` or `woocommerce-product-attributes-item__value`.
* **Understanding `!important` Usage**: I learned that `!important` is used to forcibly override existing stronger styles, but its overuse should be avoided.
* **Importance of Comments**: Adding detailed comments to complex customization code greatly aids in maintenance by making the intent clear, **especially when CSS familiarity is low or when managing code as a non-designer.**

### 🔜 Future Study Direction

* **In-depth PHP Hooks Learning**: I will learn how to use WordPress and WooCommerce Action/Filter hooks and practice extending WooCommerce functionalities using the `functions.php` file (e.g., exploring how to add/modify functions).
* **In-depth JavaScript Role Learning**: I will learn how JavaScript actually implements dynamic UI, event handling, and AJAX in the WooCommerce environment through specific code examples.
* **Deepening WooCommerce Core Concepts**: In preparation for functional requirements difficult to resolve with CSS, I will continue to deeply study and apply advanced WooCommerce settings such as Shipping Zones, Shipping Classes, and Tax Rates, practicing their application in real scenarios.
* **Developer Tools Mastery & Pattern Recognition**: I will further master the habit of using developer tools on various WooCommerce pages to understand HTML structures and CSS selectors. I will start organizing frequently used WooCommerce element names and CSS patterns to build my own snippet library.
* **Documenting Failures and Attempts**: I will maintain the habit of recording attempted methods and failed codes with comments during problem-solving, utilizing trial and error itself as valuable learning material.

* ---

* # 📅 Day 02 (2025-05-27, 화)

## 🎓 오늘 한 일

**📌 오전 9시 일일 개발 미팅 참석.**  
**📌 WooCommerce 페이지 디자인 커스터마이징을 위한 CSS 우선 접근 방식 이해 및 실전 적용.**  
**📌 `Simple Custom CSS and JS` 플러그인 활용법 및 주요 WooCommerce 페이지별 CSS 스타일링 경험.**  
**📌 향후 학습을 위한 JavaScript의 역할과 PHP 훅의 개념 파악.**  

### 상세 활동

* **오전 9시 일일 개발 미팅 참석:**
    * 오늘 미팅에서는 **PHP 템플릿 오버라이드에 앞서 CSS를 통한 디자인 커스터마이징을 우선적으로 시도**하라는 조언을 받았습니다. 웹사이트 구조나 기능을 손상시킬 위험 없이 디자인을 빠르고 안전하게 변경하는 실무적인 접근 방식임을 이해했습니다.

* **WooCommerce CSS 커스터마이징 실전 학습 및 적용:**
    * 개발 미팅 조언에 따라 CSS 커스터마이징에 집중하여 실습했습니다.
    * **`Simple Custom CSS and JS` 플러그인 활용:** 이 플러그인을 사용하여 워드프레스 관리자 페이지에서 커스텀 CSS 코드를 직접 추가하고 관리하며, 코드의 즉각적인 적용을 확인했습니다. 원본 테마나 플러그인 파일을 직접 수정하지 않아 업데이트 시에도 변경 사항이 유지되는 장점을 체험했습니다.
    * **크롬 개발자 도구 (F12) 활용**: 우커머스 페이지의 각 요소에 대한 정확한 CSS 선택자(클래스명, ID)를 찾아내기 위해 개발자 도구를 적극적으로 활용했습니다. 이는 복잡한 우커머스 DOM 구조 내에서 원하는 요소를 정확히 타겟팅하는 데 필수적인 과정임을 깨달았습니다.

    * **주요 WooCommerce 페이지별 CSS 스타일링 경험 (핵심 예시):**
        * **마이 어카운트 페이지:** 네비게이션(사이드바)의 불릿, 여백, 행 구분선, 배경 및 `hover` 효과 등을 조절했습니다. 로그인/회원가입 폼의 전체적인 박스 스타일(크기, 여백, 그림자) 및 입력 필드와 버튼의 디자인을 통일했습니다. Billing/Shipping 주소 박스에는 `border`와 `box-shadow`로 시각적 구분을 주었으며, `@media` 쿼리로 모바일 반응형 디자인도 고려했습니다.
        * **장바구니/결제 페이지:** WooCommerce 블록 기반 버튼(`wc-block-components-button`)과 일반 버튼(`woocommerce-button`)에 `!important`를 사용하여 색상, 폰트 굵기, 모서리 둥글기를 일관되게 적용했습니다.
        * **단일 상품 페이지:** 어트리뷰트(추가 정보) 표의 `th`와 `tr`에 스타일을 적용했으며, 특히 실제 속성 값에 스타일을 적용하기 위해 `.woocommerce-product-attributes-item__value`와 같은 특정 클래스명을 개발자 도구로 찾아 타겟팅해야 했습니다.

* **향후 학습을 위한 JavaScript의 역할 및 PHP 훅의 개념 파악:**
    * `Simple Custom CSS and JS` 플러그인이 JavaScript도 지원한다는 점을 인지하고, 앞으로 학습할 JavaScript의 WooCommerce 내 역할에 대해 간략히 파악했습니다. JavaScript는 동적 UI, 이벤트 핸들링, 그리고 특히 AJAX를 통한 비동기 통신에 활용됨을 이해했습니다.
    * 또한, CSS 커스터마이징 이후 다음 단계로 권장된 **워드프레스 및 우커머스 PHP 훅(Action 및 Filter)의 개념을 파악**했습니다. PHP 훅은 디자인을 넘어 우커머스의 핵심 기능(가격 계산, 결제 로직, 주문 처리 등)을 조작하고 확장하는 데 필수적임을 이해했습니다. 이는 `functions.php` 파일을 통해 `add_action()` 및 `add_filter()` 함수를 사용하여 구현됨을 알아볼 예정입니다.

### 🧠 배운 핵심 개념

* **WooCommerce 커스터마이징의 'CSS 우선' 원칙**: 대부분의 디자인 및 레이아웃 변경은 CSS로 안전하고 효율적으로 처리할 수 있으며, PHP 템플릿 오버라이드는 구조적 변경이 필요한 경우에만 신중하게 사용해야 함을 체득했습니다.
* **크롬 개발자 도구 활용의 중요성**: 우커머스와 같은 복잡한 시스템에서 특정 요소의 정확한 CSS 선택자를 찾아내기 위한 개발자 도구의 필수적인 활용법을 숙달했습니다.
* **JavaScript의 역할에 대한 첫 파악**: 우커머스 환경에서 JavaScript가 동적 UI, 이벤트 핸들링, 그리고 특히 AJAX를 통한 비동기 통신을 담당하며, 클라이언트 측 상호작용의 핵심임을 **앞으로 더 알아볼 예정**입니다.
* **PHP 훅 개념에 대한 첫 파악**: CSS와 JavaScript로 해결하기 어려운 우커머스 로직 및 백엔드 기능 확장을 위해서는 PHP 훅에 대한 깊이 있는 학습이 필수적임을 인지하고, **향후 학습할 주요 영역**임을 파악했습니다.

### 💡 실전 시행착오 및 팁

* **정확한 CSS 선택자 타겟팅**: `td`, `th`, `tr`과 같은 일반 태그 선택자만으로는 원하는 스타일이 **적용되지 않을 경우도 많으며**, 이 때문에 개발자 도구를 통해 `wc-block-components-button`, `woocommerce-product-attributes-item__value`와 같은 실제 클래스명을 찾아 정확히 타겟팅하는 것이 중요합니다.
* **`!important` 사용의 이해**: 기존의 더 강한 스타일을 강제로 덮어쓸 때 `!important`를 사용하지만, 남용은 지양해야 함을 인지했습니다.
* **주석의 중요성**: 복잡한 커스터마이징 코드에 주석을 상세하게 달아두면, **CSS에 대한 친숙도가 낮거나 비디자이너가 코드를 관리할 때** 어떤 의도로 작성되었는지 파악하기 쉬워 유지보수에 큰 도움이 됩니다.

### 🔜 이후 학습 방향

* **PHP 훅 심화 학습**: 워드프레스 및 우커머스의 Action/Filter 훅 사용법을 익히고, `functions.php` 파일을 활용하여 우커머스 기능 확장을 실습합니다. (예: 함수 추가/수정 방안 탐색)
* **JavaScript 역할 심화 학습**: 우커머스 환경에서 JavaScript가 실제 어떻게 동적 UI와 이벤트 핸들링, AJAX를 구현하는지 구체적인 코드 예시를 통해 학습합니다.
* **우커머스 핵심 개념 심화**: CSS로 해결하기 어려운 기능적 요구사항에 대비하여, WooCommerce Shipping Zone, Shipping Class, Tax Rate 등 핵심 설정들을 심층적으로 학습하고 실제 시나리오에 적용하는 연습을 지속합니다.
* **개발자 도구 숙달 및 패턴화**: 다양한 우커머스 페이지에서 개발자 도구를 활용하여 HTML 구조와 CSS 선택자를 파악하는 습관을 더욱 숙달하고, 자주 사용되는 우커머스 요소 이름 및 CSS 패턴을 정리하여 나만의 스니펫 라이브러리를 구축하기 시작합니다.
* **실패 및 시도 기록**: 문제 해결 과정에서 시도했던 방법과 실패했던 코드들도 주석과 함께 기록하여, 시행착오 자체를 귀중한 학습 자료로 활용하는 습관을 유지합니다.
