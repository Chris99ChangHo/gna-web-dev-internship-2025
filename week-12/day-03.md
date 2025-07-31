# 📅 Day 03 (2025-07-30, Wed)

## 🎓 What I Did Today

**📌 Although there was no development meeting in the morning, I focused on resolving JWT authentication system issues and the cPanel deployment process, stabilizing the dashboard.**    
**📌 Successfully built a secure and scalable JWT (JSON Web Token) based authentication system for the Flask dashboard, replacing the unstable existing session method.**   
**📌 Resolved various critical server errors and library conflicts, including `405 Method Not Allowed`, `500 Internal Server Error`, `TypeError: Limiter.__init__()`, and `CSRF Token is Missing`, which stabilized the dashboard.**   

### Detailed Activities

Below is a detailed summary of the JWT authentication system troubleshooting and cPanel deployment process conducted today, focusing on key issues. There was no development meeting.

**1. Token Expiration Issue in Development Mode:** Identified and addressed issues related to JWT token expiration in the development environment.

-   **Problem Description**:

    ```Plaintext
    Token check - Current: 1753852820, Expires: 1753851780, Diff: -1040401 error occurred - Token already expired
    ```
    
-   **Resolution**:
    
    -   Attempted re-access after clearing browser cookies.
    -   Tested in incognito mode.
    -   Considered extending token expiration time.

**2. cPanel Deployment Environment Issues:** Addressed challenges specific to the cPanel hosting environment.

-   **1. Repetitive SQLite Initialization Logs**
    
    -   **Problem**:
        
        ```Plaintext
        SQLite blacklist database initialized (repeated 11 times)
        ```
        
    -   **Resolution**:
        
        ```Python
        # Track initialization state globally
        _database_initialized = False
        def setup_database():
            global _database_initialized
            if _database_initialized:
                return
            # ... Initialization logic
            _database_initialized = True
        ```

**3. The Most Critical CSRF Token Issue (Core Resolution):** Successfully identified and resolved a complex CSRF token issue stemming from HttpOnly cookie settings, which was crucial for robust CSRF protection in the production environment.

-   **Issue Discovery**:

    ```Plaintext
    2025-07-30 15:58:38,893 WARNING: Unauthorized access attempt: Missing CSRF token
    PDF generation failed: 401 - Authentication Required
    ```
    
-   **Root Cause Analysis**: The core of the problem was precisely identified: The **`JWT_COOKIE_HTTPONLY = True`** setting made all JWT cookies `HttpOnly`. This inadvertently applied to the **`csrf_access_token` cookie**, preventing JavaScript from accessing it. Consequently, the `getCsrfToken()` function always returned `null`, and the `X-CSRF-TOKEN` header was empty in API requests, triggering the "Missing CSRF token" error on the server.
    
-   **Complete Solution**:

    ```Python
    # Add to app.py
    app.config["JWT_COOKIE_HTTPONLY"] = True        # Keep Access Token protected (XSS prevention)
    app.config["JWT_CSRF_COOKIE_HTTPONLY"] = False  # Allow JS access to CSRF token (for Double Submit Pattern)
    ```
    
-   **Post-Resolution Verification**:
    
    ```JavaScript
    [CSRF DEBUG] Found CSRF token: 3efd3038-4abc-47e3-9edd-67b7ffa80548
    [CSRF DEBUG] CSRF Token found. Adding to header.
    ```

**4. Initial Access Token Initialization Timing Issue:** Resolved a subtle timing conflict where the client-side JavaScript attempted to use JWT cookies before they were fully processed by the browser, causing initial API call failures.

-   **Problem Description**: Initial access: Failed ❌ Refresh after: Success ✅
    
-   **Root Cause Analysis**: The server sends JWT tokens via the `Set-Cookie` header, but there's a timing difference between when the browser internally processes the cookie to make it accessible to JavaScript and when `main.js` attempts API calls.
    
-   **Resolution**:

    ```JavaScript
    // main.js에서 JWT 쿠키 대기 로직
    async function waitForJWTCookie(timeout = 5000) {
        const start = Date.now();
        while (Date.now() - start < timeout) {
            if (document.cookie.includes('jwt_access_token=')) {
                return true;
            }
            await new Promise(resolve => setTimeout(resolve, 100));
        }
        return false;
    }
    ```

## 🧠 Key Concepts Learned

-   **JWT-based Authentication System Design and Implementation**: Gained a deeper understanding of utilizing Access/Refresh tokens, secure token storage with **`HttpOnly`**, **`SameSite=Strict`**, and **`Secure`** cookie options, and implementing token blacklisting.
    
-   **Complex Error Diagnosis and Resolution Strategies**: Faced and resolved various types of errors, including **`405 Method Not Allowed`**, **`500 Internal Server Error`**, **`TypeError`**, and **`CSRF` conflicts**. This process enhanced my ability to analyze and resolve complex issues stemming from library/framework interactions, environmental configurations, and HTTP method mismatches.
    
-   **Trade-off Between Security and Development Convenience**: Experienced that it might be necessary to temporarily disable certain security features during development and testing, and was reminded to always revert these temporary measures before production deployment.

## 💡 Practical Trial-and-Error and Tips

-   **HTTP Method Mismatch Error (`405`) Diagnosis**: When a `405 Method Not Allowed` error occurs, first verify that the HTTP methods allowed by the Flask route decorator's `methods` argument match the client's request method.
    
-   **External Service Dependency Issues (`500` Redis) and Hosting Constraints**: If a feature working well in development causes a `500 Internal Server Error` in the deployment environment, check if the external service (e.g., Redis) is actually installed and running on the server. If necessary, adjust settings like `storage_uri` to suit the environment. **Be especially mindful that in restrictive shared hosting environments like cPanel, introducing external services might be difficult or require additional configuration.**
    
-   **Managing Conflicts with Multiple Security Libraries**: When combining multiple security-related libraries (e.g., `Flask-WTF` and `Flask-JWT-Extended`), feature overlap or conflicts can arise. Clearly understanding each library's role and configuration options, and then removing or disabling unnecessary or conflicting features, is crucial.
    
-   **Preventing Missing Essential Environment Variables**: Runtime errors can occur if essential environment variables, such as `SECRET_KEY` required by frameworks or libraries, are missing. Meticulously manage `.env` files and `app.config` settings to proactively prevent such issues.  

## 🔜 Next Steps

-   **Enable and Finalize CSRF Protection Testing**: Re-enable the temporarily disabled CSRF protection and conduct final tests to ensure the client correctly handles CSRF tokens.
    
-   **Rate-Limiter for Persistent/Shared Storage Solutions Exploration**: Specifically explore and implement a persistent and shared storage solution for `Flask-Limiter` that's suitable for the production environment.
    
-   **Anti-Bot & Scraping Prevention Implementation Initiation**: Based on the research requested by the senior developer, I will start implementing anti-bot and scraping prevention features for the Flask app.
    
-   **Project Technical Documentation Drafting**: Following the senior developer's directive, I will begin drafting the technical documentation covering the project's site structure, workflow, and the programming languages/technology stack used.
    
-   **Flask App & WP Integration Final Testing**: Once all features are implemented, I will conduct integrated testing for the WordPress login integration and all Flask app functionalities.

### 🛡️ Final Security Configuration (Production Environment)

```Python
# Recommended robust security settings for production environment
app.config["JWT_COOKIE_CSRF_PROTECT"] = True    # CSRF protection enabled
app.config["JWT_COOKIE_HTTPONLY"] = True        # Access token XSS protection
app.config["JWT_CSRF_COOKIE_HTTPONLY"] = False  # CSRF token JS access allowed
app.config["JWT_COOKIE_SECURE"] = True          # HTTPS required
```

**Security Level Achieved:**

-   ✅ **XSS Attack Prevention**: Access tokens are set as `HttpOnly`, preventing JavaScript access.
-   ✅ **CSRF Attack Prevention**: The Double Submit Token method effectively defends against CSRF attacks.
-   ✅ **HTTPS Enforcement**: The `Secure` cookie option enforces HTTPS usage in production, enhancing data transmission security.

----------

# 📅 3일차 (2025-07-30, 수)

## 🎓 오늘 한 일

**📌 오전 개발 미팅은 없었지만, JWT 인증 시스템 문제 해결 및 cPanel 배포 과정에 집중하여 대시보드를 안정화했습니다.**   
**📌 기존의 불안정한 세션 방식을 대체하는 JWT(JSON Web Token) 기반의 안전하고 확장성 높은 인증 시스템을 Flask 대시보드에 성공적으로 구축했습니다.**   
**📌 `405 Method Not Allowed`, `500 Internal Server Error`, `TypeError: Limiter.__init__()`, `CSRF Token is Missing` 등 여러 치명적인 서버 오류와 라이브러리 충돌을 해결하여 대시보드를 안정화했습니다.**   

### 상세 활동

오늘 하루 동안 진행된 JWT 인증 시스템 문제 해결 및 cPanel 배포 과정을 중요한 이슈 중심으로 상세히 정리해드리겠습니다. 개발 미팅은 없었습니다.

**1. 개발 모드에서 토큰 만료 문제:**

-   **문제 상황**:

    ```Plaintext
    Token check - Current: 1753852820, Expires: 1753851780, Diff: -1040401 에러 발생 - 토큰이 이미 만료됨
    ```
    
-   **해결책**:
    
    -   브라우저 쿠키 삭제 후 재접속
    -   시크릿 모드 테스트
    -   토큰 만료 시간 연장 고려

**2. cPanel 배포 환경 문제들:**

-   **1. 반복적인 SQLite 초기화 로그**
    
    -   **문제**:

        ```Plaintext
        SQLite blacklist database initialized (11번 반복)
        ```
        
    -   **해결책**:

        ```Python
        # 전역 변수로 초기화 상태 추적
        _database_initialized = False
        def setup_database():
            global _database_initialized
            if _database_initialized:
                return
            # ... 초기화 로직
            _database_initialized = True
        ```

**3. 가장 중요한 CSRF 토큰 문제 (핵심 해결):**

-   **문제의 발견**:

    ```Plaintext
    2025-07-30 15:58:38,893 WARNING: Unauthorized access attempt: Missing CSRF token
    PDF generation failed: 401 - Authentication Required
    ```
    
-   **근본 원인 분석**: 문제의 핵심을 정확히 파악: `JWT_COOKIE_HTTPONLY = True` 설정으로 모든 JWT 쿠키가 HttpOnly가 됨 `csrf_access_token` 쿠키도 HttpOnly가 되어 JavaScript 접근 불가 `getCsrfToken()` 함수가 항상 `null` 반환 `X-CSRF-TOKEN` 헤더가 비어있음 서버에서 "Missing CSRF token" 에러 발생
    
-   **완벽한 해결책**:

    ```Python
    # app.py에 추가
    app.config["JWT_COOKIE_HTTPONLY"] = True   # Access token 보호 유지
    app.config["JWT_CSRF_COOKIE_HTTPONLY"] = False  # CSRF 토큰은 JS 접근 허용
    ```
    
-   **해결 후 확인**:

    ```JavaScript
    [CSRF DEBUG] Found CSRF token: 3efd3038-4abc-47e3-9edd-67b7ffa80548
    [CSRF DEBUG] CSRF Token found. Adding to header.
    ```

**4. 첫 접속 시 토큰 초기화 타이밍 문제:**

-   **문제 상황**: 첫 접속: 실패 ❌ 새로고침 후: 성공 ✅
    
-   **원인 분석**: 서버에서 Set-Cookie 헤더를 통해 JWT 토큰을 보내지만, 브라우저가 쿠키를 내부적으로 처리하여 JavaScript에서 접근 가능하게 만드는 시점과 main.js의 API 호출 시점 사이의 타이밍 차이
    
-   **해결 방안**:

    ```JavaScript
    // main.js에서 JWT 쿠키 대기 로직
    async function waitForJWTCookie(timeout = 5000) {
        const start = Date.now();
        while (Date.now() - start < timeout) {
            if (document.cookie.includes('jwt_access_token=')) {
                return true;
            }
            await new Promise(resolve => setTimeout(resolve, 100));
        }
        return false;
    }
    ```


## 🧠 배운 핵심 개념

-   **JWT 기반 인증 시스템 설계 및 구현**: Access/Refresh 토큰 활용, **`HttpOnly`**, **`SameSite=Strict`**, **`Secure`** 쿠키 옵션을 통한 안전한 토큰 저장, 토큰 블랙리스트 구현 등 **JWT의 핵심 개념과 실제 적용 방법**을 익혔습니다.
    
-   **복합적인 에러 진단 및 해결 전략**: **`405 Method Not Allowed`**, **`500 Internal Server Error`**, **`TypeError`**, **`CSRF` 충돌** 등 다양한 유형의 에러를 직면하고 해결하는 과정을 통해, 라이브러리/프레임워크 간의 상호작용, 환경 설정, HTTP 메서드 불일치 등 **복합적인 원인을 분석하고 해결하는 능력**을 향상시켰습니다.
    
-   **보안과 개발 편의성 간의 트레이드오프**: 개발 및 테스트 단계에서 특정 보안 기능을 임시로 비활성화하는 결정이 필요할 수 있음을 경험하며, 운영 환경 배포 전에는 이러한 임시 조치를 반드시 되돌려야 함을 상기했습니다.

## 💡 실전 시행착오 및 팁

-   **HTTP Method 불일치 오류 (`405`) 진단**: `405 Method Not Allowed` 오류 발생 시, Flask 라우트 데코레이터의 `methods` 인자가 허용하는 HTTP 메서드와 클라이언트의 요청 메서드가 일치하는지 가장 먼저 확인해야 합니다.
    
-   **외부 서비스 의존성 문제 및 호스팅 제약**: 개발 환경에서 잘 작동하던 기능이 배포 환경에서 `500 Internal Server Error`를 발생시킨다면, 서버에 해당 외부 서비스가 실제로 설치 및 실행 중인지 확인하고, 필요한 경우 `storage_uri`와 같은 설정을 변경하여 환경에 맞게 조정해야 합니다. **특히, cPanel과 같이 제약이 있는 공유 호스팅 환경에서는 외부 서비스의 도입이 어렵거나 추가적인 설정이 필요할 수 있음을 염두에 두어야 합니다.**
    
-   **다중 보안 라이브러리 사용 시 충돌 관리**: 여러 보안 관련 라이브러리(예: `Flask-WTF`와 `Flask-JWT-Extended`)를 함께 사용할 경우, 기능 중복이나 충돌이 발생할 수 있습니다. 각 라이브러리의 역할과 설정 옵션을 명확히 이해하고, 불필요하거나 충돌하는 기능은 제거하거나 비활성화하는 전략이 필요합니다.
    
-   **필수 환경 변수 누락 방지**: `SECRET_KEY`와 같이 프레임워크나 라이브러리에서 필수로 요구하는 환경 변수가 누락되면 런타임 에러가 발생합니다. `.env` 파일 관리 및 `app.config` 설정을 꼼꼼히 확인하여 이러한 문제를 사전에 방지해야 합니다.

## 🔜 다음 학습 방향

-   **CSRF 보호 기능 활성화 및 최종 테스트**: 임시 비활성화했던 CSRF 보호 기능을 다시 활성화하고, 클라이언트가 CSRF 토큰을 정상적으로 처리하는지 최종 테스트를 진행할 것입니다.
    
-   **Rate-Limiter를 위한 영구적/공유 스토리지 솔루션 탐색**: 운영 환경에 적합한 `Flask-Limiter`의 영구적이고 공유 가능한 저장소 솔루션을 구체적으로 탐색하고 적용할 것입니다.
    
-   **안티봇 및 스크래핑 방지 구현 착수**: 개발 선임의 요청에 따라 리서치한 내용을 바탕으로 Flask 앱에 안티봇 및 스크래핑 방지 기능을 구현하기 시작할 것입니다.
    
-   **프로젝트 기술 문서 초안 작성**: 개발 선임의 지시에 따라 프로젝트의 사이트 구조, 워크플로우, 사용된 언어 및 기술 스택에 대한 기술 문서 초안 작성을 시작할 것입니다.
    
-   **Flask 앱 및 WP 통합 최종 테스트**: 모든 기능 구현이 완료되면, WP 로그인 연동 및 Flask 앱의 모든 기능에 대한 통합 테스트를 진행할 것입니다.

### 🛡️ 최종 보안 설정 (운영 환경)

```Python
# 운영 환경에서 권장되는 완벽한 보안 설정
app.config["JWT_COOKIE_CSRF_PROTECT"] = True    # CSRF 보호 활성화
app.config["JWT_COOKIE_HTTPONLY"] = True        # Access token XSS 보호
app.config["JWT_CSRF_COOKIE_HTTPONLY"] = False  # CSRF token JS 접근 허용
app.config["JWT_COOKIE_SECURE"] = True          # HTTPS 필수
```

**보안 레벨**:

-   ✅ XSS 공격 방지: Access token HttpOnly
-   ✅ CSRF 공격 방지: Double submit token 방식
-   ✅ HTTPS 강제: 운영 환경에서 보안 쿠키
