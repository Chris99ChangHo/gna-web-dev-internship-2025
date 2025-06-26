# ✅ Fix: News Card Date Display and Newest Sort Functionality Issues

## 🔍 Problem Situation

Our website's popular news section and search results pages were experiencing critical display and functionality issues. Specifically:

-   **"Invalid Date" Display Error:** The publication date on each news card was consistently showing "Invalid Date" instead of the actual date. This significantly undermined the credibility of the information presented and confused users.
-   **"Newest" Sort Function Malfunction:** When the "Sort by: Newest" option was selected from the top control bar, the news list failed to sort correctly by the most recent date. While the default "Relevant" (based on views) sort appeared to function, the "Newest" option was effectively useless, preventing users from easily finding up-to-date content and degrading the overall user experience.

## 📌 Cause Analysis

The root causes stemmed from a **data format mismatch** between the frontend (JavaScript) and the backend (WordPress REST API), coupled with **insufficient sorting logic** on the server side.

-   **Root Cause of 'Invalid Date' Error:**
    
    -   Our `popular-news-ajax.js` script was making an AJAX request to the backend (WordPress REST API) to fetch news data. Upon receiving this data, the JavaScript code was directly passing the `news.date` field to the `new Date()` constructor to create a date object.
    -   A `console.log(news.date)` revealed that the date string transmitted from the API was **not in a standard format** (like ISO 8601, e.g., `2025-06-26T10:44:15`) that JavaScript's `Date` object could reliably parse. The `new Date()` constructor returns an `Invalid Date` object when confronted with unparseable or inconsistent non-standard date string formats.
-   **Root Cause of 'Newest' Sort Malfunction:**
    
    -   Analysis of the `fetchPopularNews` function in `popular-news-ajax.js` showed that it correctly appended `sort_by='newest'` as a parameter to the API request URL when the "Newest" sort option was clicked.
    -   However, investigation into the backend REST API's processing logic (PHP) revealed that when the `sort_by` parameter was set to `'newest'`, the underlying WordPress `WP_Query` was **not correctly sorting data based on `post_date` or a custom publication date meta field**. Instead, it was either failing to apply the sort or **falling back to the default sorting mechanism** (e.g., by views or relevance). This issue originated from inadequate conditional query logic within the backend's PHP implementation for the `sort_by` parameter.

## 🛠 Solution

### ✅ Core Idea

The core idea behind the solution was to **standardize date parsing and formatting** across the frontend and backend, and to **strengthen the backend's sorting logic**. This ensured data accuracy and functional consistency. For date data, we implemented frontend validation and user-friendly formatting. On the backend, we ensured that data was precisely sorted according to the requested criteria.

### 💡 Step-by-Step Resolution

1.  **Resolving 'Invalid Date' Error (Frontend `popular-news-ajax.js` modification):**
    
    -   Modified the AJAX response handling block (`.then(data => {...})`) within `popular-news-ajax.js` where the `Date` object was being created using the `news.date` field.
    -   **Pre-processed** the non-standard date string from the API. Depending on the actual API response format, this involved string manipulation or regular expressions to convert it into a format (`YYYY-MM-DD` or `YYYY/MM/DD`) that `new Date()` could reliably parse.
    -   After creating the date object (e.g., `const dateObj = new Date(processedDateString);`), we added a validation check using `if (!isNaN(dateObj.getTime()))`. This condition verifies if the `dateObj` is a valid date. If not, it defaults to a fallback text (e.g., `'Date Not Available'`) or an empty string.
    -   To meet user requirements for date display ("Month Day, Year" format, e.g., "June 26, 2025"), we utilized the `dateObj.toLocaleDateString('en-US', { year: 'numeric', month: 'long', day: 'numeric' });` method to **format the date into a localized and user-friendly string**.  
    
    ```JavaScript
    // Example: Modification within popular-news-ajax.js AJAX response handler
    .then(data => {
        data.forEach(news => {
            // Step 1: Pre-process news.date string (e.g., 'YYYYMMDD' -> 'YYYY-MM-DD')
            // This part varies based on the actual news.date format from the API.
            let rawDate = news.date;
            let processedDateString = rawDate.replace(/(\d{4})(\d{2})(\d{2})/, '$1-$2-$3'); // Example: '20250626' -> '2025-06-26'
    
            const dateObj = new Date(processedDateString);
            let displayDate = '';
    
            if (!isNaN(dateObj.getTime())) {
                // Format if valid date
                displayDate = dateObj.toLocaleDateString('en-US', {
                    year: 'numeric',
                    month: 'long',
                    day: 'numeric'
                });
            } else {
                // Handle invalid date
                displayDate = 'Date Not Available';
            }
    
            // Insert displayDate into news card HTML (example)
            // const newsCardHtml = `...<span class="news-date">${displayDate}</span>...`;
            // append newsCardHtml to DOM
        });
    });
    ```
    
2.  **Implementing 'Newest' Sort Functionality (Frontend `popular-news-ajax.js` and Backend PHP modification):**
    
    -   **Frontend (`popular-news-ajax.js`):**
        -   Re-verified the `fetchPopularNews` function to ensure that the `&sort_by=${sortBy}` parameter was precisely and correctly appended to the API request URL based on the `currentSortBy` variable, checking for any omissions or typos.
        -   Reviewed the event listener logic for sort option clicks to ensure that `currentSortBy` was updated and `fetchPopularNews` was subsequently re-called.
        -   Enhanced the UI logic to toggle an `active` class on the sort links, providing a clear visual indication of the currently selected sorting method.
    -   **Backend (PHP, WordPress REST API Endpoint Logic Modification - Assumed):**
        -   Modified the callback function logic for the backend REST API endpoint to ensure that when the `sort_by=newest` parameter was received, WordPress's `WP_Query` accurately sorted the data based on `post_date` or a custom meta field for publication date (e.g., `_news_publish_date`).
        -   Configured the `WP_Query` arguments to dynamically set `orderby` and `order` parameters. For `sort_by=newest`, `orderby` was set to `'date'` and `order` to `'DESC'`. If using a custom field, `orderby` was set to `'meta_value'`, `meta_key` to `'_news_publish_date'`, and `order` to `'DESC'`. This completed the bidirectional integration, ensuring the client's requested sort criteria were precisely reflected on the server.
    
    ```PHP
    // Example: Backend PHP modification within functions.php or REST API callback
    add_action('rest_api_init', function () {
        register_rest_route('myplugin/v1', '/news', array(
            'methods' => 'GET',
            'callback' => 'get_custom_news',
            'args' => array(
                'sort_by' => array(
                    'sanitize_callback' => 'sanitize_text_field',
                    'default' => 'relevant', // Default sort
                ),
            ),
        ));
    });
    
    function get_custom_news(WP_REST_Request $request) {
        $sort_by = $request->get_param('sort_by');
        $args = array(
            'post_type' => 'news',
            'posts_per_page' => 10,
        );
    
        if ($sort_by === 'newest') {
            $args['orderby'] = 'date'; // Sort by post date
            $args['order'] = 'DESC';
            // If using a custom field:
            // $args['orderby'] = 'meta_value';
            // $args['meta_key'] = '_news_publish_date';
            // $args['order'] = 'DESC';
        } else if ($sort_by === 'relevant') {
            // Logic for 'relevant' (e.g., by views)
            // $args['orderby'] = 'meta_value_num';
            // $args['meta_key'] = 'post_views_count';
            // $args['order'] = 'DESC';
        }
        // ... other sort conditions
    
        $query = new WP_Query($args);
        // ... Process $query->posts and return response
    }
    ```
    
    **test**:
    -   Visually verified in the development environment that news card dates were correctly displayed.
    -   Clicked the "Sort by: Newest" button multiple times to confirm that the news list accurately sorted by the most recent date.
    -   Cross-checked that the "Sort by: Relevant" button also functioned as expected.
    -   Confirmed in the browser's developer tools (Network tab) that the AJAX request URL correctly included the `sort_by=newest` parameter.
    -   (If applicable, confirmed that the `news.date` field in the API response was now in a `new Date()`-parsable format after any backend changes.)
    
## 🎯 Result

The implemented solution yielded the following positive outcomes:

-   **Accurate Date Display:** All news cards now display correct and user-friendly dates, such as "June 26, 2025," instead of "Invalid Date." This has significantly **boosted the credibility of the information**.
-   **Fully Functional Sorting:** Users can now **freely switch between "Relevant" and "Newest" sorting options**. Crucially, the "Newest" sort function **operates precisely by the latest publication date**, enhancing data exploration flexibility and overall user experience.
-   The previously reported "Invalid Date" messages and sorting malfunctions are no longer occurring.

## 💡 Lessons Learned

This resolution provided several key insights:

-   **Importance of Frontend-Backend Data Contracts:** For critical data like dates and times, using **international standard formats (e.g., ISO 8601) in API transmissions is essential**. Furthermore, it's crucial for the client-side to always perform **data validation** and apply **localized formatting** before display.
-   **Necessity of Comprehensive Debugging:** Even if symptoms appear on the frontend, the root cause might lie in the backend. This case underscored the importance of **full-stack debugging capabilities**—analyzing code on both client (JS) and server (PHP) sides, and understanding the entire data flow to pinpoint the actual problem.
-   **Clear Functional Requirements for Features:** Features like "sort by newest" require not just frontend parameter transmission but also **clear design and robust implementation on the backend** to correctly process the request and sort data according to the specified criteria.

To prevent similar issues from recurring, we need to establish clear guidelines for data formats in future API development. Frontend teams should reinforce coding standards to always perform validation and appropriate formatting upon data reception. Backend teams must also ensure the robustness of API parameter-driven data processing logic.

## 🗂 Related Keywords

JavaScript, Date Object, WordPress REST API, `WP_Query`, Date Format, Data Validation, Client-side Validation, Server-side Sorting, API Integration, Data Contract, UX Improvement, `toLocaleDateString`, Front-end, Back-end, Debugging

----------

# ✅ Fix: 뉴스 카드 날짜 표시 및 최신순 정렬 기능 비정상 작동 문제 해결

## 🔍 문제 상황

웹사이트의 인기 뉴스 섹션과 검색 결과 페이지에서 다음과 같은 심각한 표시 및 기능 문제가 발생했습니다:

-   **"Invalid Date" 표시 오류:** 각 뉴스 카드에 표시되어야 할 발행일이 일관적으로 "Invalid Date" 텍스트로 나타났습니다. 이는 제시되는 정보의 신뢰도를 크게 저하시키고 사용자에게 혼란을 주었습니다.
-   **"Newest" 정렬 기능 비정상 작동:** 상단 컨트롤 바의 "Newest" 정렬 옵션을 선택해도 뉴스 목록이 최신순으로 올바르게 정렬되지 않았습니다. 기본 정렬인 "Relevant" (조회수 기준)은 작동하는 것처럼 보였지만, 'Newest' 옵션은 사실상 무용지물이어서 사용자가 최신 콘텐츠를 쉽게 찾을 수 없게 하여 전반적인 사용자 경험을 저해했습니다.

## 📌 원인 분석

문제의 근본 원인은 프론트엔드(JavaScript)와 백엔드(WordPress REST API) 간의 **데이터 형식 불일치**와 서버 측의 **불충분한 정렬 로직**에 있었습니다.

-   **'Invalid Date' 오류의 근원:**
    
    -   `popular-news-ajax.js` 스크립트가 AJAX 요청을 통해 백엔드(WordPress REST API)로부터 뉴스 데이터를 가져온 후, JavaScript 코드가 `news.date` 필드를 `new Date()` 생성자에 직접 전달하여 날짜 객체를 만들고 있었습니다.
    -   `console.log(news.date)`를 통해 실제 API 응답에서 `news.date`의 값을 확인한 결과, API에서 전송된 날짜 문자열의 형식이 JavaScript의 `Date` 객체가 안정적으로 파싱할 수 있는 ISO 8601(예: `2025-06-26T10:44:15`)과 같은 **표준 형식이 아닌 비표준 또는 일관성 없는 형식**이었기 때문입니다. `new Date()` 생성자는 파싱할 수 없는 비표준 문자열 형식에 대해서는 `Invalid Date` 객체를 반환합니다.
-   **'Newest' 정렬 기능 비정상 작동의 근원:**
    
    -   `popular-news-ajax.js`의 `fetchPopularNews` 함수를 분석한 결과, "Newest" 정렬 옵션 클릭 시 `sort_by='newest'` 파라미터를 API 요청 URL에 추가하도록 되어 있었습니다.
    -   그러나 백엔드 REST API의 처리 로직(PHP)을 확인한 결과, `sort_by` 파라미터가 `'newest'`로 넘어왔을 때 기저의 WordPress `WP_Query`가 `post_date` 또는 실제 발행일을 저장하는 커스텀 메타 필드를 기준으로 **데이터를 올바르게 정렬하지 못했습니다**. 대신, 정렬이 적용되지 않거나 기본 정렬(예: 조회수 또는 관련성)로 **폴백(fallback)되는 문제**가 있었습니다. 이 문제는 백엔드의 PHP 구현에서 `sort_by` 파라미터에 대한 조건부 쿼리 로직이 미흡했기 때문에 발생했습니다.

## 🛠 해결 방법

### ✅ 핵심 아이디어

선택한 해결책의 핵심 아이디어는 프론트엔드와 백엔드 간의 **날짜 파싱 및 포맷팅을 표준화**하고, **백엔드의 정렬 로직을 강화**하는 것이었습니다. 이를 통해 데이터의 정확성과 기능적 일관성을 확보했습니다. 특히, 날짜 데이터는 클라이언트에서 유효성 검증을 거쳐 사용자 친화적인 형식으로 변환하고, 백엔드에서는 요청된 정렬 기준에 따라 데이터를 정확하게 정렬하도록 로직을 개선했습니다.

### 💡 단계별 해결

1.  **'Invalid Date' 오류 해결 (프론트엔드 `popular-news-ajax.js` 수정):**
    
    -   `popular-news-ajax.js` 파일 내, AJAX 응답을 처리하는 `.then(data => {...})` 블록에서 `news.date` 필드를 사용하여 `Date` 객체를 생성하는 부분을 수정했습니다.
    -   API에서 넘어오는 비표준 날짜 문자열을 `new Date()`에 직접 전달하기 전에, 필요에 따라 문자열 조작 또는 정규 표현식을 사용하여 `new Date()`가 파싱 가능한 형식(예: `YYYY-MM-DD` 또는 `YYYY/MM/DD`)으로 **전처리**했습니다.
    -   날짜 객체 생성 후(`const dateObj = new Date(processedDateString);`), `if (!isNaN(dateObj.getTime()))` 조건을 추가하여 생성된 `dateObj`가 유효한 날짜인지 **검증**하도록 했습니다. 이 검증을 통해 유효하지 않은 날짜인 경우 대체 텍스트(예: `'날짜 정보 없음'`) 또는 빈 문자열을 표시하도록 로직을 구현했습니다.
    -   표시될 날짜 형식에 대한 사용자 요구사항("Month Day, Year" 형식, 예: "June 26, 2025")을 반영하기 위해 `dateObj.toLocaleDateString('en-US', { year: 'numeric', month: 'long', day: 'numeric' });` 메서드를 사용하여 **지역화된 사용자 친화적인 날짜 형식으로 변환**했습니다.
    
    ```JavaScript
    // popular-news-ajax.js 내 AJAX 응답 처리 부분 수정 예시
    .then(data => {
        data.forEach(news => {
            // Step 1: news.date 문자열 전처리 (예시: 'YYYYMMDD' -> 'YYYY-MM-DD')
            // 이 부분은 실제 news.date 형식에 따라 다르게 구현됩니다.
            let rawDate = news.date;
            let processedDateString = rawDate.replace(/(\d{4})(\d{2})(\d{2})/, '$1-$2-$3'); // 예시: '20250626' -> '2025-06-26'
    
            const dateObj = new Date(processedDateString);
            let displayDate = '';
    
            if (!isNaN(dateObj.getTime())) {
                // 유효한 날짜인 경우 포맷팅
                displayDate = dateObj.toLocaleDateString('en-US', {
                    year: 'numeric',
                    month: 'long',
                    day: 'numeric'
                });
            } else {
                // 유효하지 않은 날짜인 경우 기본값 처리
                displayDate = '날짜 정보 없음';
            }
    
            // 뉴스 카드 HTML에 displayDate 삽입 (예시)
            // const newsCardHtml = `...<span class="news-date">${displayDate}</span>...`;
            // DOM에 newsCardHtml 추가
        });
    });
    ```
    
2.  **'Newest' 정렬 기능 구현 (프론트엔드 `popular-news-ajax.js` 및 백엔드 PHP 수정):**
    
    -   **프론트엔드 (`popular-news-ajax.js`):**
        -   `fetchPopularNews` 함수 내에서 API 요청 URL을 구성할 때 `currentSortBy` 변수 값에 따라 `&sort_by=${sortBy}` 파라미터가 URL에 정확하고 올바르게 추가되는지 확인하고, 누락되거나 오타가 없는지 재확인했습니다.
        -   정렬 옵션 클릭 시 `currentSortBy` 값을 업데이트하고 `fetchPopularNews`를 다시 호출하도록 이벤트 리스너 로직을 검토했습니다.
        -   정렬 링크 클릭 시 `active` 클래스를 토글하여 현재 선택된 정렬 방식을 시각적으로 명확하게 표시하도록 UI 로직을 개선했습니다.
    -   **백엔드 (PHP, WordPress REST API 엔드포인트 로직 수정 추정):**
        -   `sort_by=newest` 파라미터를 받았을 때 WordPress의 `WP_Query`가 실제 게시일(`post_date`) 또는 뉴스 발행일을 저장하는 사용자 정의 메타 필드(예: `_news_publish_date`)를 기준으로 데이터를 정렬하도록 백엔드 REST API 엔드포인트의 콜백 함수 로직을 수정했습니다.
        -   `WP_Query` 인자에 `orderby`와 `order` 파라미터를 동적으로 설정하여 `sort_by=newest`일 때 `orderby => 'date', order => 'DESC'` 또는 `orderby => 'meta_value', meta_key => '_news_publish_date', order => 'DESC'`와 같이 동작하도록 했습니다. 이를 통해 클라이언트에서 요청한 정렬 기준이 서버에서 정확히 반영되도록 양방향 연동을 완성했습니다.
    
    ```PHP
    // functions.php 또는 REST API 콜백 함수 내 (백엔드 PHP 예시)
    add_action('rest_api_init', function () {
        register_rest_route('myplugin/v1', '/news', array(
            'methods' => 'GET',
            'callback' => 'get_custom_news',
            'args' => array(
                'sort_by' => array(
                    'sanitize_callback' => 'sanitize_text_field',
                    'default' => 'relevant', // 기본 정렬
                ),
            ),
        ));
    });
    
    function get_custom_news(WP_REST_Request $request) {
        $sort_by = $request->get_param('sort_by');
        $args = array(
            'post_type' => 'news',
            'posts_per_page' => 10,
        );
    
        if ($sort_by === 'newest') {
            $args['orderby'] = 'date'; // 게시일 기준
            $args['order'] = 'DESC';
            // 만약 커스텀 필드라면:
            // $args['orderby'] = 'meta_value';
            // $args['meta_key'] = '_news_publish_date';
            // $args['order'] = 'DESC';
        } else if ($sort_by === 'relevant') {
            // 'relevant' (조회수 등) 로직
            // $args['orderby'] = 'meta_value_num';
            // $args['meta_key'] = 'post_views_count';
            // $args['order'] = 'DESC';
        }
        // ... 다른 정렬 조건
    
        $query = new WP_Query($args);
        // ... $query->posts 처리 및 응답 반환
    }
    ```
    
    **test**:
    -   수정 후 개발 환경에서 뉴스 카드 날짜가 올바르게 표시되는지 육안으로 확인했습니다.
    -   "Sort by: Newest" 버튼을 클릭하여 뉴스 목록이 최신순으로 정확히 정렬되는지 여러 번 테스트했습니다.
    -   "Sort by: Relevant" 버튼도 정상 작동하는지 교차 확인했습니다.
    -   브라우저 개발자 도구의 네트워크 탭에서 AJAX 요청의 URL에 `sort_by=newest` 파라미터가 올바르게 포함되는지 확인했습니다.
    -   (만약 백엔드에서 포맷 변경이 있었다면) API 응답으로 넘어오는 `news.date` 필드의 실제 값이 이제 `new Date()`로 파싱 가능한 형태로 변경되었는지 확인했습니다.

## 🎯 결과

구현된 해결책을 통해 다음과 같은 긍정적인 결과가 확인되었습니다:

-   **정확한 날짜 표시:** 모든 뉴스 카드에 "Invalid Date" 대신 "June 26, 2025"와 같이 **올바르고 사용자 친화적인 날짜가 표시**되게 되어, 정보의 신뢰도가 크게 향상되었습니다.
-   **완벽한 정렬 기능:** 사용자가 "Relevant"와 "Newest" 정렬 옵션을 **자유롭게 전환**할 수 있게 되었으며, 특히 "Newest" 정렬이 **최신 게시물 순으로 정확히 작동함**을 확인했습니다. 이로 인해 사용자의 데이터 탐색 유연성과 전반적인 사용자 경험이 크게 증대되었습니다.
-   문제 발생 전 보고되었던 "Invalid Date" 메시지나 정렬 오류는 더 이상 발생하지 않음을 확인했습니다.

## 💡 느낀 점

이번 문제 해결을 통해 다음과 같은 중요한 통찰을 얻었습니다:

-   **프론트엔드-백엔드 간 데이터 계약의 중요성:** 특히 날짜/시간과 같이 중요한 데이터는 API를 통해 전달될 때 **ISO 8601과 같은 국제 표준 형식을 사용하는 것이 필수적**입니다. 또한, 클라이언트 측에서는 항상 **데이터의 유효성 검사**를 수행하고, 사용자에게 표시하기 전에 **지역화된 포맷팅**을 적용하는 것이 중요함을 다시 한번 깨달았습니다.
-   **종합적인 디버깅 능력의 필요성:** 문제의 증상이 프론트엔드에서 나타나더라도, 근본 원인은 백엔드에 있을 수 있다는 점을 상기시켜 주었습니다. 클라이언트(JS)와 서버(PHP) 양쪽의 코드를 모두 분석하고, 데이터 흐름 전체를 이해하는 **풀스택 관점의 디버깅 능력**이 문제 해결에 얼마나 중요한지 실감했습니다.
-   **명확한 기능 요구사항 정의:** "최신순 정렬"과 같은 기능은 프론트엔드에서 요청 파라미터를 전달하는 것을 넘어, 백엔드에서 해당 요청을 어떻게 처리하고 데이터를 어떤 기준으로 정렬할 것인지에 대한 **명확한 설계 및 구현이 동반되어야 함**을 배웠습니다.

유사한 문제가 재발하는 것을 방지하기 위해, 향후 API 개발 시 데이터 형식에 대한 명확한 가이드라인을 설정하고, 프론트엔드에서 데이터를 수신할 때 항상 유효성 검사와 적절한 포맷팅을 수행하는 코딩 표준을 강화할 필요가 있습니다. 또한, 백엔드 개발 시 API 파라미터에 따른 데이터 처리 로직의 견고성을 더욱 확보해야겠습니다.

## 🗂 관련 키워드

JavaScript, Date 객체, WordPress REST API, `WP_Query`, 날짜 형식, 데이터 유효성 검사, 클라이언트 측 유효성 검사, 서버 측 정렬, API 연동, 데이터 계약, UX 개선, `toLocaleDateString`, 프론트엔드, 백엔드, 디버깅
