# 📝 Week 6 Reflection (2025.06.16 ~ 06.20)

## ✅ Key Tasks This Week

**📌 Completed the migration of the ISAAC Painting website to WordPress with Elementor**, applying **advanced Elementor features** like Loop Grid and multiple Loop Item templates for dynamic layouts. This included extensive **responsive layout optimization** and overall **migration task completion**.  
**📌 Focused heavily on web scraping script refinement**, particularly for the ABC News site, by **implementing duplicate skipping logic** and diagnosing persistent `404 API errors` and **dynamic content loading issues** (using Selenium/Beautiful Soup). This highlighted the critical need for **ongoing maintenance and anti-bot bypass strategies**.   
**📌 Gained practical experience with Cron jobs**, setting up an automation structure to publish privately uploaded articles daily, and exploring **WP-Cron vs. System Cron** for future automation.   
**📌 Successfully integrated Google Social Login** into WordPress using the Nextend Social Login plugin, navigating OAuth complexities like redirect URI mismatches.   
**📌 Explored and prepared for deeper REST API utilization**, specifically focusing on **sending data externally from WordPress** to enable broader service applications, beyond just data ingestion.   
**📌 Addressed DevNewsHub UI/UX challenges**, including standardizing login/signup forms, debugging search result display (which still requires code-based layout customization), and integrating a **translation plugin (GTranslate)** for multilingual support.  

## 🧠 What I Learned

-   **Advanced Elementor Application**: Mastered using **Elementor's Loop Grid with multiple Loop Item templates** to create highly complex and dynamic post layouts without custom coding, significantly streamlining design processes.
-   **Web Scraping Resilience**: Experienced firsthand that web scraping demands **continuous adaptation** to website structural changes and sophisticated **anti-bot mechanisms**. This underscored the necessity of robust error handling, iterative debugging with developer tools, and considering advanced techniques (Selenium, proxies).
-   **Automated Task Scheduling (Cron)**: Understood the distinct roles of **WP-Cron** (WordPress-dependent, visit-triggered) and **System Cron (Linux)** (system-level, precise scheduling) for various automation needs, and how to integrate them for a full data pipeline.
-   **Bi-directional REST API Utilization**: Reinforced that the **WordPress REST API** is a powerful tool not only for importing data but also for **exporting it for external applications**, opening avenues for broader service integration. This involves designing custom endpoints and securing them.
-   **Practical OAuth 2.0 Integration**: Gained hands-on experience with the entire **OAuth flow**, from client creation to resolving common errors like `redirect_uri_mismatch` during Google Social Login integration.
-   **Importance of Logging**: Confirmed the critical value of Python's **`logging` module** over simple `print()` statements for debugging, maintainability, and understanding script execution.
-   **Client Work Realities**: Learned that client projects often involve iterative optimization (e.g., font consistency, mobile responsiveness) even after initial "completion," and that initial scopes can evolve into complex migration tasks.

## 🔧 Technical Problem-Solving Experience

-   **Elementor Flexbox Layout Debugging**: Successfully resolved complex responsive alignment issues in ISAAC Painting by meticulously adjusting **Flexbox properties (Direction, Justify Content, Align Items)** and **mobile breakpoints** within Elementor, often using fixed `px` values for stable elements like logos.
-   **Web Scraping `404` API Error & Dynamic Content**: Diagnosed and attempted to resolve persistent `404 Not Found` errors in the ABC News scraping script, realizing the API endpoint had changed. This necessitated re-analyzing network requests and preparing for **Selenium-based dynamic content loading** challenges, highlighting the ongoing effort required for scraping maintenance.
-   **OAuth `redirect_uri_mismatch` Resolution**: Solved `redirect_uri_mismatch` errors during Google Social Login integration by carefully verifying and accurately registering the exact callback URI in the Google Cloud Console.
**WordPress Search Result Layout Discrepancy**: Identified an issue where DevNewsHub's internal search results, though successfully displayed via AJAX within a widget on the same page (instead of a new window), reverted to the WordPress default theme structure rather than applying the Elementor Pro theme builder's custom layout. This indicated that despite the AJAX implementation, **custom code solutions are required to ensure the search results inherit the intended Elementor theme builder design** as widget-based solutions alone are insufficient.
-   **Python Scraping Duplicate Handling**: Implemented logic to prevent re-scraping and re-publishing of duplicate articles by comparing newly found links with a CSV file of previously collected data, improving efficiency.

## 💡 Reflections

-   This week was a deep dive into **practical application and problem-solving**. I didn't just learn concepts; I actively applied them to real-world scenarios on client sites and personal projects.
-   The **dynamic nature of web scraping** became explicitly clear. It's not a set-and-forget task; it requires constant vigilance, technical analysis (developer tools are indispensable!), and adaptability to website changes. This was a challenging but invaluable lesson.
-   Gaining hands-on experience with **WP-Cron and the REST API** for automated content management (private to public) was a significant step towards understanding full-stack automation within WordPress.
-   The advice to explore **sending data _out_ of WordPress via REST API** was a perspective shift, broadening my understanding of WordPress's role as a data hub for other applications. This is definitely a crucial area for future growth.
-   Managing **client site optimizations** concurrently with personal project development allowed me to balance immediate task execution with long-term skill development.

## 🌱 Points of Improvement & Next Week's Goals

-   **Refine Advanced Web Scraping Skills**: Focus on implementing more sophisticated strategies (e.g., Selenium for headless Browse, proxy rotation) to effectively bypass anti-bot security on challenging sites like BBC. This will be a priority to ensure data collection stability.
-   **Implement Code-Based DevNewsHub Search Layout**: Dedicate time to writing custom code to ensure the internal search results on DevNewsHub adopt the desired theme builder's layout, overcoming the current default theme display.
-   **Deepen WP-Cron/System Cron Integration**: Thoroughly investigate best practices for running Python scripts as scheduled tasks on a server (e.g., using `crontab`) and how to reliably communicate results back to WordPress, moving beyond manual execution.
-   **Begin Custom REST API Endpoint Implementation**: Start building actual custom REST API endpoints to export specific data from WordPress, such as personalized article feeds or analytics, to prove the concept of external data distribution.
-   **Complete Isaac Painting Mobile Optimization**: Ensure absolute font consistency and flawless mobile responsiveness across all devices for the Isaac Painting client site.

----------

# 📝 6주차 회고 (2025.06.16 ~ 06.20)

## ✅ 이번 주 주요 작업

**📌 ISAAC Painting 웹사이트의 WordPress + Elementor 마이그레이션 작업을 완료**했으며, 동적 레이아웃을 위해 Loop Grid 및 여러 Loop Item 템플릿과 같은 **Elementor의 고급 기능들을 적용**했습니다. 이는 광범위한 **반응형 레이아웃 최적화** 및 전반적인 **마이그레이션 작업 완료**를 포함합니다.   
**📌 웹 스크래핑 스크립트 개선에 집중**했습니다. 특히 ABC 뉴스 사이트에서 **중복 건너뛰기 로직을 구현**하고, 지속적인 `404 API 오류`와 **동적 콘텐츠 로딩 문제** (Selenium/Beautiful Soup 활용)를 진단했습니다. 이는 **지속적인 유지보수 및 안티봇 우회 전략**의 중요성을 강조했습니다.   
**📌 크론 작업 실질적인 경험**을 쌓았고, 비공개로 업로드된 기사를 매일 게시하는 자동화 구조를 설정하며, 향후 자동화를 위한 **WP-Cron vs. 시스템 Cron**을 탐색했습니다.   
**📌 Nextend Social Login 플러그인을 활용하여 워드프레스 구글 소셜 로그인을 성공적으로 연동**했으며, `redirect_uri_mismatch`와 같은 OAuth 복잡성을 해결했습니다.   
**📌 더 심층적인 REST API 활용을 탐색하고 준비**했으며, 특히 워드프레스로 데이터를 가져오는 것을 넘어 **외부로 데이터를 전송**하여 더 광범위한 서비스 애플리케이션을 가능하게 하는 데 중점을 두었습니다.   
**📌 DevNewsHub UI/UX 과제를 해결**했습니다. 로그인/회원가입 양식 표준화, 검색 결과 표시 디버깅 (코드 기반 레이아웃 사용자 정의가 여전히 필요함), 다국어 지원을 위한 **번역 플러그인(GTranslate) 통합** 등을 포함합니다.  

## 🧠 배운 핵심 개념

-   **Elementor 고급 기능 활용**: **Elementor의 Loop Grid와 여러 Loop Item 템플릿**을 조합하여 커스텀 코딩 없이도 매우 복잡하고 동적인 게시물 레이아웃을 생성하는 방법을 마스터하여 디자인 프로세스를 크게 간소화했습니다.
-   **웹 스크래핑의 견고성**: 웹 스크래핑이 웹사이트 구조 변경 및 정교한 **안티봇 메커니즘**에 대한 **지속적인 적응**을 요구한다는 것을 직접 경험했습니다. 이는 견고한 오류 처리, 개발자 도구를 사용한 반복적인 디버깅, 고급 기술(Selenium, 프록시) 고려의 필요성을 강조했습니다.
-   **자동화된 작업 스케줄링 (크론)**: 다양한 자동화 요구사항에 맞는 **WP-Cron** (워드프레스 종속, 방문 트리거)과 **시스템 Cron (Linux)** (시스템 수준, 정밀한 스케줄링)의 뚜렷한 역할을 이해했으며, 전체 데이터 파이프라인을 위해 이들을 통합하는 방법을 배웠습니다.
-   **양방향 REST API 활용**: **워드프레스 REST API**가 데이터를 가져오는 것뿐만 아니라 **외부 애플리케이션으로 데이터를 내보내는 강력한 도구**임을 재확인하여, 더 광범위한 서비스 통합의 길을 열었습니다. 여기에는 커스텀 엔드포인트 설계 및 보안이 포함됩니다.
-   **실질적인 OAuth 2.0 연동**: 구글 소셜 로그인 연동 과정에서 클라이언트 생성부터 `redirect_uri_mismatch`와 같은 일반적인 오류 해결에 이르기까지 **전체 OAuth 흐름**을 직접 경험했습니다.
-   **로깅의 중요성**: 파이썬의 **`logging` 모듈**이 디버깅, 유지보수성, 스크립트 실행 이해를 위해 단순 `print()` 문보다 훨씬 중요하다는 것을 확인했습니다.
-   **클라이언트 작업의 현실**: 클라이언트 프로젝트가 초기 "완료" 후에도 (예: 폰트 일관성, 모바일 반응성) 반복적인 최적화 작업을 포함하며, 초기 범위가 복잡한 마이그레이션 작업으로 발전할 수 있다는 것을 배웠습니다.

## 🔧 기술적 문제 해결 경험

-   **Elementor Flexbox 레이아웃 디버깅**: ISAAC Painting에서 **Flexbox 속성(Direction, Justify Content, Align Items)과 모바일 브레이크포인트**를 세심하게 조정하여 복잡한 반응형 정렬 문제를 성공적으로 해결했습니다. 로고와 같은 안정적인 요소에는 종종 고정 `px` 값을 사용했습니다.
-   **웹 스크래핑 `404` API 오류 및 동적 콘텐츠**: ABC 뉴스 스크래핑 스크립트에서 지속적인 `404 Not Found` 오류를 진단하고 해결하려 시도했으며, API 엔드포인트가 변경되었음을 확인했습니다. 이는 네트워크 요청을 재분석하고 **Selenium 기반 동적 콘텐츠 로딩** 문제에 대비해야 함을 의미하며, 스크래핑 유지보수에 지속적인 노력이 필요함을 강조합니다.
-   **OAuth `redirect_uri_mismatch` 해결**: 구글 소셜 로그인 연동 중 발생한 `redirect_uri_mismatch` 오류를 구글 콘솔에 실제 콜백 URI를 정확하게 확인하고 등록함으로써 해결했습니다.
**워드프레스 검색 결과 레이아웃 불일치**: DevNewsHub의 내부 검색 결과가 새 창으로 이동하는 대신 AJAX를 통해 동일 페이지 내 위젯에 표시되도록 구현했으나, Elementor Pro 테마 빌더의 커스텀 레이아웃이 아닌 워드프레스 기본 테마 구조로 출력되는 문제가 발생했습니다. 이는 AJAX 구현에도 불구하고, 위젯 기반 솔루션만으로는 부족하며, **검색 결과가 의도한 Elementor 테마 빌더 디자인을 상속받도록 코드 기반의 추가적인 사용자 정의가 필요함**을 시사합니다.
-   **파이썬 스크래핑 중복 처리**: 새로 찾은 링크를 이전에 수집된 데이터가 포함된 CSV 파일과 비교하여 중복 기사가 다시 스크래핑되거나 게시되는 것을 방지하는 로직을 구현하여 효율성을 높였습니다.

## 💡 느낀 점

-   이번 주는 **실질적인 적용과 문제 해결**에 깊이 파고든 한 주였습니다. 단순히 개념을 배우는 것을 넘어, 클라이언트 사이트와 개인 프로젝트의 실제 시나리오에 적극적으로 적용했습니다.
-   **웹 스크래핑의 동적인 특성**이 명확해졌습니다. 한 번 설정하고 잊어버리는 작업이 아니라, 웹사이트 변경에 대한 지속적인 감시, 기술적 분석(개발자 도구는 필수!), 적응력이 필요합니다. 이것은 도전적이지만 매우 귀중한 교훈이었습니다.
-   **WP-Cron 및 REST API**를 활용한 자동화된 콘텐츠 관리(비공개에서 공개로 전환)를 직접 경험한 것은 워드프레스 내에서 풀스택 자동화를 이해하는 데 중요한 단계였습니다.
-   **REST API를 통해 워드프레스에서 데이터를 _내보내는_** 방법을 탐색하라는 조언은 워드프레스의 역할을 다른 애플리케이션을 위한 데이터 허브로 확장하는 관점의 전환이었습니다. 이는 향후 성장에 있어 분명히 중요한 영역입니다.
-   **클라이언트 사이트 최적화**와 개인 프로젝트 개발을 동시에 관리함으로써, 당면 과제 실행과 장기적인 기술 개발 간의 균형을 맞출 수 있었습니다.

## 🌱 아쉬운 점 및 다음 주 목표

-   **고급 웹 스크래핑 기술 향상**: BBC와 같은 까다로운 사이트의 안티봇 보안을 효과적으로 우회하기 위한 더 정교한 전략(예: 헤드리스 브라우징을 위한 Selenium, 프록시 로테이션) 구현에 집중할 것입니다. 이는 데이터 수집 안정성을 확보하는 데 우선순위가 될 것입니다.
-   **코드 기반 DevNewsHub 검색 레이아웃 구현**: DevNewsHub의 내부 검색 결과가 현재 기본 테마 표시를 넘어 원하는 테마 빌더의 레이아웃을 채택하도록 커스텀 코드를 작성하는 데 시간을 할애할 것입니다.
-   **WP-Cron/시스템 Cron 연동 심화**: 서버에서 파이썬 스크립트를 예약된 작업으로 실행하는 최적의 방법(예: `crontab` 사용)과 워드프레스로 결과를 안정적으로 통신하는 방법을 철저히 조사하여 수동 실행을 넘어설 것입니다.
-   **커스텀 REST API 엔드포인트 구현 시작**: 워드프레스에서 개인 맞춤형 기사 피드 또는 분석과 같은 특정 데이터를 내보내기 위한 실제 커스텀 REST API 엔드포인트를 구축하기 시작하여 외부 데이터 배포 개념을 증명할 것입니다.
-   **Isaac Painting 모바일 최적화 완료**: Isaac Painting 클라이언트 사이트의 모든 기기에서 절대적인 폰트 일관성과 완벽한 모바일 반응성을 확보할 것입니다.
