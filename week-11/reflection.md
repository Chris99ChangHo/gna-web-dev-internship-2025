# 📝 Week 11 Reflection (2025.07.21 ~ 07.25)

## ✅ Key Tasks This Week

**📌 Successfully deployed Flask dashboard to cPanel and resolved operational environment issues**: Overcame various shared hosting constraints, including missing WSGI executable files and Playwright installation problems, successfully establishing the basic Flask app runtime environment.   
**📌 Successfully implemented PDF report auto-generation feature**: After attempting multiple libraries, the PDF report auto-generation feature using HTML/CSS was finally implemented with `xhtml2pdf`.   
**📌 Established WordPress integration and security enhancement plan**: Concrete strategies for integrating the Flask app with WordPress were defined, and a detailed security protocol plan for user access control was established.  

## 🧠 What I Learned

-   **Practical Server Deployment and Infrastructure Importance**: I gained hands-on experience deploying a Flask app developed locally to a live cPanel environment, troubleshooting initial issues like file/folder structures and Python App configurations. Crucially, I realized that **fundamental server infrastructure problems**, such as a missing `lswsgi` executable or the inability to install Playwright, **cannot be solved by developers alone**. This highlighted the **necessity of external support** and the **importance of efficient escalation through a senior developer**.
    
-   **Systematic Approach to Technical Problem Solving and Sequential Nature**: I experienced the sequential nature of technical problem-solving, where resolving one major issue often reveals the next hidden one. Through this process, I learned that **systematic information provision**—including **error log analysis, detailed replication steps, and screenshots**—is **key to reducing problem-solving time**. I also realized the importance of **persistence and creative problem-solving** in seeking various alternatives and finding optimal solutions under unexpected constraints.
    
-   **Importance of Flexible Planning and Time Management**: I learned that initial project plans can be significantly delayed by unforeseen technical challenges, such as `xhtml2pdf`'s CSS compatibility issues. This experience taught me the importance of **flexible schedule adjustments** and how **utilizing idle time** (e.g., waiting for server responses) to **concurrently research other tasks** (e.g., WordPress plugin research and security plan development) can be a crucial way to enhance project efficiency.

## 🔧 Technical Problem-Solving Experience

-   **Missing `lswsgi` Executable Issue for Flask App on cPanel**:
    
    -   **Problem**: After deploying the Flask app, accessing the website only displayed "Proudly Served by LiteSpeed Web Server...", indicating the Flask app wasn't running. The `stderr.log` showed the error `/opt/alt/python312/bin/lswsgi: No such file or directory`.
        
    -   **Resolution**: I diagnosed this as a server infrastructure issue beyond direct developer control. I provided detailed replication steps and error log screenshots to the senior developer, who then requested support from the hosting provider. The `lswsgi` executable for Python 3.12 was successfully installed, allowing the Flask app to run correctly.
        
-   **Playwright Installation Failure for PDF Report Generation and Alternative Solution**:
    
    -   **Problem**: After the `lswsgi` issue was resolved, the PDF report generation feature failed with a `Playwright Browser Binaries Missing` error. The hosting provider stated Playwright could not be installed on shared hosting and recommended a VPS.
        
    -   **Resolution**: Migrating to a VPS was deemed too complex and risky for now. I then attempted various PDF generation libraries like `WeasyPrint`, `ReportLab`, and `FPDF2`, but faced issues with environmental dependencies or excessive development complexity. Finally, I chose **`xhtml2pdf`**. I implemented a hybrid approach where charts generated with `matplotlib` were Base64-encoded and embedded into HTML `<img>` tags. The complete HTML was then converted to PDF by `xhtml2pdf`, successfully circumventing all previous server dependency issues and leveraging existing HTML designs.

## 💡 Reflections

-   **Gap Between Plan and Reality**: I keenly felt that initial project plans could be significantly delayed by unexpected server environment issues or library compatibility problems during actual development. This experience reinforced the importance of **flexible planning** that considers technical depth alongside realistic constraints.
    
-   **Importance and Method of Communication**: I directly experienced how crucial it is to provide clear replication steps and error logs to the hosting provider when server issues arise. I also learned that when reporting progress to team members, it's not enough to simply state the outcome; **specifically explaining what challenges were faced, what efforts were made, and what the next steps are** strengthens trust and collaboration.
    
-   **Growth Through Challenge**: Throughout this week, I continuously faced difficult technical problems. However, by resolving each issue, I gained a deeper understanding of server environments, library characteristics, and problem-solving strategies. This served as a significant opportunity to **enhance my capabilities and confidence as a developer**.

## 🌱 Points of Improvement & Next Week's Goals

-   **Areas for Improvement**:
    
    -   **`xhtml2pdf` CSS Compatibility Issues**: The PDF design rework is taking much longer than expected due to `xhtml2pdf`'s limited recognition of CSS elements, delaying the start of other tasks. It's regrettable that there was **insufficient in-depth pre-testing of the library's CSS rendering capabilities** during the initial library selection phase.
        
    -   **Lack of Early Problem Prediction**: I allocated time to research Playwright, not adequately predicting the impossibility of installing browser-based PDF generation libraries on a shared hosting environment.
        
-   **Next Week's Goals**:
    
    -   **Complete PDF Design Rework**: I will **prioritize and complete** the PDF report design rework using `xhtml2pdf` **by next week**. I will aim to implement the optimal design while resolving CSS compatibility issues.
        
    -   **Implement Flask App Access Control with WordPress Login Integration**: Following the security plan established today (HTTPS, secret key generation/verification, token issuance/verification), I will fully implement and test the Flask app access control feature integrated with WordPress login.
        
    -   **Begin WordPress Plugin Development**: I will start developing the MVP WordPress plugin to integrate dashboard functionalities with WordPress.

----------

# 📝 11주차 회고 (2025.07.21 ~ 07.25)

## ✅ 이번 주 주요 작업

**📌 Flask 대시보드 cPanel 서버 배포 및 운영 환경 문제 해결**: WSGI 실행 파일 부재 및 Playwright 설치 문제 등 공유 호스팅 환경의 다양한 제약을 극복하고 Flask 앱의 기본 구동 환경을 성공적으로 구축했습니다.   
**📌 PDF 보고서 자동 생성 기능 구현 성공**: 여러 라이브러리 시도 끝에 `xhtml2pdf`를 활용하여 HTML/CSS 기반의 PDF 보고서 자동 생성 기능을 최종 구현했습니다.   
**📌 워드프레스 연동 및 보안 강화 계획 수립**: Flask 앱과 워드프레스의 연동 전략을 구체화하고, 사용자 접근 제어를 위한 상세 보안 프로토콜 계획을 수립했습니다.  

## 🧠 배운 핵심 개념

-   **서버 환경 배포의 실질적 이해와 인프라의 중요성**: 로컬에서 개발한 Flask 앱을 실제 cPanel 환경에 배포하는 과정에서 파일/폴더 구조, Python App 설정 등 초기 문제들을 직접 해결했습니다. 특히, `lswsgi` 실행 파일 부재나 Playwright 설치 불가와 같은 **근본적인 서버 인프라 문제가 개발자 단독으로 해결하기 어렵다**는 것을 명확히 인지하게 되었습니다. 이는 개발 범위 밖의 문제에 대한 **외부 지원의 필요성**과 **선임을 통한 효율적인 에스컬레이션의 중요성**을 깨닫게 해주었습니다.
    
-   **기술 문제 해결의 체계적인 접근과 연쇄성**: 한 가지 문제가 해결되면 또 다른 숨겨진 문제가 드러나는 기술 문제 해결의 연쇄적인 특성을 경험했습니다. 이 과정에서 **에러 로그 분석, 상세한 재현 단계, 스크린샷 등 체계적인 정보 제공이 문제 해결 시간을 단축하는 데 핵심적**임을 배웠습니다. 또한, **예상치 못한 제약 속에서 다양한 대안을 모색하고 최적의 솔루션을 찾아내는 끈기와 창의적 문제 해결 능력**이 중요함을 실감했습니다.
    
-   **유연한 계획 조정 및 시간 관리**: `xhtml2pdf`의 CSS 호환성 문제처럼 예상치 못한 기술적 난관으로 인해 초기 계획이 지연될 수 있음을 경험했습니다. 이때 **유연하게 일정을 조정하고, 서버 응답 대기 시간과 같은 유휴 시간을 활용하여 다른 업무(예: 워드프레스 플러그인 리서치 및 보안 계획 수립)를 병렬적으로 진행하는 것이 프로젝트 효율성을 높이는 중요한 방법**임을 체득했습니다.

## 🔧 기술적 문제 해결 경험

-   **cPanel Flask 앱 `lswsgi` 실행 파일 부재 문제**:
    
    -   **문제**: Flask 앱 배포 후 웹사이트 접속 시 "Proudly Served by LiteSpeed Web Server..."만 표시되고 Flask 앱이 실행되지 않았습니다. `stderr.log`에서 `/opt/alt/python312/bin/lswsgi: No such file or directory` 오류가 확인되었습니다.
        
    -   **해결**: 이 문제가 개발자 단독 해결 불가능한 서버 인프라 문제임을 진단했습니다. 상세한 재현 단계와 에러 로그 스크린샷을 개발 선임께 전달하여 호스팅 제공업체에 지원을 요청했고, Python 3.12용 `lswsgi` 실행 파일이 성공적으로 설치되어 Flask 앱이 정상 구동되었습니다.
        
-   **PDF 보고서 생성 Playwright 설치 불가 및 대안 마련**:
    
    -   **문제**: `lswsgi` 문제 해결 후 PDF 보고서 생성 기능에서 `Playwright Browser Binaries Missing` 오류가 발생했습니다. 호스팅 제공업체는 공유 호스팅 환경에서 Playwright 설치가 불가하며 VPS 구매를 권장했습니다.
        
    -   **해결**: VPS 이전은 관리 복잡성으로 인해 보류되었고, `WeasyPrint`, `ReportLab`, `FPDF2` 등 다양한 PDF 생성 라이브러리를 시도했으나 환경 의존성이나 개발 복잡성 문제로 실패했습니다. 최종적으로 **`xhtml2pdf`**를 채택하여 `matplotlib`으로 생성한 차트를 Base64로 인코딩하여 HTML `<img>` 태그에 삽입하는 하이브리드 방식을 통해 HTML/CSS를 PDF로 변환하는 데 성공했습니다. 이로써 서버 의존성 문제를 완벽히 우회하고 기존 HTML 디자인을 활용할 수 있게 되었습니다.

## 💡 느낀 점

-   **계획과 현실 간의 간극**: 프로젝트 초기에 수립한 계획이 실제 개발 과정에서 예상치 못한 서버 환경 문제나 라이브러리 호환성 문제로 인해 크게 지연될 수 있음을 체감했습니다. 이는 기술적인 깊이와 함께 현실적인 제약을 고려한 **유연한 계획 수립**의 중요성을 다시 한번 상기시켜 주었습니다.
    
-   **소통의 중요성과 방식**: 서버 문제 발생 시 호스팅사에 명확한 재현 단계와 에러 로그를 제공하는 것이 얼마나 중요한지 직접 경험했습니다. 또한, 팀원에게 진행 상황을 보고할 때 단순히 결과만 말하는 것이 아니라, **어떤 문제에 직면했고, 어떤 노력을 했으며, 다음 단계는 무엇인지 구체적으로 설명**하는 것이 신뢰와 협업을 강화한다는 것을 느꼈습니다.
    
-   **도전이 곧 성장**: 이번 주 내내 해결하기 어려운 기술적 문제에 연속적으로 부딪혔지만, 각 문제를 해결해 나가는 과정에서 서버 환경, 라이브러리 특성, 문제 해결 전략 등에 대한 깊이 있는 이해를 얻을 수 있었습니다. 이는 **개발자로서의 역량과 자신감을 크게 향상시키는 계기**가 되었습니다.

## 🌱 아쉬운 점 및 다음 주 목표

-   **아쉬운 점**:
    
    -   **`xhtml2pdf` CSS 호환성 문제**: PDF 디자인 재작업 시 `xhtml2pdf`가 인식하지 못하는 CSS 요소들이 많아 예상보다 훨씬 많은 시간이 소요되고 있으며, 이로 인해 다른 작업 착수가 지연되었습니다. 초기 라이브러리 선택 단계에서 해당 라이브러리의 **CSS 렌더링 능력에 대한 심층적인 사전 테스트가 부족했던 점**이 아쉽습니다.
        
    -   **초기 문제 예측 부족**: 공유 호스팅 환경에서 Playwright와 같은 브라우저 기반 PDF 생성 라이브러리가 설치되지 않을 가능성을 사전에 충분히 예측하지 못하고 리서치에 시간을 할애했던 점.
        
-   **다음 주 목표**:
    
    -   **PDF 디자인 재작업 완료**: `xhtml2pdf`를 활용한 PDF 보고서 디자인 재작업을 **다음 주 내로 최우선적으로 완료**할 것입니다. CSS 호환성 문제를 해결하며 최적의 디자인을 구현하겠습니다.
        
    -   **워드프레스 로그인 연동 Flask 앱 접근 제어 구현**: 오늘 수립한 보안 계획(HTTPS, 비밀키 생성/검증, 토큰 발급/검증)에 따라 워드프레스 로그인 연동 Flask 앱 접근 제어 기능을 본격적으로 구현하고 테스트할 것입니다.
        
    -   **워드프레스 플러그인 개발 착수**: 대시보드 기능을 워드프레스에 연동하기 위한 MVP 워드프레스 플러그인 개발을 시작할 것입니다.
