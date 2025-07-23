# 📅 Day 05 (2025-07-18, Fri)

## 🎓 What I Did Today

**📌 Participated in today's development meeting, reporting project progress nearing completion, discussing the new AI summary feature, and outlining future deployment, integration, and security challenges.**   
**📌 Successfully implemented a preliminary API route (`@app.route('/api/ai_summary')`) for the AI-powered analytical summary feature after obtaining the necessary API key.**   
**📌 Initiated critical research into deploying the local server environment to cPanel, integrating the project with the WordPress development server, and establishing robust security measures for sensitive data.**   
**📌 Began detailed research on Shopify and Shopify Plus strengths, weaknesses, and starter plan specifics, in preparation for an upcoming presentation.**   
**📌 Addressed PDF design feedback and began debugging issues related to abnormal graph output in generated reports.**  

### Detailed Activities

**1. Development Meeting Summary:**

-   **Project Progress:** Reported that the project is nearing completion.
    
-   **AI Summary Feature Request:** Following yesterday's manager instruction, completed the request for an API key for the AI summary feature this morning from the senior developer.
    
-   **Report Implementation Feedback:** Shared the implemented Report features before leaving yesterday and received no significant feedback, indicating good initial reception.
    
-   **Current Environment:** Confirmed the current setup operates as a Python-based local server environment.
    
-   **Future Challenges & Considerations:**
    
    -   **Server Deployment:** Began discussing strategies to move from a local environment to a production deployment, including server selection, deployment methods, and monitoring structure.
        
    -   **Backend/DB/WP Integration:** Identified the need to efficiently connect the project (especially media assets residing in the WP backend) with the WordPress backend, discussing REST API integration, authentication methods, etc.
        
    -   **Security:** Acknowledged the need for phased security reviews considering service launch, including authentication, access control, API key security, and the WordPress user role structure.
        
-   **Feedback Received:** Received feedback to prioritize and implement technical decisions sequentially for each stage (Server → Backend Integration → Security).
    

**2. Project Environment & Security Research:**

-   **cPanel Deployment Research:** Began researching how to migrate the current local server environment to a cPanel hosting setup.
    
-   **WordPress Server Integration:** Initiated research on methods to integrate the developed backend and frontend project into the existing WordPress development server to enable practical usage.
    
-   **Security Protocol Research:** Started exploring solutions for critical security concerns, specifically how to protect sensitive data to prevent unauthorized access.
    

**3. Shopify/Shopify Plus Research Task:**

-   **Topic:** Commenced detailed research on the strengths and weaknesses (including critical limitations) of Shopify and Shopify Plus, specifically covering the Shopify Starter Plan ($7/month).
    
-   **Collaboration:** This research is a collaborative effort with Chris and Heejoo, due by next Tuesday morning.
    
-   **Presentation Preparation:** Emphasized the need for detailed investigation as one person will present after lunch, followed by a Q&A session.
    
-   **Reminder:** Re-emphasized the research PPT presentation task scheduled for July 22nd.
    

**4. PDF Design Feedback & Bug:**

-   **Design Modifications:** Applied corrections based on recent PDF design feedback.
    
-   **Abnormal Output:** Encountered issues where graph elements were outputting abnormally (graphs not visible or ranking change values displaying incorrectly).
    
-   **Debugging Plan:** This phenomenon occurred during repetitive design/logic modification, and you plan for additional debugging and review of recent changes.
    

**5. AI-Powered Summary Feature Implementation (Initial):**

-   **GPT API Key Acquisition:** Successfully obtained the necessary API key from the senior developer this morning.
    
-   **Preliminary API Route Implementation:** A preliminary API route, `@app.route('/api/ai_summary', methods=['POST'])`, was implemented to facilitate the initial integration of the GPT API, allowing for basic POST requests for AI summaries.
    
-   **Goal:** The overarching goal remains to develop a feature that collects all key data from the dashboard, defines a "role (persona)" and "analysis perspective," and then provides automated analysis results and concise brief reports.

## 🧠 Key Concepts Learned

-   **Deployment Strategy Fundamentals:** Began to grasp the core considerations for moving a local development environment to a production server, including server types, deployment pipelines, and post-deployment monitoring.
    
-   **CMS Integration Complexities:** Understood the inherent challenges in integrating custom-built applications with existing Content Management Systems (CMS) like WordPress, especially concerning data synchronization, API communication, and authentication.
    
-   **Multi-layered Security Planning:** Recognized that comprehensive security involves addressing various layers, from API key management and access controls to user role structures within the broader system.
    
-   **Structured Research & Collaboration:** Experienced the process of structured research, collaboration, and preparing for a technical presentation, highlighting the need for thorough investigation and organized findings.
    
-   **Rapid API Integration & Prototyping:** Demonstrated the ability to quickly set up a basic API endpoint for a new feature (AI summary) after securing the necessary credentials, enabling faster prototyping and initial testing.

## 💡 Practical Trial-and-Error and Tips

-   **Phased Technical Decision-Making:** When facing multiple complex challenges (e.g., server, integration, security), feedback emphasized a **prioritized, phased approach** to decision-making and implementation, which is crucial for managing complexity.
    
-   **Proactive Deployment Research:** Realized the importance of researching deployment environments (like cPanel) early in the project lifecycle to avoid last-minute hurdles.
    
-   **Debugging Visual Anomalies:** When visual elements (like graphs in PDFs) output abnormally after design/logic changes, a systematic **review of recent code modifications** and a focus on **rendering engine interactions** (e.g., how PDF generation libraries interpret CSS/SVG) is critical.
    
-   **Anticipating Integration Challenges:** Integrating with an established CMS like WordPress requires careful planning for API endpoints, authentication, and data consistency to prevent unforeseen issues.
    
-   **Immediate API Key Utilization:** Once an API key is obtained, immediately setting up a basic route/function for it (even a simple POST request as you did) allows for quick validation and unblocks further development.

## 🔜 Next Steps

-   **Continue Deployment & Security Research:** Deepen research into cPanel deployment, WordPress integration methods (REST API, authentication), and comprehensive security protocols.
    
-   **Debug PDF Graph Issues:** Prioritize debugging and resolving the abnormal graph output in PDF reports.
    
-   **Prepare Shopify Presentation:** Collaborate on and finalize the research and presentation for Shopify/Shopify Plus for next Tuesday.
    
-   **Develop AI Summary Feature Logic:** Proceed with developing the full logic for the AI summary feature beyond the basic API route, including data collection, persona/analysis definition, and prompt engineering.
    
-   **Plan for 2nd Confirmation:** Prepare for the next review with stakeholders after key features (AI summary, design refinements) are implemented.

----------

# 📅 5일차 (2025-07-18, 금)

## 🎓 오늘 한 일

**📌 오늘 개발 미팅에 참여하여 프로젝트의 마무리 단계 진척도를 보고하고, 새로운 AI 요약 기능에 대해 논의했으며, 향후 배포, 통합 및 보안 과제에 대해 설명했습니다.**   
**📌 필요한 API 키를 확보한 후 AI 기반 분석 요약 기능의 예비 API 경로(`@app.route('/api/ai_summary')`)를 성공적으로 구현했습니다.**   
**📌 로컬 서버 환경을 cPanel로 배포하는 방안, 프로젝트를 워드프레스 개발 서버와 통합하여 실제 사용 가능하도록 하는 방법, 민감한 데이터에 대한 강력한 보안 대책 수립에 대한 핵심 리서치를 시작했습니다.**   
**📌 다가올 발표 준비를 위해 Shopify 및 Shopify Plus의 강점, 약점, Starter Plan의 세부 사항에 대한 심층 리서치를 시작했습니다.**   
**📌 PDF 디자인 피드백을 반영하고, 생성된 보고서에서 그래프 요소가 비정상적으로 출력되는 버그를 디버깅하기 시작했습니다.**  

### 상세 활동

**1. 개발 미팅 요약:**

-   **프로젝트 진척도:** 프로젝트가 거의 완료 단계에 이르렀음을 보고했습니다.
    
-   **AI 요약 기능 추가 요청:** 어제 매니저 지시에 따라 오늘 아침 개발 선임에게 AI 요약 기능의 API 키 발급 요청을 완료했습니다.
    
-   **리포트 구현물 피드백:** 어제 퇴근 전에 리포트 관련 구현물을 공유했으며, 큰 피드백이 없어서 초기 반응이 좋았음을 시사했습니다.
    
-   **현재 환경:** 현재 설정이 Python 기반의 로컬 서버 환경에서 동작하고 있음을 확인했습니다.
    
-   **향후 과제 및 고민:**
    
    -   **서버 배포:** 로컬 환경이 아닌 프로덕션 배포 환경으로 옮길 방안(서버 선택, 배포 방법, 모니터링 구조 등)에 대한 논의를 시작했습니다.
        
    -   **백엔드/DB/WP 연동:** 워드프레스 백엔드에 있는 미디어 자산 등을 포함하여 프로젝트를 워드프레스 백엔드와 어떻게 효율적으로 연결할 것인지(REST API 연동, 인증 방식 등) 논의의 필요성을 제기했습니다.
        
    -   **보안:** 서비스 오픈을 고려한 인증, 접근 권한, API 키 보안, 워드프레스 내 사용자 권한 구조 등 단계별 점검의 필요성을 인지했습니다.
        
-   **받은 피드백:** 각 단계별로 우선순위(서버 → 백엔드 연동 → 보안)에 따라 기술적 의사결정 및 구현이 필요하다는 피드백을 받았습니다.
    

**2. 프로젝트 환경 및 보안 리서치:**

-   **cPanel 배포 리서치:** 현재 로컬 서버 환경을 cPanel 호스팅 설정으로 마이그레이션하는 방법에 대한 리서치를 시작했습니다.
    
-   **워드프레스 서버 통합:** 개발된 백엔드 및 프론트엔드 프로젝트를 기존 워드프레스 개발 서버에 통합하여 실제 사용 가능하도록 하는 방법에 대한 리서치를 시작했습니다.
    
-   **보안 프로토콜 리서치:** 민감한 데이터를 무단 접근으로부터 보호하는 방법을 포함한 핵심 보안 문제에 대한 해결책을 모색하기 시작했습니다.
    

**3. Shopify/Shopify Plus 리서치 과제:**

-   **주제:** Shopify 및 Shopify Plus의 강점과 약점(치명적 한계 포함), 특히 Shopify Starter Plan(월 $7)의 세부 사항에 대한 심층 리서치를 시작했습니다.
    
-   **협업:** 이 리서치는 다음 주 화요일 오전까지 크리스, 희주와 함께 진행하는 협업 과제입니다.
    
-   **발표 준비:** 점심 식사 후 한 명이 대표로 발표하고 Q&A 세션이 있으므로, 상세 조사의 필요성을 강조했습니다.
    
-   **재강조:** 7월 22일로 예정된 리서치 PPT 발표 과제를 재강조했습니다.
    

**4. PDF 디자인 피드백 및 버그:**

-   **디자인 수정:** 최근 PDF 디자인 피드백에 따라 수정을 진행했습니다.
    
-   **비정상적인 출력:** 그래프 요소가 비정상적으로 출력되는 문제(그래프가 안 보이거나, 랭킹 Change 값이 이상하게 출력됨)가 발생했습니다.
    
-   **디버깅 계획:** 이 현상은 반복적인 디자인/로직 수정 과정에서 발생했으며, 추가적인 디버깅과 최근 수정 내역 점검을 예정하고 있습니다.
    

**5. AI 기반 요약 기능 구현 (초기):**

-   **GPT API 키 획득:** 오늘 아침 선임 개발자로부터 필요한 API 키를 성공적으로 획득했습니다.
    
-   **예비 API 경로 구현:** GPT API의 초기 통합을 용이하게 하기 위해 예비 API 경로인 `@app.route('/api/ai_summary', methods=['POST'])`를 구현하여 AI 요약을 위한 기본적인 POST 요청이 가능하도록 했습니다.
    
-   **목표:** 대시보드의 모든 핵심 데이터를 수집하고, "역할(페르소나)"과 "분석 관점"을 정의한 다음, 자동화된 분석 결과와 간결한 브리프 리포트를 제공하는 것이 궁극적인 목표입니다.

## 🧠 배운 핵심 개념

-   **배포 전략의 기본:** 로컬 개발 환경을 프로덕션 서버로 옮기는 핵심 고려 사항(서버 유형, 배포 파이프라인, 배포 후 모니터링)에 대한 이해를 시작했습니다.
    
-   **CMS 통합의 복잡성:** 기존 콘텐츠 관리 시스템(CMS)인 워드프레스와 맞춤형으로 구축된 애플리케이션을 통합할 때 데이터 동기화, API 통신, 인증과 관련된 본질적인 문제들을 이해하게 되었습니다.
    
-   **다단계 보안 계획:** 포괄적인 보안이 API 키 관리 및 접근 제어부터 더 넓은 시스템 내의 사용자 역할 구조에 이르기까지 다양한 계층을 다루어야 함을 인식했습니다.
    
-   **구조화된 리서치 및 협업:** 구조화된 리서치, 협업, 그리고 기술 발표 준비 과정을 경험했으며, 철저한 조사와 정리된 결과의 필요성을 강조하게 되었습니다.
    
-   **빠른 API 통합 및 프로토타이핑:** 필요한 자격 증명을 확보한 후 새로운 기능(AI 요약)을 위한 기본적인 API 엔드포인트를 신속하게 설정하여, 더 빠른 프로토타이핑 및 초기 테스트를 가능하게 하는 능력을 보여주었습니다.

## 💡 실전 시행착오 및 팁

-   **단계별 기술 의사결정:** 여러 복잡한 과제(예: 서버, 통합, 보안)에 직면했을 때, 피드백을 통해 의사결정 및 구현에 **우선순위를 둔 단계별 접근 방식**이 복잡성 관리에 필수적임을 깨달았습니다.
    
-   **선제적 배포 리서치:** 프로젝트 초기 단계에서 배포 환경(예: cPanel)에 대한 리서치를 수행하는 것이 막바지 난관을 피하는 데 중요하다는 것을 인지했습니다.
    
-   **시각적 이상 현상 디버깅:** 디자인/로직 변경 후 PDF의 그래프와 같은 시각적 요소가 비정상적으로 출력될 때, **최근 코드 수정 내역에 대한 체계적인 검토**와 **렌더링 엔진 상호작용**(예: PDF 생성 라이브러리가 CSS/SVG를 해석하는 방식)에 집중하는 것이 중요합니다.
    
-   **통합 과제 예측:** 워드프레스와 같은 확립된 CMS와 통합하는 것은 예상치 못한 문제를 방지하기 위해 API 엔드포인트, 인증 및 데이터 일관성에 대한 신중한 계획이 필요합니다.
    
-   **즉각적인 API 키 활용:** API 키를 획득한 즉시 (귀하가 한 것처럼 간단한 POST 요청이라도) 이를 위한 기본적인 경로/함수를 설정하면 빠른 유효성 검사 및 추가 개발 진행이 가능해집니다.

## 🔜 이후 학습 방향

-   **배포 및 보안 리서치 계속:** cPanel 배포, 워드프레스 통합 방법(REST API, 인증), 포괄적인 보안 프로토콜에 대한 리서치를 심화할 것입니다.
    
-   **PDF 그래프 문제 디버깅:** PDF 보고서의 비정상적인 그래프 출력 문제를 우선적으로 디버깅하고 해결할 것입니다.
    
-   **Shopify 발표 준비:** 다음 주 화요일 Shopify/Shopify Plus 발표를 위한 리서치 및 발표 자료를 협력하여 완성할 것입니다.
    
-   **AI 요약 기능 로직 개발:** 기본적인 API 경로를 넘어, 데이터 수집, 페르소나/분석 정의, 프롬프트 엔지니어링을 포함한 AI 요약 기능의 전체 로직을 개발할 것입니다.
    
-   **2차 확인 계획:** 핵심 기능(AI 요약, 디자인 개선)이 구현된 후 이해관계자들과의 다음 검토를 준비할 것입니다.
