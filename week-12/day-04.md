# 📅 Day 04 (2025-07-31, Thu)

## 🎓 What I Did Today

**📌 I shared updates on the JWT authentication system implementation and its current status during the morning development meeting, also receiving a new requirement for dynamically changing PDF cover images.**   
**📌 I thoroughly stabilized the JWT authentication system by resolving key bugs, including the CSRF token issue, and refining the token generation logic.**   
**📌 I analyzed and planned solutions for server resource issues in the cPanel deployment environment, and implemented optimization strategies for multi-language fonts and CSS in `xhtml2pdf`.**  

### Detailed Activities

Today's development work focused on a morning meeting, stabilizing the JWT authentication system, optimizing the cPanel deployment environment, and enhancing the PDF generation system.

**1. Development Meeting & New Requirements**

-   **Status Report**:
    
    -   **JWT Authentication System Implemented:** I reported the successful transition from Flask sessions to a JWT token-based security approach.
        
    -   **CSRF Token Issue Resolved:** I confirmed that the 'CSRF double submit tokens do not match' error and the `getCsrfToken()` function's token mix-up issue from yesterday (July 30) were completely resolved.
        
    -   **System Stabilization:** I verified that all core dashboard functionalities, including JWT authentication, CSRF protection, and PDF generation, are now operating correctly.
        
-   **Senior Developer Feedback**:
    
    -   The implemented **JWT approach was approved**, and it was confirmed that the system is ready for testing.
        
    -   I was asked to continue incorporating previous feedback on **AI summarization and PDF output text content improvements**.
        
    -   A **new requirement for a dynamic PDF cover image system** was introduced (using WordPress-sourced images as backgrounds instead of CSS colors, with existing content overlaid).
        
    -   With no immediate new tasks, I was instructed to continue modifying and improving the report dashboard project.
        

**2. Full Stabilization of JWT Authentication System 🔐**

-   **A. Complete Resolution of CSRF Token Issue**
    
    -   **Core Problem:** The `JWT_COOKIE_HTTPONLY = True` setting caused the `csrf_access_token` cookie to also become HttpOnly, preventing JavaScript access. This led to `getCsrfToken()` returning `null` and "Missing CSRF token" errors from the server.
        
    -   **Perfect Solution:** By setting `app.config["JWT_CSRF_COOKIE_HTTPONLY"] = False`, I allowed JavaScript access to the CSRF token while keeping the Access Token HttpOnly, establishing a **dual-layer security system** against XSS and CSRF attacks.
        
    -   **Result:** Verified successful implementation by observing `[CSRF DEBUG] Found CSRF token:` messages.
        
-   **B. Token Generation Bug Fix**
    
    -   **Root Cause Discovered:** A bug was found where the 'type' attribute of a Refresh Token was copied when generating a new Access Token, leading to an "Only non-refresh tokens are allowed" error and an infinite 401 error loop.
        
    -   **Solution:** I filtered **JWT reserved claims (`RESERVED_CLAIMS = {"sub", "exp", "iat", "nbf", "jti", "aud", "iss", "type"}`)** to prevent the 'type' attribute of the Refresh Token from being copied to the new Access Token.
        

**3. cPanel Environment Optimization 🖥️**

-   **A. Server Resource Issue Analysis & Solution Planning (Testing Scheduled for Tomorrow)**
    
    -   **Problem Discovered:** Repeated process killing (`Child process was killed by signal: 15`) occurred on cPanel.
        
    -   **Root Cause Analysis:** Overuse of server resources during Google Analytics OAuth authentication, excessive data requests from WordPress API (`per_page=100`), and memory overuse due to debug mode being active in the production environment were identified as primary causes.
        
    -   **Solution Plan:** I've implemented code to activate debug mode only in the development environment, reduced WordPress API `per_page` to 10 and `timeout` to 5 seconds, and adjusted logging levels to `WARNING`. This will be tested tomorrow.
        
-   **B. GA4 Authentication Strategy Improvement Plan (Not Yet Implemented)**
    
    -   **Proposed Solution:** The strategy involves performing OAuth authentication locally to generate a light `credentials.json` file, then uploading only this file to the server to minimize server resource burden.
        

**4. PDF Generation System Enhancements 📄**

-   **A. `xhtml2pdf` Optimization Implementation (Improved Version Not Yet Tested)**
    
    -   **Problems Discovered:** During PDF generation, issues like 'Arial' font not found, incorrect percentage sizing (`100%`) in CSS, and CSS syntax errors were encountered with `xhtml2pdf`.
        
    -   **Solution Implemented:** I added an HTML pre-processing function to `pdf_generator.py` to convert percentage sizes to fixed dimensions (e.g., A3 landscape), replace 'Arial' with `xhtml2pdf`-compatible fonts (`"DejaVu Sans", "Liberation Sans", sans-serif`), and automatically correct CSS syntax errors. This is yet to be tested.
        
-   **B. Dynamic Cover Image System Design**
    
    -   **WordPress Integration Concept:** The plan is to utilize the Enhanced Media Library plugin in WordPress to randomly fetch cover images from a "PDF Report Covers" category.
        

**5. Initialization Timing Issue Resolution ⚡**

-   **Problem:** API calls failed on the first access but succeeded after a refresh.
    
-   **Root Cause:** This was due to a timing difference between when the server issued the `Set-Cookie` header and the browser processed it for JavaScript access, and when `main.js` made its initial API call.
    
-   **Solution Strategy:** I added a `waitForJWTCookie()` function to `main.js`. This JavaScript logic waits for the JWT cookie to be fully loaded in the browser before proceeding with initial API calls, ensuring stability.


## 🧠 Key Concepts Learned

-   **Deeper Understanding of JWT-based Authentication System**: I gained a clear understanding of practical applications of `HttpOnly`, `SameSite=Strict`, `Secure` cookie options, and the mechanism of controlling JavaScript access to CSRF tokens via `JWT_CSRF_COOKIE_HTTPONLY` settings. This experience solidified the importance of **building a dual-layer security system** to defend against both XSS and CSRF attacks.
    
-   **Debugging Strategies in Complex Server Environments**: I learned to analyze the root causes of unpredictable server resource issues (like `Child process was killed`) in constrained shared hosting environments like cPanel. This involved multi-faceted analysis (e.g., Google Analytics OAuth, WordPress API calls, Debug Mode activation) and **developing the ability to devise solutions through environment variable and code optimization**.
    
-   **Importance of Font Management for Multi-Language PDF Generation**: I recognized the multi-language text corruption issue in PDF generation from libraries like `xhtml2pdf` due to the **lack of automatic font substitution in server environments**. This highlighted the necessity of **directly including and explicitly specifying integrated fonts (like Noto Sans)** for comprehensive language support.


## 💡 Practical Trial-and-Error and Tips

-   **Subtle Differences in `Flask-JWT-Extended` CSRF Protection Settings**: I initially faced CSRF token access issues by confusing `JWT_COOKIE_HTTPONLY` and `JWT_CSRF_COOKIE_HTTPONLY`. The key is to **keep Access Tokens HttpOnly for XSS protection, but explicitly set `JWT_CSRF_COOKIE_HTTPONLY = False` to allow JavaScript access for CSRF tokens**.
    
-   **Necessity of `Flask-JWT-Extended` Token Claim Filtering**: Generating new Access Tokens from Refresh Tokens sometimes copied the `type` claim, leading to an "Only non-refresh tokens are allowed" error. It's crucial to **filter out unnecessary JWT reserved claims (`RESERVED_CLAIMS`) from being included in reissued tokens**.
    
-   **Environment-Independent `xhtml2pdf` Optimization**: PDF generation often encounters issues with `width: 100%` CSS percentages or font rendering. To ensure stable PDF generation regardless of the environment, it's vital to **preprocess HTML to convert percentages to fixed units (e.g., `mm`) and explicitly specify multi-language supporting fonts (e.g., Noto Sans)**.
    
-   **Resolving Client-Server Initialization Timing Issues**: Initial API call failures on first access often stem from the time lag between the server issuing cookies and the browser fully processing them for JavaScript access. Implementing a **JavaScript logic (e.g., `waitForJWTCookie`) that waits for necessary cookies to load by checking `document.cookie`** can significantly improve the stability of initial API calls.


## 🔜 Next Steps

-   **Complete PDF Multi-Language Font Support System**: I will upload the planned Noto Sans font files to the server and modify `pdf_generator.py` to **ensure multi-language (including Korean and Chinese) text is displayed correctly and without corruption in generated PDFs**.
    
-   **Test cPanel Server Resource Optimization Results**: I will thoroughly test and verify whether the changes applied today (debug mode, WordPress API call settings, logging level adjustments) **effectively reduce server resource usage and resolve process killing issues in the cPanel environment**.
    
-   **Begin Dynamic PDF Cover Image System Development**: Following the senior developer's feedback, I will start implementing the **dynamic cover image system** that fetches images from WordPress to use as PDF cover backgrounds, replacing the current CSS background color method.
    
-   **Incorporate AI Summary & PDF Text Content Feedback**: I will specifically review and implement the previously received feedback for improving the AI summarization feature and the quality of text content within generated PDFs.
    
-   **Final Integrated Testing of Flask App and WP**: Once all feature implementations are complete, I will conduct comprehensive integrated testing of the WP login integration and all Flask app functionalities to ensure final stability.

----------

# 📅 4일차 (2025-07-31, 목)

## 🎓 오늘 한 일

**📌 오전 개발 미팅에서 JWT 인증 시스템 구현 완료 및 현황을 공유하고, PDF 커버 이미지 동적 변경 시스템 구축에 대한 새로운 요구사항을 전달받았습니다.**   
**📌 JWT 인증 시스템의 CSRF 토큰 문제를 포함한 주요 버그를 해결하고, 토큰 생성 로직을 개선하여 시스템을 완벽하게 안정화했습니다.**   
**📌 cPanel 배포 환경에서의 서버 리소스 문제 분석 및 해결 방안을 모색했으며, `xhtml2pdf`의 다국어 폰트 및 CSS 최적화 방안을 구현했습니다.**  

### 상세 활동

오늘 하루 동안 진행된 개발 미팅 내용과 JWT 인증 시스템 문제 해결, cPanel 배포 환경 최적화, 그리고 PDF 생성 시스템 개선 과정을 중요한 이슈 중심으로 상세히 정리했습니다.

**1. 개발 미팅 내용 공유 및 새로운 요구사항 확인**

-   **보고 사항**:
    
    -   **JWT 인증 시스템 구현 완료:** 기존 Flask 세션 방식에서 JWT 토큰 기반으로 보안 접근법을 성공적으로 전환했음을 보고했습니다.
        
    -   **CSRF 토큰 문제 해결:** 어제(7월 30일) 발생했던 'CSRF double submit tokens do not match' 문제와 `getCsrfToken()` 함수 토큰 혼용 문제를 완전히 해결했음을 밝혔습니다.
        
    -   **시스템 안정화:** 현재 JWT 인증, CSRF 보호, PDF 생성 등 대시보드의 모든 핵심 기능이 정상적으로 작동하고 있음을 확인했습니다.
        
-   **개발 선임 피드백**:
    
    -   현재 구현된 **JWT 방식의 방향성이 승인**되었고, 테스트 진행이 가능한 상태임을 확인받았습니다.
        
    -   **AI 요약 및 PDF 결과물 텍스트 콘텐츠 개선**에 대한 기존 피드백들을 계속 반영해달라는 요청을 받았습니다.
        
    -   **새로운 요구사항:** **PDF 커버 이미지 동적 변경 시스템** 구축에 대한 피드백을 받았습니다. (CSS 배경색 대신 WordPress에서 가져온 이미지를 배경으로 사용하고, 그 위에 기존 콘텐츠를 오버레이하는 방식).
        
    -   현재는 추가로 맡길 업무가 없으므로, 리포트 대시보드 프로젝트의 수정 및 개선 작업을 계속 진행해달라는 지시를 받았습니다.
        

**2. JWT 인증 시스템 완전 안정화 🔐**

-   **A. CSRF 토큰 문제 완전 해결**
    
    -   **문제의 핵심:** `JWT_COOKIE_HTTPONLY = True` 설정으로 인해 `csrf_access_token` 쿠키도 HttpOnly가 되어 JavaScript 접근이 불가능했던 문제가 있었습니다. 이로 인해 `getCsrfToken()` 함수가 `null`을 반환하고 서버에서 "Missing CSRF token" 에러가 발생했습니다.
        
    -   **완벽한 해결책:** `app.config["JWT_CSRF_COOKIE_HTTPONLY"] = False`로 설정하여 CSRF 토큰은 JavaScript 접근을 허용하고, Access Token은 HttpOnly로 유지하여 XSS 공격을 방어하는 **이중 보안 시스템을 구축**했습니다.
        
    -   **결과:** `[CSRF DEBUG] Found CSRF token:` 메시지 확인으로 완벽한 성공을 검증했습니다.
        
-   **B. 토큰 생성 버그 수정**
    
    -   **발견된 근본적 문제:** 서버에서 Refresh Token으로 새 Access Token을 생성할 때, Refresh Token의 'type' 속성까지 복사되는 버그가 발견되어 "Only non-refresh tokens are allowed" 에러가 발생하고 무한 401 에러 루프가 발생했습니다.
        
    -   **해결책:** JWT 예약 클레임(`RESERVED_CLAIMS = {"sub", "exp", "iat", "nbf", "jti", "aud", "iss", "type"}`)을 필터링하여 Refresh Token의 'type' 속성이 새 Access Token에 복사되지 않도록 수정했습니다.
        

**3. cPanel 환경 최적화 🖥️**

-   **A. 서버 리소스 문제 분석 및 해결 방안 모색 (내일 테스팅 예정)**
    
    -   **발견된 문제:** cPanel에서 프로세스 킬링(`Child process was killed by signal: 15`)이 반복적으로 발생했습니다.
        
    -   **원인 분석:** Google Analytics OAuth 인증 과정의 과도한 리소스 소모, WordPress API의 과도한 데이터 요청(`per_page=100`), 그리고 운영 환경에서 디버그 모드 활성화로 인한 메모리 과사용이 주 원인이었습니다.
        
    -   **해결 방안:** 디버그 모드를 개발 환경에서만 활성화하고, WordPress API `per_page` 값을 10으로, `timeout`을 5초로 단축, 로깅 레벨을 `WARNING`으로 조정하는 코드를 구현했으며, 이 부분은 내일 테스트할 예정입니다.
        
-   **B. GA4 인증 전략 개선 구상 (아직 반영 전)**
    
    -   **제안된 해결책:** 로컬에서 OAuth 인증을 수행하여 가벼운 `credentials.json` 파일만 서버에 업로드함으로써 서버 리소스 부담을 최소화하는 전략을 구상했습니다.
        

**4. PDF 생성 시스템 개선 📄**

-   **A. xhtml2pdf 최적화 구현 (개선 버전 아직 테스팅 전)**
    
    -   **발견된 문제들:** PDF 생성 시 'Arial' 폰트 미지원, `100%` 같은 백분율 크기 오류, CSS 구문 오류 등 `xhtml2pdf` 관련 문제들이 있었습니다.
        
    -   **해결책 구현:** `pdf_generator.py`에 HTML 전처리 함수를 추가하여 백분율 크기를 고정 크기(A3 가로 기준)로 변경하고, `Arial` 폰트를 `xhtml2pdf` 호환 폰트(`"DejaVu Sans", "Liberation Sans", sans-serif`)로 대체하며, CSS 구문 오류를 자동 수정하도록 구현했습니다. 이 부분은 아직 테스트 전입니다.
        
-   **B. 동적 커버 이미지 시스템 설계**
    
    -   **WordPress 연동 시스템 구상:** Enhanced Media Library 플러그인을 활용하여 WordPress의 "PDF Report Covers" 카테고리에서 랜덤으로 커버 이미지를 가져오는 시스템을 구상했습니다.
        

**5. 초기화 타이밍 문제 해결 ⚡**

-   **문제 상황:** 첫 접속 시 API 호출이 실패하고 새로고침 후에는 성공하는 현상이 있었습니다.
    
-   **근본 원인:** 서버에서 `Set-Cookie` 헤더를 통해 JWT 토큰을 보내지만, 브라우저가 쿠키를 내부적으로 처리하여 JavaScript에서 접근 가능하게 만드는 시점과 `main.js`의 초기 API 호출 시점 사이에 타이밍 차이가 발생했기 때문입니다.
    
-   **해결 전략:** `main.js`에 `waitForJWTCookie()`라는 JWT 쿠키 대기 로직을 추가하여 브라우저가 쿠키를 완전히 처리할 시간을 확보하도록 했습니다.


## 🧠 배운 핵심 개념

-   **JWT 기반 인증 시스템의 심화 이해**: `HttpOnly`, `SameSite=Strict`, `Secure` 쿠키 옵션의 실제 적용과 `JWT_CSRF_COOKIE_HTTPONLY` 설정을 통한 CSRF 토큰의 JavaScript 접근 제어 메커니즘을 명확히 이해하여 **XSS와 CSRF 공격을 동시에 방어하는 이중 보안 시스템 구축**의 중요성을 체득했습니다.
    
-   **복합적인 서버 환경에서의 디버깅 전략**: cPanel과 같은 제약된 공유 호스팅 환경에서 발생하는 `Child process was killed`와 같은 예측 불가능한 서버 리소스 문제의 원인을 다각도로 분석하고(Google Analytics OAuth, WordPress API 호출, Debug Mode 활성화 등), **환경 변수 및 코드 최적화를 통한 해결 방안을 모색하는 능력**을 길렀습니다.
    
-   **다국어 PDF 생성의 폰트 관리 중요성**: `xhtml2pdf`와 같은 라이브러리 사용 시 **운영체제의 폰트 자동 대체 기능 부재**로 인한 다국어 깨짐 현상을 인지하고, **통합 폰트(Noto Sans)를 직접 포함하고 명시적으로 지정하는 것이 필수적임**을 이해했습니다.


## 💡 실전 시행착오 및 팁

-   **`Flask-JWT-Extended` CSRF 보호 설정의 미묘한 차이**: `JWT_COOKIE_HTTPONLY`와 `JWT_CSRF_COOKIE_HTTPONLY` 설정을 혼동하여 CSRF 토큰 접근 문제를 겪었습니다. **Access Token은 HttpOnly로 유지하되, CSRF 토큰은 JavaScript에서 접근 가능하도록 `JWT_CSRF_COOKIE_HTTPONLY = False`로 명확히 설정**해야 합니다.
    
-   **`Flask-JWT-Extended` 토큰 클레임 필터링의 필요성**: Refresh Token으로 새로운 Access Token을 생성할 때 `type` 클레임이 복사되어 "Only non-refresh tokens are allowed" 에러가 발생했습니다. **`RESERVED_CLAIMS`를 활용하여 JWT 예약 클레임이 재발급 토큰에 불필요하게 포함되지 않도록 필터링**하는 것이 중요합니다.
    
-   **`xhtml2pdf` 환경 독립적 최적화**: PDF 생성 시 `width: 100%` 같은 CSS 백분율이 올바르게 적용되지 않거나 폰트 문제가 발생할 수 있습니다. **HTML 전처리 과정에서 백분율을 고정 크기(예: `mm`)로 변환하고, 다국어 지원이 가능한 특정 폰트(예: Noto Sans)를 명시적으로 지정하여 환경에 구애받지 않는 안정적인 PDF 생성**을 확보해야 합니다.
    
-   **클라이언트-서버 초기화 타이밍 문제 해결**: 첫 접속 시 API 호출이 실패하는 문제는 서버에서 쿠키를 발행하고 브라우저가 이를 처리하는 시간 차이에서 비롯됩니다. **JavaScript에서 `document.cookie`를 확인하며 필요한 쿠키가 로드될 때까지 대기하는 로직(`waitForJWTCookie`)을 구현**하여 초기 API 호출의 안정성을 높일 수 있습니다.


## 🔜 다음 학습 방향

-   **PDF 다국어 폰트 지원 시스템 구축 완료**: 오늘 계획된 Noto Sans 폰트 파일을 서버에 업로드하고 `pdf_generator.py`를 수정하여 **다국어(한국어, 중국어 포함) 텍스트가 깨지지 않고 PDF에 올바르게 표시**되도록 구현하고 테스트할 것입니다.
    
-   **cPanel 서버 리소스 최적화 결과 테스트**: 오늘 적용한 디버그 모드, WordPress API 호출 설정, 로깅 레벨 조정 등의 변경 사항이 **cPanel 환경에서 실제로 서버 리소스 사용량을 줄이고 프로세스 킬링 문제를 해결하는지** 철저히 테스트하고 검증할 것입니다.
    
-   **PDF 커버 이미지 동적 변경 시스템 개발 착수**: 개발 선임의 피드백을 반영하여 WordPress에서 이미지를 가져와 PDF 커버 배경으로 사용하는 **동적 커버 이미지 시스템 구현을 시작**하고, 기존 CSS 배경색 방식을 대체할 것입니다.
    
-   **AI 요약 및 PDF 텍스트 콘텐츠 피드백 반영**: 이전에 받은 AI 요약 기능 개선사항과 PDF 내 텍스트 콘텐츠 품질 향상에 대한 피드백을 구체적으로 확인하고 반영 작업을 진행할 것입니다.
    
-   **Flask 앱 및 WP 통합 최종 테스트**: 모든 기능 구현이 완료되면, WP 로그인 연동 및 Flask 앱의 모든 기능에 대한 통합 테스트를 진행하여 최종 안정성을 확보할 것입니다.
