
# 📅 Day 03 (2025-06-25, Wed)

## 🎓 What I Did Today

**📌 Meeting Summary: Conducted progress report and received feedback on the DevNewsHub mini-project.**   
**📌 Modularized the `functions.php` file in the WordPress theme and improved code structure.**   
**📌 Implemented a popular news page based on view counts with yearly filtering, and enhanced the news search functionality.**   
**📌 During implementation, discovered and acknowledged issues with the popular news REST API's JSON response, CSS non-application, and comment count endpoint, and began exploring solutions.**  

### Detailed Activities

**1. DevNewsHub Mini-Project Progress Report and Feedback Session**

-   **Morning Meeting Participation:** The day began with a development meeting where I reported on the progress of the DevNewsHub mini-project and outlined future plans.
-   **Attempted Application Service Implementation:** Following yesterday's advice from the senior developer to attempt implementing an application service that interacts with WordPress via REST API, I began a practical exercise to build a mobile news app using React Native Expo. Expo installation was completed yesterday, and this morning I attempted a simple data fetching test. However, I encountered difficulties adapting to the changed environment (e.g., using `index.tsx` instead of `app.js`), and data was not being properly received. I temporarily paused this task to focus on other work.
-   **Ongoing Feedback Request and Learning Advice:** The senior developer requested continuous progress sharing during development meetings for feedback purposes, and advised me to consistently pursue studies in areas like REST API and plugin development.

**2. WordPress Theme Modularization and Structure Improvement**

-   In the afternoon, I initiated a modularization effort to manage the increasing complexity of the `functions.php` file.
-   I created an `inc` folder and separated PHP files into functional categories such as `admin-customizations.php`, `ajax-handlers.php`, `cron-jobs.php`, `enqueue.php`, `one-time-scripts.php`, and `utility-functions.php`. The main `functions.php` now includes these separate files.
-   To further organize the code, I created `css` and `js` folders for custom CSS and JavaScript files, respectively, ensuring a more systematic theme structure.

**3. DevNewsHub: View Count-Based News Feature Development and Debugging**

-   **Feature Implementation:** I implemented a popular news page on the WordPress homepage, accessible via a button, leveraging a REST API endpoint that sorts news by a custom view count field. I also added a yearly dropdown filter on the page to display popular articles from specific years.
-   **News Search Functionality Enhancement:** I refined the output display of the existing news search feature. To improve readability, each news item is now formatted to show 'News Source | Category, Article Title, Body Summary (including search term), Date, Thumbnail'. Furthermore, I improved the sorting logic to use the 'actual publication date' instead of the scrape/upload date, which was crucial for data accuracy and user experience, as previous results were often in reverse order or lacked real publication dates.
-   **Challenges Encountered and Debugging:**
    -   An issue arose where the `devnewshub/v1/popular-news` REST API was not returning JSON data. I began debugging by rolling back the code to a previously working version to isolate the cause.
    -   **Related Issue:** It was identified that the date (`news-published-date`)-based yearly filtering and view count (`post-views`)-based sorting logic were not perfectly functional.
    -   **Related Issue:** The custom thumbnail size (`news-search-thumb`, 400x300) defined in `functions.php` was not being applied to the popular news section, with the default `medium` size loading instead.
    -   **Core Issue (Diagnosis):** Despite `popular-news-styles.css` being correctly enqueued in `functions.php`, its styles, including CSS grid layouts, were not applying on the web page.
    -   **Additional Issue (Comment Count Endpoint):** An attempt to create a REST API endpoint for sorting news by comment count was also made, but similar to other API issues, data was not being received correctly, leading to a temporary halt of this feature implementation.

## 🧠 Key Concepts Learned

-   **Importance of WordPress Theme Modularization:** Gained practical experience and understood the benefits of organizing the `functions.php` file into functional segments (e.g., `enqueue.php`, `utility-functions.php`) to enhance code maintainability and readability.
-   **Advanced REST API Usage and Debugging:** Learned about the complexity of implementing compound sorting (`orderby`) and filtering (`meta_query`) logic based on custom fields (view count, publication date) and the systematic approach to diagnosing API response errors through code rollback and re-verification.
-   **Diagnosing Front-end Resource (CSS/JS) Loading Issues:** Experienced situations where CSS failed to apply despite `wp_enqueue_style` being correctly set, reinforcing the need for in-depth debugging using browser developer tools (`Network`, `Elements`, `Console` tabs), and considering cache issues or file path errors.

## 💡 Practical Learnings and Tips

-   **Handling API JSON Response Errors:** When API JSON data unexpectedly fails to return during development, rolling back to a previously working version where JSON was correctly received proved effective in quickly pinpointing the source of the problem. It's often more efficient to retreat and stabilize the foundation than to push forward blindly.
-   **WordPress Image Size Application Issues:** If custom thumbnail sizes defined with `add_image_size` are not loading correctly on the front end, it's crucial to explicitly verify if the API response provides the correct URL for that size and if the front end is accurately utilizing that URL.
-   **Systematic Debugging Approach:** Reconfirmed the effectiveness of recognizing and resolving issues step-by-step by utilizing `error_log` within the code, checking server-side `debug.log` and `error.log` files, and inspecting content in browser developer tools (console, network tab, etc.).

## 🔜 Next Steps

-   **Most Pressing Issue Resolution:** Prioritize resolving the JSON response issues and CSS non-application problems of the `DevNewsHub` view count-based news endpoint. This includes gathering browser developer tool information and re-verifying file paths as requested by the senior developer.
-   **REST API and Thumbnail Logic Improvement:** Once JSON response issues are resolved, optimize the yearly filtering and view count sorting logic for the `popular-news` endpoint, and complete the work to ensure the `news-search-thumb` (thumbnail size) is correctly applied across all popular news sections.
-   **New Feature Implementation Progress:** Plan to begin the development and page implementation for the comment count-based popular news endpoint, as well as the initial stages of Expo app development.
-   **In-depth REST API Research:** Plan to conduct in-depth research on general REST API concepts and various application methods, beyond just WordPress REST API.
-   **Code Modularization Principles Research:** Intend to study code modularization principles and effective patterns applicable across various programming languages, including PHP.
-   **Advanced React Native Expo Utilization Research:** Aim to research best practices, performance optimization techniques, and advanced feature implementation methods for React Native app development using the Expo framework.

----------

# 📅 3일차 (2025-06-25, 수)

## 🎓 오늘 한 일

**📌 개발 미팅 요약: DevNewsHub 미니 프로젝트 진행 상황 보고 및 피드백을 진행했습니다.**   
**📌 워드프레스 테마의 `functions.php` 모듈화 및 코드 구조를 개선했습니다.**   
**📌 조회수 순 인기 뉴스 페이지 구현 및 연도별 필터링 기능을 추가했으며, 뉴스 검색 기능도 개선했습니다.**   
**📌 구현 과정에서 인기 뉴스 REST API의 JSON 응답 오류, CSS 미적용, 댓글 수 엔드포인트 문제 등을 발견하고 인지하여, 해결 방안을 모색하기 시작했습니다.**  

### 상세 활동

**1. DevNewsHub 미니 프로젝트 진행 상황 보고 및 프로그레스 보고**

-   **오전 미팅 참여:** 하루는 개발 미팅으로 시작되었으며, DevNewsHub 미니 프로젝트의 진행 상황과 앞으로의 계획에 대해 보고했습니다.
-   **응용 서비스 구현 실습 시도:** 어제 개발 선임으로부터 워드프레스와 REST API를 활용해 데이터를 "주고받는" 응용 서비스 구현에 도전해보라는 조언을 받았습니다. 이를 바탕으로 React Native 기반의 Expo를 활용하여 워드프레스 REST API와 연동되는 모바일 뉴스 앱을 구현해보는 실습을 진행하기 시작했습니다. 어제 Expo 설치를 완료했으며, 오전 중 간단하게 데이터를 받아오는 실습을 시도했습니다. 하지만 `app.js` 대신 `index.tsx`에서 작업하는 등 변경된 환경에 적응하는 데 어려움을 겪었고, 데이터가 제대로 넘어오지 않는 문제가 발생하여 일단 이 작업을 잠시 중단하고 다른 업무를 진행했습니다.
-   **지속적인 피드백 요청 및 학습 조언:** 개발 선임으로부터 피드백을 위해 지속해서 개발 미팅 때 진척 상황을 공유해달라는 요청을 받았으며, REST API나 플러그인 개발과 같은 학습도 꾸준히 이어갈 것을 조언받았습니다.

**2. 워드프레스 테마 모듈화 및 구조 개선**

-   오후에 `functions.php` 파일이 길어지는 문제를 해결하기 위해 코드를 모듈화하는 작업을 진행했습니다.
-   `inc` 폴더를 생성하고 `admin-customizations.php`, `ajax-handlers.php`, `cron-jobs.php`, `enqueue.php`, `one-time-scripts.php`, `utility-functions.php` 등 기능별 PHP 파일들을 분리하여 정리했습니다. `functions.php`에서는 이 파일들을 불러와 사용하도록 변경했습니다.
-   테마의 커스텀 CSS 파일들을 저장하는 `css` 폴더와 커스텀 JavaScript 파일들을 저장하는 `js` 폴더를 각각 생성하여 코드를 체계적으로 분리했습니다.

**3. DevNewsHub: 조회수 기반 뉴스 기능 개발 및 디버깅**

-   **기능 구현:** 조회수 커스텀 필드를 활용한 REST API 엔드포인트를 기반으로, 워드프레스 홈에 조회수 순 인기 뉴스 페이지를 구현하고 버튼을 추가했습니다. 페이지 내에 연도 드롭다운 필터링 기능을 넣어 연도별로 조회수가 높은 기사를 볼 수 있도록 구현했습니다.
-   **뉴스 검색 기능 개선:** 뉴스 검색 기능의 결과 출력 방식을 개선했습니다. 시인성 향상을 위해 각 뉴스 항목이 '뉴스 출처 | 카테고리, 기사 제목, 본문 요약(검색어 포함), 날짜, 썸네일' 순으로 표시되도록 레이아웃을 조정했습니다. 더불어, 스크랩 시점의 업로드(퍼블리시) 날짜가 아닌 '실제 발행일' 기준으로 정렬되도록 로직을 개선하여 데이터의 정확성과 사용 편의성을 높였습니다. 이는 데이터가 역순으로 보이거나 실제 발행일이 없는 기사에 대한 시급한 개선점이었습니다.
-   **직면 문제 및 디버깅:**
    -   `devnewshub/v1/popular-news` REST API에서 JSON 데이터가 넘어오지 않는 문제가 발생했습니다. 원인 파악을 위해 코드를 이전 정상 동작 버전으로 롤백하고 디버깅을 시작했습니다.
    -   **연관 문제:** 날짜(`news-published-date`) 기반 연도 필터링 및 조회수(`post-views`) 기반 정렬 로직이 완벽하게 동작하지 않는 문제가 파악되었습니다.
    -   **연관 문제:** `functions.php`에서 정의한 썸네일 크기(`news-search-thumb`, 400x300)가 인기 뉴스 섹션에 적용되지 않고 기본 `medium` 사이즈로 로드되는 문제도 확인했습니다.
    -   **핵심 문제 (진단):** `popular-news-styles.css` 파일이 `functions.php`에서 올바르게 enqueue되었음에도 불구하고, 실제 웹 페이지에서 CSS 그리드 레이아웃을 포함한 스타일이 전혀 적용되지 않는 문제가 지속되고 있습니다.
    -   **추가 문제 (댓글 수 엔드포인트):** 댓글 수를 기준으로 뉴스를 정렬하기 위한 REST API 엔드포인트를 작성했으나, 마찬가지로 데이터가 제대로 넘어오지 않아 이 기능 구현도 잠정 중단된 상태입니다.

## 🧠 배운 핵심 개념

-   **워드프레스 테마 모듈화의 중요성:** `functions.php` 파일의 기능별 분리(예: `enqueue.php`, `utility-functions.php`)를 통해 코드 관리 효율성과 가독성을 높이는 방법을 실제 적용하며 그 이점을 체감했습니다.
-   **REST API의 고급 활용 및 디버깅:** 커스텀 필드(조회수, 발행일)를 활용한 복합 정렬(`orderby`) 및 필터링(`meta_query`) 로직 구현의 복잡성과, API 응답 오류 발생 시 체계적인 코드 롤백 및 재확인 과정을 통한 문제 진단 접근법을 배웠습니다.
-   **프런트엔드 리소스(CSS/JS) 로딩 문제 진단:** `wp_enqueue_style`이 올바르게 되어 있어도 CSS가 적용되지 않을 수 있음을 경험하며, 캐시 문제, 파일 경로 오류, 브라우저 개발자 도구(`Network`, `Elements`, `Console` 탭)를 통한 심층 진단의 필요성을 재확인했습니다.

## 💡 실전 시행착오 및 팁

-   **API JSON 응답 오류 발생 시 대처:** 개발 중 API에서 JSON 데이터가 갑자기 넘어오지 않는 문제가 발생했을 때, 최근 변경 사항을 모두 되돌려 JSON이 정상적으로 오던 지점으로 돌아가는 것이 문제의 원인을 빠르게 특정하는 데 효과적임을 경험했습니다. 무작정 앞으로 나아가기보다 후퇴하여 기반을 다지는 것이 중요합니다.
-   **워드프레스 이미지 크기 적용 문제:** `add_image_size`로 정의한 커스텀 썸네일 크기가 프런트엔드에서 제대로 로드되지 않는 문제는, API 응답에서 해당 크기의 URL이 제대로 제공되는지, 그리고 프런트엔드에서 그 URL을 정확히 사용하는지 명시적으로 확인해야 함을 알게 되었습니다.
-   **체계적인 디버깅 접근:** 코드 내 `error_log`를 활용하고, 서버의 `debug.log`, `error.log` 파일 그리고 브라우저 개발자 도구(콘솔, 네트워크 탭 등)에서 나타나는 내용들을 통해 문제를 인식하고 단계별로 해결하는 것이 효과적임을 다시 한번 확인했습니다.

## 🔜 이후 학습 방향

-   **가장 시급한 문제 해결:** `DevNewsHub` 조회수 기반 뉴스 엔드포인트의 JSON 응답 문제 및 CSS 미적용 문제를 최우선으로 해결할 예정입니다. 개발 선임이 요청한 브라우저 개발자 도구 정보 수집과 파일 경로 재확인을 진행할 것입니다.
-   **REST API 및 썸네일 로직 개선:** JSON 응답 문제가 해결되면, `popular-news` 엔드포인트의 연도 필터링 및 조회수 정렬 로직을 최적화하고, 썸네일 크기(`news-search-thumb`)가 모든 인기 뉴스 섹션에 올바르게 적용되도록 개선 작업을 완료할 예정입니다.
-   **신규 기능 구현 진행:** 댓글 순 인기 뉴스 엔드포인트 개발 및 페이지 구현, 그리고 Expo 앱 개발 초기 단계에 착수할 계획입니다.
-   **REST API 심화 연구:** 워드프레스 REST API뿐만 아니라 일반적인 REST API 개념과 다양한 활용 방안에 대해 심층적으로 연구할 예정입니다.
-   **코드 모듈화 원칙 연구:** PHP를 포함한 다양한 프로그래밍 언어에서 적용되는 코드 모듈화 원칙과 효과적인 패턴에 대해 학습할 것입니다.
-   **React Native Expo 활용 심화 연구:** Expo 프레임워크를 활용한 React Native 앱 개발의 베스트 프랙티스, 성능 최적화 기법, 그리고 고급 기능 구현 방식에 대해 더 깊이 연구할 것입니다.
