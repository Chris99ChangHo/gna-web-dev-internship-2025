# 📅 Day 04 (2025-06-12, Thu)

## 🎓 What I Did Today

**📌 Participated in the morning development meeting, discussing mini-project progress and receiving feedback.**   
**📌 Initiated practical implementation of the ISAAC Painting website cloning task, focusing on responsive layout.**   
**📌 Confirmed options for Breadcrumb Navigation and Google Review integration, planning further action for tomorrow.**   
**📌 Python script for automated news article scraping from ABC News to WordPress is in progress, demonstrating initial success.**  

### Detailed Activities

**1. Morning Development Meeting & Mini-Project Discussion** Today's morning development meeting involved a discussion on the progress of my mini-project, the "Development News Hub" (Dev News Hub) site.

-   **Progress Update**: I shared the initial success of the automated scraping and WordPress upload script, mentioning that I had drafted the code and successfully scraped and uploaded 8 articles to the `news` custom post type in WordPress.
-   **Discussion on WP REST API vs. Hooks**: I explained how this task, initially intended as practice for hooks and actions, unexpectedly became a practical exercise in using the WordPress REST API, demonstrating the connection via a Python script with an application password. The team acknowledged it as a good experience and asked for an update upon completion.
-   **Future Hook Application**: It was decided that we would move to the next step regarding hooks once I gain more confidence and proficiency in their practical application.
-   **Client Communication & New Task Assignment**:
    -   Chris inquired about my previous work on the K-Painting website (`kpainting.com.au`), asking for the link if I had worked on it. I explained that I had worked on it on a development server and that the homepage has since changed, but confirmed I still had the backend pages (including header and footer).
    -   I was then assigned to work on the `isaacpainting.com.au` homepage in Elementor on my development server.
    -   I confirmed receiving the Isaac Painting site copy on my development server.
    -   I inquired about the deadline for the ISAAC site.
    -   **Responsive Layout Units & Debugging**: I raised questions regarding best practices for responsive layouts, specifically concerning margin/padding units (`px`, `%`, `em`, `vw`) and debugging alignment issues that appear correct in the editor but break on live view or other devices.
        -   **Feedback**: Chris advised using a **1400px maximum width for desktop containers** and **100% width with 20px padding left and right for other devices (mobile/tablet)**.
    -   **Hooks Application Clarity**: I also expressed that while I understood the concept of WordPress hooks and basic exercises, I still felt unsure about their practical application in real projects and the specific problems they solve. Chris provided clarification: **hooks and actions are useful for adding more functionality or content within existing structures, such as placing an image icon on top of a featured image in a Post List.**

**2. ISAAC Painting Site Practical Task Implementation** I commenced the practical task of cloning the `isaacpainting.com.au` site, marking it as a new practical assignment after a while.

-   **Responsive Layout Implementation**: I actively implemented the responsive layout following the guidelines discussed:
    -   **Desktop**: Container maximum width set to **1400px**.
    -   **Mobile/Tablet & Other Devices**: Container width set to **100%** (default).
    -   **Padding**: Consistent **20-25px padding on both left and right sides** for responsive layout implementation.
-   **Breadcrumb Navigation**: Currently, I am proceeding with the layout implementation _excluding_ breadcrumb navigation. I plan to install a free plugin (e.g., Breadcrumb NavXT) and add it tomorrow.
-   **Google Review Functionality**: I confirmed that Google Reviews can be integrated via both API and plugin methods. I installed a plugin, but actual reviews are not displayed as a business account is not yet linked.

**3. WordPress Hooks/Actions/Filters** I plan to utilize hooks, actions, and filters as needed during the practical implementation. However, as of now, there hasn't been a critical need, so they haven't been applied yet.

**4. Other Project Status**

-   **Dev News Hub & Docscraper**: Development on the Dev News Hub and Docscraper projects is currently paused due to other ongoing tasks.
-   **Presentation Schedule**: The presentation scheduled for today has been postponed to next week.
-   **Current Focus**: My current focus is primarily on the ISAAC Painting site practical task and personal study.

## 🧠 Key Concepts Learned

-   **Practical Application of Responsive Design Principles**: Applied specific unit and padding guidelines (1400px max, 100% width, 20-25px padding) for implementing truly responsive layouts, addressing a previous uncertainty.
-   **Real-world Project Prioritization**: Understood how project priorities shift based on new client tasks, leading to the temporary pausing of ongoing internal development like the Dev News Hub and Docscraper.
-   **Clarifying Abstract Concepts (Hooks)**: Gained a clearer understanding of the practical scenarios where WordPress hooks (Actions/Filters) are valuable, moving beyond theoretical knowledge to concrete use cases for extending existing functionality.
-   **Client Interaction & Task Management**: Experienced the full cycle of receiving a new client task, understanding requirements, and beginning implementation, including managing communication and clarifying technical details.
-   **WordPress Ecosystem Tooling**: Confirmed the availability and methods for integrating common website features like Breadcrumb Navigation and Google Reviews using WordPress plugins and APIs.

## 💡 Practical Trial-and-Error and Tips

-   **Consistent Responsive Units**: Adhering to the advised `1400px` max container for desktop and `100%` with fixed padding for mobile/tablet provides a straightforward and effective strategy for responsive design.
-   **Strategic Plugin Use**: Recognizing when to use a plugin for common functionalities (like breadcrumbs or reviews) versus custom code is key for efficiency, especially when time is a factor.
-   **Proactive Questioning in Meetings**: Asking specific questions about confusing topics (like `px` vs. `%` for responsiveness or the practical use of hooks) during dedicated Q&A sessions in meetings is highly effective for gaining clarity from experienced developers.
-   **Debugging Layout Issues**: The tip on responsive unit application directly addresses my previous concern about layout inconsistencies, providing a clear starting point for debugging.

## 🔜 Next Steps

-   **ISAAC Painting Site Homepage Completion**: Continue developing the `isaacpainting.com.au` homepage in Elementor, focusing on accurately cloning the layout and ensuring responsiveness.
-   **Breadcrumb Navigation Integration**: Install and configure a breadcrumb plugin (e.g., Breadcrumb NavXT) for the ISAAC Painting site tomorrow.
-   **Google Review Integration**: Attempt to integrate Google Reviews further, potentially exploring alternative display methods or understanding business account linking for actual review display tomorrow.
-   **Preparation for CMS/Web Builder Presentation**: Although the presentation is postponed, keep the materials ready for next week.

----------

# 📅 4일차 (2025-06-12, 목)

## 🎓 오늘 한 일

**📌 오전 개발 미팅 참여, 미니 프로젝트 진행 상황 논의 및 피드백 수령.**   
**📌 ISAAC Painting 웹사이트 클로닝 실습 과제 착수, 반응형 레이아웃 구현에 집중.**   
**📌 브레드크럼 내비게이션 및 구글 리뷰 기능 연동 방안 확인, 내일 추가 조치 예정.**   
**📌 ABC 뉴스 기사 워드프레스 자동 스크래핑 파이썬 스크립트 개발 진행, 초기 성공 확인.**  

### 상세 활동

**1. 오전 개발 미팅 및 미니 프로젝트 논의** 오늘 오전 개발 미팅에서는 제가 진행하고 있는 '개발 뉴스 허브(Dev News Hub)' 미니 프로젝트의 진행 상황에 대해 논의했습니다.

-   **진행 상황 보고**: 어제 작성한 스크래핑 및 워드프레스 업로드 자동화 코드 초안이 성공적으로 작동하여, 실제로 기사 8개를 스크래핑해 WP 커스텀 포스트 `news`에 업로드한 것을 확인했다고 보고했습니다.
-   **WP REST API vs. 훅 논의**: 처음에는 훅과 액션 실습을 목표로 했으나, WP REST API를 파이썬 코드와 워드프레스 애플리케이션 비밀번호로 연결하여 사용하게 된 경험에 대해 설명했습니다. 팀에서는 이를 좋은 경험으로 평가했으며, 완성되면 알려달라고 요청했습니다.
-   **향후 훅 활용 방안**: 훅 사용에 자신감이 생기면 다음 단계로 넘어가자고 논의했습니다.
-   **고객 업무 배정 및 질의응답**:
    -   크리스로부터 과거 `kpainting.com.au` 작업 경험에 대한 질문을 받고, 개발 서버에서 작업하여 현재 홈페이지가 변경되었지만 백엔드 페이지(헤더/푸터 포함)는 보관하고 있다고 답변했습니다.
    -   이후 `isaacpainting.com.au` 홈페이지를 Elementor로 복제하는 실습 과제를 개발 서버에서 진행하도록 배정받았습니다.
    -   ISAAC 사이트 마감 기한을 문의했습니다.
    -   **반응형 레이아웃 단위 및 디버깅**: 레이아웃 작업 시 마진/패딩에 어떤 단위(px, %, em, vw 등)를 사용하는 것이 반응형에 가장 적합한지, 그리고 에디터에서는 완벽해 보여도 라이브나 다른 기기에서 깨지는 원인 및 디버깅 방법에 대해 질문했습니다.
        -   **피드백**: 크리스는 **데스크탑 버전 컨테이너는 1400px, 모바일/태블릿 등 나머지 디바이스는 100% 너비(기본값)에 좌우 패딩을 20px로 통일**하는 것을 권장했습니다.
    -   **훅 개념의 명확화**: 훅의 개념과 사용법은 알지만, 실제 프로젝트에서 언제 왜 사용해야 하는지, 어떤 문제를 해결하는지에 대한 추상적인 느낌이 여전하다고 언급했습니다. 크리스는 **훅과 액션은 기존 구조 내에 더 많은 기능이나 콘텐츠를 추가하고 싶을 때 유용하며, 예를 들어 게시물 목록의 추천 이미지 위에 이미지 아이콘을 추가하는 경우**와 같이 설명해주었습니다.

**2. ISAAC Painting 사이트 실습 과제 진행** 오랜만에 실무 과제로 `isaacpainting.com.au` 사이트 클론 실습에 착수했습니다.

-   **반응형 레이아웃 구현**: 논의된 가이드라인에 따라 반응형 레이아웃을 직접 구현했습니다.
    -   **데스크탑**: 컨테이너 최대 너비를 **1400px**로 설정.
    -   **모바일/태블릿 등**: 나머지 디바이스는 **100%** 너비(기본값).
    -   **패딩**: 반응형 레이아웃을 위해 좌우 **20~25px** 패딩을 통일해서 적용했습니다.
-   **브레드크럼 내비게이션**: 현재는 브레드크럼(경로 표시) 내비게이션을 제외하고 작업 진행 중입니다. 내일쯤 무료 플러그인(예: Breadcrumb NavXT)을 설치해서 추가할 계획입니다.
-   **구글 리뷰 기능**: 구글 리뷰(고객 리뷰) 연동이 API 방식과 플러그인 방식 모두 가능하다는 것을 확인했습니다. 플러그인은 설치했으나, 현재 비즈니스 계정이 없어 실제 리뷰는 표시되지 않는 상태입니다.

**3. 워드프레스 훅/액션/필터** 실습 중 필요해지면 워드프레스 훅/액션/필터를 활용할 계획입니다. 하지만 아직은 꼭 필요한 부분이 없어 적용하지 않았습니다.

**4. 기타 업무 상황**

-   **기존 프로젝트 일시 중단**: 데브뉴스허브 개발, Docscraper 등 기존 프로젝트는 다른 업무(ISAAC Painting 사이트 실습)로 인해 잠시 중단했습니다.
-   **발표 일정 연기**: 오늘 예정되었던 발표는 다음 주로 연기되었습니다.
-   **현재 집중**: 현재는 ISAAC Painting 사이트 실습 과제와 개인 공부에 집중하고 있습니다.

## 🧠 배운 핵심 개념

-   **반응형 디자인 원칙의 실무 적용**: 이전의 불확실했던 부분인 반응형 레이아웃 구현을 위해 특정 단위 및 패딩 가이드라인(최대 1400px, 100% 너비, 20-25px 패딩)을 적용하는 실질적인 경험을 했습니다.
-   **실제 프로젝트 우선순위 조정**: 새로운 고객 업무에 따라 프로젝트 우선순위가 어떻게 변경되는지 이해했으며, 이로 인해 데브 뉴스 허브나 Docscraper와 같은 내부 개발이 일시적으로 중단될 수 있음을 알게 되었습니다.
-   **추상적 개념(훅)의 명확화**: 워드프레스 훅(액션/필터)이 실제 프로젝트에서 언제 유용하게 사용되는지, 기존 기능을 확장하기 위한 구체적인 사용 사례를 통해 이론적 지식에서 벗어나 더 명확하게 이해했습니다.
-   **클라이언트 상호작용 및 작업 관리**: 새로운 클라이언트 작업을 받고, 요구사항을 이해하며, 구현을 시작하는 전체 사이클을 경험했습니다. 이는 커뮤니케이션 관리 및 기술적 세부사항 명확화의 중요성을 포함합니다.
-   **워드프레스 생태계 도구 활용**: 브레드크럼 내비게이션 및 구글 리뷰와 같은 일반적인 웹사이트 기능을 워드프레스 플러그인 및 API를 사용하여 통합하는 방법과 사용 가능성을 확인했습니다.

## 💡 실전 시행착오 및 팁

-   **일관된 반응형 단위 사용**: 데스크탑 컨테이너에 1400px 최대 너비를, 모바일/태블릿에 100% 너비와 고정 패딩을 적용하는 것은 반응형 디자인을 위한 명확하고 효과적인 전략이 됩니다.
-   **전략적 플러그인 사용**: 브레드크럼이나 리뷰와 같은 일반적인 기능에 플러그인을 사용할 시기와 커스텀 코드를 사용할 시기를 파악하는 것은 효율성을 위해 중요합니다.
-   **미팅 중 적극적인 질문**: 미팅 중 혼란스러웠던 주제(반응형 단위, 훅의 실제 사용처 등)에 대해 구체적인 질문을 하는 것은 숙련된 개발자로부터 명확한 설명을 얻는 데 매우 효과적입니다.
-   **레이아웃 문제 디버깅**: 반응형 단위 적용에 대한 팁은 레이아웃 불일치에 대한 이전의 우려를 직접적으로 해소해주어 명확한 디버깅 시작점을 제공했습니다.

## 🔜 이후 학습 방향

-   **ISAAC Painting 사이트 홈페이지 완성**: Elementor를 사용하여 `isaacpainting.com.au` 홈페이지 개발을 계속하고, 레이아웃을 정확하게 복제하고 반응형을 확보하는 데 집중할 것입니다.
-   **브레드크럼 내비게이션 통합**: 내일 ISAAC Painting 사이트에 브레드크럼 플러그인(예: Breadcrumb NavXT)을 설치하고 구성할 계획입니다.
-   **구글 리뷰 통합**: 내일 구글 리뷰 통합을 더 진행하여, 실제 리뷰 표시를 위한 대체 표시 방법이나 비즈니스 계정 연결 방법을 이해하려고 시도할 것입니다.
-   **CMS/웹 빌더 발표 준비**: 발표가 다음 주로 연기되었지만, 자료를 미리 준비된 상태로 유지할 것입니다.
