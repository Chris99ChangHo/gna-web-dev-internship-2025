# 📅 Day 01 (2025-06-16, Mon)

## 🎓 What I Did Today

**📌 Completed the ISAAC Painting website development, focusing on advanced Elementor features for dynamic layouts.**  
**📌 Diagnosed an API error in the ABC News scraping script and learned about the importance of logging and ongoing web scraping maintenance.**  

### Detailed Activities

**1. Morning Development Meeting & Task Review** The day started with a development meeting where I provided updates on ongoing projects.

-   **ISAAC Painting Progress**: I reported that only one page implementation remained for the ISAAC Painting website.
-   **Mini-Project Progress (REST API)**: I confirmed that the mini-project involving the REST API is currently on hold and will resume once the ISAAC Painting task is completed.
-   **Future Learning Path Feedback**: I received feedback to inform the team once the ISAAC Painting site is finished, and was advised to continue practicing with **WordPress hooks, APIs, and plugins** to gain further proficiency.

**2. ISAAC Painting Site Development Completion (Morning)** Following the meeting, I focused on completing the remaining sections of the ISAAC Painting website throughout the morning.

-   **Utilized Elementor Loop Grid and Multiple Loop Item Templates**:
    
    -   Successfully implemented post list, card, and magazine-style layouts using the **Loop Grid widget**.
    -   Created **multiple Loop Item templates** to apply different designs to individual posts within a single Loop Grid (e.g., a large featured post, with smaller thumbnail + text for other posts in a horizontal arrangement).
    -   Achieved diverse layouts solely by combining various Loop Item templates within the Loop Grid.
-   **Identified Need for Separate Research on Sticky Header/Logo Animations**:
    
    -   Determined that achieving complex animations like sticky headers or shrinking logos purely with CSS and JS was limited by the current theme/plugin structure.
    -   Concluded that these features would require additional research and custom development, and therefore, were excluded from the current implementation.

**3. Python Script Logging Module Application & Issue Diagnosis (Afternoon)** In the afternoon, I reviewed the **logging module application** in the ABC News scraping Python script and identified the cause of a new error.

-   **Logging Module Confirmed**: Verified that the `logging` module was successfully applied to the script from last week, reducing unnecessary `print()` outputs and improving log readability.
-   **Diagnosed API `404 Not Found` Error**: Discovered a **`404 Client Error: Not Found` occurring during scraping attempts**. This indicates that the ABC News website's API endpoint (`https://www.abc.net.au/news/topic/technology/_ajax_component/story-list?offset=0&count=20`) may have changed or is no longer valid.
-   **Recognized Importance of Web Scraping Maintenance**: This error highlighted the crucial need for **continuous maintenance and re-analysis of web scraping logic** due to potential website structure changes.

## 🧠 Key Concepts Learned

-   **Strategic Elementor Feature Utilization**: Deepened understanding of how to effectively use Elementor's Loop Grid widget in conjunction with multiple Loop Item templates to create complex and dynamic post layouts without extensive custom coding, demonstrating Elementor's powerful capabilities.
-   **Realistic Scope Definition in Web Development**: Learned the importance of recognizing the limitations of current tools (theme/plugins) for complex features like advanced animations and prioritizing implementable elements, understanding that some features require more in-depth research and custom work.
-   **Python `logging` Module Best Practices**: Understood the benefits of using the `logging` module over `print()` for better log readability, debugging efficiency, maintainability, and performance. Gained practical experience in setting logging levels and formatting.
-   **Core Principles of WordPress REST API Interaction**: Reconfirmed the fundamental concepts of interacting with WordPress via its REST API for content management (posts, media, taxonomies), including **secure authentication using Application Passwords**.
-   **Dynamic Nature and Maintenance of Web Scraping**: Experienced firsthand that web scraping is not a one-time setup but requires **continuous monitoring and adaptation** to website changes (e.g., API endpoint modifications), emphasized by the `404 Not Found` error.
-   **Importance of Data Cleansing for Automation**: Reinforced the critical role of refining data cleansing and filtering logic in scraping scripts to ensure high-quality, relevant content for automated WordPress uploads.

## 💡 Practical Trial-and-Error and Tips

-   **Leveraging Elementor Loop Item Templates for Layout Complexity**: Realized that Elementor's **Loop Item templates offer a highly efficient way to design varied post layouts** within a single Loop Grid, significantly reducing the need for custom PHP logic for display.
-   **Proactive Recognition of Feature Complexity**: It's crucial to identify early on when a desired feature (like complex header animations) might exceed the capabilities of off-the-shelf tools, necessitating dedicated research or custom development.
-   **Immediate Debugging Benefits of `logging`**: Implementing the `logging` module allowed for **much quicker identification of the critical `404 Not Found` API error**, demonstrating its real-world value in streamlining the debugging process.
-   **Web Scraping Requires Ongoing Vigilance**: The `404` error highlighted that web scraping solutions demand **continuous maintenance and regular verification** of target website structures and APIs through browser developer tools (Network tab) to ensure data collection stability.

## 🔜 Next Steps

-   **Analyze ABC News Scraping API Changes and Modify Script**: Dedicate time outside of core project hours to re-analyze the ABC News website's article listing page using browser developer tools, identify changes in the "Load more stories" button's network requests (URL and parameters), and update the Python script accordingly.
-   **Continue WordPress Hooks, API, and Plugin Practice**: As advised in the morning meeting, I will continue hands-on practice with WordPress hooks, REST API, and various plugins to strengthen my practical skills and understanding.

----------

# 📅 1일차 (2025-06-16, 월)

## 🎓 오늘 한 일

**📌 ISAAC Painting 웹사이트 개발을 완료했으며, 동적 레이아웃을 위해 Elementor의 고급 기능을 활용했습니다.**  
**📌 ABC 뉴스 스크래핑 스크립트의 API 오류를 진단하고 로깅 및 웹 스크래핑 유지보수의 중요성에 대해 학습했습니다.**  

### 상세 활동

**1. 오전 개발 미팅 및 업무 점검** 하루는 개발 미팅으로 시작되었고, 진행 중인 프로젝트에 대한 업데이트를 공유했습니다.

-   **ISAAC Painting 진행 상황**: ISAAC Painting 웹사이트는 페이지 구현이 하나만 남았다고 보고했습니다.
-   **미니 프로젝트(REST API) 진행 상황**: REST API를 활용한 미니 프로젝트는 현재 보류 중이며, ISAAC Painting 작업이 끝나면 다시 진행할 예정임을 확인했습니다.
-   **향후 학습 방향 피드백**: ISAAC Painting 작업을 끝내면 확인해 줄 테니 알려달라는 피드백을 받았고, 이후 **훅(Hook), API, 플러그인을 계속 사용하며 감각을 익히라는 조언**을 들었습니다.

**2. ISAAC Painting 사이트 개발 완료 (오전)** 미팅 이후, 오전 내내 ISAAC Painting 웹사이트의 남은 부분을 완성하는 데 집중했습니다.

-   **Elementor Loop Grid 및 여러 Loop Item 템플릿 활용**:
    
    -   **Loop Grid 위젯**을 사용하여 포스트 리스트, 카드, 매거진 스타일의 레이아웃을 구현했습니다.
    -   **여러 개의 Loop Item 템플릿**을 만들어, 하나의 Loop Grid에서 포스트마다 다른 디자인(예: 대표 포스트, 일반 포스트)을 적용했습니다.
    -   대표 포스트는 크게, 나머지 포스트는 썸네일과 텍스트를 가로로 배치하는 등 **다양한 레이아웃을 Loop Grid의 템플릿 조합만으로 완성**했습니다.
-   **Sticky 헤더/로고 애니메이션 등 추가 리서치 필요 사항**:
    
    -   테마/플러그인 구조상 CSS, JS만으로 sticky 헤더, 로고 축소(shrink logo)와 같은 복잡한 애니메이션을 완벽하게 구현하는 데 한계가 있음을 확인했습니다.
    -   이러한 기능들은 추가적인 리서치와 커스텀 작업이 필요하다고 판단하여, 이번 구현에서는 제외했습니다.

**3. Python 스크립트 로깅 모듈 적용 및 문제 진단 (오후)** 오후에는 지난주부터 진행하던 ABC 뉴스 스크래핑 파이썬 스크립트의 **로깅 모듈 적용 상태를 확인**하고, 발생한 문제의 원인을 파악했습니다.

-   **Logging 모듈 적용 확인**: 지난주 작업했던 스크립트에 `logging` 모듈이 성공적으로 적용되어 불필요한 `print()` 출력이 줄어들고 로그 가독성이 향상되었음을 확인했습니다.
-   **API `404 Not Found` 오류 진단**: 현재 스크래핑 시도 시 **`404 Client Error: Not Found` 오류가 발생**하고 있음을 확인했습니다. 이는 ABC News 웹사이트의 API 엔드포인트(`https://www.abc.net.au/news/topic/technology/_ajax_component/story-list?offset=0&count=20`)가 변경되었거나 더 이상 유효하지 않음을 의미합니다.
-   **웹 스크래핑 유지보수의 중요성 인지**: 이 오류를 통해 웹사이트 구조 변화에 따른 스크래핑 로직의 **지속적인 유지보수와 재분석의 필요성**을 다시 한번 깨달았습니다.

## 🧠 배운 핵심 개념

-   **Elementor 고급 기능의 실질적 활용**: Loop Grid 위젯과 여러 Loop Item 템플릿을 조합하여 동적 콘텐츠의 다양한 레이아웃을 효율적으로 구현하는 방법을 익혔습니다. 이는 페이지 빌더만으로도 복잡한 디자인을 구현할 수 있는 강력한 방법임을 깨달았습니다.
-   **웹 개발에서의 현실적인 범위 설정**: 고급 애니메이션과 같은 복잡한 기능을 현재의 도구(테마/플러그인)만으로는 완벽하게 구현하기 어려울 수 있음을 인지하고, 구현 가능한 요소에 우선순위를 두는 것의 중요성을 배웠습니다. 일부 기능은 더 심층적인 연구와 맞춤형 개발이 필요함을 판단했습니다.
-   **Python `logging` 모듈 사용법 및 모범 사례**: `print()` 대신 `logging` 모듈을 사용하면 **로그 가독성, 디버깅 효율성, 유지보수성, 성능** 측면에서 더 나은 이점을 얻을 수 있음을 이해했습니다. 로깅 레벨 설정 및 형식 지정에 대한 실제 경험을 쌓았습니다.
-   **워드프레스 REST API 상호작용의 핵심 원리**: 워드프레스 REST API를 통한 콘텐츠 관리(게시물, 미디어, 텍소노미)의 기본 개념과 **애플리케이션 비밀번호(Application Password)를 활용한 보안 인증** 방식을 재확인했습니다.
-   **웹 스크래핑의 동적 특성 및 유지보수**: 웹 스크래핑이 일회성 설정이 아니라, 웹사이트 변경(예: API 엔드포인트 수정)에 대한 **지속적인 모니터링 및 적응**이 필요함을 `404 Not Found` 오류를 통해 직접 경험했습니다.
-   **자동화를 위한 데이터 정제의 중요성**: 자동화된 워드프레스 업로드를 위해 고품질의 관련성 높은 콘텐츠를 확보하려면, 스크래핑 스크립트에서 데이터 정제 및 필터링 로직을 정교하게 다듬는 것이 중요함을 재확인했습니다.

## 💡 실전 시행착오 및 팁

-   **Elementor Loop Item 템플릿을 활용한 레이아웃 복잡성 해결**: Elementor의 **Loop Item 템플릿은 단일 Loop Grid 내에서 다양한 게시물 레이아웃을 설계하는 데 매우 효율적인 방법**임을 깨달았으며, 이는 디스플레이를 위한 커스텀 PHP 로직의 필요성을 크게 줄여줍니다.
-   **기능 복잡성에 대한 선제적 인식**: 원하는 기능(예: 복잡한 헤더 애니메이션)이 현재 사용 가능한 도구의 역량을 넘어설 수 있음을 조기에 파악하여, 전용 연구나 맞춤형 개발이 필요함을 인지하는 것이 중요합니다.
-   **`logging` 모듈의 즉각적인 디버깅 효과**:  `logging` 모듈을 적용한 후, 콘솔의 불필요한 출력이 줄어들어 **치명적인 `404 Not Found` API 오류를 훨씬 더 빠르게 식별**할 수 있었고, 이는 디버깅 프로세스를 간소화하는 데 실제적인 가치가 있음을 입증했습니다.
-   **웹 스크래핑은 지속적인 관리 영역**: 오늘 발생한 `404` 오류는 웹 스크래핑 솔루션이 **일회성 개발로 끝나는 것이 아니라, 웹사이트 구조 및 API에 대한 지속적인 모니터링과 브라우저 개발자 도구(Network 탭)를 통한 정기적인 검증이 필요하다는 강력한 교훈**을 주었습니다.

## 🔜 이후 학습 방향

-   **ABC 뉴스 스크래핑 API 변경 사항 분석 및 스크립트 수정**: 핵심 프로젝트 시간 외에 ABC 뉴스 웹사이트의 기사 목록 페이지를 개발자 도구로 재분석하고, "더보기" 버튼의 네트워크 요청(URL 및 파라미터) 변경 사항을 확인하여 파이썬 스크립트를 업데이트할 예정입니다.
-   **워드프레스 훅, API, 플러그인 실습 지속**: 오전 미팅에서 조언받은 대로 워드프레스 훅, REST API, 다양한 플러그인을 계속 실습하여 실질적인 기술력과 이해도를 강화할 것입니다.
