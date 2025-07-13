# 📝 Week 09 Reflection (2025.07.07 ~ 07.11)

## ✅ Key Tasks This Week

**📌 Successfully completed the comprehensive Shopify product migration from Wix, including robust image uploads to CDN and critical HTML cleaning to remove platform-specific elements.**   
**📌 Initiated and significantly advanced the Report Automation project, achieving Google Analytics 4 (GA4) API connectivity, resolving data fetching issues, and integrating SERanking API.**   
**📌 Prepared and delivered two technical presentations, adapting to schedule changes and actively incorporating feedback on presentation delivery.**  

----------

## 🧠 What I Learned

-   **Robust Cross-Platform Data Migration:** I gained a deep understanding of the complexities involved in migrating data between platforms (Wix to Shopify). This included mastering **HTML sanitization** to remove platform-dependent elements, implementing **Shopify GraphQL Staged Uploads** with **exponential backoff retry logic** for reliable image hosting on CDN, and effectively managing API rate limits.
    
-   **Comprehensive API Integration & Troubleshooting:** I navigated various Google APIs (GA4 Data API, Google Ads API) and SERanking API. This involved overcoming **authentication challenges**, correcting **metric mapping**, understanding **multi-client access nuances** (MCC vs. direct GA4 properties), and recognizing the critical importance of **precise API endpoint integrity** and **systematic debugging** over hurried approaches.
    
-   **Effective Project & Self-Management:** I learned to prioritize tasks strategically, especially when balancing urgent deadlines (presentations) with ongoing development projects (migration, reports). This involved proactive task initiation, maintaining iterative development cycles with continuous feedback loops from seniors, and adapting swiftly to changing project scopes.
    
-   **Enhanced Presentation & Communication Skills:** I identified key elements of effective technical communication, including the critical role of pacing, audience engagement, and conversational delivery during presentations. I also learned the value of structured problem-solving communication with senior team members.
    

----------

## 🔧 Technical Problem-Solving Experience

-   **Google Analytics 4 API Connectivity & Data Display Issues:**
    
    -   **Problem:** Encountered multiple issues, including `client_secret.json` type errors, `403 access_denied` during OAuth, incorrect GA4 metric names (`views` instead of `screenPageViews`), and API access restrictions on GA4 demo accounts, leading to a dashboard displaying zeroes.
        
    -   **Resolution:** Explicitly passed authentication via `InstalledAppFlow`, added my Google account as a 'test user' in the OAuth consent screen, corrected metric names to GA4 standards, and bypassed demo account restrictions by setting up and using a personal GA4 property for development and testing. Also, recognized the need to fully restart the server and adjust date ranges for new `GA4_PROPERTY_ID` to apply.
        
-   **Wix Element Persistence in Shopify Migration & CDN Image Acquisition:**
    
    -   **Problem:** Directly migrating `outerHTML` from Wix included platform-specific `wix-*` tags and dependencies, posing a risk of broken content if Wix service ceased. Additionally, Shopify's CDN URL for newly uploaded images wasn't immediately available after `fileCreate` API calls.
        
    -   **Resolution:** Devised and implemented a robust HTML cleaning function to **rigorously filter out all Wix-related elements**, preserving only essential HTML and styles. For image hosting, I implemented a **two-step GraphQL Staged Uploads process** and crucially added an **exponential backoff retry mechanism (up to 5 attempts)** to reliably acquire the permanent Shopify CDN URLs for images, ensuring long-term stability.
        
-   **SERanking API Endpoint Inaccuracies:**
    
    -   **Problem:** Initial integration attempts with the SERanking API failed to fetch data due to incorrect API endpoints within the code.
        
    -   **Resolution:** After a methodical review post-presentation, identified and corrected all faulty endpoints, enabling successful fetching of SER client information and GA4 data. This reinforced the importance of careful, manual code review.
        

----------

## 💡 Reflections

-   **Validate Assumptions Proactively:** A major insight was realizing that assumptions in system integration (e.g., "images will automatically re-host" or "external elements will gracefully degrade") can lead to critical and time-consuming issues. It's crucial to proactively identify and explicitly handle all potential risks during migration or API integration.
    
-   **Prioritize Methodical Debugging:** When facing complex technical problems, I found that a systematic, step-by-step review of fundamental code elements (like API endpoints) is often far more efficient and reliable than rushing or immediately resorting to advanced tools or external help, especially under time pressure.
    
-   **Mastering Technical Communication:** Beyond just technical competence, this week highlighted the immense value of effective communication. This includes optimizing presentation delivery (pacing, visual synchronization, audience engagement) and maintaining structured, clear communication loops with senior team members for project alignment and problem-solving.
    
-   **Strategic Task Management:** I experienced firsthand the importance of being able to flexibly prioritize and switch between urgent tasks (like presentation preparations) and ongoing development, while also breaking down larger projects into manageable segments for better self-management and reporting.
    

----------

## 🌱 Points of Improvement & Next Week's Goals

-   **Improve Presentation Delivery Pacing:** Consciously practice speaking at a slower, more deliberate pace during presentations, ensuring that visual aids and verbal explanations are perfectly synchronized.
    
-   **Enhance Proactive Code Review:** Adopt a more methodical and manual review process for fundamental code elements (e.g., API endpoints, HTML cleaning logic) to prevent simple yet critical errors, even when under tight deadlines.
    
-   **Strengthen Assumption Validation in Migrations:** For all future data migrations, establish a more rigorous pre-migration checklist or validation process to explicitly account for and handle platform-specific elements, avoiding unverified assumptions and ensuring data integrity.
    
-   **Advance Report Project Development:** Fully integrate and develop the client dashboard, leveraging the resolved SER API and GA4 data fetching. Prioritize the customer ID dropdown functionality and comprehensive GA4 data visualization.
    
-   **Practice Conversational Presentation Delivery:** Actively practice a more conversational and engaging delivery style for all future technical presentations, directly applying the feedback received this week to improve audience interaction and comprehension.
    
-   **Initiate Marketing Automation Prototype Planning:** Begin concrete planning and initial development for the automated marketing material creation prototype, focusing on translating strategic ideas into actionable development steps.
    
-   **Refine Google Ads MCC Centralization Proposal:** Further develop and concretize the proposal for Google Ads MCC centralization, outlining the benefits and a clear strategy for unified client advertising account management.
    

----------

# 📝 09주차 회고 (2025.07.07 ~ 07.11)

## ✅ 이번 주 주요 작업

**📌 Wix에서 Shopify로의 종합적인 상품 마이그레이션을 성공적으로 완료했으며, CDN으로의 이미지 업로드 및 플랫폼 종속적 요소를 제거하는 중요한 HTML 클리닝 작업을 포함했습니다.**    
**📌 리포트 자동화 프로젝트를 착수하고 상당한 진전을 이루어, Google Analytics 4 (GA4) API 연결을 확립하고 데이터 가져오기 문제를 해결했으며, SERanking API를 통합했습니다.**    
**📌 두 건의 기술 발표 자료를 준비하고 발표했으며, 일정 변경에 유연하게 대응하고 발표 전달력에 대한 피드백을 적극적으로 반영했습니다.**   

----------

## 🧠 배운 핵심 개념

-   **견고한 크로스 플랫폼 데이터 마이그레이션:** Wix에서 Shopify로 데이터를 마이그레이션하는 복잡성에 대해 깊이 이해했습니다. 특히, 플랫폼 종속적인 요소를 제거하기 위한 **HTML 정제(Sanitization)**, **지수 백오프(Exponential Backoff) 재시도 로직**을 활용한 Shopify CDN으로의 **GraphQL Staged Uploads**를 통한 안정적인 이미지 호스팅, 그리고 API 요청 제한 관리의 중요성을 배웠습니다.
    
-   **포괄적인 API 통합 및 문제 해결:** Google API (GA4 Data API, Google Ads API) 및 SERanking API를 다루면서 광범위한 경험을 얻었습니다. **인증 문제** 극복, **지표 이름 매핑** 수정, **다중 클라이언트 접근 방식**의 미묘한 차이(MCC vs. 직접 GA4 속성) 이해, 그리고 **정확한 API 엔드포인트의 무결성**과 체계적인 디버깅의 중요성을 파악했습니다.
    
-   **효과적인 프로젝트 및 자기 관리:** 긴급한 마감 기한(발표)과 지속적인 개발 프로젝트(마이그레이션, 보고서) 사이에서 작업을 전략적으로 우선순위화하는 것의 중요성을 깨달았습니다. 이는 선제적인 업무 착수, 시니어로부터의 지속적인 피드백을 통한 반복적인 개발 주기 유지, 그리고 변경되는 프로젝트 범위에 대한 신속한 적응을 포함합니다.
    
-   **향상된 발표 및 커뮤니케이션 기술:** 기술적 역량 외에 효과적인 커뮤니케이션의 핵심 요소를 파악했습니다. 특히 발표 시 속도 조절, 청중과의 눈맞춤, 대화형 전달 방식의 중요성, 그리고 시니어 팀원과의 구조화된 문제 해결 커뮤니케이션의 가치를 배웠습니다.
    

----------

## 🔧 기술적 문제 해결 경험

-   **Google Analytics 4 API 연결 및 데이터 표시 문제:**
    
    -   **문제:** `client_secret.json` 유형 오류, OAuth 중 `403 access_denied`, 잘못된 GA4 지표 이름(`views` 대신 `screenPageViews`), GA4 데모 계정의 API 접근 제한 등 여러 문제에 직면하여 대시보드에 0이 표시되었습니다.
        
    -   **해결:** `InstalledAppFlow`를 통해 인증 정보를 명시적으로 전달했고, OAuth 동의 화면에서 저를 '테스트 사용자'로 추가하여 `403 access_denied` 오류를 해결했습니다. 지표 이름을 GA4 표준에 맞게 수정했으며, 데모 계정 제한을 우회하기 위해 개인 GA4 속성을 설정하고 사용했습니다. 또한, `GA4_PROPERTY_ID` 적용을 위해 서버를 완전히 다시 시작하고 날짜 범위를 조정해야 함을 인지했습니다.
        
-   **Shopify 마이그레이션 시 Wix 요소 잔존 및 CDN 이미지 획득 문제:**
    
    -   **문제:** Wix에서 `outerHTML`을 직접 마이그레이션할 때 플랫폼 고유의 `wix-*` 태그와 종속성이 포함되어, Wix 서비스 종료 시 내용이 깨질 위험이 있었습니다. 또한, `fileCreate` API 호출 후 Shopify의 CDN URL이 즉시 반환되지 않는 문제가 있었습니다.
        
    -   **해결:** 모든 Wix 관련 태그를 철저히 필터링하고 필수 HTML과 스타일만 유지하는 견고한 HTML 클리닝 함수를 개발 및 적용했습니다. 이미지 호스팅의 경우, **두 단계의 GraphQL Staged Uploads 프로세스**를 구현했으며, 특히 **지수 백오프 재시도 메커니즘(최대 5회 시도)**을 추가하여 새로 업로드된 이미지의 영구적인 Shopify CDN URL을 안정적으로 획득하도록 보장했습니다.
        
-   **SERanking API 엔드포인트 부정확성:**
    
    -   **문제:** SERanking API 초기 연동 시 코드 내의 엔드포인트가 올바르지 않아 데이터를 가져오지 못했습니다.
        
    -   **해결:** 발표 후 체계적인 검토를 통해 모든 잘못된 엔드포인트를 식별하고 수정하여, SER 고객사 정보 및 GA4 데이터를 성공적으로 가져올 수 있었습니다. 이는 신중한 수동 코드 검토의 중요성을 다시 한번 상기시켜주었습니다.
        

----------

## 💡 느낀 점

-   **시스템 통합 시 '가정'의 위험성:** 마이그레이션이나 API 통합 시 "이미지가 자동으로 호스팅될 것" 또는 "외부 플랫폼 요소가 문제없이 사라질 것"과 같은 안일한 가정이 치명적이고 시간 소모적인 문제로 이어질 수 있음을 깨달았습니다. 잠재적 위험을 선제적으로 식별하고 명시적으로 처리하는 것이 필수적입니다.
    
-   **성급함보다 체계적인 디버깅의 가치:** 복잡한 기술적 문제에 직면했을 때, 서두르거나 고급 도구 또는 외부 도움에 즉시 의존하기보다, API 엔드포인트와 같은 기본적인 코드 요소들을 체계적이고 단계적으로 검토하는 것이 훨씬 효율적이고 신뢰할 수 있음을 경험했습니다.
    
-   **프로젝트 우선순위 설정 및 소통의 균형:** 긴급한 발표와 같은 우선순위가 높은 작업과 진행 중인 개발 작업을 효과적으로 관리하는 법을 배웠습니다. 리더와의 명확한 소통, 유연한 작업 전환, 그리고 세분화된 진행 상황 보고가 중요하다는 것을 알게 되었습니다.
    
-   **기술 역량 그 이상의 커뮤니케이션 능력:** 기술적 능력도 중요하지만, 이번 주를 통해 효과적인 커뮤니케이션의 중요성을 절감했습니다. 특히 발표 시의 속도 조절과 청중 참여 유도, 그리고 팀원과의 구조화된 피드백 루프 유지가 매우 중요하다고 느꼈습니다.
    

----------

## 🌱 아쉬운 점 및 다음 주 목표

-   **발표 전달 속도 조절:** 향후 발표 시 의식적으로 더 느리고 신중한 속도로 말하는 연습을 하여, 시각 자료와 설명이 완벽하게 동기화되도록 개선할 것입니다.
    
-   **선제적 코드 검토 강화:** 촉박한 마감일에도 불구하고, API 엔드포인트나 HTML 클리닝 로직과 같은 핵심 코드 요소들에 대해 성급하게 처리하기보다, 더 체계적이고 수동적인 검토 프로세스를 채택하여 단순하지만 치명적인 오류를 사전에 방지할 것입니다.
    
-   **마이그레이션 시 가정 검증 강화:** 향후 모든 데이터 마이그레이션에서, 플랫폼 고유 요소를 명시적으로 고려하고 처리하는 더욱 엄격한 사전 체크리스트 또는 유효성 검사 프로세스를 구축하여, 검증되지 않은 가정을 피하고 데이터 무결성을 보장할 것입니다.
    
-   **리포트 프로젝트 개발 진전:** 해결된 SER API 및 GA4 데이터 연동을 활용하여 대시보드를 완전히 통합하고 개발할 것입니다. 특히 고객사 ID 드롭다운 기능과 포괄적인 GA4 데이터 시각화에 집중할 것입니다.
    
-   **대화형 발표 전달 연습:** 이번 주 받은 피드백을 직접 적용하여, 향후 모든 기술 발표에서 대화형 전달 방식과 속도 조절을 적극적으로 연습하여 청중 참여도와 이해도를 높일 것입니다.
    
-   **마케팅 자동화 프로토타입 계획 수립:** 자동화된 마케팅 자료 제작 프로토타입에 대한 구체적인 계획 수립 및 초기 개발을 시작하여, 전략적 아이디어를 실행 가능한 개발 단계로 전환할 것입니다.
    
-   **Google Ads MCC 중앙화 제안 구체화:** 향후 효율적인 클라이언트 광고 계정 관리를 위해 Google Ads MCC 중앙화 방안에 대한 제안 내용을 더욱 구체화하고 다듬을 것입니다.
