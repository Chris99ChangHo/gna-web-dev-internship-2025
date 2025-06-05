# 📅 Day 04 (2025-06-05, Thu)

## 🎓 Today's Work

**📌 Reviewed current development processes and emphasized the importance of diverse customization experiences in the development meeting.**   
**📌 Delivered a PPT presentation on social media auto-posting and design tools, discussing their practical applicability.**   
**📌 Gained awareness and discussed legal risks associated with AI-generated content under Australian law.**   
**📌 Implemented user list pagination (OFFSET calculation, permalink handling).**   
**📌 Implemented AJAX-driven dynamic updates for user lists (search/filter/page navigation).**  

### Detailed Activities

**1. Development Meeting & Key Discussions** Today's development meeting focused on reviewing our current development process and stressing the importance of diverse practical experience to enhance our real-world skills.

-   **Current Development Process Review:** We took time to review the overall flow of our project to date, which helped us understand our current position and set future directions.
-   **Emphasis on Diverse Customization Experience:** During the meeting, we received advice highlighting the critical importance of **hands-on experience in building various common functionalities and structures**. This active practice is essential for developing practical problem-solving skills beyond theoretical knowledge.

**2. Social Media Auto-Posting & Design Tool Presentation** You were busy preparing and delivering a presentation on social media tools from yesterday afternoon until 1:00 PM today.

-   **Preparation & Delivery:**
    -   Yesterday afternoon: You started preparing a PPT presentation on **social media auto-posting and design tool analysis**.
    -   This morning: After the development meeting, you finalized and refined the presentation materials.
    -   At 1:00 PM: The presentation was successfully delivered. You received **positive feedback and praise** for your work, which was a rewarding moment.
-   **Discussion:** Following the presentation, there was an in-depth discussion about the **practical applicability** of these tools in our actual workflow. A significant point raised was that **Australian law is notably stricter** than other countries, and **particular caution is needed when using AI-generated content** due to potential legal risks. This discussion provided valuable insight into considering legal aspects when adopting new technologies.

**3. User List Pagination Implementation** You implemented pagination for the user list to display users in manageable chunks (e.g., 10 per page) and allow navigation through page numbers.

-   **Goal:** To display users in batches of 10 per page when there are many users, enabling navigation to subsequent pages by clicking page numbers.
-   **Key Code & Logic:**
    -   Set `$per_page` (users per page) to 10.
    -   When fetching the current page number `$paged`, you considered both WordPress's **permalink structure (`get_query_var('paged')`)** and standard GET parameters (`$_GET['paged']`).
    -   The **`OFFSET` calculation** used the formula `($paged - 1) * $per_page` to ensure the correct subset of users was retrieved for each page.
    -   Performed the query using `WP_User_Query` with `number` and `offset` arguments.
    -   Dynamically generated the pagination UI by calculating the total number of users and total pages.
-   **Pagination UI:**
    -   Displayed pagination links only if the total number of pages exceeded 1.
    -   When clicking each page link, you ensured that only the `paged` parameter was updated while preserving existing URL parameters using `http_build_query()`.
    -   Visually emphasized the current page number by making its text bold.
-   **Key Takeaways:**
    -   You reconfirmed that **accurate `OFFSET` calculation is essential for displaying distinct users on each page**.
    -   You learned that it's crucial to **always check `get_query_var('paged')` to properly handle the page number, especially with WordPress permalink structures**.

**4. AJAX User List Implementation** You implemented AJAX functionality to dynamically update the user list area without a full page reload when performing search, filter, or page navigation actions.

-   **Goal:** To dynamically refresh only the user list area without a full page reload when searching, filtering, or navigating between pages.
-   **Core Workflow:**
    -   **HTML:** Defined a `form` tag for user search and filtering, and a `div` element (`#user-list-result`) to display the dynamically loaded user list.
    -   **JavaScript (user-list-ajax.js):**
        -   Prevented default browser refresh on form submissions by calling `e.preventDefault()`.
        -   Called the `ajaxUserList()` function for search/filter actions and page navigation.
        -   Inside `ajaxUserList()`, serialized form data and appended the current page number, then sent an AJAX POST request to `admin-ajax.php` with `action=ajax_user_list`.
        -   Upon receiving the AJAX response, dynamically updated the HTML content of the `#user-list-result` area.
        -   Ensured the initial user list loaded automatically on page load.
    -   **PHP (functions.php or similar):**
        -   Registered the `ajax_user_list_callback` function to handle AJAX requests using `wp_ajax_ajax_user_list` and `wp_ajax_nopriv_ajax_user_list` actions.
        -   Within the callback, retrieved and sanitized POST data (search term, role, page number) to construct `WP_User_Query` arguments.
        -   Generated the HTML for the user list and pagination links based on the query results and `echo`ed it out.
        -   Crucially, called the `wp_die()` function at the end to properly terminate the AJAX request.
    -   **JavaScript Enqueue & Localize:**
        -   Properly enqueued the `user-list-ajax.js` file using the `wp_enqueue_scripts` action hook.
        -   Utilized `wp_localize_script` to make `admin_url('admin-ajax.php')` accessible in JavaScript as `ajax_user_list.ajax_url`.
-   **Key Takeaways:**
    -   **AJAX** enables a **smoother user experience** by allowing search, filter, and page navigation to operate without full page reloads.
    -   You learned an efficient structure where **JavaScript sends form data and page numbers to PHP**, PHP uses `WP_User_Query` to **return only the necessary results**, and JS then **updates only the relevant section** of the page.

## 🧠 Key Concepts Learned

-   **Expanded Development Process Understanding:** Through the development meeting and PPT presentation, you re-evaluated the current progress and gained deeper insights into the **importance of practical customization experience** and real-world considerations like **legal risks associated with AI content usage**.
-   **Efficient Pagination Implementation:** You mastered a practical method for implementing pagination by accurately calculating the `offset` argument for `WP_User_Query` and **handling WordPress permalinks (`get_query_var('paged')`)**.
-   **AJAX-based Dynamic Content Loading:** You directly implemented the communication between JavaScript and PHP (`admin-ajax.php`) to asynchronously load and update user lists, understanding the significance of a **seamless user experience without full page refreshes**, but **felt the need for further learning** in this area.
-   **Client-Server Data Communication:** You practiced using key JavaScript and PHP functions essential for AJAX communication, such as `jQuery.serialize()`, `$.post()`, and `wp_localize_script()`, to exchange data between the client and server, but **felt the need to delve deeper into these concepts.**

## 💡 Practical Trial-and-Error and Tips

-   **`WP_User_Query` Utilization:** You reconfirmed that `WP_User_Query` is a powerful and flexible tool for filtering, sorting, and paginating complex user data.
-   **Choosing GET/POST Methods:** You made a practical decision to use GET for traditional pagination (to allow **bookmarking and sharing URLs**) and POST for AJAX-driven search/filter/pagination (to keep **data out of the URL**).
-   **AJAX Debugging:** You found that inspecting request and response data in the browser's developer tools (Network tab) is highly effective for troubleshooting AJAX implementations.
-   **Importance of `wp_die()`:** You learned that failing to call `wp_die()` in an AJAX callback function can result in unnecessary HTML output, confirming its crucial role in properly terminating AJAX requests.

## 🔜 Next Steps

-   **Learning WordPress Database Optimization Techniques:** Plan to delve into advanced topics like database query optimization, indexing strategies, and caching methods to enhance performance when handling large datasets.
-   **Analyzing and Defending Against Security Vulnerabilities:** Intend to understand common security vulnerabilities in WordPress development (e.g., XSS, SQL Injection) and learn secure coding practices and WordPress security features to mitigate these risks.

----------

### 🕸️ Docscraper Program Update (Web Scraping Development for LLM Learning Assistant)

**`Docscraper`** development is currently underway. Following earlier feedback, I've shifted focus from indiscriminate data scraping to deeply considering **'how to select and structure meaningful data.'** This has led to a re-evaluation of the development direction, and for now, I'm prioritizing WordPress learning. Moving forward, I plan to enhance efficiency by focusing on goal-oriented data scraping rather than collecting data aimlessly.

---

# 📅 Day 04 (2025-06-05, Thu)

## 🎓 Today's Work

**📌 개발 미팅에서 현재까지의 개발 프로세스 리뷰 및 다양한 커스터마이즈 경험의 중요성 강조.**   
**📌 소셜 미디어 자동 게시 및 디자인 툴 분석 PPT 발표 진행 및 실무 적용 가능성 토론.**   
**📌 AI 생성 콘텐츠 활용 시 호주 법적 리스크에 대한 인지 및 논의.**   
**📌 유저 리스트 페이지네이션 구현 (OFFSET 계산, 퍼머링크 대응).**   
**📌 AJAX를 활용한 유저 리스트 동적 갱신 기능 구현 (검색/필터/페이지 이동).**  

### Detailed Activities

**1. 개발 미팅 및 주요 논의** 오늘 개발 미팅은 현재까지의 개발 프로세스를 검토하고, 실무 역량 강화를 위한 다양한 경험의 중요성을 강조하는 자리였습니다.

-   **현재까지의 개발 프로세스 리뷰:** 지금까지 프로젝트가 어떤 흐름으로 진행되었는지 전체적으로 점검하는 시간을 가졌습니다. 이는 현재 위치를 파악하고 앞으로의 방향을 설정하는 데 도움이 되었습니다.
-   **다양한 커스터마이즈 경험의 중요성 강조:** 미팅에서는 실무에서 자주 사용되는 다양한 기능과 구조를 **직접 만들어보는 경험**이 매우 중요하다는 조언을 받았습니다. 이는 단순한 이론 학습을 넘어 실제 문제 해결 능력을 키우는 데 필수적인 부분임을 다시 한번 상기했습니다.

**2. 소셜 미디어 자동 게시 및 디자인 툴 발표** 어제 오후부터 오늘 오후 1시까지, 소셜 미디어 자동 게시 및 디자인 툴에 대한 발표 준비와 진행으로 분주하게 임했습니다.

-   **발표 준비 및 진행:**
    -   어제 오후: **소셜 미디어 자동 게시 및 디자인 툴 분석**을 주제로 PPT 발표 자료를 급하게 제작했습니다.
    -   오늘 오전: 개발 미팅 직후 발표 자료를 수정하고 완성하여, 오후 1시에 성공적으로 발표를 마쳤습니다.
    -   발표 후 **"잘했다"는 긍정적인 피드백과 칭찬**을 받았습니다. 이는 노력이 결실을 맺는 보람 있는 순간이었습니다.
-   **토론:** 발표 후에는 해당 툴들을 **실무에 실제로 도입하고 활용할 수 있을지**에 대한 심도 깊은 논의가 이어졌습니다. 특히, **호주 법이 다른 나라에 비해 엄격**하다는 점, 그리고 **AI 생성 콘텐츠 사용 시 법적 리스크에 각별히 주의**해야 한다는 중요한 의견이 공유되었습니다. 이는 기술 도입 시 법률적 측면을 고려하는 실무적 시야를 넓히는 데 도움이 되었습니다.

**3. 유저 리스트 페이지네이션 구현** 유저 수가 많을 때 한 페이지에 10명씩만 보여주고, 페이지 번호를 통해 다음 유저들을 볼 수 있도록 페이지네이션을 구현했습니다.

-   **목표:** 유저 목록이 많을 경우 한 페이지에 10명씩만 보여주고, 페이지 번호를 클릭하여 다음/이전 유저를 조회하도록 구현합니다.
-   **핵심 코드 및 로직:**
    -   `$per_page` (페이지 당 유저 수)를 10으로 설정했습니다.
    -   현재 페이지 번호 `$paged`를 가져올 때, 워드프레스 **퍼머링크 구조(`get_query_var('paged')`)**와 일반 GET 파라미터(`$_GET['paged']`) 모두를 고려하여 처리했습니다.
    -   `OFFSET` 계산은 `($paged - 1) * $per_page` 공식을 사용하여 각 페이지마다 올바른 유저 집합을 가져오도록 했습니다.
    -   `WP_User_Query`에 `number`와 `offset` 인자를 전달하여 쿼리를 수행했습니다.
    -   전체 유저 수와 전체 페이지 수를 계산하여 페이지네이션 UI를 동적으로 생성했습니다.
-   **페이지네이션 UI:**
    -   전체 페이지 수가 1을 초과할 경우에만 페이지네이션 링크를 표시하도록 했습니다.
    -   각 페이지 링크를 클릭할 때 `paged` 파라미터만 변경하고 기존 URL 파라미터(`$_GET`)는 유지되도록 `http_build_query()`를 활용했습니다.
    -   현재 페이지는 글씨를 굵게 표시하여 시각적으로 강조했습니다.
-   **핵심 포인트:**
    -   **`OFFSET` 계산이 정확해야 페이지마다 다른 유저가 나옴**을 다시 한번 확인했습니다.
    -   **퍼머링크 구조 대응을 위해 `get_query_var('paged')`를 반드시 체크**해야 함을 체득했습니다.

**4. AJAX 유저 리스트 실습** 검색, 필터, 페이지 이동 시 새로고침 없이 유저 리스트 영역만 동적으로 갱신되도록 AJAX 기능을 구현했습니다.

-   **목표:** 검색/필터링, 그리고 페이지 이동 시 전체 페이지 새로고침 없이 유저 리스트 영역만 동적으로 업데이트되도록 구현합니다.
-   **핵심 흐름:**
    -   **HTML:** 유저 검색 및 필터링을 위한 `form` 태그와 유저 리스트 결과를 표시할 `div` (`#user-list-result`)를 정의했습니다.
    -   **JavaScript (user-list-ajax.js):**
        -   `submit` 이벤트 시 `e.preventDefault()`를 호출하여 기본 새로고침을 방지했습니다.
        -   검색/필터링 및 페이지 이동 시 `ajaxUserList()` 함수를 호출하여 AJAX 요청을 보냈습니다.
        -   `ajaxUserList()` 함수 내에서 폼 데이터와 현재 페이지 번호를 조합하여 `action=ajax_user_list`와 함께 POST 요청을 `admin-ajax.php`로 보냈습니다.
        -   AJAX 응답을 받아 `#user-list-result` 영역의 HTML을 동적으로 업데이트했습니다.
        -   페이지 로드 시 초기 유저 리스트를 자동으로 로드하도록 했습니다.
    -   **PHP (functions.php 등):**
        -   `wp_ajax_ajax_user_list` 및 `wp_ajax_nopriv_ajax_user_list` 액션을 사용하여 AJAX 요청을 처리할 `ajax_user_list_callback` 함수를 등록했습니다.
        -   콜백 함수 내에서 `$_POST`로 전달된 검색어, 역할, 페이지 번호 등을 받아 `WP_User_Query` 인자를 구성했습니다.
        -   쿼리 결과를 바탕으로 유저 리스트 HTML과 페이지네이션 HTML을 생성하여 `echo`로 출력했습니다.
        -   AJAX 요청을 정상적으로 종료하기 위해 `wp_die()` 함수를 반드시 호출했습니다.
    -   **JavaScript 등록:**
        -   `wp_enqueue_scripts` 액션 훅을 사용하여 `user-list-ajax.js` 파일을 올바르게 등록했습니다.
        -   `wp_localize_script`를 통해 `admin_url('admin-ajax.php')`를 JavaScript에서 `ajax_user_list.ajax_url` 변수로 사용할 수 있도록 설정했습니다.
-   **핵심 요약:**
    -   **AJAX**를 통해 검색/필터/페이지 이동 시 **새로고침 없이 매끄럽게 동작**하는 유저 경험을 제공했습니다.
    -   **JavaScript에서 폼 데이터와 페이지 번호를 PHP로 넘기고**, PHP에서 **`WP_User_Query`로 필요한 결과만 반환**하며, JS에서 해당 **결과 영역만 갱신**하는 효율적인 구조를 학습했습니다.

## 🧠 Key Concepts Learned

-   **개발 프로세스 이해 확장:** 개발 미팅과 PPT 발표를 통해 현재 진행 상황을 점검하고, **커스터마이즈 경험의 중요성**과 **AI 콘텐츠 활용 시 법적 리스크** 등 실무적 고려사항을 깊이 있게 인지했습니다.
-   **효율적인 페이지네이션 구현:** `WP_User_Query`의 `offset` 인자를 정확히 계산하고 **워드프레스 퍼머링크(`get_query_var('paged')`)에 대응**하여 페이지네이션을 구현하는 실무적 방법을 체득했습니다.
-   **AJAX 기반 동적 콘텐츠 로딩:** JavaScript와 PHP(`admin-ajax.php`) 간의 통신을 통해 유저 리스트를 비동기적으로 로드하고 업데이트하는 과정을 직접 구현하며 **새로고침 없는 사용자 경험**의 중요성을 이해했지만, **더 학습할 필요성을 느꼈습니다.**
-   **클라이언트-서버 데이터 통신:** `jQuery.serialize()`, `$.post()`, `wp_localize_script()` 등 AJAX 통신에 필요한 핵심 JavaScript 및 PHP 함수들을 활용하여 데이터를 주고받는 방법을 실습했지만, 이 개념들에 대해 **더 깊이 학습할 필요성을 느꼈습니다.**

## 💡 Practical Trial-and-Error and Tips

-   **`WP_User_Query` 활용:** 복잡한 유저 데이터를 필터링하고 정렬하며 페이지네이션을 적용하는 데 `WP_User_Query`가 매우 강력하고 유연한 도구임을 다시 한번 확인했습니다.
-   **GET/POST 방식의 선택:** 전통적인 페이지네이션은 GET 방식으로 URL에 페이지 정보를 포함하여 **북마크 및 공유가 가능**하도록 구현했고, 검색/필터/AJAX 페이지네이션은 **POST 방식**을 사용하여 데이터가 URL에 노출되지 않도록 하는 실무적 판단을 했습니다.
-   **AJAX 디버깅:** AJAX 구현 시 요청 및 응답 데이터를 개발자 도구(Network 탭)로 확인하는 것이 문제 해결에 매우 유용함을 경험했습니다.
-   **`wp_die()`의 중요성:** AJAX 콜백 함수에서 `wp_die()`를 호출하지 않으면 불필요한 HTML이 함께 반환되어 문제가 발생할 수 있음을 확인하고, 그 중요성을 체득했습니다.

## 🔜 Next Steps

-   **워드프레스 데이터베이스 최적화 기법 학습:** 대규모 데이터 처리 시 성능 향상을 위한 데이터베이스 쿼리 최적화, 인덱싱 전략, 캐싱 기법 등에 대해 심도 있게 학습할 예정입니다.
-   **보안 취약점 분석 및 방어:** 워드프레스 개발 시 발생할 수 있는 주요 보안 취약점(XSS, SQL Injection 등)을 이해하고, 이를 방어하기 위한 코드 작성 및 워드프레스 보안 기능을 학습할 계획입니다.

----------

### 🕸️ Docscraper 프로그램 진행 상황 (LLM 학습 도우미를 위한 웹 스크래핑 개발)

**`Docscraper`** 개발은 현재 진행 중입니다. 이전 피드백을 통해 무작정 데이터를 긁어모으기보다는 **'의미 있는 데이터 선별 및 구조화'**에 대한 깊은 고민을 시작했습니다. 이로 인해 개발 방향을 재고했으며, 당분간은 워드프레스 학습에 우선순위를 두려 합니다. 앞으로는 명확한 목표를 가진 데이터 스크래핑에 집중해 효율성을 높일 계획입니다.
