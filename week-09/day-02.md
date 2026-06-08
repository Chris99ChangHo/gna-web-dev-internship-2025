# 📅 Day 02 (2025-07-08, Tue)

## 🎓 What I Did Today

**📌 Participated in the morning development meeting, discussing the Melbourne Market product migration review and receiving a new directive for report automation R&D.**   
**📌 Initiated R&D for client report automation, setting up the development environment and confirming initial Google Analytics 4 (GA4) data retrieval.**   
**📌 Engaged in self-directed development, continually refining project direction by posing questions and seeking clarification from senior team members.**  

### Detailed Activities

**1. Morning Development Meeting & New Project Directives:** The day began with a development meeting where project statuses were reviewed, and new tasks were assigned based on current priorities.

-   **Melbourne Market Product Migration Review:**
    
    -   The team acknowledged the completion of the Shopify product migration.
        
    -   It was communicated that the **migrated product data will be reviewed at a later stage, and any issues identified will be communicated** for further action.
        
-   **Report Automation Project Kick-off:**
    
    -   Received a directive to **commence research and development for report automation**.
        
    -   I mentioned that I had already done some initial work yesterday (setting up the development environment and successfully connecting to GA4 to retrieve data), which was well received.
        
    -   It was highlighted that the current manual process for creating one report takes approximately **30 minutes due to manual copy-pasting**. Automating this process is expected to significantly reduce report generation time.
        
    -   Received advice to explore **cleaner and more modern PDF generation methods** than the existing `fpdf` (PHP-based) system, or to propose other ideas for improving the current marketing material creation process.
        

**2. Report Automation & Google API Integration Strategy Discussion:** Today's meeting included a comprehensive discussion on the architectural approach for report automation and the specifics of Google Ads and GA4 API integration, including key strategic decisions.

-   **Report Generation Implementation Approaches:**
    
    -   **PHP-based Approach:** Discussed modifying the "Generate Report" button to "Go to Dashboard" in PHP, where client information would automatically load. The plan was to code for automatic data input into PHP metric fields. _Initial focus is on the dashboard development, but this PHP approach remains a possibility after prototype review._
        
    -   **Python + JS (Full Dashboard) Approach:** Discussed implementing the entire report generation process within a Python + JavaScript dashboard. This would require extracting all client IDs to facilitate search or selection via a dropdown.
        
    -   **Strategic Decision:** We decided to **prioritize development using the Python + JS dashboard approach** for now, with the PHP method as a potential fallback after prototype evaluation.
        
-   **Google Ads & GA4 API Integration and MCC Account Clarification:**
    
    -   **Query on MCC Account:** I questioned if the company possesses a Google Ads MCC (My Client Center) manager account, and if it could be used to create client accounts and link to Google Analytics for centralized data management (stats, ads, etc.). I also noted the inefficiency of integrating individual client APIs without an MCC.
        
    -   **Google Ads API (without MCC):** It was confirmed that retrieving Google Ads data via API for multiple clients without an MCC account is highly inefficient and complex. Currently, this is handled manually. **Feedback received was to prioritize GA4 integration without MCC for now**, as not all clients utilize full web development, SEO, and Ads services. The long-term strategy will be to **propose MCC centralization** for unified management and data retrieval.
        
    -   **GA4 API (without MCC):** It was confirmed that GA4 integration **is possible without an MCC account**. If your Google account has access to all client GA4 properties, you can retrieve all client GA4 data using a single `client_secret.json` and `credentials.json` file, requiring only the individual GA4 property IDs.
        
-   **Google Ads API Automation & CSV UI Redundancy:**
    
    -   **Data Retrieval (Query) Capability:** Confirmed that automatically retrieving campaign performance data via the Google Ads API is fully feasible (currently demonstrated by dummy data in `app-test.py`'s `get_google_ads_data` function).
        
    -   **Data Writing (Campaign/Ad Group Management):** The Google Ads API is capable not only of data querying but also automating all ad management tasks, including campaign creation, ad group additions, keyword management, and budget setting. This means manual CSV file uploads become unnecessary, as Python code can directly manage Google Ads campaigns.
        
    -   **Conclusion:** The CSV-related UI is **not necessary for a fully automated system**. It likely served as a remnant of previous manual management or a fallback for difficult API integrations. We **decided to pursue full automation via the Google Ads API's 'write' capabilities**, eliminating the need for CSV-based management.
        

**3. Initial Research & Development for Report Automation:** Following the meeting, I immediately started on the new report automation directive.

-   **Development Environment Setup:** Confirmed my existing development environment was ready for this task.
    
-   **GA4 Data Integration:** Successfully connected to Google Analytics 4 (GA4) and verified the capability to retrieve data, building upon the experience from the dashboard project. This initial step is crucial for automating report generation, as GA4 is a primary data source.
    

**4. Self-Directed Development & Communication Process:** Actively managed my development process by continuously evaluating direction, raising self-posed questions, and formulating specific inquiries. These questions were then directed to senior developers or managers to align with existing company processes, ensuring a cycle of adjustment and improvement throughout development. This iterative approach helps refine solutions and ensures they integrate seamlessly with company standards.

## 🧠 Key Concepts Learned

-   **Strategic Architecture Decision-Making:** Understanding when to prioritize a full-stack solution (Python/JS) over a simpler integration (PHP), and the agility to revisit decisions based on prototype feedback.
    
-   **Differentiated API Access Models (Google Ads MCC vs. GA4 direct):** Critical understanding of how Google's various APIs handle multi-client access, particularly the significance of MCC for centralized Google Ads management versus GA4's more flexible direct property access.
    
-   **True Automation Scope of Google Ads API:** Grasping that Google Ads API can handle both data retrieval and campaign _management_ (write operations), making manual CSV uploads obsolete for full automation. This fundamentally changes the scope of what "automation" means for Ads.
    
-   **Client-Centric Development Prioritization:** Adapting immediate development goals (GA4 without MCC) based on current client service needs, while still planning for future, more centralized solutions (MCC proposal), balancing short-term feasibility with long-term vision.
    
-   **Proactive Task Initiation:** Recognizing and beginning work on a potential future task (like initial GA4 data retrieval) before it's formally assigned can lead to a head start and positive feedback.
    
-   **Efficiency Through Automation:** Reconfirmed the significant time-saving potential of automating manual processes, especially for repetitive tasks like report generation.
    
-   **Modernizing Legacy Systems:** Understood the importance of continuously evaluating and proposing updates to older systems (like `fpdf` for PDF generation) to improve efficiency, maintainability, and quality.
    
-   **Iterative Development & Communication:** Reinforced the value of a continuous feedback loop with senior team members to ensure development aligns with company goals and best practices, adapting and refining as needed.

## 💡 Practical Trial-and-Error and Tips

-   **Navigating API Authentication & Multi-Client Management:** The nuances of API authentication and management across different Google services (Google Ads vs. GA4), particularly concerning multi-client setups and the implications of MCC accounts, require careful planning to avoid pitfalls.
    
-   **Balancing Immediate Client Needs with Long-Term Architectural Goals:** It's crucial to align development priorities with current client service demands while continuously assessing and proposing future architectural improvements (e.g., MCC centralization) for greater long-term efficiency.
    
-   **Anticipate Future Needs:** Staying aware of broader project goals or company pain points can help you pre-emptively explore solutions, giving you an advantage when new tasks arise.
    
-   **Quantify Impact:** When proposing automation or improvements, being able to quantify the current manual effort (e.g., "30 minutes per report") clearly demonstrates the potential time/resource savings, strengthening your case.
    
-   **Look Beyond the Immediate Task:** When asked to improve a specific function (like PDF generation), consider the broader context and propose entirely new approaches or technologies if they offer significant advantages.
    
-   **Document and Ask:** Maintain a clear list of questions that arise during self-directed exploration. This structured approach makes your communication with seniors more efficient and productive.

## 🔜 Next Steps

-   **Focus on Python + JS Dashboard Development:** Focus on developing a Python + JS dashboard for report automation, **specifically prioritizing the implementation of extracting all client IDs and linking them to a dropdown**.
    
-   **Complete GA4 Data Integration:** Fully integrate and visualize GA4 data on the dashboard utilizing the GA4 property IDs of all clients.
    
-   **Initiate Google Ads API (Read) Integration:** Start automatically fetching campaign performance data via the Google Ads API and integrating it into the dashboard. (Aligning with the ultimate goal of API automation)
    
-   **Flesh Out Google Ads MCC Centralization Proposal:** Detail the proposal for centralizing Google Ads MCC accounts for efficient ad account management in the future.
    
-   **Continue Dashboard Project Debugging:** Continue debugging the dashboard project's 500 Internal Server Error, focusing specifically on the SERanking API integration.
    
-   **Prepare for Melbourne Market Migration Feedback:** Stand by to address and resolve any issues that may arise during the team's review of the migrated Shopify product data.
    
-   **Finalize Client One-Page Website:** Apply the remaining feedback for the "Gisa Restaurant" website and prepare for the final deployment.
    
-   **Deepen AI Security Threat Research & PPT Preparation:** Continue in-depth research and presentation material preparation on "The Evolution of AI-driven Hacking, Scams, and Spam — and Their Impact on Server Security," focusing on CPanel/WHM server security impacts, aiming for a presentation on Thursday, July 10, 2025.

----------

# 📅 2일차 (2025-07-08, 화)

## 🎓 오늘 한 일

**📌 오전 개발 미팅에 참여하여 멜번마켓 상품 마이그레이션 검토 계획을 논의하고, 리포트 자동화 관련 리서치 및 개발 착수 지시를 받았습니다.**   
**📌 클라이언트 리포트 자동화 R&D를 시작했으며, 개발 환경 설정 및 초기 Google Analytics 4 (GA4) 데이터 연동을 확인했습니다.**   
**📌 자기 주도적인 개발을 진행하며, 스스로 질문을 던지고 개발 선임/매니저와 소통하여 회사 프로세스에 맞춰 방향을 지속적으로 개선했습니다.**  

### 상세 활동

**1. 오전 개발 미팅 및 신규 프로젝트 지시:** 하루는 개발 미팅으로 시작되었고, 진행 중인 프로젝트 현황을 검토하고 새로운 전략적 업무를 배정받았습니다.

-   **멜번마켓 상품 마이그레이션 검토:**
    
    -   Shopify 상품 마이그레이션 완료를 팀에 알렸습니다.
        
    -   **마이그레이션된 상품 데이터는 추후 검토 후, 문제 발생 시 별도 안내**될 것이며, 추가 조치가 필요할 경우 진행될 예정임을 전달받았습니다.
        
-   **리포트 자동화 프로젝트 착수:**
    
    -   **리포트 자동화 관련 리서치 및 개발 업무를 시작**하라는 지시를 받았습니다.
        
    -   어제 이미 초기 작업을 시작했다(개발 환경 설정 및 GA4 연결을 통한 데이터 가져오기 확인)고 보고하자, 긍정적인 피드백을 받았습니다.
        
    -   현재 수동 복사/붙여넣기 방식으로 리포트 1건 제작에 **약 30분 소요**된다는 점이 강조되었으며, 자동화 시 리포트 생성 시간이 대폭 단축될 것으로 예상됩니다.
        
    -   기존 `fpdf`(PHP 기반)를 사용하는 PDF 생성 방식이 다소 구식임을 언급하며, **더 깔끔하고 모던한 PDF 생성 방식 도입** 또는 기존 마케팅 자료 제작 프로세스를 개선할 새로운 아이디어 적용을 제안하라는 조언을 받았습니다.
        

**2. 보고서 자동화 및 Google API 연동 전략 논의:** 오늘 미팅에서는 보고서 자동화를 위한 아키텍처 접근 방식과 Google Ads, GA4 API 연동의 구체적인 내용, 그리고 주요 전략적 결정들이 심도 있게 논의되었습니다.

-   **보고서 생성 구현 접근 방식 논의:**
    
    -   **PHP 기반 방식:** '보고서 생성 버튼'을 '대시보드로 가기' 정도로 변경하여 PHP에서 고객사 정보 자동 로드까지 처리하고 대시보드에서 지표를 동적으로 추가/삭제하는 방안을 논의했습니다. PHP 코드 내 지표 칸에 고객사 데이터 값을 자동으로 채워 넣는 것이 핵심이었습니다.
        
    -   **Python + JS 기반 방식:** 대시보드에서 보고서 생성까지 전체를 Python 및 JavaScript로 처리하는 방안을 논의했습니다. 이 방식에서는 모든 고객사 ID를 추출하여 드롭다운 형태로 관리하는 것이 필요하다는 결론을 내렸습니다.
        
    -   **전략적 결정:** 현재는 **Python + JS 대시보드 방식으로 개발을 우선 진행**하기로 결정했습니다. 다만, 프로토타입 확인 후 필요에 따라 PHP 기반 방식으로 돌아갈 가능성도 열어두었습니다.
        
-   **Google Ads 및 GA4 API 연동 및 MCC 계정 관련 질의응답:**
    
    -   **MCC 계정 필요성 질문:** 회사에 Google Ads MCC(My Client Center) 관리자 계정이 있는지, 그리고 이 계정을 통해 고객사 계정을 만들고 Google Analytics까지 연결하여 모든 데이터(광고, 통계 등)를 한 번에 관리할 수 있는지 질문했습니다. MCC 계정 없이 모든 고객사의 API를 하나하나 가져오는 것은 비효율적임을 언급했습니다.
        
    -   **Google Ads API (MCC 없이) 현황:** MCC 계정 없이 여러 고객사의 Google Ads 데이터를 API로 가져오는 것은 매우 비효율적이고 복잡하다는 점이 확인되었습니다. 현재는 수동으로 처리하고 있었고, 실제 고객들도 웹사이트 제작, SEO, 광고까지 모두 진행하는 경우가 많지 않기 때문에 **현 단계에서는 MCC 없이 GA4만 연동하여 자동화 해달라**는 피드백을 받았습니다. 향후에는 MCC를 통해 중앙 집중식 관리 및 데이터 통합이 가능하다는 점을 제안하는 방향으로 결정했습니다.
        
    -   **GA4 API (MCC 없이) 가능 여부:** Google 계정이 모든 고객사의 GA4 속성 접근 권한을 가지고 있다면, MCC 계정 없이도 하나의 `client_secret.json` 및 `credentials.json` 파일로 모든 고객사의 GA4 데이터를 가져올 수 있음을 확인했습니다. 각 고객사의 GA4 속성 ID만 알고 있으면 됩니다.
        
-   **Google Ads API 자동화 및 CSV UI 불필요성 논의:**
    
    -   **데이터 조회 가능성:** Google Ads API를 통해 캠페인 실적 데이터를 자동으로 가져오는 것이 완전히 가능하며, 현재 `app-test.py`의 `get_google_ads_data` 함수(현재 더미 데이터)가 그 역할을 할 수 있음을 확인했습니다.
        
    -   **데이터 쓰기 및 관리 자동화:** Google Ads API는 단순히 데이터를 조회하는 것을 넘어, 캠페인 생성, 광고 그룹 추가, 키워드 관리, 예산 설정 등 모든 광고 관리 작업을 자동화할 수 있음을 확인했습니다. 즉, CSV 파일을 수동으로 업로드할 필요 없이 파이썬 코드로 직접 Google Ads 계정의 캠페인을 생성하고 수정할 수 있습니다.
        
    -   **결론:** 완전 자동화된 시스템에서는 CSV 관련 UI가 필요 없다는 결론에 도달했습니다. 이는 기존 시스템의 수동 관리 방식을 반영한 것이거나, API 연동이 어려운 경우를 위한 대체 수단이었을 수 있습니다. **진정한 자동화를 위해 Google Ads API를 통한 자동화로 변경하기로 결정했습니다.**
        

**3. 리포트 자동화 초기 리서치 및 개발:** 미팅 후, 새로운 리포트 자동화 지시에 따라 즉시 작업을 시작했습니다.

-   **개발 환경 설정:** 기존 개발 환경이 이 작업을 수행할 준비가 되었음을 확인했습니다.
    
-   **GA4 데이터 연동:** 대시보드 프로젝트 경험을 바탕으로 Google Analytics 4 (GA4)에 성공적으로 연결하고 데이터 수집 가능성을 확인했습니다. 이는 GA4가 주요 데이터 소스이므로 리포트 자동화에 필수적인 초기 단계입니다.
    

**4. 개발 진행 방식 및 커뮤니케이션:** 개발 진행 중 지속적으로 방향을 점검하며, 스스로 의문을 제기하고 필요한 질문을 도출했습니다. 이러한 질문은 개발 선임 또는 매니저님께 전달하여 회사 기존 프로세스와 연계하여 방향을 조정하고 개선하는 과정을 반복했습니다. 이러한 반복적인 접근 방식은 해결책을 다듬고 회사 표준과 원활하게 통합되도록 돕습니다.

## 🧠 배운 핵심 개념

-   **보고서 자동화 아키텍처 설계의 복합성:** 단순한 데이터 연동을 넘어, PHP와 Python/JS 중 어떤 기술 스택을 선택할 것인지, 그리고 동적 지표 관리와 같은 기능적 요구사항을 어떻게 충족시킬 것인지에 대한 전략적 사고의 중요성을 배웠습니다.
    
-   **Google API별 계정 관리 및 접근 방식의 차이:** Google Ads API의 다중 클라이언트 관리에서 MCC 계정의 중요성과, 이와 대조적으로 GA4 API가 MCC 없이도 개별 속성 ID를 통해 유연하게 접근 가능한 점을 명확히 이해했습니다. 이는 향후 API 연동 전략 수립에 필수적인 지식입니다.
    
-   **완전 자동화의 범위와 목표 설정:** Google Ads API가 데이터 조회뿐 아니라 '쓰기' 기능(캠페인 관리)까지 지원하여 진정한 자동화를 구현할 수 있음을 파악했습니다. 이를 통해 CSV 업로드와 같은 수동 개입 요소를 완전히 제거하는 것이 자동화의 궁극적인 목표임을 재확인했습니다.
    
-   **현실적 제약(클라이언트 니즈)과 장기 비전의 균형:** 현재 클라이언트의 상황(웹/SEO/광고 통합이 드문 경우) 때문에 당장은 GA4 연동에 집중하되, 향후 MCC를 통한 중앙 집중식 관리 시스템을 제안할 계획을 세우는 등, 단기적인 실현 가능성과 장기적인 목표를 동시에 고려하는 접근법을 배웠습니다.
    
-   **선제적 업무 착수:** 공식적으로 할당되기 전에 잠재적인 미래 작업(예: 초기 GA4 데이터 검색)을 인지하고 시작하는 것은 좋은 출발과 긍정적인 피드백으로 이어질 수 있습니다.
    
-   **자동화를 통한 효율성:** 리포트 생성과 같은 반복적인 작업을 포함하여 수동 프로세스를 자동화함으로써 얻을 수 있는 상당한 시간 절약 잠재력을 재확인했습니다.
    
-   **레거시 시스템 현대화:** `fpdf`와 같은 오래된 시스템(PDF 생성용)을 지속적으로 평가하고 업데이트를 제안하여 효율성, 유지 보수성 및 품질을 향상시키는 것의 중요성을 이해했습니다.
    
-   **반복적 개발 및 커뮤니케이션:** 개발이 회사 목표 및 모범 사례와 일치하도록 선임 팀원과의 지속적인 피드백 루프의 가치를 강화하고 필요에 따라 조정하고 개선했습니다.
    

## 💡 실전 시행착오 및 팁

-   **API 연동 전 상세한 요구사항 및 환경 확인:** Google Ads API와 GA4 API의 계정 및 접근 권한 요구사항이 다르다는 점은, 개발 착수 전에 명확히 확인해야 할 중요한 요소입니다. 미팅을 통해 이 부분을 미리 파악하여 불필요한 시행착오를 줄일 수 있었습니다.
    
-   **내부 전문가와의 소통을 통한 방향 재설정:** 스스로 제기한 기술적/운영적 질문에 대해 개발 선임 및 매니저님과 심도 있게 논의하며, 회사 내부의 기존 프로세스와 클라이언트 니즈에 맞춰 개발 방향을 유연하게 조정할 수 있었습니다. 이는 효율적인 개발을 위한 핵심 팁입니다.
    
-   **자동화 범위에 대한 명확한 이해와 목표 설정:** '자동화'라는 목표가 단순히 데이터 가져오기를 넘어 '쓰기' 기능(캠페인 관리)까지 포함할 수 있음을 인지하고, 이를 통해 불필요한 UI(CSV 업로드)를 제거하는 결정을 내린 것은 '진정한 자동화'를 위한 중요한 의사결정 과정이었습니다.
    
-   **미래 요구 사항 예측:** 더 넓은 프로젝트 목표나 회사의 문제점을 파악하고 있으면, 새로운 작업이 발생했을 때 미리 해결책을 탐색하여 유리한 위치를 차지할 수 있습니다.
    
-   **영향 정량화:** 자동화 또는 개선을 제안할 때 현재 수동 작업량(예: "리포트당 30분")을 정량화할 수 있으면 잠재적인 시간/자원 절약을 명확하게 보여주어 주장의 설득력을 높일 수 있습니다.
    
-   **당면 과제 너머를 보기:** 특정 기능(예: PDF 생성)을 개선하라는 요청을 받았을 때, 더 넓은 맥락을 고려하고 상당한 이점을 제공한다면 완전히 새로운 접근 방식이나 기술을 제안하세요.
    
-   **문서화하고 질문하기:** 자기 주도적 탐색 중에 발생하는 질문들을 명확하게 목록화하세요. 이러한 체계적인 접근 방식은 선임자와의 커뮤니케이션을 더 효율적이고 생산적으로 만듭니다.
    

## 🔜 이후 학습 방향

-   **Python + JS 대시보드 개발 집중:** 보고서 자동화를 위해 Python + JS 대시보드 개발에 집중하고, **특히 모든 고객사 ID를 추출하여 드롭다운에 연동하는 기능을 우선 구현**할 것입니다.
    
-   **GA4 데이터 연동 완성:** 모든 고객사의 GA4 속성 ID를 활용하여 GA4 데이터를 완벽하게 연동하고 대시보드에 시각화하는 작업을 진행할 것입니다.
    
-   **Google Ads API (조회) 통합 시작:** Google Ads API를 통해 캠페인 실적 데이터를 자동으로 가져와 대시보드에 연동하는 작업을 시작할 것입니다. (궁극적인 API 자동화 목표에 맞춰)
    
-   **Google Ads MCC 계정 중앙화 제안 구체화:** 향후 효율적인 광고 계정 관리를 위해 Google Ads MCC 계정 중앙화 방안에 대한 제안 내용을 구체화할 것입니다.
    
-   **대시보드 프로젝트 디버깅 계속:** 대시보드 프로젝트의 500 Internal Server Error, 특히 SERanking API 통합에 집중하여 계속 디버깅할 것입니다.
    
-   **멜번마켓 마이그레이션 피드백 준비:** 마이그레이션된 Shopify 상품 데이터에 대한 팀의 검토에서 발생할 수 있는 모든 문제를 기다리고 해결할 준비를 할 것입니다.
    
-   **클라이언트 원페이지 웹사이트 최종 마무리:** "기사식당" 웹사이트에 대한 남은 피드백을 반영하고 최종 배포를 준비할 것입니다.
    
-   **AI 보안 위협 리서치 및 PPT 준비 심화:** 2025년 7월 10일(목) 발표를 목표로 CPanel/WHM 서버 보안 영향을 중심으로 "AI를 활용한 해킹, 스캠, 스팸의 진화 — 그리고 서버 보안에 미치는 영향"에 대한 심층 리서치 및 발표 자료 준비를 계속할 것입니다.
