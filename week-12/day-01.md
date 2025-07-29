# 📅 Day 01 (2025-07-28, Mon)

## 🎓 What I Did Today

**📌 Reported on the `xhtml2pdf` PDF report design rework completion and shared the WordPress (WP) integrated Flask app security system plan in the morning development meeting.**   
**📌 Finally completed the PDF report design work, though it was delayed more than expected due to `xhtml2pdf`'s CSS compatibility issues.**   
**📌 Successfully built and demonstrated a robust access control security system for the Flask dashboard, integrated with WordPress login, and received feedback on it.**   
**📌 Received a directive from the senior developer to prepare comprehensive technical documentation for the project and was asked to research anti-bot and scraping prevention methods.**  

### Detailed Activities

**1. Morning Development Meeting Summary:**

-   **Report Project Progress**:
    
    -   **PDF Module Dependency**: Reported that `xhtml2pdf` was chosen for optimization due to module dependency issues when uploading to cPanel.
        
    -   **Design Readjustment Challenges**: Explained that adapting the existing design and structure to `xhtml2pdf` was lengthy, and **modern CSS technologies were not supported**, causing significant delays.
        
-   **Security Feature Implementation Plan Share**:
    
    -   **HTTPS Handling**: Confirmed that HTTPS is automatically applied by cPanel's `AutoSSL`.
        
    -   **Authentication Method**: Explained the plan to generate a token for authentication, allowing WP to grant access to the Flask app upon successful verification.
        
    -   **WP Login Integration**: Stated the plan to integrate security directly with WP login.
        
-   **Senior Developer Feedback & Directives**:
    
    -   The implementation plan was positively evaluated as a "sound process."
        
    -   **Additional Directive**: Asked to research methods to prevent crawling bots and scraping tools (e.g., `robots.txt`, WP security plugins, WAF, Rate Limiting, CAPTCHA).
        
    -   **Next Step**: Agreed to conduct final testing once all features are implemented.
        

**2. PDF Report Design Rework Completion:**

-   I focused on redesigning the PDF reports using the `xhtml2pdf` library.
    
-   **Challenges Faced**: The work was significantly slower than expected because `xhtml2pdf` has limited recognition of CSS elements. Even simple style expressions required searching for and applying older syntax.
    
-   **Outcome**: **I finally completed all PDF report design rework.**
    

**3. WordPress-Flask Security System Building and Demonstration:**

-   **Project Overview**: The goal was to resolve the issue where anyone could access the Flask dashboard if they knew the URL, by building a system that allows only WordPress administrators to access it securely.
    
-   **Achieved Results**:
    
    -   WordPress login integration completed.
        
    -   1-hour session + auto-renewal system implemented (preventing URL token exposure via POST method).
        
    -   Real-time session warning system established.
        
-   **Core Security Structure**:
    
    -   **Dual Authentication System**: WordPress → [Simple Auth + JWT Token] → Flask → Verification → Access Granted.
        
        -   Simple Auth (`md5($username . $timestamp . $secret_key)`).
            
        -   JWT-style Token (`base64_encode($payload . '|||' . $hmac_signature)`).
            
    -   **64-character Secret Key System**: WordPress and Flask share the same `SECRET_KEY`, used as the master key for token signing/verification.
        
-   **Session Management System**:
    
    -   **Final Timeline**: 0 min (Initial Auth) → 20 min (⚠️ "10 min left" warning) → 30 min (🔄 1st auto-renewal +15 min) → 40 min (⚠️ "5 min left" warning) → 45 min (🔄 2nd auto-renewal +15 min [final]) → 55 min (🚨 "5 min left" final warning) → 60 min (💀 Forced expiration → WordPress re-login).
        
    -   **Auto-Renewal Logic**: Max 2 renewals (15 min each), 1-hour absolute limit, activity-based renewal.
        
-   **WordPress Implementation**:
    
    -   **File Location**: `wp-content/themes/siteorigin-unwind/functions.php`.
        
    -   **POST Method Security**: `generate_secure_dashboard_link()` function returns a POST form after permission check and token generation.
        
    -   **UI Implementation**: `[secure_dashboard]` shortcode, "New Dashboard" admin menu, button design on Report Page.
        
-   **Flask Implementation**:
    
    -   **Module Structure**: `.env`, `app.py`, `wp_auth.py`, `static/js/session-guard.js`, `templates/index.html`.
        
    -   **`wp_auth.py` Core Functions**: MD5 hash verification, JWT token verification, auto-renewing decorator, session status API.
        
    -   **`app.py` Application**: `@wp_auth.require_auto_renewing_auth` decorator applied to root path and session status API.
        
-   **User Warning System**:
    
    -   **`session-guard.js` Functionality**: Detects warnings from response headers, displays pop-ups, checks session status every 5 minutes.
        
    -   **Warning Message Types**: Normal (yellow), Final (red), Expiration Modal (full-screen overlay).
        
-   **Troubleshooting & Resolutions**:
    
    -   **Unicode Encoding Error**: Emoji error on cPanel server → Replaced emojis with text in Flask.
        
    -   **WordPress Critical Error**: `functions.php` syntax error causing site downtime → Restored backup and implemented safely step-by-step.
        
    -   **API Authentication Conflict**: Dashboard JavaScript calling API without token → Changed to session-based authentication.
        
    -   **URL Token Exposure**: Sensitive info exposed in URL with GET method → Changed to POST method.
        
    -   **404 Session Status Error**: JavaScript calling `/api/session_status` but not present in Flask → Added session status API to `app.py`.
        
-   **Final Security Level**:
    
    -   **Multi-layered Security**: WP login check, admin privilege verification, dual token verification (MD5 + HMAC), time-based expiration (1-hour absolute limit), session-based state management, POST method data transmission.
        
    -   **Attack Defense**: Brute force (64-char secret key), token forgery (HMAC-SHA256 signature), token theft (1-hour auto-expiration), XSS (only session cookie exposed), URL sniffing (no token in URL).
        
-   **Achievements & Completeness**: Achieved perfect access control, user-friendliness (auto-renewal + friendly warnings), URL security. Designed and implemented dual authentication, session-based auto-renewal, cross-platform security, and real-time warning system. Completed a perfect reference for WordPress-Flask security integration.
    

**4. Anti-Bot & Scraping Prevention Research (Future Plan):**

-   **Solutions Researched**:
    
    -   **Flask-based**: `Flask-Limiter` (request rate limiting), User-Agent filtering, IP-based protection (Rate limiting).
        
    -   **Server-level**: `Cloudflare Bot Fight Mode` (DNS-level protection), Header-based detection (browser header verification).
        
-   **Recommended Combination**: Cloudflare (1st layer) → Flask-Limiter (2nd layer) → Custom Bot Detection (3rd layer).
    
-   **Future Plan**: Anti-bot/scraping prevention can be implemented as needed, based on the research.

## 🧠 Key Concepts Learned

-   **Cross-Platform Security System Design & Implementation**: Designed and implemented a multi-layered security authentication system (secret key, token generation/verification, session management) spanning disparate environments like WordPress (PHP) and Flask (Python). This enhanced my ability to manage data flow and authentication across different technology stacks.
    
-   **Practical Problem Solving and System Hardening**: Gained experience in resolving various troubleshooting issues (encoding, WP errors, API conflicts, etc.) encountered during complex security system implementation, which improved the system's stability and robustness. This also enhanced my ability to handle unpredictable problems in real operational environments.
    
-   **Challenges of Design & Optimization under Technical Constraints**: Experienced that specific libraries like `xhtml2pdf` may not fully support modern CSS technologies, leading to unexpected delays in design rework. This highlighted the importance of **in-depth pre-testing of design compatibility and optimization** during the library selection phase, not just functional aspects.
    
-   **Documentation and Scalability for the Future**: Received a directive from the senior developer to document the project's technical aspects (`Site Structure`, `Workflow`, `Languages Used`), recognizing that current implementation is a crucial asset for future maintenance and scalability. Preliminary research into additional security layers like anti-bot/scraping prevention also broadened my perspective on considering system scalability from the outset.

## 💡 Practical Trial-and-Error and Tips

-   **Multi-layered Defense in Security System Design**: Instead of relying on a single authentication method, applying multiple layers of security, such as **dual token verification (MD5 + HMAC), time-based expiration, and POST method data transmission**, is essential for building a much more robust system.
    
-   **Considering User Experience in Session Management**: Even with strict security policies (e.g., 1-hour session limit), implementing a **real-time warning system (`session-guard.js`)** that preemptively alerts users about session expiration and offers auto-renewal opportunities can balance security with user convenience.
    
-   **Thorough CSS Compatibility Testing for PDF Libraries**: When using libraries with fewer external dependencies like `xhtml2pdf`, it's crucial to **thoroughly test in advance whether complex CSS elements used in the actual project are rendered correctly** by that library. Failure to do so can result in unexpectedly high costs for design rework.
    
-   **Importance of Communication**: When reporting progress, it's vital to transparently share not only the status of feature implementation but also **any difficulties encountered (e.g., CSS compatibility issues) and the resulting delays**. This helps the team understand and plan for realistic next steps.

## 🔜 Next Steps

-   **Begin Anti-Bot & Scraping Prevention Implementation**: Based on the research requested by the senior developer, I will begin implementing anti-bot and scraping prevention features for the Flask app.
    
-   **Draft Project Technical Documentation**: Following the senior developer's directive, I will start drafting the technical documentation covering the site structure, workflow, and programming languages/technology stack used.
    
-   **Finalize Flask App & WP Integration Testing**: Once all features are implemented, I will conduct integrated testing for the WP login integration and all Flask app functionalities.

----------

# 📅 1일차 (2025-07-28, 월)

## 🎓 오늘 한 일

**📌 오전 개발 미팅에서 `xhtml2pdf`를 사용한 PDF 보고서 디자인 재작업 완료 상황과 워드프레스(WP) 연동 Flask 앱 보안 시스템 구축 완료 계획을 공유했습니다.**   
**📌 PDF 보고서 디자인 작업을 드디어 완료했지만, `xhtml2pdf`의 CSS 호환성 문제로 인해 예상보다 작업이 지연되었습니다.**   
**📌 워드프레스(WP) 로그인과 연동되는 Flask 대시보드 접근 제어 보안 시스템을 성공적으로 구축하고 시연 후 피드백 받았습니다.**   
**📌 개발 선임으로부터 프로젝트의 기술 문서 작성 지시를 받았으며, 안티봇 및 스크래핑 방지 방법에 대한 추가 리서치 요청을 받았습니다.**  

### 상세 활동

**1. 오전 개발 미팅 요약:**

-   **리포트 프로젝트 진행 상황 보고**:
    
    -   **PDF 모듈 관련 의존성 문제**: cPanel 업로드 시 문제가 없는 `xhtml2pdf` 모듈을 선택하여 최적화 작업을 진행 중임을 보고했습니다.
        
    -   **디자인 재조정의 어려움**: 기존에 완성된 디자인과 구조를 `xhtml2pdf`에 맞춰 조정하는 과정이 길고, 특히 **최신 CSS 기술들이 적용되지 않아 작업이 지연**되었음을 설명했습니다.
        
-   **보안 기능 구현 계획 공유**:
    
    -   **HTTPS 처리**: cPanel 자체적으로 HTTPS(`AutoSSL`)가 적용되어 있음을 확인했습니다.
        
    -   **인증 방식**: 토큰을 생성하여 인증하고, 인증되면 WP에서 Flask 앱으로의 접근을 허용하는 방식임을 설명했습니다.
        
    -   **WP 로그인 연동**: WP 로그인과 연동하여 보안을 적용할 계획임을 밝혔습니다.
        
-   **개발 선임 피드백 및 지시사항**:
    
    -   구현 계획에 대해 "괜찮은 프로세스 같다"고 긍정적으로 평가했습니다.
        
    -   **추가 지시**: 크롤링 봇이나 스크래핑 도구들을 피할 수 있는 방법(예: `robots.txt`, WP 보안 플러그인, WAF, Rate Limiting, CAPTCHA 등)도 알아보라고 요청했습니다.
        
    -   **다음 단계**: 모든 기능이 구현되면 최종 테스트를 진행하기로 했습니다.
        

**2. PDF 보고서 디자인 재작업 완료:**

-   `xhtml2pdf` 라이브러리를 사용하여 PDF 보고서의 디자인을 재작업하는 데 집중했습니다.
    
-   **직면한 문제**: `xhtml2pdf`가 인식하지 못하는 CSS 요소들이 많아 예상보다 작업이 훨씬 더뎠습니다. 간단한 스타일 표현조차도 옛날 문법을 검색하고 적용해야 하는 어려움이 있었습니다.
    
-   **결과**: **드디어 모든 PDF 보고서 디자인 재작업을 완료했습니다.**
    

**3. 워드프레스-Flask 보안 시스템 구축 및 시연:**

-   **프로젝트 개요**: 기존에 URL만 알면 누구나 Flask 대시보드에 접근 가능했던 문제를 해결하고, WordPress 관리자만 안전하게 접근할 수 있는 시스템을 구축하는 것이 목표였습니다.
    
-   **달성한 결과**:
    
    -   WordPress 로그인 연동 완료.
        
    -   1시간 세션 + 자동 갱신 시스템 구현 (POST 방식으로 URL 토큰 노출 방지).
        
    -   실시간 세션 경고 시스템 구축.
        
-   **핵심 보안 구조**:
    
    -   **이중 인증 시스템**: WordPress → [간단한 인증 + JWT 토큰] → Flask → 검증 → 접근 허용.
        
        -   간단한 인증 (`md5($username . $timestamp . $secret_key)`).
            
        -   JWT 스타일 토큰 (`base64_encode($payload . '|||' . $hmac_signature)`).
            
    -   **64자 비밀키 시스템**: WordPress와 Flask가 동일한 비밀키(`SECRET_KEY`)를 공유하며, 토큰 서명/검증의 마스터 키로 사용됩니다.
        
-   **세션 관리 시스템**:
    
    -   **최종 타임라인**: 0분 (초기 인증) → 20분 (⚠️ "10분 남음" 경고) → 30분 (🔄 1차 자동 연장 +15분) → 40분 (⚠️ "5분 남음" 경고) → 45분 (🔄 2차 자동 연장 +15분 [마지막]) → 55분 (🚨 "5분 남음" 최종 경고) → 60분 (💀 무조건 만료 → WordPress 재로그인).
        
    -   **자동 갱신 로직**: 최대 2회 연장 (각 15분씩), 1시간 절대 한계, 활동 기반 갱신.
        
-   **WordPress 구현**:
    
    -   **파일 위치**: `wp-content/themes/siteorigin-unwind/functions.php`.
        
    -   **POST 방식 보안 구현**: `generate_secure_dashboard_link()` 함수를 통해 권한 체크 후 토큰 생성 및 POST 폼 반환.
        
    -   **UI 구현**: `[secure_dashboard]` 숏코드, "New Dashboard" 관리자 메뉴 추가, 리포트 페이지에 버튼 디자인 적용.
        
-   **Flask 구현**:
    
    -   **모듈 구조**: `.env`, `app.py`, `wp_auth.py`, `static/js/session-guard.js`, `templates/index.html`.
        
    -   **`wp_auth.py` 핵심 기능**: MD5 해시 검증, JWT 토큰 검증, 자동 갱신 데코레이터, 세션 상태 API.
        
    -   **`app.py` 적용**: `@wp_auth.require_auto_renewing_auth` 데코레이터를 루트 경로 및 세션 상태 API에 적용.
        
-   **사용자 경고 시스템**:
    
    -   **`session-guard.js` 기능**: 응답 헤더에서 경고 감지, 팝업 표시, 5분마다 세션 상태 체크.
        
    -   **경고 메시지 타입**: 일반 경고(노란색), 최종 경고(빨간색), 만료 모달(전체 화면 오버레이).
        
-   **트러블슈팅 & 해결**:
    
    -   **Unicode 인코딩 오류**: cPanel 서버 이모지 오류 → Flask에서 이모지를 텍스트로 교체.
        
    -   **WordPress Critical Error**: `functions.php` 문법 오류 → 백업 복원 후 단계별 안전 구현.
        
    -   **API 인증 충돌**: 대시보드 JS에서 토큰 없이 API 호출 → 세션 기반 인증으로 변경.
        
    -   **URL 토큰 노출**: GET 방식 민감정보 노출 → POST 방식으로 변경.
        
    -   **404 세션 상태 오류**: JS가 `/api/session_status` 호출 시 Flask에 없음 → `app.py`에 세션 상태 API 추가.
        
-   **최종 보안 수준**:
    
    -   **다층 보안 구조**: WP 로그인 체크, 관리자 권한 확인, 이중 토큰 검증 (MD5 + HMAC), 시간 기반 만료 (1시간 절대 한계), 세션 기반 상태 관리, POST 방식 데이터 전송.
        
    -   **공격 방어 체계**: 브루트 포스(64자 비밀키), 토큰 위조(HMAC-SHA256), 토큰 탈취(1시간 자동 만료), XSS(세션 쿠키만 노출), URL 스니핑(POST 방식).
        
-   **성과 및 완성도**: 완벽한 접근 제어, 사용자 친화적(자동 갱신 + 친절한 경고), URL 보안 달성. 이중 인증, 세션 기반 자동 갱신, 크로스 플랫폼 보안, 실시간 경고 시스템 구축. WordPress-Flask 보안 연동의 완벽한 레퍼런스 완성.
    

**4. 안티봇 & 스크래핑 방지 리서치 (향후 계획):**

-   **조사한 솔루션들**:
    
    -   **Flask 기반**: `Flask-Limiter`(요청 빈도 제한), User-Agent 필터링, IP 기반 보호(Rate limiting).
        
    -   **서버 레벨**: `Cloudflare Bot Fight Mode`(DNS 레벨 보호), 헤더 기반 탐지(브라우저 헤더 검증).
        
-   **권장 조합**: Cloudflare (1차) → Flask-Limiter (2차) → 커스텀 봇 탐지 (3차).
    
-   **향후 계획**: 안티봇/스크래핑 방지는 필요시 리서치한 내용을 바탕으로 언제든 추가 구현 가능합니다.

## 🧠 배운 핵심 개념

-   **크로스 플랫폼 보안 시스템 설계 및 구현**: WordPress(PHP)와 Flask(Python)라는 이질적인 환경을 아우르는 다층 보안 인증 시스템(비밀키, 토큰 생성/검증, 세션 관리)을 설계하고 구현하며, 서로 다른 기술 스택 간의 데이터 흐름 및 인증 관리 역량을 강화했습니다.
    
-   **실전적인 문제 해결 및 시스템 견고화**: 복잡한 보안 시스템 구현 과정에서 발생한 다양한 트러블슈팅(인코딩, WP 오류, API 충돌 등)을 해결하며 시스템의 안정성과 견고성을 높이는 경험을 했습니다. 이는 단순한 기능 구현을 넘어, 실제 운영 환경에서의 예측 불가능한 문제에 대한 대처 능력을 향상시켰습니다.
    
-   **기술적 제약 속 디자인 및 최적화의 어려움**: `xhtml2pdf`와 같은 특정 라이브러리가 최신 CSS 기술을 완벽하게 지원하지 않아 디자인 재작업에 예상보다 많은 시간이 소요됨을 경험했습니다. 이는 기술 선택 시 기능적 측면뿐 아니라 **디자인 호환성 및 최적화에 대한 심층적인 사전 검토**의 중요성을 일깨워 주었습니다.
    
-   **미래를 위한 문서화 및 확장성 고려**: 개발 선임으로부터 프로젝트의 기술 문서화(`Site Structure`, `Workflow`, `Languages Used`) 지시를 받으며, 현재의 구현이 미래의 유지보수 및 확장을 위한 중요한 자산이 됨을 인식했습니다. 또한, 안티봇/스크래핑 방지와 같은 추가 보안 계층에 대한 사전 리서치를 통해 시스템의 확장성을 미리 고려하는 시야를 넓혔습니다.

## 💡 실전 시행착오 및 팁

-   **보안 시스템 설계 시 다층 방어**: 단일 인증 방식에 의존하기보다, **이중 토큰 검증(MD5 + HMAC), 시간 기반 만료, POST 방식 데이터 전송** 등 여러 계층의 보안을 적용하는 것이 훨씬 견고한 시스템을 구축하는 데 필수적입니다.
    
-   **세션 관리의 사용자 경험 고려**: 엄격한 보안 정책(예: 1시간 세션 제한)을 적용하더라도, **실시간 경고 시스템(`session-guard.js`)**을 통해 사용자에게 세션 만료를 미리 알리고 자동 갱신 기회를 제공함으로써 보안과 사용자 편의성 사이의 균형을 맞출 수 있습니다.
    
-   **PDF 라이브러리 CSS 호환성 검증**: `xhtml2pdf`와 같이 외부 의존성이 적은 라이브러리를 사용할 때는, 실제 프로젝트에서 사용할 **복잡한 CSS 요소들이 해당 라이브러리에서 제대로 렌더링되는지 사전에 충분히 테스트**해야 합니다. 그렇지 않으면 디자인 재작업에 예상치 못한 큰 비용이 발생할 수 있습니다.
    
-   **커뮤니케이션의 중요성**: 진행 상황 보고 시, 단순히 기능 구현 여부뿐 아니라 **직면한 어려움(예: CSS 호환성 문제)과 그로 인한 작업 지연 요인**을 투명하게 공유하는 것이 팀의 이해를 돕고 현실적인 다음 계획을 수립하는 데 도움이 됩니다.

## 🔜 다음 학습 방향

-   **안티봇 및 스크래핑 방지 구현 착수**: 개발 선임의 요청에 따라 리서치한 내용을 바탕으로 Flask 앱에 안티봇 및 스크래핑 방지 기능을 구현하기 시작할 것입니다.
    
-   **프로젝트 기술 문서 초안 작성**: 개발 선임의 지시에 따라 프로젝트의 사이트 구조, 워크플로우, 사용된 언어 및 기술 스택에 대한 기술 문서 초안 작성을 시작할 것입니다.
    
-   **Flask 앱 및 WP 통합 최종 테스트**: 모든 기능 구현이 완료되면, WP 로그인 연동 및 Flask 앱의 모든 기능에 대한 통합 테스트를 진행할 것입니다.
