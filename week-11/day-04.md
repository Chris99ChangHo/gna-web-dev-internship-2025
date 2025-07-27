# 📅 Day 04 (2025-07-24, Thu)

## 🎓 What I Did Today

**📌 Participated in a morning development meeting to discuss the PDF generation feature's blocker due to Playwright installation issues, exploring alternatives based on the hosting provider's response.** **📌 Successfully implemented PDF generation using the `xhtml2pdf` library after various attempts with other libraries, addressing previously encountered problems.** **📌 Began implementing PDF preview and download functionalities with `xhtml2pdf`, noting several improvements but requiring further work.**

### Detailed Activities

**1. Morning Development Meeting Summary:**

-   **Discussion Topic**: Finding an alternative for the PDF report generation feature due to `Playwright` installation issues.
    
-   **Hosting Provider's Response**: The senior developer shared the official response from the hosting provider regarding the `Playwright` installation request.
    
    -   **Summary of Response**:
        
        -   `Playwright` cannot be installed on the current shared hosting environment.
            
        -   Reasons cited include potential server instability if issues arise during installation and the inability to receive vendor support if problems occur on the server due to unauthorized installations.
            
        -   They recommended purchasing and configuring a separate **VPS (Virtual Private Server)**.
            
-   **Team Decision & Alternative Discussion**:
    
    -   The senior developer decided against migrating to a VPS at this time, considering the management complexity and risks.
        
    -   I proposed **WeasyPrint** as an alternative library, and the senior developer accepted this suggestion.
        
-   **Conclusion & Next Steps**: The decision was made to proceed with implementing PDF generation using WeasyPrint and to provide updates on its progress.

### **2. PDF Report Automation Project Progress Report**

Although we agreed to try WeasyPrint after yesterday's (July 23rd) meeting, I encountered difficulties with its environmental dependencies during subsequent work. This led to the evaluation of additional alternatives.

#### **Technical Attempts and Failure Analysis (The Journey)**

I explored **five different technical approaches** for automatic PDF report generation. Each attempt was aimed at overcoming the failure points of the previous method, which proved crucial in finding the final solution.

| Stage | Library | Reason for Attempt (Expectation) | Cause of Failure & Analysis |
| :--- | :--- | :--- | :--- |
| **1st Attempt (Discussed in yesterday's meeting)** | Playwright | Expected to perfectly replicate web pages (HTML) into PDF. Optimized for JavaScript-based dynamic chart rendering. | **Server Dependency Issue**. No terminal permissions to install browser executables (e.g., Chromium) via `playwright install` on shared hosting. Hosting provider refused installation due to server stability. |
| **2nd Attempt (Agreed in today's meeting)** | WeasyPrint | Lighter than Playwright, with excellent HTML/CSS to PDF conversion capabilities. | **External Program Dependency Issue**. Requires system libraries like `GTK+` (essential for Windows/Linux environments). Installation was uncertain due to server environment constraints. |
| **3rd Attempt** | ReportLab | A 100% pure Python library with no external dependencies. | **Excessive Development Complexity**. Required abandoning existing HTML designs and drawing all text, tables, and images directly using Python code, which was inefficient and hard to maintain. |
| **4th Attempt** | FPDF2 | Similar to ReportLab, a pure Python library, but with simpler usage. | **Limitations of the Approach**. Like ReportLab, it couldn't leverage HTML templates, leading to fundamental inefficiency. Difficult to handle automatic line breaks or complex table layouts, keeping code complexity high. |
| **5th Attempt (Final Success)** | **xhtml2pdf** | A **pure Python** library (no server dependencies) that also allows direct use of **HTML/CSS**, satisfying both key requirements. | **Success**. Implemented a hybrid approach: charts generated with `matplotlib`, Base64-encoded, and embedded into HTML `<img>` tags. The complete HTML was then converted to PDF by `xhtml2pdf`, perfectly circumventing all previous failure points. |

### **3. Key Improvements After Adopting `xhtml2pdf`**

By finalizing the technology with `xhtml2pdf` and implementing the PDF report feature, I successfully addressed previously encountered issues and achieved the following significant improvements:

-   **HTML Design Preservation**: We can now **perfectly reproduce our meticulously crafted HTML and CSS templates**, generating PDFs with a **100% identical, pixel-perfect design** as seen on the web, free from broken layouts or ignored styles.
    
-   **Dynamic Data Handling (Titles, Clients, Dates)**: The existing method of populating HTML with data using `render_template` was retained, ensuring that all dynamic data is accurately reflected in the PDF.
    
-   **JavaScript Logic Migration to Python**: Logic previously handled by JavaScript (e.g., for "Change" values) was successfully migrated to **Python code within `app.py`**, resulting in more stable and efficient data processing.
    
-   **Optimized Development Environment**: This approach successfully bypassed all prior server constraints on the cPanel shared hosting environment, allowing for stable operation of the PDF generation feature.

### **4. Next Steps**

I will continue working on resolving additional issues encountered during the implementation of PDF preview and download functionalities tomorrow (July 25, 2025).

## 🧠 Key Concepts Learned

-   **Deep Technical Constraint Analysis**: I learned to methodically diagnose and document the specific reasons for technical failures. This process was crucial for identifying the root cause of the problem (server-side dependencies) and systematically finding a viable alternative.
    
-   **Persistence and Creative Problem-Solving**: The experience of trying five different libraries highlighted the importance of persistence in the face of blockers. The final successful solution was a hybrid approach, demonstrating that combining different tools can be the key to overcoming seemingly unresolvable issues.
    
-   **Optimizing for the Environment**: I learned that a server's limitations must be considered from the very beginning of the technical design. The most powerful tool isn't always the best fit if it's incompatible with the deployment environment.

## 💡 Practical Trial-and-Error and Tips

-   **Prioritize Pure Python Libraries on Shared Hosting**: If you need to perform a task that relies on external binaries (like headless browsers for PDF generation), always consider a pure Python alternative first. It will save you from dependency-related headaches and unresolvable server-side limitations.
    
-   **Don't Be Afraid to Pivot**: Sticking with a single, non-functional solution is a waste of time. My journey from Playwright to `xhtml2pdf` shows that quickly pivoting to a new approach after a failure analysis can lead to a breakthrough.
    
-   **Leverage Existing Assets**: The `xhtml2pdf` solution's success hinged on its ability to leverage our pre-existing HTML and CSS templates. This saved a significant amount of time and effort compared to recreating everything from scratch.

## 🔜 Next Steps

-   **Finalize PDF Functionality**: Complete the implementation of the PDF preview and download features using `xhtml2pdf`.
    
-   **Begin Security Protocol Implementation**: Start implementing security protocols for the Flask dashboard, beginning with user authentication and login functionality.
    
-   **Finalize WordPress Integration Plan**: With the core functionality now stable, I will finalize the plan for integrating the Flask dashboard with the WordPress site.

# 📅 3일차 (2025-07-24, 목)

## 🎓 오늘 한 일

**📌 오전 개발 미팅에서 PDF 생성 기능의 주요 걸림돌에 대해 개발 선임과 논의했습니다.**   
**📌 다른 라이브러리 시도들이 실패한 후, `xhtml2pdf` 라이브러리를 성공적으로 사용하여 PDF 생성에 대한 실행 가능한 해결책을 찾았습니다.**   
**📌 호스팅 제한으로 인한 Playwright의 초기 실패부터 `xhtml2pdf`를 통한 최종 성공적인 구현까지, 전체 문제 해결 과정을 상세히 기록했습니다.**   
**📌 `xhtml2pdf`를 사용한 PDF 미리보기 및 다운로드 기능 구현을 시작했으며, 몇 가지 개선점을 확인했으나 내일을 위한 추가 작업이 필요합니다.**  
 
### 상세 활동

**1. 오전 개발 미팅 요약:**

-   **논의 주제**: Playwright 설치 불가에 따른 PDF 보고서 생성 기능 구현 대안 마련.
    
-   **서버 제공업체 답변 공유**: 개발 선임으로부터 Playwright 설치 요청에 대한 서버 제공업체의 공식 답변을 전달받았습니다.
    
    -   **답변 요지**:
        
        -   현재 공유 호스팅 환경에서는 Playwright 설치가 불가능함.
            
        -   이는 설치 시 서버 안정성 문제 발생 가능성 및 문제 발생 시 상위 벤더의 기술 지원을 받을 수 없다는 점 때문임.
            
        -   별도의 **VPS(가상 사설 서버)**를 구매하여 직접 구성할 것을 권장함.
            
-   **팀 결정 및 대안 논의**:
    
    -   개발 선임은 VPS로의 이전은 현재로서는 관리 복잡성 및 위험 부담을 고려하여 채택하지 않기로 결정했습니다.
        
    -   이에 대한 대안으로 제가 **WeasyPrint** 라이브러리를 제안했으며, 개발 선임이 이를 수용했습니다.
        
-   **결론 및 다음 단계**: WeasyPrint를 활용하여 PDF 생성 기능을 구현하고, 진행 상황을 업데이트하기로 결정했습니다.

### **2. PDF 보고서 자동 생성 프로젝트 진행 보고**

어제(7월 23일) 미팅 후 WeasyPrint로 시도하기로 했으나, 이후 작업 과정에서 WeasyPrint 역시 환경 문제로 어려움을 겪어 다른 대안들을 추가적으로 검토했습니다.

#### **기술적 시도 및 실패 분석 (여정)**

PDF 보고서 자동 생성을 위해 **총 5가지**의 다른 기술적 접근법을 시도했습니다. 각 시도는 이전 방식의 실패 원인을 극복하기 위해 진행되었으며, 이 과정은 최종 해결책을 찾는 중요한 밑거름이 되었습니다.

| 단계 | 라이브러리 | 시도 이유 (기대) | 실패 원인 및 분석 |
| :--- | :--- | :--- | :--- |
| **1차 시도 (어제 미팅 내용)** | Playwright | 웹 페이지(HTML)를 가장 완벽하게 PDF로 복제. JS 기반 동적 차트 렌더링에 최적. | **서버 의존성 문제**. 공유 호스팅 환경에서 `playwright install` 명령어로 브라우저 실행 파일 설치 불가. 호스팅 업체가 서버 안정성을 이유로 설치 거부. |
| **2차 시도 (오늘 미팅에서 합의)** | WeasyPrint | Playwright보다 가볍고, HTML/CSS를 PDF로 변환하는 능력 우수. | **외부 프로그램 의존성 문제**. 윈도우/리눅스 환경에서 GTK+ 같은 시스템 라이브러리 설치 필수. 서버 환경 제약으로 설치 불확실. |
| **3차 시도** | ReportLab | 외부 의존성이 전혀 없는 100% 순수 파이썬 라이브러리. | **과도한 개발 복잡성**. HTML 설계를 버리고 모든 요소를 파이썬 코드로 직접 그려야 함. 유지보수 매우 어려움. |
| **4차 시도** | FPDF2 | ReportLab과 같이 순수 파이썬 라이브러리. 사용법이 더 간단하다는 장점. | **개발 방식의 한계**. HTML 템플릿 활용 불가. 자동 줄바꿈이나 복잡한 표 레이아웃 처리가 어려워 코드 복잡성 여전함. |
| **5차 시도 (최종 성공)** | **xhtml2pdf** | **순수 파이썬** 라이브러리(서버 의존성 없음)이면서, **HTML/CSS를 그대로 사용**할 수 있다는 두 가지 핵심 장점을 모두 만족. | **성공**. matplotlib으로 차트를 생성하고 Base64로 인코딩하여 HTML `<img>` 태그에 삽입. 완성된 HTML을 `xhtml2pdf`로 통째로 PDF 변환하여 이전 모든 실패 원인 회피. |

### **3. `xhtml2pdf` 적용 후 주요 개선점**

`xhtml2pdf` 라이브러리를 통해 PDF 보고서 기능을 구현한 결과, 기존에 겪었던 문제들을 해결하고 다음과 같은 주요 개선점을 달성했습니다.

-   **디자인 원점 회귀 문제 해결**: 우리가 공들여 만든 HTML 및 CSS 템플릿을 그대로 사용하여 디자인을 완벽하게 재현할 수 있게 되었습니다. 웹에서 보던 것과 **100% 동일한, 픽셀 단위까지 완벽한 디자인의 PDF**가 생성됩니다.
    
-   **데이터 문제 해결 (제목, 고객사, 날짜)**: `render_template`을 사용하여 HTML에 모든 데이터를 채워 넣는 기존 방식을 그대로 유지했습니다. 완성된 HTML 문자열을 처리하여 동적 데이터가 정확하게 PDF에 반영됩니다.
    
-   **Change 값 문제 해결 (JS 로직을 Python으로 이동)**: 이전에 JavaScript로 처리하던 `Change` 값 계산 로직을 더 안정적인 **파이썬 코드(`app.py` 내)**로 옮겨와 데이터 처리의 안정성과 효율성을 높였습니다.
    
-   **개발 환경 최적화**: 모든 실패 원인을 회피하는 방식으로, cPanel 공유 호스팅 서버의 제약을 극복하고 PDF 생성 기능을 안정적으로 구동할 수 있게 되었습니다.

### **4. 다음 단계**

PDF 미리보기 및 다운로드 기능 구현 과정에서 발생한 추가적인 문제들을 해결하는 작업을 내일(2025-07-25) 이어서 진행할 예정입니다.

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
