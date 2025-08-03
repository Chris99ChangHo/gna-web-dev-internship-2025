# 📝 Week 12 Reflection (2025.07.29 ~ 08.01)

## ✅ Key Tasks This Week

📌 **Successfully migrated the Flask dashboard from a session-based authentication system to a secure JWT-based one.**   
📌 **Stabilized the application's deployment on cPanel by resolving multiple critical server errors and optimizing resource usage.**   
📌 **Initiated a plan and attempted to implement a multi-language PDF report system with dynamic cover images.**  


## 🧠 What I Learned

-   **Deep Dive into JWT Security**: I learned how to implement a dual-layer security system using `HttpOnly` cookies for Access Tokens to prevent XSS and a separate, non-`HttpOnly` cookie for CSRF tokens to enable the **Double Submit Token** pattern. This taught me the nuance of security trade-offs and the importance of a layered defense.
    
-   **Debugging in Production Environments**: I developed strategies for diagnosing complex issues in restricted hosting environments like cPanel. By analyzing process kill signals (`Child process was killed by signal: 15`), I traced resource overloads back to inefficient API calls and debug mode settings. This experience highlighted the importance of designing for the target environment, not just the development one.


## 🔧 Technical Problem-Solving Experience

-   **CSRF Token Conflict Resolution**: A major problem was a `Missing CSRF token` error caused by `JWT_COOKIE_HTTPONLY = True` inadvertently applying to the CSRF token. I resolved this by explicitly setting `app.config["JWT_CSRF_COOKIE_HTTPONLY"] = False`, which allowed JavaScript to access the CSRF token while keeping the Access Token secure from XSS.
    
-   **Multi-language PDF Generation Failure**: I attempted to solve multi-language font and dynamic image issues in PDF reports by using Base64 encoding. While the encoding itself was successful, the `xhtml2pdf` library failed to render the Base64 data, leading me to conclude that the library itself was the root cause. This problem-solving journey taught me to identify when a technology stack is the limiting factor and that it may be necessary to pivot to an alternative solution like `WeasyPrint`.


## 💡 Reflections

-   **The Project is Never "Done"**: I learned that even after a "completion" milestone, a project enters a new phase of feedback, optimization, and continuous improvement. This week was a clear example of moving from feature implementation to stabilization and enhancement, which is a crucial part of the development lifecycle.
    
-   **The Value of Communication**: Regular meetings and clear directives from senior developers were essential. The feedback I received for a dynamic PDF cover image system and the directive to optimize for performance guided my work and prevented me from getting stuck on less critical tasks.


## 🌱 Points of Improvement & Next Week's Goals

-   **Improvement**: My initial approach of using `xhtml2pdf` to render Base64 content was ultimately a dead end. I need to more quickly assess the capabilities and limitations of third-party libraries before investing significant time in them.
    
-   **Next Week's Goal 1**: Research and begin implementing a more robust PDF generation library, such as `WeasyPrint` or a Headless Chrome-based solution, to correctly render multi-language fonts and dynamic images.
    
-   **Next Week's Goal 2**: Finalize the implementation of the dynamic PDF cover image system using a newly selected library and conduct integrated testing with the WordPress API to ensure all features function as expected.

----------

# 📝 12주차 회고 (2025.07.29 ~ 08.01)

## ✅ 이번 주 주요 작업

📌 **기존 세션 기반 인증 시스템을 안전한 JWT 기반 인증 시스템으로 성공적으로 전환했습니다.**  
📌 **여러 치명적인 서버 오류를 해결하고 리소스 사용을 최적화하여 cPanel 배포 환경에서 애플리케이션을 안정화했습니다.**   
📌 **다국어 PDF 리포트와 동적 커버 이미지 기능을 구현하기 위한 계획을 수립하고 초기 시도를 진행했습니다.**   

## 🧠 배운 핵심 개념

-   **JWT 보안 심화**: XSS를 방지하기 위해 `HttpOnly` 쿠키를 Access Token에 사용하고, CSRF 방어 패턴인 **Double Submit Token**을 위해 CSRF 토큰에는 `HttpOnly`를 적용하지 않는 이중 보안 시스템을 구축하는 방법을 배웠습니다. 이를 통해 보안 트레이드오프의 미묘한 차이와 다층 방어의 중요성을 이해했습니다.
    
-   **운영 환경에서의 디버깅**: cPanel과 같은 제약된 호스팅 환경에서 복잡한 문제를 진단하는 전략을 세웠습니다. 프로세스 킬 신호(`Child process was killed by signal: 15`)를 분석하여 비효율적인 API 호출과 디버그 모드 설정이 리소스 과부하의 원인임을 파악했습니다. 이는 개발 환경뿐 아니라 실제 배포 환경에 맞춰 코드를 설계하는 것의 중요성을 강조합니다.


## 🔧 기술적 문제 해결 경험

-   **CSRF 토큰 충돌 해결**: `JWT_COOKIE_HTTPONLY = True` 설정이 CSRF 토큰에 의도치 않게 적용되어 `Missing CSRF token` 오류가 발생했습니다. `app.config["JWT_CSRF_COOKIE_HTTPONLY"] = False`로 명시적으로 설정하여 JavaScript가 CSRF 토큰에 접근할 수 있도록 하고, Access Token은 안전하게 유지하여 문제를 해결했습니다.
    
-   **다국어 PDF 생성 실패**: 다국어 폰트와 동적 이미지 문제를 해결하기 위해 Base64 인코딩을 시도했지만, `xhtml2pdf` 라이브러리가 Base64 데이터를 렌더링하지 못했습니다. 이를 통해 라이브러리 자체가 문제의 근본 원인이라고 판단하고, `WeasyPrint`와 같은 대안을 모색해야 함을 깨달았습니다.


## 💡 느낀 점

-   **프로젝트는 결코 '완료'되지 않는다**: 프로젝트의 '완료'라는 이정표는 피드백, 최적화, 지속적인 개선의 새로운 단계로 이어집니다. 이번 주는 기능 구현에서 안정화와 개선으로 넘어가는 중요한 전환점이었으며, 이는 개발 라이프사이클의 필수적인 부분임을 배웠습니다.
    
-   **소통의 가치**: 정기적인 미팅과 선임 개발자의 명확한 지시는 매우 중요합니다. 동적 PDF 커버 이미지 시스템에 대한 피드백과 성능 최적화에 대한 지시 덕분에 덜 중요한 작업에 매달리지 않고 핵심 과제에 집중할 수 있었습니다.


## 🌱 아쉬운 점 및 다음 주 목표

-   **아쉬운 점**: `xhtml2pdf`를 이용한 Base64 콘텐츠 렌더링 시도는 결국 실패로 끝났습니다. 앞으로는 서드파티 라이브러리에 많은 시간을 투자하기 전에 그 기능과 한계를 더 빠르게 파악해야 합니다.
    
-   **다음 주 목표 1**: 다국어 폰트와 동적 이미지를 올바르게 렌더링할 수 있는 `WeasyPrint` 또는 Headless Chrome 기반 솔루션과 같은 더 강력한 PDF 생성 라이브러리를 조사하고 구현을 시작할 것입니다.
    
-   **다음 주 목표 2**: 새로 선정한 라이브러리를 사용하여 동적 PDF 커버 이미지 시스템 구현을 완료하고, WordPress API와의 통합 테스트를 진행하여 모든 기능이 예상대로 작동하는지 확인할 것입니다.
