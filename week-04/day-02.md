# 📅 Day 02 (2025-06-03, Tue)

## 🎓 Today's Work

**📌 Summary of a Full Cycle of WordPress Custom Development (CPT, Custom Fields, WP_Query).**   
**📌 Practical Exercise and Summary of WP_User_Query and Related Concepts.**   
**📌 Identification and Resolution Summary of Custom Field Mismatch and PHP/HTML Commenting Issues.**  

### Detailed Activities

Summary of a Full Cycle of WordPress Custom Development (CPT, Custom Fields, WP_Query) I practiced a complete cycle of custom WordPress development, from designing data structures to displaying and styling them, based on guidance from the morning's development meeting.

-   **Custom Post Type (CPT) Creation with WCK:**
    -   Created a new content type, `Movies`. This automatically added a "Movies" menu item to the WordPress admin dashboard.
-   **Custom Fields (Meta Boxes) Addition with WCK:**
    -   Added custom fields like `Director`, `Release Year`, and `Genre` to the `Movie` post type. This allowed for detailed information input when registering new movies.
-   **Movie Data (Post) Registration:**
    -   Registered actual movie posts under the "Movies" section, including titles, content, thumbnails, and custom field values.
-   **WP_Query for Custom Post Type Data Output:**
    -   Created a custom template file (e.g., `page-movies-list.php`) within the theme.
    -   Used `WP_Query` to fetch and display a list of registered movies, including their custom field values, on the frontend.
-   **Connecting WordPress Page to Custom Template:**
    -   Created a new WordPress page titled "Movies List."
    -   Selected the `Movies List` custom template from the page editor, confirming that the movie list was correctly displayed on the frontend page.
-   **Styling Movie List with Card Layout:**
    -   Designed a visually appealing card layout for the movie list using HTML and CSS, including thumbnails, information, and descriptions. For quick iteration, the CSS was directly embedded in the template's header using `<style>` tags.

Practical Exercise and Summary of WP_User_Query and Related Concepts I explored `WP_User_Query` for user data retrieval and also reviewed the relationship between PHP templates and Elementor.

-   **WP_User_Query Practice:**
    -   Experimented with `WP_User_Query` to display a list of site users (including myself as administrator) in a card-like format, numbered (e.g., USER 0001), including their roles.
    -   Tested querying users based on different conditions like roles and meta values, noting how results would diversify with more users.
-   **Elementor / Design Concepts Integration:**
    -   Gained an understanding of the relationship between PHP templates and Elementor.
    -   Realized that while Elementor offers extensive design freedom on individual pages, **Elementor Pro's Theme Builder** is essential for drag-and-drop design of archive and single post templates (like movie archive or single movie detail pages).
-   **VS Code Extensions & Error Handling:**
    -   Learned that PHP/WordPress function recognition issues in VS Code often don't affect actual script execution.
    -   Explored useful VS Code extensions for WordPress development and practiced debugging common errors.

Identification and Resolution Summary of Custom Field Mismatch and PHP/HTML Commenting Issues During the practice, I encountered and successfully resolved two common development pitfalls.

-   **Custom Field Slug Mismatch:**
    -   **Problem:** The "Release Year" value for a Movie custom post type was not displaying, even after entering "2011". `get_post_meta` yielded no results.
    -   **Cause:** A **mismatch in the custom field (meta key) name (slug)**. When creating the custom field in WCK, the slug was `release-year` (hyphen), but the code used `release_year` (underscore). WordPress requires an exact match.
    -   **Resolution:** Used `print_r(get_post_meta(get_the_ID()))` to identify the correct slug, then modified the code to `get_post_meta(get_the_ID(), 'release-year', true)`.
-   **PHP & HTML Commenting Error:**
    -   **Problem:** Encountered an error when mixing PHP code and HTML comments in a template file (e.g., after `get_header()`).
    -   **Cause:** HTML comments (``) were placed directly inside a PHP code block (`<?php ... ?>`) without proper PHP comment syntax.
    -   **Resolution:** Ensured that HTML comments and inline styles were placed **outside of PHP code blocks** (i.e., after closing the PHP tag `?>` and before reopening it `<?php`).

## 🧠 Key Concepts Learned

-   **WordPress Custom Development Cycle:** Experienced the full flow from data structure design (CPT, custom fields) through data input, querying (`WP_Query`, `WP_User_Query`), output, and frontend design.
-   **Importance of Exact Match for Custom Field Keys:** Crucially learned that custom field (meta key) names must be **absolutely identical** (including hyphens, underscores, and case sensitivity) between definition and code to ensure proper data retrieval.
-   **PHP and HTML Commenting Rules:** Gained a solid understanding that HTML comments must reside _outside_ PHP code blocks, and PHP-specific comment syntax (`//` or `/* */`) must be used _within_ PHP blocks to avoid errors.
-   **Debugging with `print_r`:** Discovered the power of `print_r(get_post_meta(get_the_ID()))` as a fundamental debugging tool for custom field issues, allowing direct inspection of stored meta keys.
-   **Structured Troubleshooting:** Developed a systematic approach for custom field issues: 1) Verify the custom field slug, 2) Check for exact consistency between the slug and the code's `meta_key`, and 3) Use `print_r` to confirm actual data.
-   **WordPress Core Queries:** Gained practical experience with `WP_Query` for post retrieval and `WP_User_Query` for user data.

## 💡 Practical Trial-and-Error and Tips

-   **Custom Field Meta Key Consistency:** This was a primary learning point—a small difference in a hyphen vs. underscore can completely break functionality. Always double-check.
-   **PHP File Structure for Mixed Content:** Understanding where to open and close PHP tags (`<?php ... ?>`) and place HTML/CSS comments is vital for avoiding parsing errors in WordPress template files.
-   **Debugging Tool `print_r`:** This function became an indispensable tool for quickly identifying the exact meta keys stored in the database, greatly speeding up troubleshooting.

## 🔜 Next Steps

-   **WordPress REST API Basics:** I plan to learn about the concepts, endpoint structure, and authentication methods of the REST API, which is essential for utilizing WordPress data externally or fetching external data.
-   **Social Media Automation Tool Research Deep Dive:** I will deepen my research for the social media automation tool assignment due next Wednesday to enhance the report's completeness.

## 📚 References

-   [WP_Query Official Documentation](https://developer.wordpress.org/reference/classes/wp_query/)
-   [WP_User_Query Official Documentation](https://developer.wordpress.org/reference/classes/wp_user_query/)
-   [WCK (WordPress Creation Kit) Plugin](https://wordpress.org/plugins/wck-custom-fields-and-custom-post-types-creator/)

### 🕸️ Docscraper Program Update (Web Scraping Development for LLM Learning Assistant)

`Docscraper` development is currently underway. Following earlier feedback, I've shifted focus from indiscriminate data scraping to deeply considering **'how to select and structure meaningful data.'** This has led to a re-evaluation of the development direction, and for now, I'm prioritizing WordPress learning. Moving forward, I plan to enhance efficiency by focusing on goal-oriented data scraping rather than collecting data aimlessly.

----------

# 📅 Day 02 (2025-06-03, 화)

## 🎓 오늘 한 일

**📌 워드프레스 커스텀 개발 전체 사이클(CPT, 커스텀 필드, WP_Query) 실습 및 정리.**    
**📌 WP_User_Query 및 관련 개념 실습 및 정리.**   
**📌 커스텀 필드 불일치 및 PHP/HTML 주석 문제 확인 및 해결 정리.**  

### 상세 활동

워드프레스 커스텀 개발 전체 사이클(CPT, 커스텀 필드, WP_Query) 실습 및 정리 오전 개발 미팅에서 받은 가이드에 따라, 데이터 구조 설계부터 화면 표시 및 스타일링까지 워드프레스 커스텀 개발의 전체 사이클을 실습했습니다.

-   **WCK 플러그인으로 커스텀 포스트 타입(CPT) 생성:**
    -   `Movies`(영화)라는 새로운 콘텐츠 유형을 만들었습니다. 이는 워드프레스 관리자 대시보드에 자동으로 "Movies" 메뉴 항목을 추가했습니다.
-   **WCK로 커스텀 필드(메타박스) 추가:**
    -   `Movie` 포스트 타입에 감독(Director), 개봉연도(Release Year), 장르(Genre)와 같은 커스텀 필드를 추가했습니다. 이를 통해 새로운 영화 등록 시 상세 정보 입력이 가능해졌습니다.
-   **영화 데이터(포스트) 실제 등록:**
    -   "Movies" 섹션에 실제 영화 포스트를 등록하고, 제목, 본문, 썸네일 및 커스텀 필드 값을 입력했습니다.
-   **WP_Query로 커스텀 포스트 타입 데이터 출력:**
    -   테마 내에 `page-movies-list.php`와 같은 커스텀 템플릿 파일을 생성했습니다.
    -   `WP_Query`를 사용하여 등록된 영화 목록과 커스텀 필드 값을 프론트엔드에 출력했습니다.
-   **워드프레스 "페이지"와 커스텀 템플릿 연결:**
    -   "Movies List"라는 새 워드프레스 페이지를 만들었습니다.
    -   페이지 편집 화면에서 `Movies List` 커스텀 템플릿을 선택하여, 영화 목록이 프론트엔드 페이지에 올바르게 출력되는 것을 확인했습니다.
-   **카드형 HTML/CSS로 영화 목록 꾸미기:**
    -   썸네일, 정보, 설명 등을 포함한 시각적으로 매력적인 카드형 레이아웃으로 영화 목록을 디자인했습니다. 빠른 테스트를 위해 CSS는 템플릿 상단에 `<style>` 태그를 사용하여 직접 임베드했습니다.

WP_User_Query 및 관련 개념 실습 및 정리 사용자 데이터 검색을 위한 `WP_User_Query`를 탐색하고, PHP 템플릿과 Elementor의 관계도 검토했습니다.

-   **WP_User_Query 실습:**
    -   `WP_User_Query`를 활용하여 사이트 사용자 목록(관리자 본인 포함)을 번호(예: USER 0001)와 역할(role)을 포함한 카드 형식으로 출력하는 연습을 했습니다.
    -   역할, 메타 값 등 다양한 조건으로 사용자 쿼리 결과를 변경하며 확인했고, 사용자가 많아질수록 쿼리 결과가 다양해짐을 이해했습니다.
-   **Elementor/디자인 개념 통합:**
    -   PHP 템플릿과 Elementor의 관계를 이해했습니다.
    -   Elementor는 개별 페이지 디자인에 광범위한 자유를 제공하지만, 아카이브 및 단일 포스트 템플릿(예: 영화 아카이브 또는 단일 영화 상세 페이지)의 드래그 앤 드롭 디자인에는 **Elementor Pro의 테마 빌더**가 필수적임을 파악했습니다.
-   **VS Code 확장 및 에러 처리:**
    -   VS Code에서 PHP/워드프레스 함수 인식 문제는 실제 스크립트 실행에 영향을 미치지 않는 경우가 많음을 알게 되었습니다.
    -   워드프레스 개발에 유용한 VS Code 확장 기능을 탐색하고 일반적인 에러 디버깅 방법을 연습했습니다.

커스텀 필드 불일치 및 PHP/HTML 주석 문제 확인 및 해결 정리 실습 중 흔히 발생할 수 있는 두 가지 개발 문제를 만나 성공적으로 해결했습니다.

-   **커스텀 필드 슬러그 불일치:**
    -   **문제:** 영화 커스텀 포스트 타입의 "출시년도" 값이 "2011"로 입력되었음에도 화면에 표시되지 않았고, `get_post_meta`도 아무 값도 반환하지 않았습니다.
    -   **원인:** **커스텀 필드(메타 키) 이름(슬러그)의 불일치**였습니다. WCK에서 `release-year` (하이픈)로 설정했으나, 코드에서는 `release_year` (언더스코어)를 사용했습니다. 워드프레스는 정확한 일치를 요구합니다.
    -   **해결:** `print_r(get_post_meta(get_the_ID()))`를 사용하여 올바른 슬러그를 확인한 후, 코드를 `get_post_meta(get_the_ID(), 'release-year', true)`로 수정했습니다.
-   **PHP 및 HTML 주석 오류:**
    -   **문제:** 템플릿 파일(예: `get_header()` 뒤)에서 PHP 코드와 HTML 주석을 혼용할 때 오류가 발생했습니다.
    -   **원인:** HTML 주석(``)이 PHP 코드 블록(`<?php ... ?>`) 내부에 PHP 주석 문법 없이 직접 배치되었습니다.
    -   **해결:** HTML 주석 및 인라인 스타일이 **PHP 코드 블록 바깥**(즉, PHP 닫는 태그 `?>` 뒤, 다시 여는 태그 `<?php` 앞)에 위치하도록 조치했습니다.

## 🧠 배운 핵심 개념

-   **워드프레스 커스텀 개발 사이클:** 데이터 구조 설계(CPT, 커스텀 필드)부터 데이터 입력, 쿼리(`WP_Query`, `WP_User_Query`), 출력, 프론트엔드 디자인까지의 전체 흐름을 경험했습니다.
-   **커스텀 필드 키의 정확한 일치 중요성:** 커스텀 필드(메타 키) 이름은 정의(예: WCK)와 코드(`get_post_meta`) 사이에서 **완전히 동일**(하이픈, 언더스코어, 대소문자 구분 포함)해야만 올바른 데이터 검색이 가능함을 절실히 배웠습니다.
-   **PHP 및 HTML 주석 규칙:** HTML 주석은 PHP 코드 블록 _외부_에, PHP 주석 문법(`//` 또는 `/* */`)은 PHP 블록 _내부_에 사용해야 오류를 피할 수 있음을 명확히 이해했습니다.
-   **`print_r`을 활용한 디버깅:** `print_r(get_post_meta(get_the_ID()))`가 커스텀 필드 문제 해결을 위한 필수적인 디버깅 도구임을 깨달았으며, 저장된 메타 키를 직접 확인하여 문제를 빠르게 파악하는 데 큰 도움이 되었습니다.
-   **체계적인 문제 해결:** 커스텀 필드 문제 발생 시, 1) 커스텀 필드 슬러그 확인, 2) 슬러그와 코드의 `meta_key` 일치 여부 점검, 3) `print_r`로 실제 데이터 확인 순서로 접근하면 문제 해결이 빠르다는 체계적인 방법을 정립했습니다.
-   **워드프레스 핵심 쿼리:** 포스트 검색을 위한 `WP_Query`와 사용자 데이터 검색을 위한 `WP_User_Query`를 실무적으로 경험했습니다.

## 💡 실전 시행착오 및 팁

-   **커스텀 필드 메타 키 일관성:** 하이픈과 언더스코어의 작은 차이가 전체 기능에 영향을 미칠 수 있음을 직접 경험하며, 항상 꼼꼼하게 확인하는 습관의 중요성을 깨달았습니다.
-   **PHP 파일 구조 이해:** 워드프레스 템플릿 파일에서 PHP 태그(`<?php ... ?>`)를 열고 닫는 위치와 HTML/CSS 주석을 배치하는 방식이 파싱 오류를 방지하는 데 매우 중요하다는 것을 알게 되었습니다.
-   **디버깅 도구 `print_r`의 활용:** 이 함수는 데이터베이스에 저장된 정확한 메타 키를 신속하게 식별하여 문제 해결 시간을 크게 단축시키는 데 결정적인 역할을 했습니다.

## 🔜 이후 학습 방향

-   **WordPress REST API 기초 학습:** 워드프레스 데이터를 외부에서 활용하거나 외부 데이터를 가져오는 데 필수적인 REST API의 개념, 엔드포인트 구조, 인증 방식 등에 대해 학습할 예정입니다.
-   **소셜 미디어 자동화 툴 리서치 심화:** 다음 주 수요일까지 제출해야 하는 소셜 미디어 자동화 툴 리서치 과제를 심화하여 보고서 완성도를 높일 계획입니다.

## 📚 참고자료

-   [WP_Query 공식 문서](https://developer.wordpress.org/reference/classes/wp_query/)
-   [WP_User_Query 공식 문서](https://developer.wordpress.org/reference/classes/wp_user_query/)
-   [WCK (WordPress Creation Kit) 플러그인](https://wordpress.org/plugins/wck-custom-fields-and-custom-post-types-creator/)

### 🕸️ Docscraper 프로그램 진행 상황 (LLM 학습 도우미를 위한 웹 스크래핑 개발)

`docscraper` 개발은 현재 진행 중입니다. 이전 피드백을 통해 무작정 데이터를 긁어모으기보다는 **'의미 있는 데이터 선별 및 구조화'**에 대한 깊은 고민을 시작했습니다. 이로 인해 개발 방향을 재고했으며, 당분간은 워드프레스 학습에 우선순위를 두려 합니다. 앞으로는 명확한 목표를 가진 데이터 스크래핑에 집중해 효율성을 높일 계획입니다.
