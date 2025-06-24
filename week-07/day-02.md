# 📅 Day 02 (2025-06-24, Tue)

## 🎓 What I Did Today

**📌 **Development Meeting Brief**: Reported ISAAC Painting migration and tablet/mobile optimization complete.**  
**📌 Focused on ensuring data integrity for news archiving and improving WordPress administration.**   
**📌 Identified and addressed a critical issue regarding `post_date` discrepancies in automated news uploads, implementing a custom field for "actual published date."**   
**📌 Successfully implemented and populated a "news-published-date" custom field by meticulously extracting date and time from post content.**   
**📌 Addressed initial issues with news source taxonomy assignment for scraped articles.**   
**📌 Gained renewed appreciation for detailed debugging, confirming WordPress's native logging capabilities and planning for their optimal configuration.**  

### Detailed Activities

**1. Morning Development Meeting Key Takeaways (Morning)** The day started with a development meeting where I reported on my previous day's work and received feedback for the ongoing mini-project.

-   **Yesterday's Work Report**: I reported the successful completion of the ISAAC Painting client site migration, including its tablet and mobile optimization.
-   **DevNewsHub Mini-Project Continuation**: I confirmed my plan to continue with the DevNewsHub mini-project, emphasizing ongoing study and practical application of the WordPress REST API.
-   **Senior Developer's Feedback**: I received valuable advice to move beyond merely fetching data with the WordPress REST API. The suggestion was to try implementing a simple application that can **"send and receive" data bidirectionally** with WordPress, or even to explore developing applications/services that integrate with WordPress, such as plugins. This advice highlights a more expanded form of functional implementation.

**2. Ensuring Data Integrity for News Archiving & WP Admin Convenience (All Day)** My primary focus today was on securing data consistency for news archiving and enhancing WordPress management convenience. These were crucial preliminary tasks for implementing the "popular news by view count" feature, and they also addressed improvements identified during the automated news upload process.

-   **Initial Recognition of `post_date` Problem in Automated News Uploads**:
    
    -   **Problem**: I recognized a fundamental issue in the automated news scraping process: "older articles could be uploaded later." This meant WordPress's default `post_date` was recorded as the 'upload time,' not the 'actual publication date,' which could cause confusion for future data utilization.
    -   **Solution Direction**: To resolve this, I decided it was necessary to extract the 'actual published date' from within the `post_content` and store it in a separate database field (custom field). This was deemed highly useful for future query modifications and data utilization.
-   **Implementation of 'Actual Published Date' Custom Field (`news-published-date`) & Data Population (Resolved)**:
    
    -   **Goal**: The objective was to accurately extract the 'actual published date' information from the post body (`post_content`), store it in the `news-published-date` custom field, and ensure it was viewable in the developer dashboard (WordPress admin).
    -   **Initial Problems (Re-evaluated)**:
        -   **Missing Time Information**: The PHP extraction logic sometimes only retrieved the date, or saved a default time of '12:00:00' (midnight).
        -   **Inability to Update Existing Data**: Already populated posts were excluded from being updated due to a specific `meta_query` condition.
        -   **Critical Bug**: A critical bug was found where, despite `$extracted_datetime_string` being correctly extracted, the `update_post_meta` call erroneously referenced `$extracted_date_string`, preventing time information from being saved to the custom field.
    -   **Final Resolution**:
        -   Removed the `meta_query` condition from the `get_posts()` query entirely, ensuring all 'news' posts were included for update. This allowed re-processing of posts with previously incorrect values.
        -   Improved the logic within the PHP `extract_and_populate_news_published_date()` function to accurately parse both date and time information from various date/time patterns in `post_content` (e.g., `Posted YYYY-MM-DD HH:MM:SS`, `DayOfWeek DD Mon YYYY at HH:MMam/pm`, `<time datetime="..."> ISO 8601`).
        -   Most importantly, I corrected the `update_post_meta` call to correctly reference the `$extracted_datetime_string` variable, finally confirming that the accurate actual published date in `YYYY-MM-DD HH:MM:SS` format was successfully saved to the custom field.

**3. News Source Taxonomy Automation & Value Assignment:**

-   **Problem Recognition**: I observed that the taxonomy value corresponding to 'news source' wasn't being correctly assigned during the automated scraping process. Since only 'ABC scraping code' is currently in use, these news articles should have 'ABC News' as their source.
-   **Temporary Solution (PHP Implementation)**: I implemented PHP code to batch assign the 'ABC News' taxonomy value to already uploaded articles. (This serves as an intermediate step before implementing a long-term solution for extracting/assigning taxonomies within the scraping pipeline.)

**4. Minor Issue Resolution & Lessons Learned:**

-   I experienced how small details, such as variable name mismatches (`$extracted_datetime_string` vs. `$extracted_date_string`) and `meta_query` conditions, can cause significant problems. This re-emphasized the importance of **detailed code review and thorough debugging (using `error_log`)**.
-   **Logging Discovery**: Interestingly, `debug.log` was found to be generated, indicating that logging functionality was active. While `error.log` didn't show meaningful entries yet, the existence of `debug.log` suggests logging was inherently functional. I need to re-verify the setup for `error.log` to capture more useful information.

### Today's Key Achievements:

-   **Significantly Improved News Data Integrity**: Accurate date and time information is now stored in the 'actual published date' custom field, increasing the value of the news archive.
-   **Enhanced Management Convenience**: The 'actual published date' information is directly viewable in the developer dashboard (admin screen), facilitating easier data management.
-   **Initial Taxonomy Data Assignment**: Basic data integrity for news source taxonomy has been secured.

## 🧠 Key Concepts Learned

-   **Data Integrity in Automated Processes**: Understood the critical importance of ensuring that automated data ingestion accurately reflects the original data's context (e.g., actual publication date vs. upload date) and the necessity of custom fields for this purpose.
-   **Robust Date/Time Parsing**: Gained practical experience in handling diverse date/time formats within scraped content and implemented a more robust parsing logic.
-   **WordPress `get_posts()` & `meta_query` Nuances**: Learned how `meta_query` conditions can inadvertently exclude data from updates and the importance of precise querying for data manipulation.
-   **WordPress Taxonomy Management**: Explored methods for assigning taxonomy terms to posts programmatically, especially for ensuring data consistency in automated pipelines.
-   **Advanced Debugging & Logging in WordPress**: Reaffirmed the critical role of detailed debugging and the WordPress logging system (`debug.log`, `error_log`) for diagnosing subtle code errors and data inconsistencies.

## 💡 Practical Trial-and-Error and Tips

-   **Meticulous Variable Referencing**: A minor variable typo can lead to significant data corruption. Always double-check variable names in function calls.
    
-   **Query Scope for Data Updates**: Be cautious with `meta_query` conditions when performing bulk updates; removing them can ensure all relevant posts are processed.
    
-   **Iterative Problem-Solving in Data Integrity**: Fixing data integrity issues often involves a multi-step process: identifying the problem, re-evaluating existing data, refining extraction/population logic, and re-processing.
    
-   **WordPress Debugging Configuration**: To effectively utilize WordPress's logging capabilities, ensure these lines are correctly set in `wp-config.php`:
    
```php
define( 'WP_DEBUG', true ); // Enable debug mode
define( 'WP_DEBUG_LOG', true ); // Log errors to debug.log file
define( 'WP_DEBUG_DISPLAY', false ); // Don't display errors on screen (for production)
@ini_set( 'display_errors', 0 ); // Hide display errors
```
    
(`debug.log` will be created in `wp-content/debug.log`. For `error_log`, ensure `WP_DEBUG_LOG` is true and check your server's PHP error logs location, often configured in `php.ini` or server-specific settings.)
    

## 🔜 Next Steps

Now that crucial preliminary tasks are successfully completed, the focus shifts to implementing the "popular news by view count" feature.

-   **Review & Optimize View Count Tracking Logic**: Re-examine and, if necessary, improve the current view count increment logic to ensure accuracy and efficiency (e.g., excluding bots/admins, preventing duplicate counts). (Consider utilizing plugins like 'Post Views Counter').
-   **Implement View Count Ranking Widget in WP Dashboard**: Develop a custom widget for the WordPress admin dashboard that displays the top N most popular 'news' posts.
-   **Implement REST API Endpoint for View Count Sorting**: Extend the WordPress REST API to provide a dedicated endpoint for fetching 'news' posts sorted by view count (`post_views_count` or a similar meta key).
-   **Detail Frontend Utilization Plan (React Mini-Project Integration)**: Finalize how the implemented REST API endpoint will be called and utilized by the React mini-project to dynamically display the "Popular News" section.

----------

# 📅 2일차 (2025-06-24, 화)

## 🎓 오늘 한 일

**📌 **개발 미팅 요약**: ISAAC Painting 마이그레이션 및 테블릿/모바일 환경 최적화 완료 보고**  
**📌 뉴스 아카이빙을 위한 데이터 정합성 확보와 워드프레스 관리 편의성 향상에 중점을 두었습니다.**     
**📌 자동화된 뉴스 업로드 과정에서 `post_date`의 불일치 문제를 파악하고, '실제 발행일'을 위한 커스텀 필드를 구현했습니다.**     
**📌 게시물 본문에서 날짜와 시간을 세밀하게 추출하여 'news-published-date' 커스텀 필드를 성공적으로 채웠습니다.**     
**📌 스크래핑된 기사의 뉴스 출처 텍소노미 할당 초기 문제를 해결했습니다.**     
**📌 코드 디버깅의 중요성을 다시 한번 깨달았으며, 워드프레스의 기본 로깅 기능이 활성화되어 있음을 확인하고 최적의 설정 방법을 계획했습니다.**    

### 상세 활동

**1. 오전 개발 미팅 주요 내용 (오전)** 하루는 개발 미팅으로 시작되었고, 지난 작업 보고와 현재 진행 중인 미니 프로젝트에 대한 피드백을 받았습니다.

-   **어제 작업 보고**: ISAAC Painting 클라이언트 사이트 마이그레이션이 태블릿 및 모바일 최적화 작업까지 완료되었음을 보고했습니다.
-   **DevNewsHub 미니 프로젝트 계속 진행**: 미니 프로젝트 DevNewsHub를 계속 이어서 진행할 것이며, 워드프레스 REST API 관련 공부 및 실제 활용을 계속할 계획임을 공유했습니다.
-   **개발 선임의 추가 피드백**: 단순히 워드프레스와 REST API를 활용해 데이터만 가져오는 데 그치지 않고, 한 단계 더 나아가 워드프레스와 REST API를 활용해 데이터를 **"주고받는" 심플한 앱을 구현**해보거나, 플러그인 등 워드프레스와 연동되는 응용 프로그램/서비스 개발에도 도전해보라는 조언을 받았습니다. 이는 더 확장된 형태의 기능 구현을 시도해야 함을 시사합니다.

**2. 뉴스 아카이빙 데이터 정합성 및 워드프레스 관리 편의성 확보 (온종일)** 오늘의 주요 초점은 뉴스 아카이빙을 위한 데이터 정합성을 확보하고 워드프레스 관리 편의성을 향상시키는 것이었습니다. 이 작업들은 원래 목표였던 조회수(인기순) 뉴스 구현을 위한 사전 작업이자, 자동화된 뉴스 업로드 과정에서 발견된 개선점들을 해결하는 과정이었습니다.

-   **뉴스 스크래핑 및 업로드 자동화 과정의 `post_date` 초기 인식 문제**:
    
    -   **문제 인식**: 뉴스 스크래핑 자동화 과정에서 "과거 기사가 나중에 업로드될 수 있다"는 본질적인 문제를 인지했습니다. 이는 워드프레스 기본 `post_date`가 실제 발행일이 아닌 '업로드 시점'으로 기록되어, 추후 데이터 활용 시 혼란을 야기할 수 있음을 의미했습니다.
    -   **해결 방향 설정**: 이 문제를 해결하기 위해 `post_content` 내에서 '실제 발행일'을 추출하여 별도의 DB 필드(커스텀 필드)에 저장하는 것이 필요하다고 판단했습니다. 이는 향후 쿼리 변경이나 데이터 활용에 매우 유용할 것이라는 판단에 따른 것이었습니다.
-   **'실제 발행일' 커스텀 필드(`news-published-date`) 구현 및 데이터 채우기 (해결 완료)**:
    
    -   **목표**: 게시물 본문(`post_content`)에서 '실제 발행일' 정보를 추출하여 `news-published-date` 커스텀 필드에 정확히 저장하고, 이를 개발자 대시보드(워드프레스 관리자)에서 확인할 수 있도록 하는 것이었습니다.
    -   **초기 문제점 (재정리)**:
        -   **시간 정보 누락**: PHP 추출 로직이 날짜만 가져오거나 기본값인 자정('12:00:00')을 저장하는 문제가 있었습니다.
        -   **기존 데이터 업데이트 불가**: 이미 값이 채워진 포스트는 특정 `meta_query` 조건으로 인해 업데이트 대상에서 제외되었습니다.
        -   **최종 버그**: 제가 제공한 코드에서 `$extracted_datetime_string` 변수에 값이 잘 추출되었음에도 불구하고, `update_post_meta` 호출 시 `$extracted_date_string`이라는 잘못된 변수를 참조하여 시간 정보가 커스텀 필드에 저장되지 않는 치명적인 버그가 있었습니다.
    -   **최종 해결**:
        -   `get_posts()` 쿼리에서 `meta_query` 조건을 완전히 제거하여, 모든 'news' 포스트가 업데이트 대상에 포함되도록 했습니다. 이로써 기존에 잘못된 값이 입력된 포스트들도 재처리될 수 있었습니다.
        -   PHP `extract_and_populate_news_published_date()` 함수 내에서 `post_content`의 다양한 날짜/시간 패턴(예: `Posted YYYY-MM-DD HH:MM:SS`, `DayOfWeek DD Mon YYYY at HH:MMam/pm`, `<time datetime="..."> ISO 8601`)에서 날짜와 시간 정보까지 모두 정확히 파싱하도록 로직을 개선했습니다.
        -   가장 중요하게, `update_post_meta` 호출 시 `$extracted_datetime_string` 변수를 올바르게 참조하도록 코드를 수정하여, 최종적으로 `YYYY-MM-DD HH:MM:SS` 형식의 정확한 실제 발행일이 커스텀 필드에 성공적으로 저장됨을 확인했습니다.

**3. 뉴스 출처(텍소노미) 자동화 및 값 할당:**

-   **문제 인식**: 자동화된 스크래핑 과정에서 '뉴스 출처'에 해당하는 텍소노미 값이 제대로 들어오지 않는 것을 확인했습니다. 현재 'ABC 스크래핑 코드'만 사용하고 있으므로, 해당 뉴스들은 'ABC News'라는 출처 값을 가져야 합니다.
-   **임시 해결 (PHP 구현)**: PHP 코드를 통해 이미 업로드된 뉴스들에 대해 'ABC News' 텍소노미 값을 일괄적으로 할당하는 로직을 구현했습니다. (이는 스크래핑 파이프라인에서 텍소노미를 추출/할당하는 장기적인 해결책을 마련하기 전의 중간 단계로 보입니다.)

**4. 자잘한 이슈 해결 및 교훈:**

-   '실제 발행일' 필드의 변수명 불일치와 `meta_query` 조건과 같은 작은 디테일들이 큰 문제를 야기할 수 있음을 경험하며, 코드의 **디테일 확인과 디버깅(error_log 활용)**의 중요성을 다시 한번 상기했습니다.
-   **로깅 파일 확인**: 흥미롭게도 `debug.log` 파일이 생성되어 있었음을 확인하여 로깅 기능이 작동하고 있음을 알 수 있었습니다. 비록 `error.log`에서는 아직 유의미한 로그 내용을 보지 못했지만, `debug.log`의 존재는 로깅이 기본적으로 기능했음을 시사합니다. `error.log`에서 더 유용한 정보를 캡처할 수 있도록 설정 재확인이 필요합니다.

### 오늘의 핵심 성과:

-   **뉴스 데이터 정합성 대폭 향상**: '실제 발행일' 커스텀 필드에 정확한 날짜 및 시간 정보가 저장되어, 뉴스 아카이브로서의 가치가 높아졌습니다.
-   **관리 편의성 개선**: 개발자 대시보드(관리자 화면)에서 이 '실제 발행일' 정보를 직접 확인할 수 있게 되어 데이터 관리가 용이해졌습니다.
-   **텍소노미 데이터 초기 할당**: 뉴스 출처 데이터의 기본 정합성을 확보했습니다.

## 🧠 배운 핵심 개념

-   **자동화 프로세스에서의 데이터 정합성**: 자동화된 데이터 수집이 원본 데이터의 컨텍스트(예: 실제 발행일 vs. 업로드일)를 정확하게 반영하는 것의 중요성과 이를 위한 커스텀 필드의 필요성을 이해했습니다.
-   **견고한 날짜/시간 파싱**: 스크래핑된 콘텐츠 내의 다양한 날짜/시간 형식을 처리하는 실질적인 경험을 얻고, 더 견고한 파싱 로직을 구현했습니다.
-   **워드프레스 `get_posts()` 및 `meta_query`의 미묘한 차이**: `meta_query` 조건이 의도치 않게 데이터 업데이트에서 특정 데이터를 제외할 수 있음을 배우고, 데이터 조작을 위한 정확한 쿼리의 중요성을 깨달았습니다.
-   **워드프레스 텍소노미 관리**: 특히 자동화된 파이프라인에서 데이터 일관성을 보장하기 위해 텍소노미 용어를 프로그램적으로 게시물에 할당하는 방법을 탐색했습니다.
-   **워드프레스의 고급 디버깅 및 로깅**: 미묘한 코드 오류와 데이터 불일치를 진단하는 데 있어 상세한 디버깅과 워드프레스 로깅 시스템(`debug.log`, `error.log`)의 중요한 역할을 다시 한번 확인했습니다.

## 💡 실전 시행착오 및 팁

-   **꼼꼼한 변수 참조**: 작은 변수 오타 하나가 심각한 데이터 손상을 초래할 수 있습니다. 함수 호출 시 변수 이름을 항상 다시 확인해야 합니다.
    
-   **데이터 업데이트 시 쿼리 범위**: 대량 업데이트를 수행할 때 `meta_query` 조건에 주의해야 합니다. 이를 제거하면 모든 관련 게시물이 처리될 수 있습니다.
    
-   **데이터 정합성 문제의 반복적 해결**: 데이터 정합성 문제 해결은 문제 식별, 기존 데이터 재평가, 추출/입력 로직 개선, 재처리 등 여러 단계의 프로세스를 수반합니다.
    
-   **워드프레스 디버깅 설정**: 워드프레스의 로깅 기능을 효과적으로 활용하려면 `wp-config.php`에 다음 라인들이 올바르게 설정되어 있는지 확인해야 합니다:
    
```php
define( 'WP_DEBUG', true );         // 디버그 모드 활성화
define( 'WP_DEBUG_LOG', true );     // 오류를 debug.log 파일에 기록
define( 'WP_DEBUG_DISPLAY', false );// 화면에 오류 표시 안 함 (운영 환경용)
@ini_set( 'display_errors', 0 );    // 화면에 오류 표시 숨김
```
    
(`debug.log`는 `wp-content/debug.log`에 생성됩니다. `error_log`는 `WP_DEBUG_LOG`가 `true`일 때 서버의 PHP 오류 로그 위치(종종 `php.ini` 또는 서버별 설정에서 구성)를 확인해야 합니다.)
    

## 🔜 Next Steps

이제 중요한 사전 작업들이 성공적으로 마무리되었으므로, 조회수(인기순) 뉴스 기능 구현으로 초점을 전환합니다.

-   **조회수 추적 로직 검토 및 최적화**: 현재 구현된 조회수 증가 로직이 정확하고 효율적인지(예: 봇/관리자 제외, 중복 방지 등) 재검토하고 필요시 개선합니다. ('Post Views Counter'와 같은 플러그인 활용 고려)
-   **워드프레스 대시보드에 조회수 랭킹 위젯 추가**: 워드프레스 관리자 대시보드에 'news' 포스트 타입의 인기 뉴스 상위 N개 목록을 보여주는 커스텀 위젯을 구현합니다.
-   **REST API 엔드포인트 구현 (조회수 정렬)**: 워드프레스 REST API를 확장하여 `news` 포스트 타입을 조회수(`post_views_count` 또는 유사 메타 키) 순으로 정렬하여 가져올 수 있는 전용 엔드포인트를 제공합니다.
-   **프런트엔드 활용 방안 구체화 (React 미니 프로젝트 연동)**: 구현된 REST API 엔드포인트를 React 미니 프로젝트에서 호출하여 "인기 뉴스" 섹션을 동적으로 표시하는 방법을 구체화합니다.
