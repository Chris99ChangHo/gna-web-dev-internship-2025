# 📅 Day 03 (2025-06-04, Wed)

## 🎓 Today's Work

**📌 Emphasis on experiencing the full flow of practical WordPress development and problem-solving from the development meeting.**   
**📌 Practical exercise on dummy user creation and user management features.**   
**📌 Practical understanding of WordPress User Roles.**   
**📌 Creating taxonomies (genre/director/country) using WCK and structuring movie data.**   
**📌 Practical exercise on taxonomy-based movie lists and filtering (by director, genre, etc.).**   
**📌 Implementation of `get_the_terms()`, `tax_query`, and a plot (Read More) toggle.**  
**📌 Full hands-on experience with the practical development flow (design→register→query→output→search/filter→UI/UX improvement) and debugging experience.**  

### Detailed Activities

**1. Development Meeting Highlights** I received key takeaways from the development meeting emphasizing the importance of experiencing the full flow of practical WordPress development and hands-on practice with common customization scenarios.

-   **Full Development Flow:** It was stressed that mastering the entire cycle—Data Structure Design → Input/Registration → Query → Output → Search/Filter → UI/UX Improvement—is crucial.
-   **Practical Customization:** I was encouraged to directly practice customization scenarios frequently used in real-world projects.
-   **Test Data Utilization:** Feedback emphasized actively using test data like dummy users/posts for experiments with various roles, conditions, classifications, and filters to gain practical experience.
-   **Problem-Solving Skills:** I received feedback advising, "Don't try to master it in a day or two; cultivate problem-solving skills by experimenting hands-on with various scenarios."
-   **Facing Challenges:** I was encouraged not to fear **common real-world problems (errors, filter failures, data structure confusion, etc.)** but to tackle them head-on.

**2. Dummy User Creation & User Management Practice** I performed practical exercises on creating dummy users and managing users within WordPress.

-   **2-1. Dummy User Creation:**
    -   I wrote code in `functions.php` to batch create dummy users with various roles (**administrator**, **editor**, **author**, **contributor**, **subscriber**) using a loop.
    -   I practiced using a large number of test users for search/sort/permission experiments, as would be done in a real-world scenario.
-   **2-2. Understanding WordPress User Roles:**
    -   I learned about the permissions and practical uses of each role (**administrator**, **editor**, **author**, **contributor**, **subscriber**).
    -   I understood that general users are typically **`Subscriber`**, while content writers/external contributors are usually **`Author`**/**`Contributor`**.
-   **2-3. User List Page Customization:**
    -   I implemented a user management page accessible only to administrators using **`current_user_can('administrator')`** for access restriction.
    -   I implemented a user addition form (with role assignment), search/filter/sort functionalities, role-based grouping, and USER numbering.
    -   I displayed user information (**ID**, **name**, **email**, **role**, **registration date**, etc.), ensuring **Edit**/**Delete** buttons were visible only to administrators and integrated with WordPress's built-in administration.
-   **2-4. User Search/Insertion/Modification/Deletion/Sorting:**
    -   I used **`WP_User_Query`** to retrieve all users, users by role, and users by specific conditions. I practiced outputting lists with ascending/descending sorting, role-based grouping, and USER numbering.
    -   I directly implemented a user search box, role-based filters, and a user addition form on the front end.

**3. Custom Taxonomy Practice with WCK** I practiced creating and managing custom taxonomies using the WCK plugin.

-   **3-1. Creating Taxonomies with WCK Taxonomy Creator:**
    -   I created new taxonomies like **`genre`**, **`director`**, and **`country`**.
    -   I linked each taxonomy to the **`movie`** custom post type and specified options (hierarchical/non-hierarchical, labels, slug, etc.).
-   **3-2. Data Input/Management for Taxonomies in Admin:**
    -   I learned to directly input/select genre, director, and country within the taxonomy boxes when registering/editing movies.
    -   I also practiced selecting multiple classifications and adding new ones.

**4. Taxonomy-based Movie List/Filtering Practice** I implemented functionalities to display and filter movie lists based on taxonomies.

-   **4-1. Creating a Card-style Movie List Template:**
    -   I created a template displaying **thumbnails**, **title**, **director**, **release year**, **genre**, **country**, **rating**, **actors**, **plot summary**, etc., with a card-style CSS design applied.
-   **4-2. Outputting Taxonomy-based Data:**
    -   I used **`get_the_terms()`** to output taxonomy values like genre, director, and country, and **`get_post_meta()`** to output custom field values like rating and actors.
-   **4-3. Implementing Director-based Filtering:**
    -   I displayed a list of directors as buttons/links at the top. Clicking them filtered the movie list to show only movies by that director using **`WP_Query`**'s **`tax_query`**.
    -   An **“All”** button was included to clear filters and view all movies.
    -   URL parameters like **`?director=slug`** were used for passing filter criteria.
-   **4-4. Practical Significance:**
    -   I clearly understood the **difference between custom fields and taxonomies** (taxonomies are far more efficient for classification/search/filter).
    -   I deeply felt the practical strengths of taxonomy-based filtering/Browse.

**5. Plot (Read More) Toggle Feature Implementation** I implemented a "Read More" toggle for movie plot summaries on cards.

-   When a plot summary was long, only a portion was shown, with the full content expanding upon clicking "Read More." Each card operated independently using unique IDs.

**6. Problem Solving & Debugging Experience** I directly encountered and resolved various development issues during practice.

-   I directly fixed code errors, **WP_Query** duplication issues, and PHP commenting mistakes.
-   I gained experience in quickly resolving errors by checking error messages with **`WP_DEBUG`**.
-   I solved common real-world problems like taxonomy/custom field confusion and filter malfunctions.

**7. Practical Workflow & Today's Significance** Through today's practice, I grasped the overall practical development flow and the significance of each element.

-   I experienced the complete process: designing data structures (**taxonomies** with WCK) → inputting data in the admin → implementing taxonomy-based querying/filtering/output on the front end.
-   I fully mastered the most frequently used customization patterns in practical development.
-   I genuinely understood the **practical difference between custom fields and taxonomies** and **when/why to use taxonomies**.

## 🧠 Key Concepts Learned

-   **WordPress Custom Development Cycle:** I experienced the full flow from data structure design (**CPT**, custom fields, taxonomies) through data input, querying (**`WP_Query`**, **`WP_User_Query`**), output, search/filter, and UI/UX improvement.
-   **Understanding User Roles:** I gained a clear understanding of the permissions and practical application scenarios for WordPress's built-in user roles (**administrator**, **editor**, **author**, **contributor**, **subscriber**).
-   **Practical Difference between Custom Fields & Taxonomies:** I directly felt the efficiency and importance of taxonomies for data classification and filtering, and I learned when to use each tool appropriately.
-   **`WP_User_Query` and `tax_query` Utilization:** I gained practical experience using key queries for user data retrieval and taxonomy-based content filtering.
-   **Debugging and Problem Solving:** I experienced practical debugging techniques, including using **`WP_DEBUG`** and **`print_r`** for data inspection, and learned how to resolve common real-world development issues.

## 💡 Practical Trial-and-Error and Tips

-   **Importance of Dummy Data:** Actively using dummy user and post data with various roles/conditions/classifications proved highly useful for gaining practical experience and testing diverse scenarios.
-   **Permission Setting (`current_user_can`):** Understanding how to restrict access to specific pages or functionalities based on roles using **`current_user_can('administrator')`** helped me grasp the importance of security and user management in real services.
-   **URL Parameter-based Filtering:** Implementing filtering by dynamically manipulating **`WP_Query`**'s **`tax_query`** using URL parameters proved to be a very practical method.
-   **Separation of Code & HTML/CSS:** During the plot toggle feature implementation, I re-confirmed the importance of assigning unique IDs to each card for independent operation and managing HTML/CSS separately from PHP code.
-   **Facing and Resolving Problems:** Directly encountering and resolving common real-world problems like **WP_Query** duplication, PHP commenting mistakes, and taxonomy/custom field confusion helped me build practical problem-solving skills.

## 🔜 Next Steps

-   **WordPress REST API Basics:** I plan to learn about the concepts, endpoint structure, and authentication methods of the REST API, which is essential for utilizing WordPress data externally or fetching external data.
-   **Social Media Automation Tool Research Deep Dive:** I will deepen my research for the social media automation tool assignment due tomorrow to enhance the report's completeness.

### 🕸️ Docscraper Program Update (Web Scraping Development for LLM Learning Assistant)

**`Docscraper`** development is currently underway. Following earlier feedback, I've shifted focus from indiscriminate data scraping to deeply considering **'how to select and structure meaningful data.'** This has led to a re-evaluation of the development direction, and for now, I'm prioritizing WordPress learning. Moving forward, I plan to enhance efficiency by focusing on goal-oriented data scraping rather than collecting data aimlessly.

---

# 📅 Day 03 (2025-06-04, Wed)

## 🎓 Today's Work

**📌 개발 미팅에서 워드프레스 실무 개발의 전체 흐름과 문제 해결 강조.**   
**📌 더미 유저 자동 생성 및 유저 관리 기능 실습.**   
**📌 워드프레스 역할(Role)의 실무적 이해.**   
**📌 WCK를 활용한 텍소노미(장르/감독/국가) 생성 및 영화 데이터 구조화.**   
**📌 텍소노미 기반 영화 리스트 및 필터링(감독별, 장르별 등) 실습.**   
**📌 `get_the_terms()`, `tax_query` 활용 및 줄거리(Read More) 토글 구현.**   
**📌 실무 개발 흐름(설계→등록→쿼리→출력→검색/필터→UI/UX 개선) 완전 체험 및 디버깅 경험.**  

### Detailed Activities

**1. 개발 미팅에서 들은 내용** 워드프레스 실무 개발의 전체 흐름을 경험하는 것의 중요성과 현업에서 자주 쓰는 커스터마이징 시나리오 실습에 대한 강조를 들었습니다.

-   **전체 개발 흐름:** 데이터 구조 설계 → 입력/등록 → 쿼리 → 출력 → 검색/필터 → UI/UX 개선의 사이클을 체득하는 것이 중요함을 강조했습니다.
-   **실무 커스터마이징:** 실제 현업에서 자주 쓰는 커스터마이징 시나리오를 직접 실습해 볼 것을 권장받았습니다.
-   **테스트 데이터 활용:** 더미 유저/포스트 등 테스트 데이터를 적극 활용하여 다양한 역할, 조건, 분류, 필터 실험을 통해 실무 감각을 익히라는 피드백을 받았습니다.
-   **문제 해결 능력:** "하루이틀 만에 마스터하려 하지 말고, 다양한 시나리오를 직접 손으로 실험해보며 문제 해결 능력을 기르라"는 피드백을 받았습니다.
-   **문제 직면:** **실무에서 자주 겪는 문제(에러, 필터 불가, 데이터 구조 혼동 등)**도 겁내지 말고 직접 부딪혀볼 것을 독려받았습니다.

**2. 더미 유저 생성 및 유저 관리 실습** 워드프레스에서 더미 유저를 생성하고 이를 바탕으로 유저 관리 기능을 실습했습니다.

-   **2-1. 더미 유저 생성:**
    -   `functions.php`에 반복문을 사용하여 다양한 역할(**관리자**, **에디터**, **저자**, **기여자**, **구독자**)의 더미 유저를 일괄 생성했습니다.
    -   실무에서 대량의 테스트 유저를 활용하여 검색/정렬/권한 실험을 진행했습니다.
-   **2-2. 워드프레스 유저 역할(Role) 이해:**
    -   각 역할별 권한과 실무 용도를 학습했습니다. (**관리자**, **에디터**, **저자**, **기여자**, **구독자**)
    -   일반 유저는 대부분 **`Subscriber`** 역할, 필진/외부 기고자는 **`Author`**/**`Contributor`** 역할로 지정됨을 이해했습니다.
-   **2-3. 유저 리스트 페이지 커스터마이징:**
    -   **`current_user_can('administrator')`**를 활용하여 관리자만 접근 가능한 유저 관리 페이지를 구현했습니다.
    -   유저 추가 폼(역할 지정 기능 포함), 검색/필터/정렬 기능, 역할별 그룹핑, USER 넘버링 기능을 구현하여 유저 리스트를 커스터마이징했습니다.
    -   유저 정보(**아이디**, **이름**, **이메일**, **역할**, **등록일** 등)를 출력하고, 관리자 권한에서만 **Edit**/**Delete** 버튼이 노출되도록 설정하며 워드프레스 내장 관리자와 연동했습니다.
-   **2-4. 유저 검색/삽입/수정/삭제/정렬:**
    -   **`WP_User_Query`**를 활용하여 전체 유저, 역할별 유저, 조건별 유저를 불러오고, 오름차순/내림차순 정렬, 역할별 그룹핑, USER 넘버링 등을 포함한 리스트를 출력했습니다.
    -   프론트엔드에 직접 유저 검색창, 역할별 필터, 유저 추가 폼을 구현했습니다.

**3. WCK를 활용한 커스텀 텍소노미 실습** WCK 플러그인을 사용하여 커스텀 텍소노미를 생성하고 관리하는 방법을 실습했습니다.

-   **3-1. WCK Taxonomy Creator로 텍소노미 생성:**
    -   **`genre`**(장르), **`director`**(감독), **`country`**(국가) 등 새로운 텍소노미를 생성했습니다.
    -   각 텍소노미를 **`movie`**(영화) 커스텀 포스트 타입에 연결하고, 옵션(계층형/비계층형, 라벨, 슬러그 등)을 지정했습니다.
-   **3-2. 관리자에서 텍소노미 데이터 입력/관리:**
    -   영화 등록/수정 시 장르, 감독, 국가를 텍소노미 박스에서 직접 입력/선택하는 방법을 익혔습니다.
    -   여러 분류를 복수 선택하거나, 새로운 분류를 추가하는 실습도 진행했습니다.

**4. 텍소노미 기반 영화 리스트/필터링 실습** 텍소노미를 기반으로 영화 리스트를 출력하고 필터링하는 기능을 구현했습니다.

-   **4-1. 카드형 영화 리스트 템플릿 제작:**
    -   **썸네일**, **제목**, **감독**, **출시년도**, **장르**, **국가**, **평점**, **배우**, **줄거리** 등을 출력하는 카드형 템플릿을 제작하고 CSS 디자인을 적용했습니다.
-   **4-2. 텍소노미 기반 데이터 출력:**
    -   **`get_the_terms()`**를 사용하여 장르, 감독, 국가 등 텍소노미 값을 출력하고, **`get_post_meta()`**로 평점, 배우 등 커스텀 필드 값을 출력했습니다.
-   **4-3. 감독별 필터(조회) 기능 구현:**
    -   상단에 감독 리스트를 버튼/링크로 출력하고, 클릭 시 해당 감독의 영화만 **`WP_Query`**의 **`tax_query`**를 사용하여 필터링되도록 구현했습니다.
    -   **“All”** 버튼으로 필터를 해제하여 전체 영화를 다시 볼 수 있도록 했습니다.
    -   URL 파라미터로 **`?director=슬러그`**를 전달하는 방식을 사용했습니다.
-   **4-4. 실무적 의미:**
    -   **커스텀 필드와 텍소노미의 차이점**(**분류/검색/필터에 텍소노미가 훨씬 효율적**)을 명확히 이해했습니다.
    -   텍소노미 기반 필터/조회가 실무에서 가지는 강력한 이점을 체감했습니다.

**5. 줄거리(Read More) 토글 기능 구현** 영화 카드에서 줄거리가 길 경우 일부만 보여주고, "Read More" 클릭 시 전체 내용이 펼쳐지도록 하는 기능을 구현했습니다.

-   각 카드별 고유 ID를 사용하여 독립적으로 동작하도록 만들었습니다.

**6. 문제 해결 & 디버깅 경험** 실습 과정에서 발생한 여러 문제를 직접 해결하고 디버깅 경험을 쌓았습니다.

-   코드 에러, **WP_Query** 중복 문제, PHP 주석 실수 등을 직접 수정했습니다.
-   **`WP_DEBUG`**를 활용하여 에러 메시지를 확인하고 문제를 빠르게 해결하는 경험을 했습니다.
-   텍소노미/커스텀 필드 혼동, 필터 동작 안 함 등 실무에서 자주 겪는 문제들을 직접 해결했습니다.

**7. 실무 흐름 및 오늘의 의미** 오늘의 실습을 통해 실무 개발의 전체적인 흐름과 각 요소의 중요성을 체득했습니다.

-   WCK로 데이터 구조(텍소노미)를 설계하고, 관리자에서 데이터를 입력하며, 프론트엔드에서 텍소노미 기반 조회/필터/출력을 구현하는 과정을 경험했습니다.
-   실무에서 가장 많이 쓰는 커스터마이징 패턴을 완전히 익혔습니다.
-   **커스텀 필드와 텍소노미의 실질적 차이**를 이해하고, **언제/왜 텍소노미를 써야 하는지**를 실제로 체감했습니다.

## 🧠 Key Concepts Learned

-   **워드프레스 커스텀 개발 전체 사이클:** 데이터 구조 설계(**CPT**, 커스텀 필드, 텍소노미)부터 데이터 입력, 쿼리(**`WP_Query`**, **`WP_User_Query`**), 출력, 검색/필터, UI/UX 개선까지의 전체 흐름을 경험했습니다.
-   **유저 역할(Role)의 이해:** 워드프레스의 기본 유저 역할(`administrator`, `editor`, `author`, ``contributor`,`subscriber`)별 권한과 실무 적용 시나리오를 명확히 이해했습니다.
-   **커스텀 필드와 텍소노미의 실질적 차이:** 데이터 분류 및 필터링 관점에서 텍소노미의 효율성과 중요성을 체감하고, 각 도구의 적절한 사용 시점을 파악했습니다.
-   **`WP_User_Query` 및 `tax_query` 활용:** 사용자 데이터 조회 및 텍소노미 기반 콘텐츠 필터링을 위한 핵심 쿼리 사용법을 실무적으로 익혔습니다.
-   **디버깅 및 문제 해결:** **`WP_DEBUG`** 활용법과 **`print_r`**을 통한 데이터 확인 등 실무에서 자주 발생하는 에러와 문제 해결 노하우를 직접 경험했습니다.

## 💡 Practical Trial-and-Error and Tips

-   **더미 데이터 활용의 중요성:** 다양한 역할/조건/분류의 더미 유저 및 포스트 데이터를 활용하여 실무 감각을 익히고 다양한 시나리오를 테스트하는 것이 매우 유용했습니다.
-   **권한 설정(`current_user_can`):** 특정 페이지나 기능에 대한 접근을 역할 기반으로 제한하는 방법(`current_user_can('administrator')`)을 통해 실제 서비스의 보안 및 사용자 관리 중요성을 이해했습니다.
-   **URL 파라미터 기반 필터링:** URL 파라미터를 활용하여 **`WP_Query`**의 **`tax_query`**를 동적으로 조작하는 필터링 구현 방식이 실무에서 매우 유용함을 체감했습니다.
-   **코드와 HTML/CSS의 분리:** 줄거리 토글 기능 구현 시, 각 카드별 고유 ID를 부여하여 독립적으로 동작하게 하는 방식과 HTML/CSS를 PHP 코드와 분리하여 관리하는 중요성을 다시 한번 확인했습니다.
-   **문제 직면 및 해결:** **WP_Query** 중복, PHP 주석 실수, 텍소노미/커스텀 필드 혼동 등 실무에서 흔히 겪는 문제를 직접 부딪혀 해결하며 실질적인 문제 해결 능력을 길렀습니다.

## 🔜 Next Steps

-   **WordPress REST API 기초 학습:** 워드프레스 데이터를 외부에서 활용하거나 외부 데이터를 가져오는 데 필수적인 REST API의 개념, 엔드포인트 구조, 인증 방식 등에 대해 학습할 예정입니다.
-   **소셜 미디어 자동화 툴 리서치 심화:** 내일까지 제출해야 하는 소셜 미디어 자동화 툴 리서치 과제를 심화하여 보고서 완성도를 높일 계획입니다.

### 🕸️ Docscraper 프로그램 진행 상황 (LLM 학습 도우미를 위한 웹 스크래핑 개발)

**`Docscraper`** 개발은 현재 진행 중입니다. 이전 피드백을 통해 무작정 데이터를 긁어모으기보다는 **'의미 있는 데이터 선별 및 구조화'**에 대한 깊은 고민을 시작했습니다. 이로 인해 개발 방향을 재고했으며, 당분간은 워드프레스 학습에 우선순위를 두려 합니다. 앞으로는 명확한 목표를 가진 데이터 스크래핑에 집중해 효율성을 높일 계획입니다.

