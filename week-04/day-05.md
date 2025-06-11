# 📅 Day 05 (2025-06-06, Fri)

## 🎓 What I Did Today

**📌 Started a 'Development News Archive' mini-project, incorporating feedback from the dev meeting.**   
**📌 Designed and implemented WordPress Custom Post Type (news), Custom Fields, and Custom Taxonomies.**   
**📌 Built homepage and news archive templates using Elementor (card-style lists, search bar, latest news).**   
**📌 Scraped and confirmed output of sample news data, then began developing the scraping code.**  

### Detailed Activities

**1. Project Initiation & Background** Building on feedback from yesterday's dev meeting and a personal desire to expand practical WordPress skills, I officially kicked off the 'Development News Archive' mini-project today.

-   **Background & Motivation:** I felt a bit short on actual development progress yesterday due to presentation prep, even though I had touched on AJAX. After today's dev meeting, I realized the strong need for a mini-project that would allow me to fully experience a complete WordPress development cycle, including AJAX. This led to my decision to "build a side project to practice real-world skills like WordPress Custom Post Type customization, queries, and AJAX!" I shifted my learning focus to this 'Development News Archive' project starting today.
-   **Project Goals & Direction:** The main goal is to **build a multilingual development news archive using WordPress.** Beyond just implementation, I'm focusing on directly implementing **critical real-world features** like translation/summarization, source attribution, cost efficiency, real-time trends, and AJAX filters. I'm also mindful of **UI/UX**, paying attention to web UI components such as navigation, layout, and headers for a user-friendly design.

**2. Core Design & Data Structuring** To build the 'Development News Archive', I designed and implemented custom post types, custom fields, and taxonomies.

-   **Created `news` Custom Post Type:** I used **WCK** to create a custom post type named `news`. I configured it to support `title`, `editor`, and `custom-fields` to enable basic news content management.
-   **Added Custom Fields:** I defined and added custom fields for detailed news information, such as 'Source Name', 'Source URL', 'Translated Text', 'Summary', and 'Actual Author'.
-   **Designed Custom Taxonomies:** I considered adding custom taxonomies for additional classification, such as 'Source Name' and 'News Writer'. I also explored linking existing WordPress categories/tags to the `news` post type.
-   **Registered Sample Data & Initiated Scraping Code:** To test the designed structure, I **scraped and registered two sample news articles, confirming they displayed correctly.** Following this, I immediately **began writing scraping code** to efficiently collect more data.

**3. Frontend (Homepage/Archive) Implementation** I primarily used Elementor to build the UI for the homepage and news archive templates.

-   **Elementor Template Creation:** I created the base templates for the homepage and news archive pages using Elementor.
-   **Key UI Components:** I arranged a search bar and the latest three news articles prominently on the homepage, and designed the news to display in a card-style grid format. **The top UI elements, such as site name, menu, and language switcher, are still planned for future implementation;** my current focus was on establishing the basic framework.
-   **Archive Template Application & Widget Usage:** I applied the created template specifically to the `news` custom post type archive page. I primarily used the `Posts` or `Loop Grid` widgets to display the news list in a card/grid format. Through this process, I encountered the limitations of the `Archive Posts` widget and recognized the flexibility of the `Posts` / `Loop Grid` widgets for more versatile content display.

**4. Practical Problem-Solving & Emerging Questions** During this hands-on session, I encountered various practical problems. While I resolved some, new questions arose.

-   **`Archive Posts` Widget Not Displaying CPT (`news`) Issue:** Initially, I was puzzled why my `news` custom post type wasn't appearing in the `Archive Posts` widget. After checking CPT registration options, permalinks, template application, query sources, and even potential plugin conflicts, I realized that **the `Posts` or `Loop Grid` widgets are better suited for flexibly retrieving and controlling CPT data.** This experience highlighted the specific roles and limitations of different Elementor widgets.
-   **Limitations of the `Tag Cloud` Widget:** I discovered that the standard `Tag Cloud` widget isn't suitable for AJAX integration or real-time trending features; it functions more like a simple menu link. I concluded that **separate implementation or specialized plugins would be necessary for real-time trending.**
-   **Need for Deeper Understanding:** As I tackled these problems, I increasingly felt the strong need for **a deeper understanding of WordPress's query structure, the internal workings of Elementor widgets, and the interaction between PHP and JavaScript.** I realized that achieving truly custom functionality often requires more than just plugin usage, demanding the ability to write and debug code directly.

**5. Overall Workflow Summary** Today's practical session involved the initial stages of the 'Development News Archive' project, following this workflow:

-   Analyzing the practical background (dev meeting feedback, personal goal setting)
-   Designing and creating custom post types, fields, and taxonomies
-   Registering sample news data and starting the scraping code development
-   Attempting UI implementation (card-style lists, filters, trends, etc.) for the homepage/archive using Elementor
-   Encountering and resolving practical issues (widget limitations, query behavior, integration problems) while refining the structure.

**6. Practical Insights (Areas for Future Mastery)** Through today's hands-on experience, I encountered core elements of WordPress custom development. At the same time, I clearly identified **areas where I need to deepen my understanding and practical skills.**

-   I need to gain a more in-depth understanding of the fundamental structure of WordPress CPTs, fields, taxonomies, queries, and AJAX, as well as the organic relationships between these elements.
-   I must improve my understanding of Elementor widget limitations and practical alternatives (e.g., criteria for choosing between Posts/Loop Grid vs. Archive Posts).
-   I need to develop the ability to **design and implement** rather than just 'use' essential UX features for news hubs, such as trending, real-time filtering, and other dynamic elements.
-   I need to further consider how to technically incorporate business requirements like "cost efficiency, source attribution, translation/summarization, and practical scalability."

## 🧠 Key Concepts Learned

-   **Expanded Development Process Understanding:** Through the development meeting and PPT presentation, I re-evaluated the current progress and gained deeper insights into **the importance of practical customization experience** and real-world considerations like **legal risks associated with AI content usage.**
-   **Custom Post Type & Taxonomy Utilization:** I learned the basic process of designing and structuring data with the `news` custom post type, related fields, and taxonomies using **WCK**.
-   **Elementor-based UI/UX Implementation:** I practiced building dynamic news archives and filter UIs using various Elementor widgets, especially `Posts` and `Loop Grid`.
-   **WordPress Widget Limitations & Alternatives:** I experienced the functional limitations of Elementor's `Archive Posts` and `Tag Cloud` widgets, and recognized the need to use `Posts`/`Loop Grid` or custom implementation for more flexible solutions.

## 💡 Practical Trial-and-Error and Tips

-   **`WP_Query` Utilization:** I reconfirmed that `WP_User_Query` is a very powerful and flexible tool for filtering, sorting, and paginating complex user data. I also re-verified that `WP_Query` plays a key role in fetching CPT and taxonomy data.
-   **AJAX Debugging:** I found that inspecting request and response data in the browser's developer tools (Network tab) is extremely useful for troubleshooting AJAX implementations. This was particularly helpful in understanding how Elementor's AJAX features work.
-   **Importance of `wp_die()`:** **If `wp_die()` isn't called in an AJAX callback function, unnecessary HTML output can be returned, causing problems. `wp_die()` is used in WordPress AJAX request handling to terminate the response and stop PHP script execution. This ensures that the AJAX response only contains the necessary data, preventing client-side parsing errors and enabling clean communication.**
-   **Importance of Elementor Widget Combinations:** I realized the necessity of combining various Elementor widgets to achieve desired UI/UX, and that specific widget limitations often require compensation with other widgets or custom coding.

## 🔜 Next Steps

-   **Learning WordPress Database Optimization Techniques:** I plan to delve deeply into advanced topics like database query optimization, indexing strategies, and caching methods to enhance performance when handling large datasets.
-   **Analyzing and Defending Against Security Vulnerabilities:** I intend to understand common security vulnerabilities in WordPress development (e.g., XSS, SQL Injection) and learn secure coding practices and WordPress security features to mitigate these risks.
-   **Researching Elementor Custom Widget Development:** I plan to research how to develop custom widgets for Elementor to implement functionalities that existing widgets can't provide, thereby enhancing my ability to create more flexible and tailored UI/UX.
-   **Implementing Real-time Trends & Taxonomy-based AJAX Filter:** I plan to complete the feature for refreshing the news list via AJAX when a filter is clicked, either by utilizing `Elementor Pro`'s `Loop Grid` and `Taxonomy Filter` widgets or by implementing the code directly if necessary.

### 🕸️ Docscraper Program Update (Web Scraping Development for LLM Learning Assistant)

**`Docscraper`** development is currently underway. Based on earlier feedback, I've shifted my focus from indiscriminate data scraping to deeply considering **'how to select and structure meaningful data.'** This has led to a re-evaluation of the development direction, and for now, I'm prioritizing WordPress learning. Moving forward, I plan to enhance efficiency by focusing on goal-oriented data scraping rather than collecting data aimlessly.

----------

# 📅 5일차 (2025-06-06, 금)

## 🎓 오늘 한 일
**📌 개발 미팅 피드백 반영, '개발 뉴스 아카이브' 미니 프로젝트 본격 착수.**   
**📌 워드프레스 커스텀 포스트타입(news), 커스텀 필드, 커스텀 텍소노미 설계 및 구현.**   
**📌 Elementor를 활용한 홈페이지 및 뉴스 아카이브 템플릿 제작 (카드형 리스트, 검색창, 최신 뉴스).**   
**📌 샘플 뉴스 데이터 스크래핑 및 출력 확인, 그리고 스크래핑 코드 개발 착수.**  

### 상세활동

**1. 실습 배경 및 미니 프로젝트 착수** 어제 개발 미팅 피드백과 개인적인 아쉬움을 바탕으로, 워드프레스 실무 역량 강화를 위한 '개발 뉴스 아카이브' 미니 프로젝트를 본격적으로 시작했습니다.

-   **실습 배경 및 동기:** 어제 AJAX 실습 후 발표 준비로 인해 진도에 아쉬움을 느껴, 워드프레스 개발의 한 사이클을 온전히 경험할 미니 프로젝트의 필요성을 느꼈습니다. 이에 **'개발 뉴스 아카이브' 프로젝트를 시작하며 워드프레스 커스터마이징, 쿼리, AJAX 등 실무 연습을 쌓기로 결심**했습니다.
-   **프로젝트 목표 및 방향:** 워드프레스 기반 다국어 개발 뉴스 아카이브를 구축하며, 번역/요약, 출처 표기, 비용 효율성, 실시간 트렌드, AJAX 필터 등 **실무에 필요한 구조와 기능을 직접 구현하고 UI/UX까지 고려**하는 데 중점을 두었습니다.

**2. 기본 설계 및 데이터 구조화** '개발 뉴스 아카이브' 구축을 위해 커스텀 포스트타입과 커스텀 필드, 텍소노미를 설계하고 구현했습니다.

-   **커스텀 포스트타입 `news` 생성:** **WCK**를 활용하여 `news` 커스텀 포스트타입을 생성하고 `title`, `editor`, `custom-fields` 등을 설정했습니다.
-   **커스텀 필드 추가:** '출처명', '출처 URL', '번역문', '요약', '실제 저자' 등 뉴스의 상세 정보를 위한 커스텀 필드를 정의했습니다.
-   **커스텀 텍소노미 설계:** 필요에 따라 '출처명', '기자' 등 추가 분류를 위한 커스텀 텍소노미를 고려하고, 기존 워드프레스 카테고리/태그도 `news` 포스트타입에 연결하는 방안을 모색했습니다.
-   **샘플 데이터 등록 및 스크래핑 코드 착수:** 설계 테스트를 위해 **샘플 뉴스 두 개를 스크랩하여 등록 및 출력 확인 후, 효율적인 데이터 수집을 위한 스크래핑 코드 작성을 바로 시작**했습니다.

**3. 프론트엔드(홈페이지/아카이브) 구현** Elementor를 메인 빌더로 활용하여 홈페이지와 뉴스 아카이브 템플릿의 UI를 구현했습니다.

-   **Elementor 템플릿 제작:** Elementor로 홈페이지와 뉴스 아카이브 페이지의 기본 템플릿을 제작했습니다.
-   **주요 UI 구성:** 홈페이지에 검색창과 최신 뉴스 3개를 배치하고, 뉴스를 카드형 그리드 형태로 출력하도록 디자인했습니다. **상단 UI(사이트명, 메뉴, 언어 전환)는 아직 구현 예정**입니다.
-   **아카이브 템플릿 적용 및 위젯 활용:** `news` 커스텀 포스트타입 아카이브에 템플릿을 적용하고, `Posts` 또는 `Loop Grid` 위젯으로 뉴스 리스트를 출력했습니다. 이 과정에서 `Archive Posts` 위젯의 한계를 경험하며 `Posts`/`Loop Grid` 위젯의 유연성을 인지했습니다.

**4. 실무적 문제/해결 경험 (그리고 새로운 의문점)** 실습 과정에서 다양한 실무적 문제에 직면했으며, 일부는 해결했지만 새로운 의문점들이 생겼습니다.

-   **`Archive Posts` 위젯에서 CPT(`news`) 미표시 문제:** CPT 등록 옵션, 퍼머링크, 템플릿, 쿼리 소스 등을 점검하며 **`Posts` 또는 `Loop Grid` 위젯이 CPT 데이터를 유연하게 제어하는 데 더 적합함**을 깨달았습니다.
-   **`태그 클라우드` 위젯의 한계:** `태그 클라우드` 위젯이 AJAX 연동이나 실시간 트렌딩 기능에는 부적합하며, 단순히 메뉴 링크 역할에 가깝다는 것을 파악했습니다. **실시간 트렌드를 위해서는 별도의 구현 또는 전문 플러그인 탐색이 필요하다는 결론**을 내렸습니다.
-   **전반적인 이해의 깊이:** 문제 해결 과정에서 워드프레스 쿼리 구조, Elementor 위젯의 동작, 그리고 PHP/JS 간의 연동 방식에 대한 **더 깊은 이해가 필요하다는 것을 강하게 느꼈습니다.**

**5. 전체 워크플로우 요약** 오늘의 실습은 '개발 뉴스 아카이브' 프로젝트의 초기 단계를 경험하며 다음과 같은 워크플로우를 따랐습니다.

-   실습 배경 분석 (개발 미팅 피드백, 개인 목표 설정)
-   커스텀 포스트타입/필드/텍소노미 설계 및 생성
-   샘플 뉴스 데이터 등록 및 스크래핑 코드 작성 시작
-   Elementor를 활용한 홈페이지/아카이브 UI (카드형 리스트, 필터, 트렌드 등) 구현 시도
-   실무적 문제(위젯 한계, 쿼리 동작, 연동 이슈 등)에 직면하고 해결하며 구조를 개선하는 과정 반복

**6. 실무 인사이트 (앞으로 더 익혀야 할 것)** 오늘 실습을 통해 워드프레스 커스텀 개발의 핵심 요소들을 경험했지만, 동시에 **더 깊이 이해하고 실무적으로 익혀야 할 부분들**을 명확히 인지했습니다.

-   워드프레스 CPT/필드/텍소노미/쿼리/AJAX 구조의 본질적인 이해와 각 요소 간의 유기적인 관계를 더 심도 있게 파악해야 합니다.
-   Elementor 위젯의 한계와 이를 극복할 수 있는 실전 대안 (Posts/Loop Grid vs Archive Posts의 선택 기준 등)에 대한 이해를 높여야 합니다.
-   트렌딩/실시간 필터링 등 뉴스 허브에 필수적인 UX 구현법을 단순히 '활용'하는 것을 넘어 '직접 설계하고 구현'할 수 있는 능력을 키워야 합니다.
-   "비용 효율성, 출처 표기, 번역/요약, 실무적 확장성"과 같은 비즈니스 요구사항을 기술적으로 어떻게 반영할지 더 고민해야 합니다.

## 🧠 배운 핵심 개념

-   **개발 프로세스 이해 확장:** 개발 미팅과 PPT 발표를 통해 현재 진행 상황을 점검하고, **커스터마이즈 경험의 중요성**과 **AI 콘텐츠 활용 시 법적 리스크** 등 실무적 고려사항을 깊이 있게 인지했습니다.
-   **커스텀 포스트타입 & 텍소노미 활용:** **WCK**를 활용하여 `news` 커스텀 포스트타입과 관련 필드, 텍소노미를 설계하고 데이터를 구조화하는 기본 과정을 익혔습니다.
-   **Elementor 기반 UI/UX 구현:** Elementor의 다양한 위젯(특히 `Posts`/`Loop Grid`)을 활용하여 동적인 뉴스 아카이브 및 필터 UI를 구성하는 방법을 실습했습니다.
-   **워드프레스 위젯의 한계와 대안:** Elementor의 `Archive Posts` 위젯이나 `태그 클라우드` 위젯 등이 가지는 기능적 제약을 경험하고, 이를 해결하기 위한 `Posts`/`Loop Grid` 활용 또는 직접 구현의 필요성을 인지했습니다.

## 💡 실전 시행착오 및 팁

-   **`WP_Query` 활용:** 복잡한 유저 데이터를 필터링하고 정렬하며 페이지네이션을 적용하는 데 `WP_User_Query`가 매우 강력하고 유연한 도구임을 다시 한번 확인했습니다. 또한, `WP_Query`가 CPT와 텍소노미 데이터를 가져오는 데 핵심적인 역할을 함을 재확인했습니다.
-   **AJAX 디버깅:** AJAX 구현 시 요청 및 응답 데이터를 개발자 도구(Network 탭)로 확인하는 것이 문제 해결에 매우 유용함을 경험했습니다. 특히 Elementor의 AJAX 기능이 어떻게 동작하는지 파악하는 데 도움이 되었습니다.
-   **`wp_die()`의 중요성:** **AJAX 콜백 함수에서 `wp_die()`를 호출하지 않으면 불필요한 HTML이 함께 반환되어 문제가 발생할 수 있습니다. `wp_die()`는 워드프레스 AJAX 요청 처리 시, 응답을 종료하고 PHP 스크립트 실행을 멈추는 데 사용됩니다. 이를 통해 AJAX 응답에 오직 필요한 데이터만 포함되도록 보장하여, 클라이언트 측에서 파싱 오류를 방지하고 깔끔한 통신을 가능하게 합니다.**
-   **Elementor 위젯 조합의 중요성:** 원하는 UI/UX를 구현하기 위해 Elementor의 다양한 위젯들을 조합하고, 특정 위젯의 한계를 다른 위젯이나 직접 코딩으로 보완해야 함을 실감했습니다.

## 🔜 이후 학습 방향

-   **워드프레스 데이터베이스 최적화 기법 학습:** 대규모 데이터 처리 시 성능 향상을 위한 데이터베이스 쿼리 최적화, 인덱싱 전략, 캐싱 기법 등에 대해 심도 있게 학습할 예정입니다.
-   **보안 취약점 분석 및 방어:** 워드프레스 개발 시 발생할 수 있는 주요 보안 취약점(XSS, SQL Injection 등)을 이해하고, 이를 방어하기 위한 코드 작성 및 워드프레스 보안 기능을 학습할 계획입니다.
-   **Elementor 커스텀 위젯 개발 연구:** Elementor의 기존 위젯으로 구현하기 어려운 기능을 직접 커스텀 위젯으로 개발하는 방법을 연구하여, 더욱 유연하고 맞춤형 UI/UX를 구현하는 역량을 키울 계획입니다.
-   **실시간 트렌드 및 텍소노미 기반 AJAX 필터 기능 구현:** `Elementor Pro`의 `Loop Grid`와 `Taxonomy Filter` 위젯을 활용하거나, 필요시 직접 코드를 구현하여 필터 클릭 시 AJAX로 뉴스 리스트를 갱신하는 기능을 완성할 계획입니다.

### 🕸️ Docscraper 프로그램 진행 상황 (LLM 학습 도우미를 위한 웹 스크래핑 개발)

**`Docscraper`** 개발은 현재 진행 중입니다. 이전 피드백을 통해 무작정 데이터를 긁어모으기보다는 **'의미 있는 데이터 선별 및 구조화'**에 대한 깊은 고민을 시작했습니다. 이로 인해 개발 방향을 재고했으며, 당분간은 워드프레스 학습에 우선순위를 두려 합니다. 앞으로는 명확한 목표를 가진 데이터 스크래핑에 집중해 효율성을 높일 계획입니다.
