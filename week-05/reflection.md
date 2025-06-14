# 📝 Week 05 Reflection (2025.06.09 ~ 06.13)

This fifth week of my internship marked a significant shift from focused research to **direct client project implementation**, primarily cloning the ISAAC Painting website using Elementor. I delved into **practical responsive design, dynamic content display with Elementor's advanced features, and continued refining my web scraping automation for WordPress.** Crucially, I gained invaluable insights from client-facing discussions and practical debugging of real-world web development challenges.

_(Note: Monday, June 9th, was King's Official Birthday, a public holiday, so there are no specific work activities for that day.)_

## ✅ Key Tasks This Week

-   **📌 First Client Consultation & IT Service Proposal Insight**: Participated in the first direct client meeting, gaining practical experience in client communication, requirement elicitation, and understanding IT service proposals from a business perspective (Day 02).
-   **📌 Completed "Open-Source CMS vs. Web Builders" Research & Presentation**: Finalized comprehensive research and created presentation materials on the comparative analysis of CMS vs. Web Builders, including AI integration (Day 02, 03).
-   **📌 Automated News Article Scraping & WordPress Upload Script Development**: Designed and implemented a Python script to automatically scrape ABC News articles and upload them to WordPress as custom posts via the REST API, demonstrating practical API interaction (Day 03, 04).
-   **📌 ISAAC Painting Website Cloning & Responsive Implementation**: Commenced and actively implemented the ISAAC Painting website cloning task using Elementor, focusing on accurate responsive layout application and consistent styling (Day 04, 05).
-   **📌 Elementor Dynamic Content Mastery**: Utilized Elementor's Loop Item template and Loop Grid widget for efficient and dynamic post content display, reducing the need for custom PHP (Day 05).
-   **📌 WordPress Ecosystem Tooling Exploration**: Confirmed and explored options for integrating Breadcrumb Navigation and Google Reviews using plugins and APIs (Day 04, 05).
-   **📌 Continued WordPress Hooks & REST API Learning**: Continued deepening understanding of WordPress hooks and REST API, with discussions clarifying their practical application (Day 04, 05).

## 🧠 What I Learned

-   **Real-world Client Communication & Business Acumen**: Through direct client consultation, I grasped the practicalities of client communication, detailed requirement gathering, and understanding business decision-making processes for IT services from a non-developer perspective.
-   **API-Driven Web Scraping Efficiency**: Gained hands-on experience in identifying and directly interacting with AJAX-powered API endpoints for highly efficient data collection, proving it a more robust method than traditional HTML parsing for dynamic content.
-   **Automated WordPress Content Management**: Mastered programmatic content creation on WordPress via the REST API, including post creation, media uploads, and dynamic taxonomy/metadata assignment, revealing a powerful method for automating site updates.
-   **Practical Responsive Design Implementation**: Concretely applied consistent unit and padding guidelines (`1400px` max-width for desktop, `100%` width with `20-25px` padding for mobile/tablet) for implementing truly responsive layouts, addressing previous uncertainties.
-   **Strategic Elementor Feature Utilization**: Solidified the practice of prioritizing Elementor's native advanced features, like **Loop Item templates for dynamic content**, which effectively reduces the reliance on custom PHP (`functions.php`) for content presentation.
-   **Project Prioritization in Real Scenarios**: Understood how new client tasks can shift project priorities, leading to the temporary pausing of ongoing internal development projects like the Dev News Hub and Docscraper.
-   **Clarifying Abstract Concepts (Hooks) through Examples**: Received clearer explanations and concrete use cases for WordPress hooks (Actions/Filters), helping to bridge the gap between theoretical knowledge and practical application.
-   **Importance of Data Cleaning for Automation**: Understood the critical importance of cleaning scraped HTML content by removing unnecessary elements to ensure the quality and usability of data uploaded to WordPress.

## 🔧 Technical Problem-Solving Experience

-   **AJAX API Endpoint Discovery for Scraping**:
    -   **Problem**: Initially attempted to scrape dynamic content using standard pagination, but articles were loaded via an AJAX "Load More" button.
    -   **Cause**: The content wasn't statically present in the initial HTML; it was fetched asynchronously via an API.
    -   **Solution**: Used **browser developer tools (Network tab)** to identify the specific AJAX API endpoint (`https://www.abc.net.au/news/api/...`) called by the "Load More" button. Modified the Python script to directly call this API, making scraping much more efficient and robust than simulating button clicks or parsing traditional pagination links.
-   **HTML Content Cleaning and Validation**:
    -   **Problem**: Scraped article bodies contained unwanted elements (ads, share buttons, footers) alongside the main content.
    -   **Cause**: These elements were part of the source HTML and needed specific identification and removal.
    -   **Solution**: Iteratively refined Beautiful Soup parsing rules by identifying specific `div` classes or HTML tags in **browser developer tools (F12)**. Crucially, used a **local HTML preview file (`article_preview.html`)** generated by the script to visually inspect the cleaned output, allowing for systematic debugging and improvement of removal logic.
-   **Dynamic WordPress Taxonomy Mapping**:
    -   **Problem**: Needed to assign scraped article topics to existing WordPress categories/tags, but their IDs could change.
    -   **Cause**: Hardcoding taxonomy IDs makes the script brittle to WordPress backend changes.
    -   **Solution**: Implemented logic to **fetch WordPress category and tag IDs dynamically via the WordPress REST API** at the script's initialization. This ensured the script could correctly map topics to taxonomies without manual updates, enhancing flexibility.
-   **Responsive Layout Discrepancies Debugging**:
    -   **Problem**: Elementor editor showed correct layouts, but live site or specific device views appeared broken.
    -   **Cause**: Inconsistent application of responsive units and padding, leading to content overflow or misalignments on different screen sizes.
    -   **Solution**: Applied a consistent responsive strategy: **desktop containers with `1400px` maximum width**, and **mobile/tablet sections with `100%` width and `20-25px` fixed left/right padding.** Used **browser developer tools (F12) responsive modes** to meticulously inspect elements and adjust their properties based on these unified units.
-   **Cache and Style Conflict Resolution**:
    -   **Problem**: New CSS styles weren't applying, or old content persisted despite changes.
    -   **Cause**: Browser cache or server/plugin-level caching serving outdated versions of assets. CSS specificity or load order issues.
    -   **Solution**: Systematically **cleared browser cache (hard refresh)**, followed by **clearing any caching plugins (e.g., LiteSpeed Cache) and server-side cache.** When styles were still an issue, used **browser developer tools (F12) to inspect CSS rules**, checking for specificity conflicts or incorrect load order. Also noted the method of **temporarily deactivating plugins** to identify conflicts.

## 💡 Reflections

-   **From Theory to Practicality**: This week marked a significant pivot, moving from theoretical research (CMS/Web Builders) and basic conceptual understanding (hooks) to concrete, hands-on client project work (ISAAC Painting) and advanced automation. This direct application greatly solidified my understanding of previously abstract concepts.
-   **The Power of API Integration**: The experience with the Python scraping script reinforced the immense power and efficiency of directly interacting with web APIs. It's a game-changer for automated data handling compared to relying solely on HTML parsing.
-   **Elementor as a Robust Tool**: I discovered Elementor's capabilities for dynamic content through features like the **Loop Item template**, allowing for complex layouts without extensive custom coding. This highlights the importance of leveraging a tool's full potential.
-   **Systematic Debugging is Key**: The repeated emphasis on using browser developer tools (F12) for layout inspection, network analysis (for APIs), and CSS debugging (for cache/specificity) became central to my problem-solving workflow. This reinforced a disciplined, iterative approach to troubleshooting.
-   **Project Flow and Prioritization**: I gained a clearer understanding of how real-world project demands (new client tasks) can influence and even temporarily pause ongoing internal development, requiring adaptability.
-   **Continuous Learning Mindset**: Despite successfully implementing several features, discussions in meetings (e.g., on hooks) and observations during cloning (e.g., header shrink effect) consistently highlighted areas for deeper learning and future exploration.

## 🌱 Points of Improvement & Next Week's Goals

-   **ISAAC Painting Site Completion**: Focus on accurately cloning the remaining parts of the `isaacpainting.com.au` homepage and then begin building out the Post Archive and dedicated Articles pages, ensuring full responsiveness.
-   **Google Review Integration Research**: Deepen research into Google Review integration, exploring both plugin and potential custom API connection methods to display actual client reviews.
-   **Header Shrink Effect Research**: Investigate and plan the implementation of a "shrink on scroll" effect for the header on the ISAAC Painting site.
-   **Advanced WordPress Hooks & REST API Application**: Based on meeting feedback, actively seek opportunities within the ISAAC Painting project or a new assignment to practically apply more complex WordPress hooks and further extend REST API usage.
-   **CMS/Web Builder Presentation Preparation**: Keep the presentation materials polished and ready for the rescheduled delivery next week.

------

# 📝 5주차 회고 (2025.06.09 ~ 06.13)

인턴십 5주차는 집중적인 연구에서 벗어나 **직접적인 클라이언트 프로젝트 구현**으로 중요한 전환점을 맞이했습니다. 주로 Elementor를 사용하여 ISAAC Painting 웹사이트를 복제하는 작업에 몰두했으며, 이 과정에서 **실질적인 반응형 디자인, Elementor의 고급 기능을 활용한 동적 콘텐츠 표시, 그리고 워드프레스용 웹 스크래핑 자동화 스크립트 정교화** 작업을 계속했습니다. 특히, 클라이언트와의 직접적인 논의와 실제 웹 개발 문제 디버깅을 통해 귀중한 통찰력을 얻었습니다.

_(참고: 6월 9일 월요일은 국왕 탄신일 공휴일이어서 별도의 업무 활동은 없습니다.)_

## ✅ 이번 주 주요 작업

-   **📌 첫 고객사 상담 및 IT 서비스 제안 통찰**: 첫 대면 고객 미팅에 참여하여 고객 커뮤니케이션, 요구사항 도출, 그리고 비즈니스 관점에서 IT 서비스 제안에 대한 실무 경험을 얻었습니다 (2일차).
-   **📌 "오픈소스 CMS vs. 웹 빌더" 리서치 및 발표 완료**: AI 통합을 포함한 CMS와 웹 빌더 비교 분석에 대한 심층 리서치를 마무리하고 발표 자료를 제작했습니다 (2일차, 3일차).
-   **📌 뉴스 기사 자동 스크래핑 및 워드프레스 업로드 스크립트 개발**: ABC 뉴스 기사를 자동으로 스크래핑하여 REST API를 통해 워드프레스에 커스텀 포스트로 업로드하는 파이썬 스크립트를 설계하고 구현하여 실질적인 API 상호작용 능력을 시연했습니다 (3일차, 4일차).
-   **📌 ISAAC Painting 웹사이트 클로닝 및 반응형 구현**: Elementor를 사용하여 ISAAC Painting 웹사이트 클로닝 작업을 시작하고, 정확한 반응형 레이아웃 적용 및 일관된 스타일링 구현에 집중했습니다 (4일차, 5일차).
-   **📌 Elementor 동적 콘텐츠 마스터링**: Elementor의 루프 아이템(Loop Item) 템플릿과 루프 그리드(Loop Grid) 위젯을 활용하여 효율적이고 동적인 게시물 콘텐츠 표시를 구현했으며, 이를 통해 커스텀 PHP 코드의 필요성을 줄였습니다 (5일차).
-   **📌 워드프레스 생태계 도구 탐색**: 브레드크럼(Breadcrumb) 내비게이션 및 구글 리뷰 통합을 위한 플러그인 및 API 옵션을 확인하고 탐색했습니다 (4일차, 5일차).
-   **📌 워드프레스 훅 및 REST API 학습 지속**: 워드프레스 훅 및 REST API에 대한 이해를 계속 심화했으며, 관련 논의를 통해 실질적인 적용 방법을 명확히 했습니다 (4일차, 5일차).

## 🧠 배운 핵심 개념

-   **실무적 고객 커뮤니케이션 및 비즈니스 통찰**: 직접적인 고객 상담을 통해 고객과의 소통, 상세한 요구사항 도출, 그리고 비IT 기업의 IT 서비스 의사결정 과정을 실질적으로 파악했습니다.
-   **API 기반 웹 스크래핑의 효율성**: AJAX 기반 API 엔드포인트를 식별하고 직접 상호작용하여 데이터를 효율적으로 수집하는 실질적인 경험을 얻었습니다. 이는 동적 콘텐츠의 경우 기존 HTML 파싱보다 훨씬 강력한 방법임을 입증했습니다.
-   **워드프레스 자동 콘텐츠 관리**: 워드프레스 REST API를 사용하여 게시물 생성, 미디어 업로드, 동적 텍소노미/메타데이터 할당 등 프로그래밍 방식으로 콘텐츠를 관리하는 방법을 숙달하여, 사이트 업데이트를 자동화하는 강력한 방법을 배웠습니다.
-   **실질적인 반응형 디자인 구현**: 반응형 레이아웃 구현을 위해 특정 단위 및 패딩 가이드라인(**데스크탑 최대 1400px, 모바일/태블릿 100% 너비 및 20-25px 패딩**)을 일관되게 적용하여, 이전의 불확실했던 부분을 명확히 해결했습니다.
-   **Elementor 기능의 전략적 활용**: **루프 아이템(Loop Item) 템플릿을 활용한 동적 콘텐츠 표시**와 같이 Elementor의 고급 네이티브 기능을 우선적으로 활용하여, 특정 콘텐츠 표시에 있어 커스텀 PHP(`functions.php`) 의존도를 효과적으로 줄이는 방식을 확고히 했습니다.
-   **실제 시나리오에서의 프로젝트 우선순위**: 새로운 클라이언트 작업이 기존 내부 개발 프로젝트(데브 뉴스 허브, Docscraper 등)의 우선순위를 어떻게 변경시키고 일시 중단시킬 수 있는지 이해하며, 적응력의 중요성을 깨달았습니다.
-   **추상적 개념(훅)의 명확화**: 워드프레스 훅(액션/필터)이 실제 프로젝트에서 언제 유용하게 사용되는지에 대한 더 명확한 설명과 구체적인 사용 사례를 통해 이론적 지식과 실무 적용 사이의 간극을 줄였습니다.
-   **자동화를 위한 데이터 클리닝의 중요성**: 스크래핑된 HTML 콘텐츠에서 불필요한 요소를 제거하여 워드프레스에 업로드될 데이터의 품질과 유용성을 보장하는 것이 얼마나 중요한지 이해했습니다.

## 🔧 기술적 문제 해결 경험

-   **스크래핑을 위한 AJAX API 엔드포인트 발견**:
    -   **문제**: 처음에는 일반적인 페이지네이션 방식으로 동적 콘텐츠를 스크래핑하려고 했으나, 기사들이 AJAX "더보기" 버튼을 통해 로드되었습니다.
    -   **원인**: 콘텐츠가 초기 HTML에 정적으로 존재하지 않고, API를 통해 비동기적으로 가져와졌기 때문입니다.
    -   **해결**: **브라우저 개발자 도구(Network 탭)**를 사용하여 "더보기" 버튼이 호출하는 특정 AJAX API 엔드포인트(`https://www.abc.net.au/news/api/...`)를 식별했습니다. 파이썬 스크립트를 수정하여 이 API를 직접 호출하도록 함으로써, 버튼 클릭을 시뮬레이션하거나 기존 페이지네이션 링크를 파싱하는 것보다 훨씬 효율적이고 견고하게 스크래핑할 수 있었습니다.
-   **HTML 콘텐츠 클리닝 및 유효성 검사**:
    -   **문제**: 스크래핑된 기사 본문에 불필요한 요소(광고, 공유 버튼, 푸터 등)가 함께 포함되어 있었습니다.
    -   **원인**: 이러한 요소들이 원본 HTML의 일부였으며, 특정하여 제거해야 했습니다.
    -   **해결**: **브라우저 개발자 도구(F12)**에서 특정 `div` 클래스나 HTML 태그를 식별하여 Beautiful Soup 파싱 규칙을 반복적으로 개선했습니다. 특히, 스크립트가 생성하는 **로컬 HTML 미리보기 파일(`article_preview.html`)**을 사용하여 클리닝된 결과물을 시각적으로 확인하면서, 제거 로직을 체계적으로 디버깅하고 개선할 수 있었습니다.
-   **워드프레스 텍소노미 동적 매핑**:
    -   **문제**: 스크래핑된 기사 토픽을 기존 워드프레스 카테고리/태그에 할당해야 했지만, 이들의 ID가 변경될 수 있었습니다.
    -   **원인**: 텍소노미 ID를 하드코딩하면 워드프레스 백엔드 변경에 스크립트가 취약해집니다.
    -   **해결**: 스크립트 초기화 시 **워드프레스 REST API를 통해 워드프레스 카테고리 및 태그 ID를 동적으로 가져오는** 로직을 구현했습니다. 이를 통해 스크립트가 수동 업데이트 없이도 토픽을 텍소노미에 올바르게 매핑할 수 있어 유연성이 향상되었습니다.
-   **반응형 레이아웃 불일치 디버깅**:
    -   **문제**: Elementor 에디터에서는 레이아웃이 올바르게 보였지만, 라이브 사이트나 특정 기기에서 볼 때 깨져 보였습니다.
    -   **원인**: 반응형 단위 및 패딩 적용의 불일치로 인해 다양한 화면 크기에서 콘텐츠 오버플로우나 정렬 문제가 발생했습니다.
    -   **해결**: 일관된 반응형 전략을 적용했습니다: **데스크탑 컨테이너는 `1400px` 최대 너비**, **모바일/태블릿 섹션은 `100%` 너비에 `20-25px`의 고정 좌우 패딩**을 사용했습니다. **브라우저 개발자 도구(F12)의 반응형 모드**를 사용하여 요소를 면밀히 검사하고, 이러한 통일된 단위를 기반으로 속성을 조정했습니다.
-   **캐시 및 스타일 충돌 해결**:
    -   **문제**: 새로운 CSS 스타일이 적용되지 않거나, 변경했음에도 이전 콘텐츠가 계속 표시되었습니다.
    -   **원인**: 브라우저 캐시 또는 서버/플러그인 레벨 캐시가 오래된 버전의 자산을 제공했기 때문입니다. CSS 우선순위 또는 로드 순서 문제도 원인이 될 수 있습니다.
    -   **해결**: 먼저 **브라우저 캐시를 체계적으로 지우고 (강제 새로고침)**, 이어서 **캐싱 플러그인(예: LiteSpeed Cache) 및 서버 측 캐시를 지웠습니다.** 스타일 문제가 계속될 경우, **브라우저 개발자 도구(F12)를 사용하여 CSS 규칙을 검사**하고 우선순위 충돌이나 잘못된 로드 순서를 확인했습니다. 또한, **플러그인을 하나씩 비활성화**하여 충돌을 식별하는 방법도 고려했습니다.

## 💡 느낀 점

-   **이론에서 실무로의 전환**: 이번 주는 (CMS/웹 빌더) 연구와 (훅 등) 기본 개념 이해에서 벗어나, 실제 클라이언트 프로젝트(ISAAC Painting) 작업 및 고급 자동화로의 중요한 전환점이었습니다. 이러한 직접적인 적용은 이전에 추상적이었던 개념에 대한 이해를 크게 굳혔습니다.
-   **API 통합의 위력**: 파이썬 스크래핑 스크립트 경험은 웹 API와 직접 상호작용하는 것의 엄청난 힘과 효율성을 재확인시켜 주었습니다. 이는 전통적인 HTML 파싱에만 의존하는 것과는 달리 자동화된 데이터 처리에 있어 혁신적이었습니다.
-   **Elementor의 강력함**: **루프 아이템(Loop Item) 템플릿**과 같은 기능을 통해 Elementor의 동적 콘텐츠 처리 능력을 발견했으며, 이를 통해 복잡한 레이아웃을 광범위한 커스텀 코드 없이도 구현할 수 있다는 점을 알게 되었습니다. 이는 도구의 잠재력을 최대한 활용하는 것의 중요성을 강조합니다.
-   **체계적인 디버깅의 중요성**: 레이아웃 검사, 네트워크 분석(API), CSS 디버깅(캐시/우선순위)을 위해 브라우저 개발자 도구(F12)를 반복적으로 활용하는 것은 문제 해결 워크플로우의 핵심이 되었습니다. 이는 체계적이고 반복적인 문제 해결 접근 방식의 중요성을 강화했습니다.
-   **프로젝트 흐름 및 우선순위**: 실제 프로젝트 요구사항(새로운 클라이언트 작업)이 진행 중인 내부 개발에 어떻게 영향을 미치고 일시적으로 중단시킬 수 있는지에 대한 명확한 이해를 얻었으며, 이에 대한 적응력의 중요성을 깨달았습니다.
-   **지속적인 학습 마인드**: 여러 기능을 성공적으로 구현했음에도 불구하고, 미팅에서의 논의(예: 훅)와 클로닝 과정에서의 관찰(예: 헤더 축소 효과)을 통해 더 깊은 학습과 향후 탐색이 필요한 영역이 계속해서 드러났습니다.

## 🌱 아쉬운 점 및 다음 주 목표

-   **ISAAC Painting 사이트 완성**: `isaacpainting.com.au` 홈페이지의 남은 부분을 정확히 클로닝하는 데 집중하고, 이후 포스트 아카이브 및 전용 Articles 페이지 구축을 시작하여 완벽한 반응형을 확보할 것입니다.
-   **Google Review 통합 리서치**: 구글 리뷰 통합에 대한 리서치를 심화하여, 플러그인 방식과 함께 실제 클라이언트 리뷰를 표시하기 위한 잠재적인 커스텀 API 연결 방식도 탐색할 것입니다.
-   **헤더 축소 효과 리서치**: `ISAAC Painting` 사이트에서 스크롤 시 헤더가 줄어드는("shrink on scroll") 효과 구현 방법을 조사하고 계획할 것입니다.
-   **고급 워드프레스 훅 및 REST API 적용**: 미팅 피드백을 바탕으로, `ISAAC Painting` 프로젝트 또는 새로운 과제 내에서 더 복잡한 워드프레스 훅을 실질적으로 적용하고 REST API 활용을 더욱 확장할 기회를 적극적으로 모색할 것입니다.
-   **CMS/웹 빌더 발표 준비**: 다음 주에 재조정된 발표를 위해 발표 자료를 잘 다듬고 준비된 상태로 유지할 것입니다.
