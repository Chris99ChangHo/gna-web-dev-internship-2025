# 📅 Day 02 (2025-07-29, Tue)

## 🎓 What I Did Today

**📌 In the morning development meeting, received positive feedback on the `report project` completed yesterday (Day 01) and discussed plans for future testing and continuous improvement.**   
**📌 Quickly completed a new task of uploading products to WooCommerce.**   
**📌 Successfully built a secure and scalable JWT (JSON Web Token)-based authentication system for the Flask dashboard, replacing the unstable existing session method.**   
**📌 Resolved multiple critical server errors and library conflicts, including `405 Method Not Allowed`, `500 Internal Server Error` (Redis connection issues), `TypeError: Limiter.__init__()`, and `CSRF Token is Missing`, stabilizing the dashboard.**   
**📌 Afterwards, dedicated time to improving the Flask application's security and anti-bot code.**  

### Detailed Activities

**1. Morning Development Meeting Review:**

-   **Report Project Feedback**: The "report project," which included the PDF reports and Flask dashboard and was primarily completed yesterday, received an overall positive evaluation.
    
-   **Future Plans & Feedback**: Discussions focused on conducting further tests, continuously incorporating feedback, and making subsequent improvements.
    
-   **Documentation Directive**: I was informed of the future necessity to create comprehensive documentation for this project, although this isn't an immediate task.
    

**2. WooCommerce Product Upload Task:**

-   **New Assignment**: Today, I was assigned a different task: uploading products to WooCommerce. This was a welcome change of pace.
    

**3. Core Objective: Authentication System Modernization (JWT Implementation) & Key Implementations:**

-   **Core Objective**: The main goal was to abandon the existing unstable session method and build a secure, scalable JWT-based authentication system. This aimed to automatically extend user sessions while they remain on the page and create a more secure environment.
    
-   **Key Implementations & Improvements**:
    
    -   **JWT-based Authentication System (`app.py`)**:
        
        -   **Access Token (30 min) / Refresh Token (30 days)**: Completed a structure supporting both short-term sessions and long-term logins.
            
        -   **Secure Cookie Storage**: Stored tokens in cookies with **`HttpOnly`, `SameSite=Strict`, and `Secure`** options, enhancing defense against XSS and CSRF attacks.
            
        -   **Token Blacklisting**: Implemented a feature to invalidate used tokens upon logout to prevent reuse.
            
        -   **Rate-Limiter Application**: Applied `Flask-Limiter` to restrict API call frequency based on IP, preventing excessive requests.
            
    -   **Client-side Automatic Token Renewal System (`jwt-manager.js`)**:
        
        -   **Automatic Renewal**: Automatically renews the Access Token every 20 minutes to keep users logged in.
            
        -   **Real-time Status Display**: Added a "🔒 Secure Session Active" status bar at the top of the screen to visually show the current login status and token expiration time.
            
        -   **User Experience (UX) Improvement**: Provides transparent feedback to the user, such as warnings when token expiration is imminent and notifications upon successful renewal.
            

**4. Major Issues Resolved (Bug Fixes):**

Today, complex errors occurred due to various configuration conflicts and omissions, which were resolved step by step.

-   **First Issue: `405 Method Not Allowed` Error**:
    
    -   **Problem**: Immediately after attempting WordPress login, the dashboard page did not load, and a "Method Not Allowed" 405 error occurred. During a previous code modification, the application's main access path (`@app.route('/')`) was changed to accept only `GET` requests. However, the WordPress authentication system was sending login information via `POST`, causing the server to reject the request with "This address cannot process POST requests."
        
    -   **Resolution**: The route setting in `app.py` was modified to `@app.route('/', methods=['GET', 'POST'])`, allowing both `GET` and `POST` requests. This successfully resolved the 405 error.
        
-   **Second Issue: `500 Internal Server Error` (`redis.exceptions.ConnectionError`)**:
    
    -   **Problem**: Immediately after resolving the 405 error, a more severe 500 internal server error occurred, still preventing dashboard access. A detailed analysis of the server logs revealed `redis.exceptions.ConnectionError` as the core issue. The request rate limiting feature (`Flask-Limiter`) included in the code attempted to connect to a Redis database server to record data, but Redis was not installed on the cPanel hosting environment where the app was running, leading to connection refusal.
        
    -   **Resolution**: Considering the cPanel environment constraints, the setting was changed to use the application's own memory instead of relying on an external Redis server. The `Flask-Limiter`'s `storage_uri` was modified from `"redis://localhost:6379"` to **`"memory://"`**. This resolved the 500 error by preventing attempts to connect to a non-existent service.
        
-   **Incident 1: `TypeError: Limiter.__init__()` Error**:
    
    -   **Problem**: The latest version of the `flask-limiter` library was incompatible with the initialization code.
        
    -   **Resolution**: The initialization code was modified to use `limiter.init_app(app)` after creating the `Limiter` object.
        
-   **Incident 2: "CSRF Token is Missing" and `SECRET_KEY` Omission Error**:
    
    -   **Problem**: Two CSRF protection features, `Flask-WTF`'s `CSRFProtect` and `Flask-JWT-Extended`'s `JWT_COOKIE_CSRF_PROTECT` were conflicting. Additionally, `Flask-WTF` requires `app.config['SECRET_KEY']`, which was missing, causing a `RuntimeError`.
        
    -   **Resolution**: The `SECRET_KEY` omission was resolved by adding `app.config['SECRET_KEY'] = os.getenv('FLASK_SECRET_KEY')`. It was decided to use only JWT's own CSRF protection, and all `Flask-WTF` `CSRFProtect`-related code was commented out/deleted. Finally, for development convenience, JWT's CSRF protection was temporarily disabled (`JWT_COOKIE_CSRF_PROTECT = False`) to fully control the issue.
        

**5. Security and Anti-Bot Code Improvement:**

-   **Focus**: After completing all the above tasks, I dedicated time to enhancing the Flask application's security features and implementing anti-bot measures.
    

**6. Final Status and Future Recommendations:**

-   **Current Status**: The dashboard is in a stable development/testing state with CSRF protection temporarily disabled and the Rate-Limiter storage set to memory. All core functionalities are working correctly.
    
-   **Recommendations Before Production Deployment**:
    
    -   **Enable CSRF Protection**: It is recommended to re-enable **`JWT_COOKIE_CSRF_PROTECT = True`** in `app.py` and conduct final tests to ensure the client correctly handles CSRF tokens.
        
    -   **Consider Persistent/Shared Storage for Rate-Limiter**: While `memory://` works for development, it's not suitable for multi-process production environments as rate limits wouldn't be shared. **Given the challenges with Redis setup on cPanel, you'll need to explore alternative persistent and shared storage solutions for `Flask-Limiter` (e.g., another database backend or a distributed caching solution supported by your hosting environment) or consider a hosting solution that provides easier Redis support.**
        
    -   **Operate in HTTPS Environment**: The **`JWT_COOKIE_SECURE = True`** setting requires the service to be run in an HTTPS environment to function correctly.

## 🧠 Key Concepts Learned

-   **JWT-based Authentication System Design and Implementation**: Gained practical knowledge of JWT's core concepts and their application, including the use of Access/Refresh tokens, secure token storage with **`HttpOnly`, `SameSite=Strict`, and `Secure`** cookie options, and implementing token blacklisting.
    
-   **Flask-Limiter Utilization and Storage Selection**: Understood the importance of rate-limiting and learned the rationale behind choosing memory-based storage for development/testing and external storage like Redis for production environments. Specifically, **I experienced how challenging it can be to deploy and manage certain external services (like Redis) in restricted hosting environments (e.g., cPanel), emphasizing the need to adapt technical solutions to environmental constraints.**
    
-   **Complex Error Diagnosis and Resolution Strategies**: Faced and resolved various types of errors, including **`405 Method Not Allowed`, `500 Internal Server Error`, `TypeError`, and `CSRF` conflicts**. This experience enhanced my ability to analyze and resolve complex issues involving library/framework interactions, environmental configurations, and HTTP method mismatches.
    
-   **Trade-off Between Security and Development Convenience**: Experienced the necessity of temporarily disabling certain security features during development and testing phases, and was reminded of the crucial need to revert such temporary measures before production deployment.
    
-   **Project Lifecycle - Post-Completion Iteration**: I learned that even after a "completion" milestone, projects often enter a phase of further testing, feedback, and iterative improvement. This highlights the importance of an adaptable development process.
    
-   **Efficient Context Switching**: Successfully transitioning from development meetings to e-commerce operations (WooCommerce) and then back to core security coding demonstrated the ability to efficiently manage diverse tasks and contexts.

## 💡 Practical Trial-and-Error and Tips

-   **HTTP Method Mismatch Error (`405`) Diagnosis**: When encountering a `405 Method Not Allowed` error, the first step should be to verify that the HTTP methods allowed by the Flask route decorator's `methods` argument match the client's request method.
    
-   **External Service Dependency Issues (`500` Redis) and Hosting Constraints**: If a feature working well in development causes a `500 Internal Server Error` in the deployment environment, confirm whether the external service (e.g., Redis) is actually installed and running on the server, and adjust settings like `storage_uri` as needed to match the environment. **Specifically, be aware that restrictive shared hosting environments like cPanel might make it difficult or require additional configuration for external services.**
    
-   **Managing Conflicts with Multiple Security Libraries**: When using multiple security-related libraries (e.g., `Flask-WTF` and `Flask-JWT-Extended`), feature duplication or conflicts can occur. It's essential to clearly understand each library's role and configuration options, and to remove or disable unnecessary or conflicting features.
    
-   **Preventing Missing Essential Environment Variables**: The omission of essential environment variables like `SECRET_KEY`, required by frameworks or libraries, can lead to runtime errors. Meticulously managing `.env` files and `app.config` settings is crucial to prevent such issues proactively.
    
-   **Proactive Communication on Future Needs**: Being made aware of future requirements like documentation helps in mentally preparing and potentially collecting necessary information during current development phases.

## 🔜 Next Steps

-   **Enable and Finalize CSRF Protection Testing**: Re-enable the temporarily disabled CSRF protection and conduct final tests to ensure the client correctly handles CSRF tokens.
    
-   **Explore Persistent/Shared Storage Solutions for Rate-Limiter**: Actively research and implement a persistent and shared storage solution for `Flask-Limiter` suitable for the production environment, given the cPanel Redis limitations.
    
-   **Test `JWT_COOKIE_SECURE = True` in HTTPS Environment**: Verify that the `JWT_COOKIE_SECURE = True` setting functions correctly in an HTTPS environment.
    
-   **Begin Anti-Bot & Scraping Prevention Implementation**: Based on the research requested by the senior developer, I will begin implementing anti-bot and scraping prevention features for the Flask app.
    
-   **Draft Project Technical Documentation**: Following the senior developer's directive, I will start drafting the technical documentation covering the site structure, workflow, and programming languages/technology stack used.
    
-   **Finalize Flask App & WP Integration Testing**: Once all features are implemented, I will conduct integrated testing for the WP login integration and all Flask app functionalities.

----------

# 📅 2일차 (2025-07-29, 화)

## 🎓 오늘 한 일

**📌 오전 개발 미팅에서 어제 완료된 `리포트 대시보드 프로젝트`에 대해 긍정적인 평가를 받고 향후 테스트 및 개선 계획을 논의했습니다.**   
**📌 새로운 업무로 우커머스에 상품을 업로드하는 작업을 빠르게 완료했습니다.**   
**📌 기존의 불안정한 세션 방식을 대체하는 JWT(JSON Web Token) 기반의 안전하고 확장성 높은 인증 시스템을 Flask 대시보드에 성공적으로 구축했습니다.**   
**📌 `405 Method Not Allowed`, `500 Internal Server Error` (Redis 연결 문제), `TypeError: Limiter.__init__()`, `CSRF Token is Missing` 등 여러 치명적인 서버 오류와 라이브러리 충돌을 해결하여 대시보드를 안정화했습니다.**   
**📌 이어서 Flask 애플리케이션의 보안 및 안티봇 관련 코드 개선 시간을 가졌습니다.**  

### 상세 활동

**1. 오전 개발 미팅 요약:**

-   **리포트 프로젝트 피드백**: 어제 1차적으로 완성시킨 PDF 리포트와 Flask 대시보드를 포함한 `리포트 프로젝트`에 대해 전반적으로 좋은 평가를 받았습니다.
    
-   **향후 계획 및 피드백**: 앞으로 몇 번 더 테스트를 진행하고, 지속적으로 피드백을 받아 개선해 나가자는 이야기가 오갔습니다.
    
-   **문서화 지시**: 당장은 아니지만, 나중에 이 프로젝트에 대한 설명 문서를 작성할 필요가 있으니 미리 인지하고 있으라는 지시를 받았습니다.
    

**3. 핵심 목표: 인증 시스템 현대화 (JWT 도입) 및 주요 구현**

-   **핵심 목표**: 기존의 불안정한 세션 방식을 버리고, 안전하고 확장성 높은 JWT 기반의 인증 시스템을 구축하는 것이었습니다. 이를 통해 사용자가 페이지에 머무는 동안 자동으로 세션이 연장되고, 보안이 강화된 환경을 만들었습니다.
    
-   **주요 구현 및 개선 사항**:
    
    -   **JWT 기반 인증 시스템 구축 (`app.py`)**:
        
        -   **Access 토큰 (30분) / Refresh 토큰 (30일)**: 단기 세션과 장기 로그인을 동시에 지원하는 구조를 완성했습니다.
            
        -   **안전한 쿠키 저장**: 토큰을 **`HttpOnly`, `SameSite=Strict`, `Secure`** 옵션을 적용한 쿠키에 저장하여 XSS 및 CSRF 공격에 대한 방어력을 높였습니다.
            
        -   **토큰 블랙리스트**: 로그아웃 시 사용된 토큰을 무효화하여 재사용을 방지하는 기능을 구현했습니다.
            
        -   **Rate-Limiter 적용**: `Flask-Limiter`를 사용하여 과도한 요청을 방지하기 위해 IP 기반으로 API 호출 횟수를 제한했습니다.
            
    -   **클라이언트 자동 토큰 갱신 시스템 구축 (`jwt-manager.js`)**:
        
        -   **자동 갱신**: 20분마다 자동으로 Access 토큰을 갱신하여 사용자가 로그아웃되지 않도록 했습니다.
            
        -   **실시간 상태 표시**: 화면 상단에 "🔒 Secure Session Active" 상태 바를 추가하여 현재 로그인 상태와 토큰 만료 시간을 시각적으로 보여주도록 개선했습니다.
            
        -   **사용자 경험(UX) 개선**: 토큰 만료 임박 시 경고, 갱신 성공 시 알림 등 사용자에게 투명한 피드백을 제공합니다.
            

**4. 해결된 주요 문제 (버그 수정)**

오늘은 여러 설정 충돌과 누락으로 인해 복합적인 오류가 발생했으며, 이를 단계적으로 해결했습니다.

-   **첫 번째 문제: `405 Method Not Allowed` 오류 발생**:
    
    -   **문제**: 워드프레스에서 로그인을 시도한 직후, 대시보드 페이지가 뜨지 않고 "메소드를 허용하지 않음"이라는 405 에러가 발생했습니다. 이전 코드 수정 과정에서 애플리케이션의 메인 접속 경로(`@app.route('/')`)가 `GET` 요청만 받도록 변경되었으나, 워드프레스 인증 시스템은 로그인 정보를 `POST` 방식으로 보내고 있었기 때문에 서버가 요청을 거부했던 것입니다.
        
    -   **해결 조치**: `app.py` 파일의 해당 라우트 설정을 `@app.route('/', methods=['GET', 'POST'])`로 다시 수정하여 `GET`과 `POST` 요청을 모두 허용하도록 변경했습니다. 이 조치로 405 에러는 성공적으로 해결되었습니다.
        
-   **두 번째 문제: `500 Internal Server Error` 발생 (`redis.exceptions.ConnectionError`)**:
    
    -   **문제**: 405 에러를 해결하자마자, 더 심각한 500 서버 내부 오류가 발생하며 대시보드 접속이 여전히 불가능했습니다. 서버 로그를 정밀 분석한 결과, `redis.exceptions.ConnectionError`가 문제의 핵심이었습니다. 코드에 포함된 요청 횟수 제한 기능(`Flask-Limiter`)이 데이터를 기록하기 위해 Redis 데이터베이스 서버에 접속을 시도했지만, 앱이 실행 중인 cPanel 호스팅 환경에는 Redis가 설치되어 있지 않아 연결이 거부된 것입니다.
        
    -   **해결 조치**: cPanel 환경의 제약을 고려하여, 외부 Redis 서버에 의존하는 대신 애플리케이션 자체 메모리를 사용하도록 설정을 변경했습니다. `Flask-Limiter`의 설정 값인 `storage_uri`를 `"redis://localhost:6379"`에서 **`"memory://"`**로 수정했습니다. 이 조치로 더 이상 존재하지 않는 서비스에 연결을 시도하지 않게 되어 500 에러가 완전히 해결되었습니다.
        
-   **사건 1: `TypeError: Limiter.__init__()` 오류 발생**:
    
    -   **문제**: `flask-limiter` 라이브러리의 최신 버전과 초기화 코드가 맞지 않았습니다.
        
    -   **해결**: `Limiter` 객체를 생성한 후 `limiter.init_app(app)` 방식으로 초기화 코드를 수정하여 해결했습니다.
        
-   **사건 2: "CSRF Token is Missing" 및 `SECRET_KEY` 누락 오류**:
    
    -   **문제**: `Flask-WTF`의 `CSRFProtect`와 `Flask-JWT-Extended`의 `JWT_COOKIE_CSRF_PROTECT` 두 가지 CSRF 보호 기능이 충돌하고 있었습니다. 또한, `Flask-WTF`는 `app.config['SECRET_KEY']`를 필수로 요구하는데 이 설정이 누락되어 `RuntimeError`가 발생했습니다.
        
    -   **해결**: `app.config['SECRET_KEY'] = os.getenv('FLASK_SECRET_KEY')` 코드를 추가하여 `SECRET_KEY` 누락 문제를 해결했습니다. JWT 자체의 CSRF 보호 기능만 사용하기로 결정하고, 충돌을 일으키는 `Flask-WTF`의 `CSRFProtect` 관련 코드를 모두 주석 처리/삭제했습니다. 최종적으로 개발 편의를 위해 JWT의 CSRF 보호 기능도 임시 비활성화(`JWT_COOKIE_CSRF_PROTECT = False`)하여 문제를 완전히 통제했습니다.

**6. 최종 상태 및 향후 권장 사항**

-   **현재 상태**: CSRF 보호를 임시 비활성화하고, Rate-Limiter 저장소를 메모리로 사용하는 안정적인 개발/테스트 상태입니다. 모든 핵심 기능이 정상적으로 작동합니다.
    
-   **운영 배포 전 권장 사항**:
    
    -   **CSRF 보호 기능 활성화**: `app.py`에서 **`JWT_COOKIE_CSRF_PROTECT = True`**로 다시 설정하고, 클라이언트가 CSRF 토큰을 정상적으로 처리하는지 최종 테스트를 권장합니다.
        
    -   **Rate-Limiter를 위한 영구적/공유 스토리지 고려**: `memory://` 방식은 개발 환경에서는 작동하지만, 여러 프로세스가 동작하는 운영 환경에서는 요청 제한 상태를 공유하지 못해 적합하지 않습니다. **cPanel 환경에서 Redis 설정이 어렵다는 점을 고려하여, 운영 환경에서는 다른 형태의 영구적이고 공유 가능한 저장소(예: 다른 데이터베이스 백엔드 또는 cPanel이 지원하는 분산 캐싱 솔루션)를 `Flask-Limiter`에 적용하거나, Redis를 쉽게 지원하는 호스팅 환경으로의 전환을 고려해야 합니다.**
        
    -   **HTTPS 환경에서 운영**: **`JWT_COOKIE_SECURE = True`** 설정이 올바르게 작동하려면 반드시 HTTPS 환경에서 서비스해야 합니다.

## 🧠 배운 핵심 개념

-   **JWT 기반 인증 시스템 설계 및 구현**: Access/Refresh 토큰 활용, **`HttpOnly`, `SameSite=Strict`, `Secure`** 쿠키 옵션을 통한 안전한 토큰 저장, 토큰 블랙리스트 구현 등 JWT의 핵심 개념과 실제 적용 방법을 익혔습니다.
    
-   **Flask-Limiter 활용 및 저장소 선택**: Rate-Limiting의 중요성을 이해하고, 개발/테스트 환경에서는 메모리 기반 저장소를, 운영 환경에서는 Redis와 같은 외부 저장소를 사용해야 하는 이유와 설정 방법을 배웠습니다. 특히, **호스팅 환경(예: cPanel)의 제약으로 인해 특정 외부 서비스(Redis)의 도입 및 관리가 어려울 수 있음을 경험하며, 기술 솔루션을 환경적 제약에 맞춰 조정해야 하는 중요성을 깨달았습니다.**
    
-   **복합적인 에러 진단 및 해결 전략**: **`405 Method Not Allowed`, `500 Internal Server Error`, `TypeError`, `CSRF` 충돌** 등 다양한 유형의 에러를 직면하고 해결하는 과정을 통해, 라이브러리/프레임워크 간의 상호작용, 환경 설정, HTTP 메서드 불일치 등 복합적인 원인을 분석하고 해결하는 능력을 향상시켰습니다.
    
-   **보안과 개발 편의성 간의 트레이드오프**: 개발 및 테스트 단계에서 특정 보안 기능을 임시로 비활성화하는 결정이 필요할 수 있음을 경험하며, 운영 환경 배포 전에는 이러한 임시 조치를 반드시 되돌려야 함을 상기했습니다.
    
-   **프로젝트 수명 주기 - 완료 후 반복 개선**: "완료"라는 마일스톤이 초기 피드백과 추가적인 반복 개선의 시작점인 경우가 많다는 것을 알게 되었습니다. 이는 유연한 개발 프로세스의 중요성을 보여줍니다.

## 💡 실전 시행착오 및 팁

-   **HTTP Method 불일치 오류 (`405`) 진단**: `405 Method Not Allowed` 오류 발생 시, Flask 라우트 데코레이터의 `methods` 인자가 허용하는 HTTP 메서드와 클라이언트의 요청 메서드가 일치하는지 가장 먼저 확인해야 합니다.
    
-   **외부 서비스 의존성 문제 (`500` Redis) 및 호스팅 제약**: 개발 환경에서 잘 작동하던 기능이 배포 환경에서 `500 Internal Server Error`를 발생시킨다면, 서버에 해당 외부 서비스(예: Redis)가 실제로 설치 및 실행 중인지 확인하고, 필요한 경우 `storage_uri`와 같은 설정을 변경하여 환경에 맞게 조정해야 합니다. **특히, cPanel과 같이 제약이 있는 공유 호스팅 환경에서는 외부 서비스의 도입이 어렵거나 추가적인 설정이 필요할 수 있음을 염두에 두어야 합니다.**
    
-   **다중 보안 라이브러리 사용 시 충돌 관리**: 여러 보안 관련 라이브러리(예: `Flask-WTF`와 `Flask-JWT-Extended`)를 함께 사용할 경우, 기능 중복이나 충돌이 발생할 수 있습니다. 각 라이브러리의 역할과 설정 옵션을 명확히 이해하고, 불필요하거나 충돌하는 기능은 제거하거나 비활성화하는 전략이 필요합니다.
    
-   **필수 환경 변수 누락 방지**: `SECRET_KEY`와 같이 프레임워크나 라이브러리에서 필수로 요구하는 환경 변수가 누락되면 런타임 에러가 발생합니다. `.env` 파일 관리 및 `app.config` 설정을 꼼꼼히 확인하여 이러한 문제를 사전에 방지해야 합니다.

## 🔜 다음 학습 방향

-   **CSRF 보호 기능 활성화 및 최종 테스트**: 임시 비활성화했던 CSRF 보호 기능을 다시 활성화하고, 클라이언트가 CSRF 토큰을 정상적으로 처리하는지 최종 테스트를 진행할 것입니다.
    
-   **Rate-Limiter를 위한 영구적/공유 스토리지 솔루션 탐색**: 운영 환경에 적합한 `Flask-Limiter`의 영구적이고 공유 가능한 저장소 솔루션을 구체적으로 탐색하고 적용할 것입니다.
    
-   **HTTPS 환경에서 `JWT_COOKIE_SECURE = True` 테스트**: `JWT_COOKIE_SECURE = True` 설정이 HTTPS 환경에서 올바르게 작동하는지 검증할 것입니다.
    
-   **프로젝트 기술 문서 초안 작성**: 개발 선임의 지시에 따라 프로젝트의 사이트 구조, 워크플로우, 사용된 언어 및 기술 스택에 대한 기술 문서 초안 작성을 시작할 것입니다.
    
-   **Flask 앱 및 WP 통합 최종 테스트**: 모든 기능 구현이 완료되면, WP 로그인 연동 및 Flask 앱의 모든 기능에 대한 통합 테스트를 진행할 것입니다.
