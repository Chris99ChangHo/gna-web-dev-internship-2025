# 📅 Day 01 (2025-06-02, Mon)

## 🎓 Today's Work

**📌 Summary of Practical Usage of WordPress Core Hooks and Hooks for Plugin Development.**  
**📌 Practical Exercise and Summary of Hooks Utilized in WordPress `functions.php`.**  
**📌 In-depth Comparative Analysis Report on Major Social Media Automation and Design Tools.**  
**📌 Identification and Resolution Summary of Sidebar Display Issue Encountered During `functions.php` Code Practice.**  

### Detailed Activities

Summary of Practical Usage of WordPress Core Hooks and Hooks for Plugin Development I summarized the **five most important Action and Filter Hooks** frequently used in WordPress theme and plugin development.

-   **wp_head (Action)**: Used to add scripts, stylesheets, and meta tags (e.g., Google Analytics, SEO tags) within the `<head>` section of the website. This is essential for website performance monitoring and marketing campaign tracking.
-   **wp_footer (Action)**: Used to add JavaScript code, analytics scripts, and custom messages just before the `</body>` tag of the website. This is also crucial for website performance monitoring and marketing campaign tracking.
-   **init (Action)**: This hook executes during WordPress initialization. It's essential for registering custom post types, taxonomies, enabling custom functionalities, and initializing global variables, fundamentally extending or modifying WordPress's core structure.
-   **wp_enqueue_scripts (Action)**: Used to safely and correctly register and load necessary stylesheets (CSS) and scripts (JavaScript) on the frontend. This is the standard method for preventing conflicts and optimizing performance during theme or plugin development.
-   **the_content (Filter)**: Used to modify the post content just before it's retrieved from the database and displayed on the screen. It's useful for content marketing and automation, such as automatically inserting ads or adding related article links to all blog post bodies.

Practical Exercise and Summary of Hooks Utilized in WordPress functions.php I directly applied and summarized the roles and usage of various Action and Filter Hooks within the `functions.php` file of a WordPress child theme.

-   **Adding Child Theme Styles/Scripts**: Practiced correctly loading child theme CSS and JS files using the `wp_enqueue_scripts` hook. Considerations for jQuery dependency and footer loading options were made for stability and performance.
-   **Adding a Debug Function (`pprint_r`)**: Implemented a debugging function `pprint_r` to display variable/array contents in a readable format during development. This was improved to prevent unnecessary debug output during AJAX requests.
-   **Adding Body Classes Based on Login Status**: Applied a filter hook to dynamically add `logged-in-condition` or `logged-out-condition` classes to the HTML `<body>` tag based on user login status, enabling CSS styling for different login states.
-   **Adding Footer Messages**: Added code to display a custom copyright message in the website's footer area using the `wp_footer` action hook.
-   **Adding Messages to Content/Posts/Titles (Various Filters)**: Used the `the_content` filter to add a thank-you message at the end of post bodies and the `the_title` filter to insert an emoji before single post titles. Also added custom welcome/notice messages to My Account pages and login forms using WooCommerce-related hooks.
-   **Priority Exercise Example**: Confirmed that the execution order of functions hooked to `wp_head` is controlled by the `priority` argument in `add_action`.
-   **Registering a Sidebar**: Registered a new widget area named `Custom Sidebar` in WordPress using the `widgets_init` action hook.

In-depth Comparative Analysis Report on Major Social Media Automation and Design Tools Based on research using four AI models (Deepseek, Gemini, Claude, GPT), I wrote an in-depth comparative analysis report on seven major social media automation and design tools (Canva, Buffer, Hootsuite, Later, HubSpot, Meta Business Suite, Jasper.ai). The report included each tool's feature set, pricing, differentiating factors, practical utility, basic usage, and real-world application cases. A tool selection guide was provided to help users choose the optimal tool combination based on budget, business size, and social media strategy.

Identification and Resolution Summary of Sidebar Display Issue Encountered During functions.php Code Practice Although the sidebar was successfully registered in `functions.php` using the `register_sidebar` function, it didn't appear on the website's frontend. I confirmed that simply registering a sidebar doesn't make it appear; the `dynamic_sidebar()` function must be called in the theme template files. As it didn't align with the current layout design, the sidebar was intentionally registered but not displayed on the frontend, allowing for flexibility in future layout changes.

## 🧠 Key Concepts Learned

Fundamental Understanding of WordPress Hooks: I understood the clear distinction between Action Hooks (executing code) and Filter Hooks (modifying and returning data). Importance of functions.php: Reconfirmed its role as a core file for extending and customizing WordPress theme functionalities. Standard Method for Script/Style Loading: Gained proficiency in using the `wp_enqueue_scripts` hook for safely and efficiently loading CSS and JS files. Efficiency of Debugging: Experienced how custom debug functions (`pprint_r`) can significantly reduce problem-solving time during development. AI-Based Tool Analysis and Strategy: Enhanced my ability to collect information using multiple AI models, analyze tool characteristics, and derive insights for practical application in social media strategies.

## 💡 Practical Trial-and-Error and Tips

Importance of Hook Priority: Confirmed through practice that controlling the execution order of functions hooked to the same hook via the `priority` argument in `add_action` and `add_filter` is crucial. Understanding Sidebar Display Conditions: Realized that simply registering a sidebar is not enough; calling `dynamic_sidebar()` in theme templates is essential for its display. Systematizing AI Tool Analysis: Learned the importance of a systematic approach to comparing various social media tools and selecting them based on business objectives.

## 🔜 Next Steps

WordPress REST API Basics: I plan to learn about the concepts, endpoint structure, and authentication methods of the REST API, which is essential for utilizing WordPress data externally or fetching external data. Social Media Automation Tool Research Deep Dive: I will deepen my research for the social media automation tool assignment due next Wednesday to enhance the report's completeness.

## 📚 References

-   [WP_Hooks Official Documentation](https://developer.wordpress.org/reference/hooks/)
-   [WC_User_Hooks Official Documentation](https://woocommerce.com/document/actions-and-filters/)

---

# 📅 Day 01 (2025-06-02, 월)

## 🎓 오늘 한 일

**📌 워드프레스 핵심 훅 (Core Hooks) 실무 활용 및 플러그인 개발 활용 훅 정리.**  
**📌 워드프레스 functions.php 활용 훅 실습 및 정리.**  
**📌 주요 소셜 미디어 자동 게시 및 디자인 툴 심층 비교 분석 보고서 작성.**  
**📌 functions.php 코드 실습 중 발생한 사이드바 미표시 문제 확인 및 결과 정리.**  

### 상세 활동

워드프레스 핵심 훅 (Core Hooks) 실무 활용 및 플러그인 개발 활용 훅 정리 워드프레스 테마 및 플러그인 개발에서 자주 사용되는 핵심 액션(Action) 및 필터(Filter) 훅 중 **가장 중요한 5가지**를 정리했습니다.

-   **wp_head (액션)**: 웹사이트 `<head>` 태그 내에 스크립트, 스타일시트, 메타태그(예: Google Analytics, SEO 태그) 등을 추가할 때 사용됩니다. 웹사이트 성능 모니터링, 마케팅 캠페인 추적에 필수적입니다.
-   **wp_footer (액션)**: 웹사이트 `</body>` 태그 직전에 자바스크립트 코드, 분석 스크립트, 커스텀 메시지 등을 추가할 때 사용됩니다. 웹사이트 성능 모니터링, 마케팅 캠페인 추적에 필수적입니다.
-   **init (액션)**: 워드프레스 초기화 시점에 실행되는 훅입니다. 사용자 정의 포스트 타입, 택소노미 등록, 사용자 정의 기능 활성화, 전역 변수 초기화 등 워드프레스의 핵심 구조를 변경하거나 확장할 때 반드시 사용됩니다.
-   **wp_enqueue_scripts (액션)**: 프론트엔드에 필요한 스타일시트(CSS) 및 스크립트(JavaScript)를 안전하고 올바른 방식으로 등록하고 불러올 때 사용됩니다. 테마나 플러그인 개발 시 충돌을 방지하고 성능을 최적화하는 표준적인 방법입니다.
-   **the_content (필터)**: 글 본문 내용이 데이터베이스에서 불러와져 화면에 출력되기 직전, 본문 내용을 수정할 때 사용됩니다. 모든 블로그 게시물 본문에 자동으로 광고를 삽입하거나, 관련 글 링크를 추가하는 등 콘텐츠 마케팅 및 자동화에 유용합니다.

워드프레스 functions.php 활용 훅 실습 및 정리 워드프레스 자식 테마의 functions.php 파일에 다양한 액션 및 필터 훅을 활용한 코드를 직접 적용하고 그 역할과 사용법을 정리했습니다.

-   **자식 테마 스타일/스크립트 추가**: `wp_enqueue_scripts` 훅을 사용하여 자식 테마의 CSS와 JS 파일을 올바르게 로드하는 방법을 실습했습니다. jQuery 의존성 및 푸터 로딩 옵션을 설정하여 안정성과 성능을 고려했습니다.
-   **디버그 함수 (pprint_r) 추가**: 개발 중 변수/배열 내용을 가독성 높게 출력하는 디버깅 함수를 구현했으며, AJAX 요청 시 불필요한 출력을 방지하도록 개선했습니다.
-   **로그인 상태에 따른 body 클래스 추가**: 사용자의 로그인 상태에 따라 `body` 태그에 클래스를 동적으로 추가하는 필터 훅을 적용했습니다.
-   **푸터 메시지 추가**: `wp_footer` 액션 훅을 사용하여 웹사이트 푸터에 커스텀 저작권 메시지를 출력하는 코드를 추가했습니다.
-   **콘텐츠/포스트/타이틀에 메시지 추가 (다양한 필터 활용)**: `the_content` 필터로 포스트 본문 끝에 메시지를 추가하고, `the_title` 필터로 단일 포스트 제목 앞에 이모지를 삽입했습니다. 또한 WooCommerce 관련 훅으로 마이페이지 및 로그인 폼에 커스텀 메시지를 추가했습니다.
-   **우선순위 실습 예제**: `wp_head` 훅에 두 개의 메시지 출력 함수를 연결하여, `add_action`의 우선순위 값을 통해 함수 실행 순서가 제어됨을 확인했습니다.
-   **사이드바 등록**: `widgets_init` 액션 훅을 사용하여 새로운 위젯 영역을 워드프레스에 등록했습니다.

주요 소셜 미디어 자동 게시 및 디자인 툴 심층 비교 분석 보고서 작성 Deepseek, Gemini, Claude, GPT 네 가지 AI 모델을 활용한 소셜 미디어 툴 조사 결과를 바탕으로 총 7가지 주요 자동화 툴(Canva, Buffer, Hootsuite, Later, HubSpot, Meta Business Suite, Jasper.ai)을 심층 비교 분석한 보고서를 작성했습니다. 각 툴의 기능 범위, 가격, 차별점, 실무 활용도, 사용법 및 적용 사례를 포함했습니다. 툴 선택 가이드를 통해 예산, 비즈니스 규모, 전략에 따른 최적의 툴 조합을 제안했습니다.

functions.php 코드 실습 중 발생한 사이드바 미표시 문제 확인 및 결과 정리 functions.php에서 register_sidebar 함수로 사이드바를 성공적으로 등록했으나, 웹사이트 프론트엔드에 표시되지 않는 문제가 발생했습니다. 사이드바는 등록만으로는 화면에 나타나지 않으며, 테마 템플릿 파일에서 dynamic_sidebar() 함수를 호출해야 함을 확인했습니다. 현재 레이아웃 디자인 방향과 맞지 않아, 사이드바는 워드프레스에 등록만 하고 실제 화면에는 출력되지 않도록 의도적으로 처리했습니다. 이는 향후 레이아웃 변경 시 유연성을 확보하기 위함입니다.

## 🧠 배운 핵심 개념

워드프레스 훅(Hooks)의 근본적인 이해: 액션 훅은 코드 실행, 필터 훅은 데이터 수정 및 반환이라는 명확한 차이를 이해했습니다. functions.php의 중요성: 워드프레스 테마 기능 확장 및 커스터마이징의 핵심 파일임을 재확인했습니다. 스크립트/스타일 로딩의 표준 방식: wp_enqueue_scripts 훅을 통한 안전하고 효율적인 파일 로딩 방법을 숙지했습니다. 디버깅의 효율성: 커스텀 디버그 함수(pprint_r)를 통해 개발 과정의 문제 해결 시간을 단축시키는 방법을 체감했습니다. AI 기반 툴의 분석 및 활용 전략: 여러 AI 모델을 활용한 정보 수집, 툴별 특성 분석, 그리고 실무 적용을 위한 인사이트 도출 능력을 향상시켰습니다.

## 💡 실전 시행착오 및 팁

훅 사용 시 우선순위의 중요성: add_action 및 add_filter 함수의 우선순위 인자를 통해 함수 실행 순서를 제어하는 것이 중요함을 실습으로 확인했습니다. 사이드바 표시 조건의 이해: 사이드바는 등록만으로는 표시되지 않으며, dynamic_sidebar() 호출이 필수적임을 깨달았습니다. AI 툴 분석의 체계화: 다양한 소셜 미디어 툴들의 기능을 비교하고 비즈니스 목적에 맞게 선택하는 체계적인 접근법을 익혔습니다.

## 🔜 이후 학습 방향

WordPress REST API 기초 학습: 워드프레스 데이터를 외부에서 활용하거나 외부 데이터를 가져오는 데 필수적인 REST API의 개념, 엔드포인트 구조, 인증 방식 등에 대해 학습할 예정입니다. 소셜 미디어 자동화 툴 리서치 심화: 다음 주 수요일까지 제출해야 하는 소셜 미디어 자동화 툴 리서치 과제를 심화하여 보고서 완성도를 높입니다.

## 📚 참고자료

-   [WP_Hooks 공식 문서](https://developer.wordpress.org/reference/hooks/)
-   [WC_Hooks 공식 문서](https://woocommerce.com/document/actions-and-filters/)
