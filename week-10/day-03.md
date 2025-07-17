# 📅 Day 03 (2025-07-16, Wed)

## 🎓 What I Did Today

**📌 Received feedback on the PDF generation output, including a request to consider PHP migration and design the PDF structure for dynamic image integration.**   
**📌 Completed the product information migration for newly added items on Melbourne Market.**   
**📌 Continued development and improvement of the report project, focusing on PDF template structure, data handling, and refining client selection and SERanking data processing.**  

### Detailed Activities

**1. Morning Development Meeting - Feedback & New Task Assignment:**

-   **PDF Generation Feedback:** Received overall positive feedback on the PDF generation output delivered yesterday.
    
    -   **Python to PHP Consideration:** Advised to consider methods for migrating the Python-based PDF generation to PHP in the future, to address potential server-related issues (though current completion is the priority).
        
    -   **PDF Structure for Dynamic Images:** Requested to design the PDF's internal structure to allow for the integration or replacement of image files from the report-generating website's backend.
        
-   **New Task: Melbourne Market Product Information Migration:** Assigned the task of migrating product information for newly added items on Melbourne Market.
    
    -   Priority was given to completing this migration first, followed by continued report project work, with updates on any issues.
        

**2. Product Information Migration:**

-   **Melbourne Market Migration:** Initiated the migration code for Melbourne Market product information in the morning, and **successfully completed the migration of information for newly added products to Shopify CDN.** (Initially, 20 out of 26 new products were uploaded without product information, and migration was completed for the remaining 6.)
    

**3. Continued Report Project Development:**

-   **PDF Template Structure Enhancement:** Simultaneously worked on improving the PDF template structure.
    
    -   **Client Selection & Inquiry Feature:** Successfully loaded multiple SERanking client site lists on the dashboard.
        
    -   **SERanking Data Collection & Transmission:** Successfully retrieved real-time keyword ranking data from the SERanking API. Processed the data into the required frontend format (`current_rank_display`, `previous_rank_display`, `change_display`, etc.) and structured it for PDF generation requests.
        
    -   **Jinja Template Improvement:** Improved the current Jinja template's data structure and table styles to match the dashboard. Optimally processed SER data fields that were previously missing or displayed as zeros, by refining frontend preprocessing, server-side data manipulation, and template usage across the board.
        
-   **Ongoing Development:** Continued to **develop and improve the report project** until the end of the workday.
    

## 🧠 Key Concepts Learned

-   **Prioritizing Project Goals:** Learned the importance of balancing immediate deliverables (PDF completion) with future scalability/maintenance considerations (PHP migration).
    
-   **Robust Data Handling across Platforms:** Gained experience in meticulously handling data inconsistencies (e.g., missing product info) and optimizing data flow from API to frontend display and PDF generation.
    
-   **Strategic PDF Design:** Understood that PDF generation isn't just about rendering, but also designing for dynamic content (like images) and ensuring visual fidelity between web dashboards and static PDF outputs.
    

## 💡 Practical Trial-and-Error and Tips

-   **Missing Data Management in Migration:** Encountered a significant number of products without information during migration. **Tip:** Proactively identify and categorize data quality issues (e.g., completely missing data vs. incomplete data) early in migration tasks to adjust scope or communicate necessary pre-processing.
    
-   **Maintaining Consistency from Dashboard to PDF:** Optimizing SER data fields for PDF required a holistic review of preprocessing, server-side processing, and template usage. **Tip:** When aiming for 1:1 conversion from web UI to PDF, consistently apply data processing and styling rules across both rendering environments from the outset.
    
-   **Balancing Iteration and Strategic Planning:** While focusing on immediate fixes for PDF, the feedback prompted thinking about long-term solutions like PHP migration and dynamic image integration. **Tip:** Always keep an eye on future requirements and potential architectural shifts even when deep in current development tasks.
    

## 🔜 Next Steps

-   **1:1 Conversion of SERanking Dashboard to PDF:** Ensure the SERanking tables and charts displayed on the dashboard are converted to PDF with identical content and style.
    
-   **Finalize PDF Generation Process:** Complete the PDF generation process, including template optimization and accurate reflection of dynamic data.
    
-   **Complete AutoViz-based EDA Auto-PDF Generation:** Finalize the automated PDF generation feature for Exploratory Data Analysis (EDA) reports based on AutoViz.

---------

# 📅 3일차 (2025-07-16, 수)

## 🎓 오늘 한 일

**📌 어제 퇴근 직전 전달한 PDF 생성 결과물에 대한 피드백을 받았으며, PHP 마이그레이션 고려 및 동적 이미지 통합을 위한 PDF 구조 설계를 요청받았습니다.**   
**📌 멜번마켓(링크)에 새로 추가된 상품에 대한 상품정보 마이그레이션 업무를 완료했습니다.**   
**📌 통합 대시보드 및 PDF 리포트 UI/코드 개선 작업을 시작했으며, 레이아웃 최적화, 영어 통일, 브랜딩, 고급 데이터 시각화에 중점을 두었습니다.**  

### 상세 활동

**1. 오전 개발 미팅 — 피드백 및 신규 업무 할당:**

-   **PDF 생성 결과물 피드백:** 어제 퇴근 직전에 전달드린 PDF 생성 결과물에 대해 전반적으로 괜찮다는 피드백을 받았습니다.
    
    -   **Python to PHP 고려:** 현재 Python으로 구현된 PDF 생성 기능을 추후 서버 관련 문제가 발생할 수 있으니, 가능하다면 PHP로 옮길 수 있는 방법도 고민해보라는 피드백을 받았습니다 (단, 일단은 현재 완성하는 것이 우선이라고 강조하셨습니다).
        
    -   **동적 이미지 통합을 위한 PDF 구조 설계:** 현재 사용하는 리포트 생성 웹사이트 백엔드에 이미지 파일들이 있으니, 이 이미지들을 활용하거나 교체할 수 있도록 PDF 내부 구조도 그렇게 설계해달라는 요청이 있었습니다.
        
-   **신규 업무: 멜번마켓 상품정보 마이그레이션:** 멜번마켓(링크)에 새로 추가된 상품에 대한 상품정보 마이그레이션 작업을 맡게 되었습니다.
    
    -   상품 마이그레이션을 먼저 완료하고 이어서 리포트 프로젝트 작업을 진행하며, 이슈 발생 시 업데이트해달라는 지시를 받았습니다.
        

**2. 상품정보 마이그레이션:**

-   **멜번마켓 마이그레이션:** 오전에 멜번마켓 상품 마이그레이션 코드를 실행했으며, **새로 추가된 상품들의 정보를 Shopify CDN으로 성공적으로 마이그레이션 완료했습니다.** (초기 26개 중 20개가 상품 정보 없이 업로드된 상태였고, 나머지 6개에 대한 마이그레이션을 진행했습니다.)
    

**3. 리포트 프로젝트 개발 지속:**

-   **PDF 템플릿 구조 개선:** 병행하여 PDF 템플릿 구조 개선 작업을 진행했습니다.
    
    -   **클라이언트 선택·조회 기능:** 여러 SERanking 클라이언트 사이트 목록을 대시보드에서 정상적으로 불러오는 데 성공했습니다.
        
    -   **SERanking 데이터 수집 및 전송:** SERanking API로부터 실시간 키워드 랭킹 데이터를 받아왔으며, 프론트엔드에서 필요한 포맷(`current_rank_display`, `previous_rank_display`, `change_display` 등)으로 가공하여 PDF 생성 요청을 위한 데이터 구조로 전달하는 데 성공했습니다.
        
    -   **Jinja 템플릿 개선:** 현행 Jinja 템플릿의 자료구조 및 표 스타일을 대시보드와 동일하게 개선했고, 기존에 누락되거나 0으로 표시되던 SER 데이터 필드를 프론트엔드 전처리, 서버 가공, 템플릿 사용 방식 전체를 실무적으로 최적화했습니다.
        
-   **개발 지속:** 퇴근 전까지 계속해서 **리포트 프로젝트 관련 개발 및 개선 작업을 이어갔습니다.**
    

## 🧠 배운 핵심 개념

-   **프로젝트 목표 우선순위 설정:** PDF 완성이라는 당면 과제와 서버 확장성/유지보수(PHP 마이그레이션)라는 미래 고려 사항 간의 균형을 맞추는 것의 중요성을 배웠습니다.
    
-   **플랫폼 간 견고한 데이터 처리:** (누락된 상품 정보와 같은) 데이터 불일치를 세심하게 처리하고, API에서 프론트엔드 표시 및 PDF 생성까지 데이터 흐름을 최적화하는 경험을 얻었습니다.
    
-   **전략적인 PDF 디자인:** PDF 생성은 단순히 렌더링을 넘어 동적 콘텐츠(이미지 등)를 위한 설계와 웹 대시보드 및 정적 PDF 출력물 간의 시각적 일관성을 보장하는 것이 중요함을 이해했습니다.
    

## 💡 실전 시행착오 및 팁

-   **마이그레이션 시 누락 데이터 관리:** 마이그레이션 과정에서 상품 정보가 완전히 없는 상품들이 상당수 발견되었습니다. **팁:** 마이그레이션 작업 초기 단계에서 데이터 품질 문제(예: 완전히 누락된 데이터 대 불완전한 데이터)를 사전에 식별하고 분류하여 작업 범위를 조정하거나 필요한 사전 처리 과정을 조율해야 합니다.
    
-   **대시보드와 PDF 간 일관성 유지:** PDF를 위해 SER 데이터를 최적화하는 과정에서 전처리, 서버 측 처리, 템플릿 사용 방식 전체를 포괄적으로 검토해야 했습니다. **팁:** 웹 UI에서 PDF로 1:1 변환을 목표로 할 때는 초기부터 양쪽 렌더링 환경에 데이터 처리 및 스타일링 규칙을 일관되게 적용해야 합니다.
    
-   **반복 작업과 전략적 계획의 균형:** 현재 PDF 관련 즉각적인 수정에 집중하고 있지만, 피드백을 통해 PHP 마이그레이션 및 동적 이미지 통합과 같은 장기적인 해결책을 고민하게 되었습니다. **팁:** 현재 개발 작업에 깊이 몰두하고 있더라도 항상 미래 요구사항과 잠재적인 아키텍처 변화에 대한 안목을 유지해야 합니다.
    

## 🔜 이후 학습 방향

-   **SERanking 대시보드 ↔ PDF 1:1 변환:** 대시보드에 표시되는 SERanking 표/차트가 PDF로 변환될 때 내용과 스타일이 1:1로 동일하게 유지되는지 확인하고 필요한 조치를 취할 것입니다.
    
-   **PDF화 프로세스 최종 마무리:** 템플릿 최적화 및 동적 데이터 반영을 포함한 PDF 생성 프로세스를 최종 마무리할 것입니다.
    
-   **AutoViz 기반 EDA 자동 PDF화 기능 완성:** AutoViz 기반의 탐색적 데이터 분석(EDA) 자동 PDF화 기능을 완성할 것입니다.
