# 📝 Week 07 Reflection (2025.06.23 ~ 06.27)

## ✅ Key Tasks This Week

📌 **ISAAC Painting client site migration and responsive optimization completed:** Successfully migrated all pages and optimized for mobile/tablet views.   
📌 **DevNewsHub mini-project data integrity and feature enhancement:** * Implemented "actual published date" custom field (`news-published-date`) to ensure data accuracy for automated news uploads and improve WP admin convenience. * Developed a popular news page based on view counts with yearly filtering, and enhanced existing news search functionality.   
📌 **WordPress theme code modularization and structure improvement:** Refactored `functions.php` into functional segments, enhancing code maintainability and readability.   
📌 **Initial development of React Native (Expo) mobile news app:** Successfully integrated with the WordPress REST API to fetch and display news data in a basic mobile application.   
📌 **Company Korean website AI rewriting and comparison tool development:** Created a Python script using `pandas` and `difflib` to visually compare original Korean website content with AI-rewritten versions.   
📌 **Improved UI stability with JavaScript:** Implemented search input field reset functionality and applied event delegation for dynamic elements in the news search UI.  

## 🧠 What I Learned

-   **Data Integrity in Automated Processes:** Understood the critical importance of storing accurate context (e.g., actual publication date vs. upload date) for automated data, leveraging custom fields and correctly setting `meta_type='DATETIME'` in WordPress queries.
    
-   **WordPress Theme Modularization:** Gained practical experience in organizing a growing `functions.php` file into logical, maintainable segments (e.g., `enqueue.php`, `utility-functions.php`).
    
-   **Advanced REST API Usage and Debugging:** Learned the complexities of implementing compound sorting (`orderby`) and filtering (`meta_query`) with custom fields, and the systematic approach to diagnosing API response errors and CSS loading issues through code rollback and browser developer tools.
    
-   **React Native Core Concepts for App Development:** Applied fundamental React Native hooks (`useState` for state management, `useEffect` for side effects like data fetching) and components (`FlatList` for efficient list rendering) in a real-world scenario.
    
-   **Event Delegation for Dynamic UI:** Understood and implemented event delegation as a crucial technique for efficiently handling events on dynamically added or restored DOM elements, improving UI stability and performance.
    
-   **Text Similarity Comparison with Python:** Explored `difflib` for identifying and visualizing differences between text strings, a valuable skill for evaluating AI-generated content and content rewriting tasks.
    

## 🔧 Technical Problem-Solving Experience

-   **WordPress REST API JSON Response & CSS Application Issues:**
    
    -   **Problem:** The `devnewshub/v1/popular-news` REST API unexpectedly returned no JSON data, and `popular-news-styles.css` was not applying on the web page. A similar issue occurred with a new comment count endpoint.
        
    -   **Resolution:** Employed a systematic debugging approach: rolled back code to a last-known working state, used `error_log` for internal code tracing, and leveraged browser developer tools (Network, Elements, Console) to inspect CSS loading paths, selector specificity, and API responses. Identified a critical bug where `update_post_meta` referenced a wrong variable (`$extracted_date_string` instead of `$extracted_datetime_string`), leading to time information loss, and recognized how `meta_query` conditions could inadvertently exclude posts from updates.
        
-   **Custom Thumbnail Size Loading Issue:**
    
    -   **Problem:** A custom thumbnail size (`news-search-thumb`, 400x300) defined in `functions.php` was not applying to the popular news section, defaulting to `medium`.
        
    -   **Resolution:** Realized the need to explicitly verify if the API response correctly provides the URL for the custom size and if the front-end code is correctly utilizing that URL. (Further action pending resolution of API JSON issues).
        
-   **React DevTools Setup and PATH Environment Issues:**
    
    -   **Problem:** Encountered command recognition and PATH-related issues during the global installation and execution of React DevTools (standalone version).
        
    -   **Resolution:** Identified the correct command (`react-devtools` instead of `react devtools`) and resolved PATH configuration to enable proper tool execution, confirming DevTools' role as a separate debugging utility for component state and props.
        

## 💡 Reflections

-   **The Power of Rollback:** When faced with complex, interconnected bugs or prolonged debugging, bravely rolling back to a stable previous commit proved to be a highly efficient strategy, saving significant time and providing a clearer path forward.
    
-   **Practical Application Bridges Theory and Practice:** Moving beyond merely fetching data to building a simple application that sends and receives data bidirectionally with WordPress REST API was invaluable. This hands-on experience deepened my understanding of data communication and utilization in real-world services.
    
-   **Attention to Detail is Paramount:** Even minor errors, such as a variable typo or a subtle `meta_query` condition, can lead to significant data integrity or functional problems. This reinforced the need for meticulous code review and thorough debugging.
    
-   **Embracing New Technology Stacks:** Starting with React Native Expo highlighted the initial learning curve, but also the immense potential for creating new services. It underscored the importance of dedicated time for research and foundational learning when venturing into new technologies.
    

## 🌱 Points of Improvement & Next Week's Goals

-   **Points of Improvement:**
    
    -   **Resolve Remaining WordPress Theme Issues:** The persistent JSON response issues from the `popular-news` and `comments-popular` REST API endpoints, along with the CSS non-application, are current blockers.
        
    -   **Faster Adaptation to New Tech Stacks:** Improve efficiency in setting up and beginning development with new frameworks like React Native Expo by more focused initial research.
        
    -   **Proactive App Publishing Knowledge:** Lack of prior knowledge on app publishing processes, especially for iOS, needs to be addressed for a full app development experience.
        
-   **Next Week's Goals:**
    
    -   **Complete Resolution of DevNewsHub WordPress Theme Issues:** Prioritize and resolve all outstanding JSON response issues for `popular-news` and `comments-popular` endpoints, and ensure `popular-news-styles.css` applies correctly.
        
    -   **Advance React Native Expo App Core Features:** Focus on implementing essential functionalities for the mobile app, including a comprehensive latest news list, detailed article views, and infinite scrolling.
        
    -   **Research Deep Link Technology:** Conduct in-depth research on Deep Link technology for seamless web-to-app connections and explore its practical application within the React Native app.
        
    -   **Begin Detailed Research on iOS App Store Release Procedures:** Start researching the complex steps involved in publishing an app to the Apple App Store (accounts, certifications, review process) to prepare for future release attempts.
        

----------

# 📝 7주차 회고 (2025.06.23 ~ 06.27)

## ✅ 이번 주 주요 작업

📌 **ISAAC Painting 클라이언트 사이트 마이그레이션 및 반응형 최적화 완료:** 모든 페이지 마이그레이션과 모바일/태블릿 뷰 최적화 작업을 성공적으로 마쳤습니다.   
📌 **DevNewsHub 미니 프로젝트 데이터 정합성 및 기능 개선:** * '실제 발행일' 커스텀 필드(`news-published-date`)를 구현하여 자동화된 뉴스 데이터의 정확성을 확보하고 워드프레스 관리 편의성을 높였습니다. * 조회수 기반 인기 뉴스 페이지를 구현하고 연도별 필터링 기능을 추가했으며, 기존 뉴스 검색 기능을 개선했습니다.   
📌 **워드프레스 테마 코드 모듈화 및 구조 개선:** `functions.php` 파일을 기능별로 분리하여 코드 유지보수성 및 가독성을 향상시켰습니다.   
📌 **React Native (Expo) 기반 모바일 뉴스 앱 초기 개발 착수:** 워드프레스 REST API와 연동하여 뉴스 데이터를 모바일 앱에 가져와 표시하는 기본 구조를 성공적으로 구현했습니다.   
📌 **회사 국문 웹사이트 AI 리라이팅 및 비교 도구 개발:** `pandas`와 `difflib` 라이브러리를 활용하여 원본 국문 콘텐츠와 AI 리라이팅 버전을 시각적으로 비교하는 파이썬 스크립트를 개발했습니다.   
📌 **JavaScript UI 로직 개선 및 안정화:** 뉴스 검색 UI에서 검색 입력 필드 초기화 기능을 구현하고, 동적 요소에 대한 이벤트 위임 방식을 적용하여 UI 안정성을 높였습니다.  

## 🧠 배운 핵심 개념

-   **자동화 프로세스에서의 데이터 정합성:** 자동화된 데이터 수집 시 원본 데이터의 맥락(예: 실제 발행일과 업로드일)을 정확히 반영하는 것의 중요성을 이해했습니다. 이를 위해 커스텀 필드와 워드프레스 쿼리에서 `meta_type='DATETIME'` 설정의 필요성을 학습했습니다.
    
-   **워드프레스 테마 모듈화:** 길어지는 `functions.php` 파일을 논리적인 기능 단위로 분리(예: `enqueue.php`, `utility-functions.php`)하여 유지보수성과 가독성을 높이는 실제 경험을 통해 그 이점을 체감했습니다.
    
-   **REST API 고급 활용 및 디버깅:** 커스텀 필드를 활용한 복합 정렬(`orderby`) 및 필터링(`meta_query`) 구현의 복잡성을 배웠습니다. 또한 API 응답 오류 및 CSS 로딩 문제 발생 시 코드 롤백과 브라우저 개발자 도구를 활용한 체계적인 디버깅 접근법을 익혔습니다.
    
-   **React Native 앱 개발 핵심 개념:** `useState`(상태 관리), `useEffect`(데이터 가져오기와 같은 부수 효과)와 같은 React Native 핵심 Hook, 그리고 효율적인 리스트 렌더링을 위한 `FlatList` 컴포넌트의 실제 적용을 통해 앱 개발의 기본 원리를 이해했습니다.
    
-   **이벤트 위임 (Event Delegation):** 동적으로 추가되거나 복원되는 DOM 요소에 대해 효율적으로 이벤트를 처리하기 위한 필수 기법인 이벤트 위임의 중요성을 이해하고 구현했습니다.
    
-   **파이썬을 활용한 텍스트 유사도 비교:** `difflib` 모듈을 사용하여 텍스트 문자열 간의 차이점을 식별하고 시각화하는 방법을 학습했으며, 이는 AI 생성 콘텐츠 평가 및 콘텐츠 리라이팅 작업에 유용함을 확인했습니다.
    

## 🔧 기술적 문제 해결 경험

-   **워드프레스 REST API JSON 응답 및 CSS 미적용 문제:**
    
    -   **문제:** `devnewshub/v1/popular-news` REST API에서 JSON 데이터가 넘어오지 않거나, `popular-news-styles.css` 파일이 웹 페이지에 올바르게 적용되지 않는 문제가 발생했습니다. 댓글 수 기반 정렬 엔드포인트도 유사한 문제를 겪었습니다.
        
    -   **해결 과정:** 문제 해결을 위해 체계적인 디버깅 접근 방식을 사용했습니다. 코드를 마지막으로 정상 작동하던 상태로 롤백하고, `error_log`를 이용해 코드 내부를 추적하며, 브라우저 개발자 도구(Network, Elements, Console 탭)를 활용하여 CSS 로딩 경로, 선택자 우선순위, API 응답 등을 면밀히 검토했습니다. `update_post_meta` 호출 시 잘못된 변수를 참조(`$extracted_datetime_string` 대신 `$extracted_date_string`)하여 시간 정보가 유실되는 치명적인 버그를 발견했고, `meta_query` 조건이 의도치 않게 기존 포스트 업데이트를 제외시키는 문제도 파악하여 수정했습니다.
        
-   **커스텀 썸네일 크기 로딩 문제:**
    
    -   **문제:** `functions.php`에서 정의한 커스텀 썸네일 크기(`news-search-thumb`, 400x300)가 인기 뉴스 섹션에 적용되지 않고 기본 `medium` 사이즈로 로드되는 문제를 확인했습니다.
        
    -   **해결 과정:** API 응답에서 해당 커스텀 크기의 URL이 제대로 제공되는지, 그리고 프런트엔드 코드에서 그 URL을 정확히 사용하는지 명시적으로 확인하는 과정이 필요함을 인지했습니다. (API JSON 문제 해결 후 추가 조치 예정)
        
-   **React DevTools 설정 및 PATH 환경 변수 문제:**
    
    -   **문제:** React DevTools (standalone 버전)를 글로벌 설치 후 실행 시 명령어가 인식되지 않거나 PATH 관련 문제가 발생했습니다.
        
    -   **해결 과정:** 올바른 명령어(`react-devtools` 대신 `react-devtools`)를 사용해야 함을 알게 되었고, PATH 환경 변수 설정을 해결하여 DevTools가 정상적으로 실행되도록 했습니다. 이를 통해 DevTools가 컴포넌트의 상태와 속성을 디버깅하는 별도의 유틸리티임을 확인했습니다.
        

## 💡 느낀 점

-   **문제 해결 전략의 중요성:** 복잡하고 얽힌 버그나 장시간의 디버깅에 직면했을 때, 과감하게 안정적인 이전 커밋으로 롤백하는 것이 시간 절약과 문제 해결에 매우 효과적인 전략임을 깨달았습니다.
    
-   **실질적인 개발 경험의 가치:** 워드프레스 REST API와 양방향으로 데이터를 주고받는 간단한 앱을 직접 구축해본 경험은 이론적 지식을 넘어선 실질적인 개발 역량 강화에 크게 기여했습니다. 새로운 기술 스택을 배울 때, 단순한 기능 구현을 넘어 실제 서비스를 만들어보는 것이 중요함을 느꼈습니다.
    
-   **사소한 디테일의 중요성:** 변수명의 오타나 미묘한 쿼리 조건과 같은 작은 실수가 데이터 정합성이나 기능 오작동과 같은 큰 문제로 이어질 수 있음을 경험하며, 꼼꼼한 코드 검토와 철저한 디버깅의 중요성을 다시 한번 상기했습니다.
    
-   **새로운 기술 스택에 대한 도전:** React Native Expo를 시작하며 초기 학습 곡선이 있었지만, 이를 통해 새로운 서비스를 구현할 수 있다는 큰 잠재력을 보았습니다. 이는 새로운 기술을 접할 때 충분한 사전 리서치와 기초 학습의 중요성을 강조합니다.
    

## 🌱 아쉬운 점 및 다음 주 목표

-   **아쉬운 점:**
    
    -   **잔여 워드프레스 테마 이슈 해결 지연:** `popular-news` 및 `comments-popular` REST API 엔드포인트의 JSON 응답 문제와 CSS 미적용 문제가 해결되지 않아 다음 기능 구현에 제약을 받고 있습니다.
        
    -   **새로운 기술 스택 초기 적응 속도:** React Native Expo 개발 환경 설정 및 기본 개념 적응에 예상보다 시간이 소요되어 앱 개발 진척이 다소 더뎠습니다.
        
    -   **앱 출시 절차에 대한 지식 부족:** 앱 개발 경험 확장을 위해 iOS 앱 출시 절차에 대한 사전 지식이 부족하여, 해당 부분에 대한 학습이 필요합니다.
        
-   **다음 주 목표:**
    
    -   **DevNewsHub 워드프레스 테마 주요 문제 해결 완료:** `popular-news` 엔드포인트의 JSON 응답 문제 및 CSS 미적용 문제, 그리고 `comments-popular` 엔드포인트 문제를 최우선으로 해결하고 안정화할 것입니다.
        
    -   **React Native Expo 앱 핵심 기능 구현 집중:** 최신 뉴스 리스트 표시, 기사 상세 뷰, 무한 스크롤 등 모바일 앱의 필수 기능 구현에 집중하여 실제 앱의 모습을 갖춰나갈 것입니다.
        
    -   **딥링크(Deep Link) 기술 심층 연구:** 웹에서 앱으로의 매끄러운 연결을 위한 딥링크 기술을 심도 있게 조사하고, React Native 앱에 적용할 수 있는 방안을 탐색할 것입니다.
        
    -   **애플(iOS) 앱 스토어 출시 절차 상세 조사 시작:** iOS 앱 스토어에 앱을 배포하는 복잡한 절차(계정, 인증, 심사 과정 등)를 미리 상세히 리서치하여 추후 실제 앱 출시를 위한 기반을 마련할 것입니다.
