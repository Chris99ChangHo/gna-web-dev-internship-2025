# 📅 Day 02 (2025-07-01, Tue)

## 🎓 What I Did Today

**📌 Participated in the morning development meeting, sharing DevNewsHub mini-project (WordPress and app) progress and receiving directives.**   
**📌 Significantly enhanced the DevNewsHub news app by implementing core app screens (Home, TTS, Article Detail) and integrating WordPress taxonomies/custom fields via REST API for richer content.**   
**📌 Completed the development of the "Play Excerpt" audio feature, allowing users to listen to news excerpts from the list view.**   
**📌 Implemented a persistent "Like" functionality using AsyncStorage, designed for future personalized news recommendations.**    
**📌 Successfully resolved routing issues within the app, enabling seamless navigation between different screens.**   
**📌 Client product data entry task was put on hold due to pending detailed information.**

### Detailed Activities

**1. Morning Development Meeting Summary:** Shared today's progress and discussed future plans based on feedback.

-   **DevNewsHub Mini-Project (WordPress Website) Status:**
    
    -   Shared updates on the WordPress website development, specifically noting that while Elementor widgets are useful, I've realized that directly implementing with code provides more granular control.
        
    -   Reported on the ongoing process of replacing existing Elementor "posts" widgets with custom code to continuously improve the overall UI.
        
-   **DevNewsHub Mini-Project (App Development) Status:**
    
    -   Communicated that the app development is progressing towards providing an audio news service, similar to an audiobook, utilizing Text-to-Speech (TTS) functionality.
        
    -   Confirmed that environment setup and module installation have been completed, and the ability to actually read news articles aloud has been verified.
        
-   **Feedback Received:** "Continue with the development."
    
-   **Today's New Directive:** It was decided that today, I would assist with a product data entry task for another client's website.
    

**2. DevNewsHub App Core Feature Implementation & Refinements:** Today's app development focused on building out essential app screens and integrating richer content, leading to subsequent UI/UX improvements and feature enhancements.

-   **2.1. Building Core App Structure and Content Integration:**
    
    -   Initially, the app was a simple list of 10 articles with only a TTS button. To transform it into a truly functional application, efforts focused on implementing core app screens such as a **Home screen**, a **TTS playback screen**, and **Article Detail screens**.
        
    -   Successfully integrated **WordPress taxonomies and custom field slugs via the REST API**. This allows the app to fetch more detailed and specialized news content, giving it a professional appearance.
        
    -   The **audio news function (TTS)**, now properly integrated into the refined UI, is working as expected.
        
    -   **UI improvements** naturally followed as a necessary step after implementing the core screens and content integration, ensuring better usability and visual appeal.
        
-   **2.2. Feature Implementation and Error Resolution:**
    
    -   **Enhanced Audio Playback with "Play Excerpt" Feature:** Initially, the app could play the full article. To offer greater flexibility, a specific **"Play Excerpt" button** was added to each news item in the list view. This allows users to quickly listen to just the title or a brief summary. For full articles accessed on the detail page, comprehensive playback controls (play, pause, stop) are now implemented.
        
    -   **"Like" Functionality Implemented for Personalization:** A "Like" button has been integrated into news items, allowing users to add or remove news from a "liked" list. The heart icon dynamically changes color to reflect the like status. This feature leverages **AsyncStorage** for local persistence, with a future vision to connect it to actual user login information for personalized news recommendations and push notifications.
        
    -   **Routing Issues Resolved:** The previous failure in modularization and navigation was identified not as a simple module issue, but rather a conflict with **Expo Router's file-tree based routing structure**. This problem has now been successfully resolved, enabling seamless transitions between news list, detail, and other app screens.
        
    -   **Improved Initial Loading and Error Handling:** A **loading indicator** is now displayed while news data is being fetched. In cases of data load failure, a clear **error message** is shown along with a **retry button**. Additionally, appropriate **messages** are displayed when no news items are available, preventing blank screens.
        

**3. Client Task Status:** The planned product data entry task for another client's website could not be initiated today, as detailed information and instructions from the client are still pending. Therefore, I prioritized advancing my personal app project.

## 🧠 Key Concepts Learned

-   **Structured App Development Beyond Basic Lists:** Gained experience in evolving a simple content display into a fully functional app by implementing multiple core screens (Home, Detail, Playback) and managing complex content flows.
    
-   **Strategic WordPress REST API Integration:** Learned to effectively utilize WordPress REST API to fetch not just post content, but also **taxonomies and custom fields** (`news-published-date` slug) to deliver richer, more professional-looking news data.
    
-   **Granular Audio Playback Control:** Understood the importance of providing flexible audio control (excerpt vs. full article) based on user context (list view vs. detail view) to enhance user experience.
    
-   **Proactive Personalization Infrastructure:** Applied `AsyncStorage` to build a foundational "Like" feature, recognizing its role in enabling future personalized content recommendations tied to user accounts.
    
-   **Deep Dive into Expo Router's Navigation Paradigm:** Identified and resolved complex routing issues stemming from the interaction between `React Navigation` and `Expo Router`'s file-tree based system, understanding that direct `NavigationContainer` nesting is to be avoided with Expo Router.

## 💡 Practical Trial-and-Error and Tips

-   **Phased App Feature Implementation:** Instead of attempting to implement all features simultaneously, prioritizing core screen structures and essential content integration first provides a solid foundation. UI/UX improvements become a natural subsequent step.
    
-   **Anticipating HTML Content Variations:** Even if API data appears clean initially, always implement robust **HTML entity and tag stripping** (using libraries like `he` and final regex cleanups) to safeguard against unexpected formatting in future data fetches.
    
-   **Designing for Future Personalization with Local Storage:** When implementing features like "Like" that might eventually involve user accounts, consider using local storage (`AsyncStorage`) as a preliminary step. This allows for immediate feature deployment while laying the groundwork for more complex backend integrations.
    
-   **Debugging Expo Router vs. React Navigation Conflicts:** When facing navigation errors with Expo Router and React Navigation, remember that Expo Router implicitly handles the top-level navigation. Avoid nesting `NavigationContainer` directly. Instead, focus on correctly defining routes in `app/` directory and using `router.push()` or `router.navigate()` with correct paths. Mismatched screen names or incorrect file paths are common culprits.
    
-   **Comprehensive Error and Loading State Handling:** Don't just handle successful data fetches. Implement distinct visual cues for `loading` states (e.g., activity indicator) and explicit `error` states (e.g., error message with a retry button) to significantly improve app robustness and user feedback.

## 🔜 Next Steps

-   **Assist with Client's Product Data Entry:** Proceed with this task once detailed information and instructions are received from the client.
    
-   **Continue DevNewsHub Mini-Project Development:** Based on the "continue" feedback, resume further development of both the WordPress website (e.g., implementing custom field sorting, integrating categories for "explore" functionality) and the React Native/Expo app (e.g., implementing advanced features, refining existing ones based on upcoming user feedback).
    
-   **Research and Prepare PPT on AI Security Threats:** Begin in-depth research for the presentation titled "The Evolution of Hacking, Scams, and Spamming Using AI — and Its Impact on Server Security." The objective is to understand AI-driven security threats and countermeasures from a CPanel/WHM server administrator's perspective. The presentation is scheduled for **Thursday, July 10, 2025**.
 
----------

# 📅 2일차 (2025-07-01, 화)

## 🎓 오늘 한 일

**📌 오전 개발 미팅에 참여하여 DevNewsHub 미니 프로젝트(워드프레스 및 앱) 진행 상황을 공유하고 지시사항을 받았습니다.**   
**📌 DevNewsHub 뉴스 앱의 핵심 화면(홈, TTS, 기사 상세) 구현 및 워드프레스 택소노미/커스텀 필드 REST API 연동을 통해 앱을 크게 개선했습니다.**   
**📌 리스트 뷰에서 발췌문 음성 재생 기능을 완성하여 사용자가 간편하게 뉴스를 들을 수 있게 했습니다.**   **📌 AsyncStorage를 활용한 영구적인 "좋아요" 기능을 구현했으며, 이는 향후 개인화된 뉴스 추천을 위한 기반을 마련합니다.**   
**📌 앱 내 라우팅 문제를 성공적으로 해결하여 화면 간 끊김 없는 전환이 가능해졌습니다.**   
**📌 클라이언트 상품 데이터 입력 업무는 상세 정보 미확보로 보류되었습니다.**  

### 상세 활동

**1. 오전 개발 미팅 요약:** 오늘 진행 상황을 공유하고 피드백을 바탕으로 향후 계획을 논의했습니다.

-   **DevNewsHub 미니 프로젝트 (WordPress 웹사이트) 현황:**
    
    -   워드프레스 웹사이트 개발 상황을 공유했으며, Elementor 위젯이 유용하지만 더 세밀한 컨트롤을 위해 코드로 직접 구현하는 것이 좋다는 점을 깨달았음을 강조했습니다.
        
    -   기존에 배치한 posts 위젯들을 코드 기반으로 대체하며 전체 UI를 계속 개선하고 있다고 보고했습니다.
        
-   **DevNewsHub 미니 프로젝트 (앱 개발) 현황:**
    
    -   앱 개발 측면에서 TTS(Text-to-Speech) 기능을 활용해 오디오북처럼 오디오 뉴스 서비스를 제공하는 방향으로 진행 중임을 전달했습니다.
        
    -   환경설정과 모듈 설치를 마치고, 실제로 뉴스 기사를 읽어주는 것까지 확인했다고 보고했습니다.
        
-   **받은 피드백:** "계속 진행하라"는 지시를 받았습니다.
    
-   **오늘의 새로운 지시:** 오늘은 다른 클라이언트 사이트의 상품 데이터 입력 업무를 돕기로 결정되었습니다.
    

**2. DevNewsHub 앱 핵심 기능 구현 및 개선:** 오늘의 앱 개발은 필수 앱 화면 구축과 풍부한 콘텐츠 통합에 중점을 두었으며, 이는 UI/UX 개선 및 기능 강화로 이어졌습니다.

-   **2.1. 핵심 앱 구조 구축 및 콘텐츠 통합:**
    
    -   초기에는 단순히 10개의 기사에 TTS 버튼만 달려있는 앱 수준이었으나, 진정한 앱처럼 구동하기 위해 **홈 화면, TTS 재생 화면, 기사 상세 화면** 등 핵심 앱 화면 구현에 집중했습니다.
        
    -   **워드프레스 택소노미 및 커스텀 필드 슬러그를 REST API로 성공적으로 가져와 연동했습니다.** 이를 통해 앱이 더 상세하고 전문적인 뉴스 콘텐츠를 제공할 수 있게 되었으며, 시각적으로도 전문적인 뉴스 앱처럼 보이게 되었습니다.
        
    -   정제된 UI에 통합된 **오디오 뉴스 기능(TTS)**은 현재 제대로 작동하고 있습니다.
        
    -   **UI 개선**은 핵심 화면과 콘텐츠 통합을 구현한 후 자연스럽게 수반되는 당연한 순서로 진행되어, 사용성 및 시각적 매력을 향상시켰습니다.
        
-   **2.2. 기능 구현 및 오류 해결:**
    
    -   **발췌문 음성 재생 기능 추가:** 원래는 기사 전체를 바로 읽어주는 기능만 있었다면, 이제 각 뉴스 아이템에 **"Play Excerpt" 버튼**이 추가되어 클릭 시 해당 뉴스의 발췌문을 영어로 음성 재생합니다. 이는 사용자가 리스트에서 제목이나 발췌문만 듣고 기사를 선택할 수 있도록 자유도를 높였습니다. 실제 뉴스 상세 페이지에서는 전체 재생, 멈춤, 정지 버튼을 만들어 더 자유로운 컨트롤이 가능하도록 구현했습니다.
        
    -   **"좋아요" 기능 구현:** 뉴스 아이템에 "Like" 버튼이 추가되었으며, 클릭 시 해당 뉴스를 "좋아요" 목록에 추가하거나 제거할 수 있습니다. "좋아요" 상태에 따라 하트 아이콘의 색상이 변경됩니다. 이 기능은 **AsyncStorage**를 사용하여 기기 내부에 "좋아요" 상태를 저장하여 앱을 종료해도 유지되도록 구현되었으며, 이는 **향후 실제 로그인한 사용자의 정보를 연결하여 개인화된 추천 뉴스를 푸시 알림으로 제공**할 수 있는 기반을 마련합니다.
        
    -   **라우팅 문제 해결:** 어제 모듈화에 실패했던 이유가 단순히 내비게이터가 작동하지 않는 것이 아니라 **Expo Router가 이미 파일 트리 구조를 사용하고 있었기 때문**이라는 것을 파악하고, 오늘 이 문제를 해결하여 뉴스 목록에서 아이템 클릭 시 상세 페이지로 이동하는 등 정상적인 화면 전환이 가능해졌습니다.
        
    -   **초기 로딩 및 오류 처리:** 뉴스 데이터를 불러오는 동안 **로딩 인디케이터가 표시**되고, 데이터 로드 실패 시 **오류 메시지와 함께 재시도 버튼이 제공**됩니다. 뉴스가 없는 경우에도 적절한 메시지가 표시되어 사용자 경험을 향상시켰습니다.
        

**3. 클라이언트 업무 현황:** 오늘 계획되었던 다른 클라이언트 사이트의 상품 데이터 입력 업무는 클라이언트로부터 상세 정보 및 지시를 받지 못하여 진행하지 못했습니다. 따라서 개인 프로젝트인 앱 개발에 좀 더 집중했습니다.

## 🧠 배운 핵심 개념

-   **기본 목록을 넘어서는 앱 구조 개발:** 단순 콘텐츠 표시를 넘어 여러 핵심 화면(홈, 상세, 재생)을 구현하고 복잡한 콘텐츠 흐름을 관리하며 완전히 기능하는 앱으로 발전시키는 경험을 얻었습니다.
    
-   **워드프레스 REST API의 전략적 활용:** WordPress REST API를 사용하여 단순 게시물 콘텐츠뿐만 아니라 **택소노미와 커스텀 필드**(`news-published-date` 슬러그)까지 효과적으로 가져와 더 풍부하고 전문적인 뉴스 데이터를 제공하는 방법을 배웠습니다.
    
-   **세분화된 오디오 재생 제어:** 사용자 컨텍스트(리스트 뷰 vs. 상세 뷰)에 따라 유연한 오디오 제어(발췌문 vs. 전체 기사)를 제공하는 것이 사용자 경험을 향상시키는 데 중요함을 이해했습니다.
    
-   **AsyncStorage를 통한 개인화 인프라 구축:** `AsyncStorage`를 활용하여 "좋아요" 기능의 기반을 구축하고, 이를 통해 향후 사용자 계정과 연동하여 개인화된 콘텐츠 추천을 가능하게 하는 역할을 인식했습니다.
    
-   **Expo Router 내비게이션 패러다임에 대한 심층 이해:** `React Navigation`과 `Expo Router`의 파일 트리 기반 시스템 간의 상호작용으로 인해 발생하는 복잡한 라우팅 문제를 파악하고 해결했으며, `NavigationContainer` 중첩을 피해야 함을 명확히 이해했습니다.

## 💡 실전 시행착오 및 팁

-   **앱 기능의 단계별 구현:** 모든 기능을 한 번에 구현하려고 하기보다는, 핵심 화면 구조와 필수 콘텐츠 통합을 우선적으로 진행하여 견고한 기반을 마련하는 것이 중요합니다. UI/UX 개선은 자연스럽게 다음 단계로 이어집니다.
    
-   **HTML 콘텐츠 변동성 예측 및 대비:** API 데이터가 처음에는 깔끔해 보이더라도, 향후 데이터 가져오기에서 발생할 수 있는 예상치 못한 서식에 대비하여 **HTML 엔티티 및 태그를 제거하는 강력한 처리 로직**(예: `he` 라이브러리와 최종 정규식 정리)을 항상 구현해야 합니다.
    
-   **로컬 스토리지를 활용한 미래 개인화 기능 설계:** "좋아요"와 같이 궁극적으로 사용자 계정과 연동될 수 있는 기능을 구현할 때, 로컬 스토리지(`AsyncStorage`)를 초기 단계로 활용하는 것을 고려하세요. 이는 즉각적인 기능 배포를 가능하게 하면서도 더 복잡한 백엔드 통합을 위한 기반을 마련해 줍니다.
    
-   **Expo Router와 React Navigation 충돌 디버깅:** Expo Router와 React Navigation을 함께 사용할 때 내비게이션 오류에 직면한다면, Expo Router가 최상위 내비게이션을 암묵적으로 처리한다는 점을 기억하세요. `NavigationContainer`를 직접 중첩하지 마세요. 대신 `app/` 디렉토리에 경로를 올바르게 정의하고 `router.push()` 또는 `router.navigate()`를 올바른 경로와 함께 사용하는 데 집중해야 합니다. 화면 이름 불일치 또는 잘못된 파일 경로는 흔한 원인입니다.
    
-   **포괄적인 로딩 상태 및 오류 처리 구현:** 단순히 데이터 가져오기 성공만 처리하지 마세요. 데이터 가져오는 동안에는 `isLoading` 상태와 함께 **로딩 인디케이터**를 표시하고, 가져오기 실패 시에는 **사용자에게 친숙한 오류 메시지와 명확한 "다시 시도" 버튼**을 제공하는 것이 앱의 안정성과 사용자 피드백을 크게 향상시킵니다.

## 🔜 이후 학습 방향

-   **클라이언트 상품 데이터 입력 업무 지원:** 클라이언트로부터 상세 정보 및 지시를 받는 즉시 이 업무를 진행할 것입니다.
    
-   **DevNewsHub 미니 프로젝트 개발 지속:** "계속 진행하라"는 피드백을 바탕으로 워드프레스 웹사이트(예: 커스텀 필드 정렬 구현, '탐색' 기능 위한 카테고리 연동) 및 React Native/Expo 앱(예: 고급 기능 구현, 기존 기능 개선) 개발을 계속 이어나갈 것입니다.
    
-   **AI 보안 위협 관련 PPT 리서치 및 준비:** "AI를 활용한 해킹, 스캠, 스팸의 진화 — 그리고 서버 보안에 미치는 영향"이라는 주제로 발표 자료 심층 리서치를 시작하고 준비할 것입니다. CPanel/WHM 서버 관리자 관점에서 AI 기반 보안 위협과 잠재적 대응책을 이해하는 것이 목표이며, 발표는 **2025년 7월 10일 목요일**에 예정되어 있습니다.
