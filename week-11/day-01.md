# 📅 Day 01 (2025-07-21, Mon)

## 🎓 What I Did Today

**📌 Participated in the morning development meeting, sharing Report project progress and discussing PDF structure/design modifications based on designer and senior developer feedback, along with research into local server deployment, WordPress integration, and security enhancements.**   
**📌 Focused on researching Flask dashboard server deployment methods using cPanel's Python App menu, considering WordPress (WP) integration strategies, and strengthening practical setup and error handling capabilities.**   
**📌 Began preparing for an upcoming presentation on Shopify & Shopify Plus, including an in-depth analysis of the new Starter Plan's strengths and weaknesses.**  

### Detailed Activities

**1. Morning Development Meeting Summary:**

-   **Report Project Progress Sharing**: Shared updates on the project's advancement.
    
-   **PDF Structure & Design Modification**: Reported that work is underway to refine the PDF structure and design, incorporating feedback from the designer.
    
-   **Local Server Deployment Research**: Communicated that research is ongoing, based on senior developer feedback, into methods for deploying the locally developed Report project to the company's development server (cPanel). It was confirmed that while merging with PHP might be convenient, it's not a strict requirement; the key is successful deployment to the cPanel environment.
    
-   **Emphasis on Development Purpose**: The primary goal of the development – resolving inefficiencies in existing processes and enhancing operational efficiency – was re-emphasized.
    
-   **WordPress (WP) Server Integration**: Discussion included the need to consider how the new functionalities can be effectively applied and operated within the existing WordPress (WP) based server environment.
    
-   **Security Feedback**: Data security was repeatedly highlighted as critical due to customer data involvement. Feedback stressed the necessity of implementing access control measures, such as login/administrator authentication, to prevent unauthorized access.
    

**2. Flask Dashboard Server Deployment (Operations Readiness) Research:**

-   **cPanel Python App Menu Analysis**: Focused on understanding the server deployment method for the Flask (Python) dashboard program using cPanel's Python App menu.
    
-   **Specific Setting Comprehension**: Gained a concrete understanding of and learned examples for `Application root`, `Application URL`, `startup file`, and `entry point` settings.
    
-   **File Preparation & Upload**: Clearly grasped how to prepare `requirements.txt` (Python library list) for the server and how to upload the entire project code.
    
-   **Folder & Sensitive Data Security**: Learned practices for placing and securing key folders (`templates`, `static`, etc.) and sensitive data (`.env` etc.) used by the Flask app.
    
-   **503 Error Diagnosis**: Practiced specific methods for diagnosing the cause of `503 errors` (e.g., checking app status, reviewing logs, verifying pip installations).
    

**3. Flask App and WordPress (WP) Integration Strategy Discussion:**

-   **WP Site Access Design**: Designed how the Flask dashboard could be accessed from the WP site via a "Go to Dashboard" button/menu.
    
-   **Subdomain Deployment Confirmation**: Confirmed that deploying the Flask dashboard as a subdomain of the WP site (e.g., `dashboard.yourdomain.com`) is a common and recommended practice for practical implementation.
    
-   **Parameter Difference Comprehension**: Clearly understood the differences in actual setup for path/domain/subdomain-related input values (subdomain vs. subpath).
    

**4. Enhanced Practical Setup/Error Handling Capability Research:**

-   **Deployment Flow Systematization**: Systematically organized the flow and considerations for app deployment, execution, and transition to a real service environment (local → production).
    
-   **cPanel Menu Familiarization**: Gained practical familiarity with actual input fields in cPanel menus, expected file/folder structures, and methods for determining the root for each project.
    
-   **Real-world Troubleshooting Exploration**: Explored common user confusion (from a non-expert perspective) encountered during system deployment and practical troubleshooting methods.
    

**5. Shopify/Shopify Plus Presentation Preparation:**

-   **Presentation Topic**: Began preparing for an upcoming presentation on **Shopify & Shopify Plus**, specifically analyzing their **strengths/weaknesses (particularly critical limitations)**.
    
-   **Shopify Starter Plan Analysis**: Included dedicated research into the recently launched **Shopify - Starter Plan ($7/month)**, examining its own strengths and weaknesses, especially critical limitations.
    

## 🧠 Key Concepts Learned

-   **Practical Server Deployment Fundamentals**: Gained a hands-on understanding of the concrete procedures and necessary configurations (root, startup file, entry point, etc.) for deploying a locally developed Flask application to a cPanel-based production environment, moving beyond theoretical knowledge.
    
-   **Strategic CMS (WordPress) Integration**: Explored various methods for integrating the newly developed Flask dashboard with an existing WordPress website, grasping the benefits of subdomain deployment and actual configuration methods, which underscored the importance of establishing an integration strategy in complex web environments.
    
-   **Operational Security and Error Diagnosis**: Reconfirmed the critical importance of authentication and access control for customer data protection. Learned how to diagnose and resolve common post-deployment errors (e.g., 503 errors), thereby strengthening capabilities beyond development into operational stages.
    
-   **Structured Research for Business Presentation**: Engaged in a structured research process for a business presentation, understanding the need for in-depth analysis of platform features, pricing, and critical limitations to provide valuable insights for decision-making.
    

## 💡 Practical Trial-and-Error and Tips

-   **Importance of cPanel Deployment Pre-preparation**: Realized that a precise understanding of each cPanel Python App menu item (like `Application root`, `startup file`, `entry point`) and thoroughly preparing essential files such as `requirements.txt` beforehand are crucial for minimizing deployment trial-and-error.
    
-   **Flask App Folder Structure and Security**: It's vital to plan in advance how Flask app folder structures (`templates`, `static`) will be placed within the cPanel environment and how sensitive data (e.g., `.env` files) will be securely managed. This is essential for preventing post-deployment security vulnerabilities.
    
-   **Systematic Error Diagnosis Post-Deployment**: When deployment-related errors like `503 errors` occur, developing a habit of systematically checking app status, log files, and pip installations, rather than blindly retrying, is effective in reducing problem-solving time.
    
-   **Comprehensive Platform Analysis for Presentations**: For presentations on platforms like Shopify, it's not enough to list features; deeply understanding the nuances of different plans (like the Starter Plan) and their critical limitations provides a much more robust and insightful analysis.
    

## 🔜 Next Steps

-   **Attempt cPanel Deployment**: Based on the research, attempt the actual deployment of the Flask dashboard app to the cPanel development server, troubleshooting any encountered issues to gain practical experience.
    
-   **Finalize WordPress Integration**: Define specific methods for integrating the Flask dashboard as a WordPress subdomain and research additional WP API integration methods if necessary.
    
-   **Apply Security Protocols**: Based on senior developer feedback, concretize plans for applying core security protocols to the Report project, including login/administrator authentication and API key security.
    
-   **Complete Shopify/Shopify Plus Presentation**: Finalize the research and complete the presentation materials for the Shopify and Shopify Plus review scheduled for next Tuesday.

----------

# 📅 1일차 (2025-07-21, 월)

## 🎓 오늘 한 일

**📌 오전 개발 미팅에서 Report 프로젝트 진행 상황을 공유하고, 디자이너 및 개발 선임의 피드백을 바탕으로 PDF 구조 및 디자인 수정, 로컬 서버 배포 방안 리서치, 워드프레스 연동, 그리고 보안 강화에 대한 논의를 진행했습니다.**   
**📌 cPanel의 Python App 메뉴를 활용한 Flask 대시보드 서버 배포 방법을 집중적으로 파악하고, 워드프레스(WP)와의 연동 전략 및 실무 세팅/에러 대처 역량을 강화하기 위한 리서치를 수행했습니다.**   
**📌 다가오는 Shopify & Shopify Plus 발표 준비를 시작했으며, 특히 새로운 Starter Plan의 강점과 약점에 대한 심층 분석을 포함했습니다.**  

### 상세 활동

**1. 오전 개발 미팅 요약:**

-   **Report 프로젝트 진행 상황 공유**: 프로젝트 진행 상황에 대해 공유했습니다.
    
-   **PDF 구조 및 디자인 수정**: 디자이너의 피드백을 반영하여 PDF 구조와 디자인을 수정하는 작업을 진행 중임을 보고했습니다.
    
-   **로컬 서버 배포 방안 리서치**: 개발 선임의 피드백에 따라 로컬에서 구현한 Report 프로젝트를 회사 개발 서버(cPanel)로 옮길 수 있는 방법을 리서치 중임을 보고했습니다. PHP로 병합하는 것이 편리할 수 있지만, 필수 조건은 아니며, cPanel에 정상적으로 배포할 수 있다면 언어나 방식에 제약이 없음을 확인했습니다.
    
-   **개발 목적 강조**: 기존 프로세스의 비효율적인 부분을 해소하고 업무 능률을 높이기 위한 개발의 목적이 재차 강조되었습니다.
    
-   **워드프레스(WP) 기반 서버 연동**: 실제로 워드프레스(WP) 기반 서버에 새 기능을 어떻게 적용하고 운영할 수 있을지에 대한 방향성을 고민할 필요가 있다는 점이 논의되었습니다.
    
-   **보안 관련 피드백**: 고객 데이터가 포함된 시스템 특성상 데이터 보안이 반복적으로 강조되었으며, 누구나 접근할 수 없도록 로그인/인증(특히 관리자 인증) 등 접근 제어 방안 마련이 필요하다는 피드백을 받았습니다.
    

**2. Flask 대시보드 서버 배포(운영 준비) 관련 리서치:**

-   **cPanel Python App 메뉴 파악**: cPanel의 Python App 메뉴를 기반으로 Flask(파이썬) 대시보드 프로그램 서버 배포 방법을 집중적으로 파악했습니다.
    
-   **세팅 구체적 이해**: `Application root`, `Application URL`, `startup file`, `entry point` 세팅을 구체적으로 이해하고 예시를 학습했습니다.
    
-   **파일 준비 및 업로드**: 서버용 `requirements.txt`(파이썬 라이브러리 목록) 준비와 프로젝트 전체 코드 업로드 방법을 명확히 습득했습니다.
    
-   **폴더 및 민감 데이터 보안**: Flask 앱에서 사용하는 주요 폴더(`templates`, `static` 등) 및 민감 데이터(`.env` 등)의 배치 및 보안 체크 방식을 익혔습니다.
    
-   **503 에러 진단법 학습**: `503 에러` 발생 시 원인 진단법(앱 실행 상태, 로그 확인, pip 설치 등)을 구체적으로 학습했습니다.
    

**3. Flask 앱과 워드프레스(WP) 연동 전략 고민:**

-   **WP 사이트 연동 설계**: WP 사이트에서 "대시보드 바로가기" 등의 버튼/메뉴로 Flask 대시보드에 접속하는 방안을 설계했습니다.
    
-   **하위 도메인 배포 확인**: Flask 대시보드를 WP 사이트의 하위 도메인(예: `dashboard.도메인.com`)으로 배포하는 것이 실무적으로 일반적이고 권장되는 방식임을 확인했습니다.
    
-   **입력값 차이 파악**: 경로/도메인/서브도메인 관련 입력값 차이(하위 도메인 vs 하위 경로)의 실제 설정 방식을 명확하게 파악했습니다.
    

**4. 실무 세팅/에러 대처 역량 강화 리서치:**

-   **배포 흐름 정리**: 앱 배포, 실행, 실제 서비스 환경 전환(로컬→운영) 흐름 및 유의점을 체계적으로 정리했습니다.
    
-   **cPanel 메뉴 숙지**: cPanel 메뉴의 실제 입력란, 기대하는 파일/폴더 구조, 프로젝트별 root 결정법을 경험적으로 숙지했습니다.
    
-   **실무적 대처법 탐색**: 시스템 배포 과정에서 마주치는 사용자 입장(비전문가 시점)에서의 혼란 및 실무적 대처법을 탐색했습니다.
    

**5. Shopify/Shopify Plus 발표 준비:**

-   **발표 주제**: 다가오는 **Shopify & Shopify Plus** 발표 준비를 시작했으며, 특히 **강점/약점 (주요 치명적 한계 포함)**을 분석했습니다.
    
-   **Shopify Starter Plan 분석**: 최근 출시된 **Shopify - Starter Plan(월 $7)**에 대한 심층 리서치를 포함하여, 해당 플랜의 강점과 약점, 특히 주요 치명적 한계를 검토했습니다.
    

## 🧠 배운 핵심 개념

-   **서버 환경 배포의 실질적 이해**: 로컬에서 개발한 Flask 애플리케이션을 cPanel 기반의 실제 운영 환경에 배포하기 위한 구체적인 절차와 필요한 설정(루트, 시작 파일, 엔트리 포인트 등)을 학습하며, 이론을 넘어선 실질적인 배포 과정을 이해했습니다.
    
-   **CMS(워드프레스)와의 연동 전략**: 기존 워드프레스 웹사이트와 새로 개발된 Flask 대시보드를 통합하는 다양한 방법을 고민하며, 특히 하위 도메인 배포의 이점과 실제 설정 방식을 파악하여 복합적인 웹 환경에서의 연동 전략을 수립하는 중요성을 깨달았습니다.
    
-   **운영 환경에서의 보안 및 에러 진단**: 고객 데이터 보호를 위한 인증 및 접근 제어의 중요성을 재확인하고, 배포 후 발생할 수 있는 일반적인 에러(예: 503 에러)의 원인을 진단하고 해결하는 방법을 학습하여, 개발을 넘어선 운영 단계에서의 역량을 강화했습니다.
    
-   **비즈니스 발표를 위한 구조화된 리서치**: 플랫폼의 특징, 가격 책정, 그리고 중요한 제약 사항에 대한 심층적인 분석이 의사 결정에 귀중한 통찰력을 제공함을 이해하며, 비즈니스 발표를 위한 구조화된 리서치 과정을 경험했습니다.
    

## 💡 실전 시행착오 및 팁

-   **cPanel 배포 사전 준비의 중요성**: `Application root`, `startup file`, `entry point` 등 cPanel Python App 메뉴의 각 항목이 의미하는 바를 정확히 이해하고, `requirements.txt`와 같은 필수 파일을 사전에 완벽하게 준비하는 것이 배포 과정의 시행착오를 줄이는 핵심임을 깨달았습니다.
    
-   **Flask 앱 폴더 구조와 보안**: Flask 앱의 `templates`, `static` 폴더 구조를 cPanel 환경에 맞게 배치하고, `.env` 파일과 같은 민감한 데이터를 안전하게 관리하는 방법을 미리 고려하는 것이 중요합니다. 이는 배포 후 발생할 수 있는 보안 취약점을 예방하는 데 필수적입니다.
    
-   **에러 발생 시 체계적 진단**: `503 에러`와 같은 배포 관련 에러가 발생했을 때, 무작정 재시도하기보다 앱 실행 상태, 로그 파일, `pip` 설치 여부 등을 체계적으로 확인하는 습관이 문제 해결 시간을 단축하는 데 효과적입니다.
    
-   **발표를 위한 포괄적인 플랫폼 분석**: Shopify와 같은 플랫폼에 대한 발표를 할 때, 단순히 기능 목록을 나열하는 것을 넘어 다양한 플랜(예: Starter Plan)의 미묘한 차이점과 치명적인 한계를 심층적으로 이해하는 것이 훨씬 더 견고하고 통찰력 있는 분석을 제공한다는 것을 배웠습니다.
    

## 🔜 다음 학습 방향

-   **cPanel 실제 배포 시도**: 리서치한 내용을 바탕으로 Flask 대시보드 앱을 cPanel 개발 서버에 실제로 배포하는 작업을 시도하고, 발생할 수 있는 문제점을 해결하며 실무 경험을 쌓을 것입니다.
    
-   **워드프레스 연동 구체화**: Flask 대시보드를 워드프레스 하위 도메인으로 연동하는 구체적인 방법을 설정하고, 필요한 경우 WP API 연동 방식 등을 추가로 리서치할 것입니다.
    
-   **보안 프로토콜 적용**: 개발 선임의 피드백을 바탕으로 로그인/관리자 인증 및 API 키 보안 등 핵심 보안 프로토콜을 Report 프로젝트에 적용하는 방안을 구체화할 것입니다.
    
-   **Shopify/Shopify Plus 발표 자료 완성**: 다음 주 화요일 발표를 위해 Shopify 및 Shopify Plus에 대한 리서치를 마무리하고 발표 자료를 완성할 것입니다.
