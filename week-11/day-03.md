# 📅 Day 03 (2025-07-23, Tue)

## 🎓 What I Did Today

**📌 In the morning development meeting, I reported on the progress of the `lswsgi` file issue and, in response to the hosting provider's request, provided detailed replication steps and error logs to the senior developer.**   
**📌 The `lswsgi` issue was resolved with the hosting provider's assistance, coordinated by the senior developer, but a new error (`Playwright Browser Binaries Missing`) was discovered in the PDF generation feature.**  
**📌 I identified the necessary fix (running the `playwright install` command), detailed the steps, and requested the senior developer to contact the hosting provider again to resolve the issue.**  
**📌 While waiting for the server's response, I researched WordPress plugin development and established a plan to build an MVP with SEO, AI, and Korean-related features within a week.**   
**📌 I successfully delivered my morning presentation, receiving positive feedback along with key advice on ensuring accuracy in terminology and simulating comparisons under identical conditions.**  

### Detailed Activities

**1. Morning Development Meeting & `lswsgi` Issue Resolution:**

-   **Problem Status Report**: During a brief meeting with the senior developer, I shared the progress on the `lswsgi` executable file issue that was reported to the hosting provider yesterday.
    
-   **Responding to Hosting Provider**: I responded to the hosting provider's request, relayed by the senior developer, for "a screenshot of the error and the exact steps to replicate the issue." I compiled and sent the following detailed steps and error log information:
    
    -   **Replication Steps**:
        
        1.  Log in to cPanel for the domain `dashboard.your-domain.com`.
            
        2.  Navigate to `Software > Setup Python App`.
            
        3.  Click `Create Application`.
            
        4.  Configure with Python version 3.12, Application root: `/home/cpanel-user/public_html/dashboard.your-domain.com`, Application URL: `dashboard.your-domain.com`, and Application startup file: `passenger_wsgi.py`.
            
        5.  Visit `https://dashboard.your-domain.com` to see the "Service Unavailable" error.
            
    -   **Error Log Confirmation**: I confirmed that the `stderr.log` file repeatedly showed the error `/opt/alt/python312/bin/lswsgi: No such file or directory`. I attached a screenshot and the log file to confirm that this was a server configuration issue.
        
-   **`lswsgi` Resolution**: With the hosting provider's support, which was coordinated through the senior developer, the `lswsgi` executable for Python 3.12 was successfully installed, and the Flask app began running correctly.
    

**2. New Issue and Escalation:**

-   **PDF Generation Error Found**: After the `lswsgi` issue was fixed, I confirmed that the dashboard's data loading and AI summary functions were working properly. However, a new problem emerged: the PDF report generation feature was failing with a `Playwright Browser Binaries Missing` error.
    
-   **Issue Diagnosis**: By analyzing the error log, I determined that Playwright could not find the necessary browser executable for PDF generation.
    
-   **Resolution Request**: I identified that the `playwright install` command needed to be executed within the application's virtual environment to fix this. I communicated the detailed steps to the senior developer, requesting them to forward the request to the hosting provider.
    

**3. WordPress Plugin Development Planning:**

-   While waiting for the server provider's response, I used the time to research WordPress plugin development.
    
-   I formulated a concrete plan to develop an **MVP with SEO, AI, and Korean-related functionalities** within a week, to integrate dashboard features with WordPress.
    

**4. Shopify/Shopify Plus Presentation:**

-   **Presentation Completed**: I successfully delivered the Shopify & Shopify Plus presentation that was postponed from yesterday.
    
-   **Feedback and Learning**: I received positive feedback on the content. A key piece of advice was to ensure the accuracy of terminology when using templates to prevent misinformation.
    
-   **Expanding My Thinking**: I learned a new approach to comparing two subjects: it's beneficial to simulate their differences by assuming an identical environment, which helps strengthen logical analysis.
    
## 🧠 Key Concepts Learned

-   **Systematic Communication for Technical Issues**: I realized that when facing problems beyond my direct control, like server environment issues, providing a clear and systematic response to the support team is crucial. This includes **detailed replication steps, error logs, and screenshots** to help them understand the issue quickly and efficiently.
    
-   **The Sequential Nature of Troubleshooting**: I learned that resolving one major issue can often reveal the next hidden problem. This experience highlighted that troubleshooting is not always a linear process and requires preparation for subsequent obstacles.
    
-   **The Importance of Parallel Work**: I found that utilizing idle time while waiting for a response from the server provider to **conduct research and plan new development** is an effective way to maximize productivity and maintain project momentum.
    
## 💡 Practical Trial-and-Error and Tips

-   **Handling Hosting Support Requests**: A request for "replication steps and screenshots" is a standard part of technical inquiries. The key is to provide the simplest, clearest steps possible, as if for someone unfamiliar with the project. Always include the error log (`stderr.log`).
    
-   **Identifying New Dependency Issues**: A change in the server environment can expose new dependency problems. If an error log shows messages like `...not installed` or `...cannot find`, it's highly likely that a **related installation command, like `pip install` or `playwright install`, is missing.**
    
-   **Presentation Preparation Tip**: When using templates, don't just fill in the blanks. **Verify that the terminology is accurate** to avoid miscommunication. Practicing a mock simulation of your presentation beforehand can help you check the logical flow and accuracy of your message.

## 🔜 Next Steps

-   **Finalize PDF Generation Fix**: I will confirm with the senior developer that the hosting provider has executed the necessary command and will verify that the PDF generation feature is working correctly.
    
-   **Begin WordPress Plugin Development**: Following the MVP development plan, I will start building the WordPress plugin to integrate dashboard functionalities.
    
-   **Initiate Security Feature Implementation**: After the PDF issue is resolved and plugin development is underway, I will begin implementing security-related features for the Flask dashboard, such as login and user authentication.

----------

# 📅 3일차 (2025-07-23, 수)

## 🎓 오늘 한 일

**📌 오전 개발 미팅에서 `lswsgi` 파일 부재 문제 진행 상황을 보고하고, 호스팅 제공업체의 요청에 따라 상세한 재현 단계와 에러 로그를 정리해 개발 선임께 전달했습니다.**   
**📌 개발 선임을 통해 호스팅 제공업체의 지원으로 `lswsgi` 문제가 해결되었으나, PDF 생성 기능에서 새로운 오류(`Playwright Browser Binaries Missing`)가 발견되었습니다.**  
**📌 이 문제를 해결하기 위해 필요한 조치(`playwright install` 명령어 실행)를 상세히 정리해 개발 선임께 전달하고, 서버 제공자에게 재문의하도록 요청했습니다.**  
**📌 서버 응답을 기다리는 동안, SEO, AI, 그리고 한국 관련 기능을 포함하는 워드프레스 플러그인 MVP를 일주일 내에 개발하는 계획을 수립했습니다.**   
**📌 오전 발표를 성공적으로 마쳤으며, 긍정적인 피드백과 함께 발표 자료의 용어 정확성과 비교 대상의 동일 환경 가정에 대한 중요한 조언을 받았습니다.**  

### 상세 활동

**1. 오전 개발 미팅 및 `lswsgi` 문제 해결 과정:**

-   **문제 현황 보고**: 개발 선임과의 짧은 미팅에서 어제 호스팅 제공업체에 전달한 `lswsgi` 실행 파일 부재 문제에 대한 진행 상황을 공유했습니다.
    
-   **호스팅 제공업체 요청에 대한 대응**: 개발 선임이 전달한 호스팅 제공업체의 요청에 따라, 문제를 명확히 재현할 수 있는 상세한 단계와 에러 로그를 정리했습니다.
    
    -   **이슈 재현 단계**:
        
        1.  cPanel 로그인 (도메인: `dashboard.your-domain.com`)
            
        2.  `Software > Setup Python App`으로 이동
            
        3.  `Create Application` 클릭
            
        4.  Python 버전: 3.12, Application root: `/home/cpanel-user/public_html/dashboard.your-domain.com`, Application URL: `dashboard.your-domain.com`, Application startup file: `passenger_wsgi.py` 설정 후 `Create` 클릭
            
        5.  `https://dashboard.your-domain.com` 접속 시 "Service Unavailable" 에러 발생
            
    -   **에러 로그 확인**: `stderr.log` 파일에서 `/opt/alt/python312/bin/lswsgi: No such file or directory` 에러가 반복적으로 발생하는 것을 확인하고 스크린샷 및 로그 파일을 첨부하여 개발 선임께 전달했습니다. 이 에러가 서버 구성 문제임을 명확히 밝혔습니다.
        
-   **`lswsgi` 문제 해결**: 개발 선임을 통한 호스팅 제공업체의 지원으로 Python 3.12용 `lswsgi` 실행 파일이 성공적으로 설치되었고, Flask 앱이 정상적으로 구동되기 시작했습니다.
    

**2. 새로운 문제 발생 및 해결 요청:**

-   **PDF 생성 기능 오류 발견**: `lswsgi` 문제가 해결된 후, 대시보드의 데이터 로딩 및 AI 요약 기능은 정상 작동하는 것을 확인했습니다. 그러나 PDF 보고서 생성 기능에서 `Playwright Browser Binaries Missing` 오류가 발생하는 새로운 문제가 드러났습니다.
    
-   **문제 진단**: 에러 로그를 분석하여 Playwright가 PDF 생성을 위한 브라우저 실행 파일을 찾지 못하는 것을 확인했습니다.
    
-   **해결 요청**: 이 문제를 해결하기 위해 애플리케이션 가상 환경에서 `playwright install` 명령어를 실행해야 함을 파악하고, 필요한 조치를 상세히 정리해 개발 선임께 전달했습니다. 개발 선임은 이를 서버 제공자에게 재문의하겠다고 답변했습니다.
    

**3. 워드프레스 플러그인 개발 계획 수립:**

-   서버 제공자의 답변을 기다리는 동안, 워드프레스 플러그인 개발에 대한 리서치를 진행했습니다.
    
-   **SEO, AI, 그리고 한국어 관련 기능을 포함하는 MVP**를 일주일 내로 개발하여 대시보드 기능을 워드프레스와 연동하는 구체적인 계획을 세웠습니다.
    

**4. Shopify/Shopify Plus 발표 진행:**

-   **발표 완료**: 오전에 어제 미뤄졌던 Shopify & Shopify Plus 발표를 성공적으로 마쳤습니다.
    
-   **피드백 및 배운 점**: 발표 내용에 대해 전반적으로 긍정적인 피드백을 받았습니다. 특히 발표 템플릿의 용어를 정확히 확인하여 정보 전달 오류를 방지해야 한다는 중요한 조언을 받았습니다.
    
-   **사고 확장**: 두 비교 대상을 논의할 때, 동일한 환경을 가정하고 어떤 차이가 있는지 시뮬레이션해 보는 관점에서 접근하는 것이 좋겠다는 새로운 사고방식을 배웠습니다.
    
## 🧠 배운 핵심 개념

-   **기술 문제 해결을 위한 체계적인 소통**: 서버 환경과 같이 개발자가 직접 제어하기 어려운 문제에 직면했을 때, 상대방이 문제를 명확히 이해할 수 있도록 **구체적인 재현 단계, 에러 로그, 스크린샷 등을 제공하는 것**이 문제 해결 시간을 단축하는 가장 효과적인 방법임을 실감했습니다.
    
-   **문제 해결의 연쇄성**: 한 가지 큰 문제가 해결되면 다음 단계의 숨겨진 문제(예: `lswsgi` 해결 후 `Playwright` 오류)가 드러날 수 있음을 경험했습니다.
    
-   **시간 활용 및 병렬 작업의 중요성**: 서버 응답을 기다리는 유휴 시간을 활용하여 **사전 리서치 및 새로운 개발 계획을 수립**하는 것이 업무 효율성을 극대화하는 좋은 방법임을 깨달았습니다.
    
## 💡 실전 시행착오 및 팁

-   **호스팅 지원팀 응대 요령**: "재현 단계와 스크린샷을 달라"는 요청은 기술 문의의 일반적인 절차입니다. 당황하지 않고, 마치 처음 보는 사람이 따라 할 수 있도록 **가장 단순하고 명확한 단계**를 제공하는 것이 핵심입니다. 에러 로그(`stderr.log`)는 반드시 함께 첨부해야 합니다.
    
-   **새로운 의존성 문제 파악**: 서버 환경이 바뀌면 새로운 라이브러리나 모듈의 의존성 문제가 드러날 수 있습니다. 에러 로그에 `...not installed` 또는 `...cannot find` 같은 메시지가 나타나면, 대부분 `pip install` 또는 `playwright install`과 같은 **설치 관련 명령어가 누락되었을 가능성이 높습니다.**
    
-   **발표 준비 팁**: 템플릿 사용 시, 단순히 내용만 채우지 않고 **각 용어가 의도하는 바를 정확히 파악**해야 합니다. 발표 전 모의 시뮬레이션을 통해 전달할 내용의 논리적 흐름과 정확성을 점검하는 것이 중요합니다.
    
## 🔜 다음 학습 방향

-   **PDF 생성 기능 최종 해결**: 개발 선임을 통해 `playwright install` 명령어 실행이 완료되었는지 확인하고, PDF 생성 기능이 정상 작동하는지 최종적으로 검증할 것입니다.
    
-   **워드프레스 플러그인 개발 착수**: MVP 개발 계획에 따라 워드프레스 플러그인 개발을 시작하여 대시보드 기능을 워드프레스에 연동하는 작업을 진행할 것입니다.
    
-   **보안 기능 구현 착수**: PDF 문제 해결 및 플러그인 개발 진척도를 보며, 초기 계획대로 Flask 대시보드의 로그인 및 사용자 인증 등 보안 관련 기능 구현을 시작할 것입니다.
