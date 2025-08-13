# 📅 Day 01 (2025-08-11, Mon)

## 🎓 What I Did Today

**📌 Confirmed plans for documentation and a troubleshooting guide in a development meeting, then refined the `README` and developer documentation.**  
**📌 Finalized the transition from a single GA4 property to a "registry-based" structure for integrating GA4 and SERanking data, using a `client_id` as the key.**   
**📌 Concretely designed the backend API, frontend data-fetching logic, and operational guidelines to align with the new registry-based structure.**   
**📌 Organized system-wide improvements, including simplifying the WordPress-Flask authentication flow and clarifying the quality standards for PDF reports.**  

### Detailed Activities

** development meeting**

	-   **Discussion and Agreement**: I reported the status of my documentation to the senior developer. We agreed to add **guidelines that specify which files/folders to check for specific error situations**, to help external developers with maintenance in the future.
	    
	-   **`README` and Developer Docs Refinement**: I explicitly documented the JWT security model, the plan for GA4's multi-tenancy transition, and the crucial rule that a PDF's physical image size is determined by its `mm` units.
	    
	-   **Strengthened the Troubleshooting Guide**: I created a guideline to solve problems using a **`Logs → Likely files → Actions`** flow.

1.  **Finalized GA4/SERanking Integration Structure**
    
    -   **Introduced a "Registry Approach"**: To move away from a single GA4 property dependency, we decided to implement a "registry" in an `instance/clients.json` file. This registry maps `client_id` to both GA4 and SERanking identifiers.
        
    -   **Frontend Logic**: The frontend will continue to use the SERanking site selection flow. When a `site_id` is sent to the server, the backend will use the registry to find the corresponding client's GA4 property and match it automatically.
        
    -   **Backend API Design**:
        
        -   `/api/clients` will return a list of clients based on the registry file.
            
        -   `/api/ga4_data` will be able to receive a `client_id` or `site_id` to find the `ga4_property_id` via the registry.
            
        -   `/api/seranking_data` will operate based on `site_id`, while `generate-pdf-report` will handle all identifiers at once using the `client_id`.
            
2.  **Organized System-Wide Improvements**
    
    -   **WordPress-Flask Security**: We established an `HttpOnly` cookie-based JWT session as the standard. WordPress will now serve only as an "auth gate + link hub." I also created a checklist to inspect issues like session expiration.
        
    -   **PDF Quality Standards**: I finalized the optimal image pixel specifications (e.g., **4,772×3,319px for 300 DPI**) to fit the A3 landscape content box (404×281mm). The new operational policy is to generate images directly at this target resolution rather than upscaling.
        
    -   **`pdf_generator.py` Improvements**: I outlined plans to extend `xhtml2pdf`'s `link_callback` to safely handle local images, stabilize Matplotlib, and improve error logging with detailed records.

## 🧠 Key Concepts Learned

-   **Multi-Tenancy Structure Design**: When planning for service scalability, I learned that centralizing external API identifiers (GA4 `property_id`, SERanking `site_id`) into a **separate, registry file** is far more maintainable and extensible than hardcoding them into the codebase.
    
-   **System Decoupling and Simplification**: To resolve complex integration issues between WordPress and Flask, I realized the key strategy is to **clearly separate the roles of each system** (e.g., "auth gate" vs. "data processing engine") and remove unnecessary features (like WordPress directly reading server files) to simplify the overall architecture.

## 💡 Practical Trial-and-Error and Tips

-   **Frontend-Backend Data Matching**: To handle the scenario where the frontend only has a SERanking `site_id` but needs GA4 data, I designed a solution where the backend adds a utility function to **perform a reverse mapping from `site_id` to `client_id`** using the registry. This keeps the frontend logic simple and clean.
    
-   **Separating Configuration**: It's better to manage dynamic, client-specific data (like client IDs) in a **version-controlled configuration file (`.gitignore`)** than in environment variables. Environment variables should be reserved for static, system-wide flags (e.g., `GA4_MULTI_TENANT`), which makes the system more flexible and secure.

## 🔜 Next Steps

-   Create the `instance/clients.json` file, seed it with the first few clients, and configure the `.env` file to enable multi-tenant mode.
    
-   Reflect the registry-based patches in the backend API endpoints and integrate them with the frontend's client dropdown.
    
-   Regenerate the cover and back cover source images to the confirmed high-quality pixel dimensions (4,772×3,319px) and finalize documentation synchronization.


# 📅 Day 01 (2025-08-11, 월)

## 🎓 오늘 한 일

**📌 개발 미팅에서 문서화 및 문제 해결 가이드 작성 계획을 확정하고, README와 개발 문서를 정비했습니다.**  
**📌 GA4와 SERanking 데이터 연동 방식을 단일 프로퍼티에서 `client_id` 기반의 "레지스트리 방식"으로 전환하는 구조를 최종 확정했습니다.**   
**📌 확정된 구조에 맞춰 백엔드 API, 프런트엔드 데이터 호출 로직, 운영 가이드라인을 구체적으로 설계했습니다.**   
**📌 WordPress와 Flask의 인증 플로우를 단순화하고 PDF 리포트 품질 기준을 명확히 하는 등 시스템 전반의 개선 방향을 정리했습니다.**  

### 상세 활동

**개발 미팅**

	- 논의 및 합의: 개발 선임과 문서화 현황을 공유하고, 외부 인력이 쉽게 유지보수할 수 있도록 에러 상황에 따른 파일/폴더 가이드라인을 추가하기로 합의했습니다.

	- README 및 개발 문서 정비: JWT 보안 모델, GA4의 멀티테넌시 전환 계획, PDF 이미지의 물리적 크기 결정 규칙(mm 단위 우선)을 명확히 명시했습니다.

	- 트러블슈팅 가이드 강화: 에러 발생 시 Logs → Likely files → Actions 흐름으로 문제를 해결하는 가이드라인을 작성했습니다.

1.  **GA4/SERanking 연동 구조 확정**
    
    -   **"레지스트리 방식" 도입**: 단일 GA4 프로퍼티 의존성을 해소하기 위해, `instance/clients.json` 파일에 `client_id`를 기반으로 GA4와 SERanking 식별자를 매핑하는 "레지스트리"를 도입하기로 결정했습니다.
        
    -   **프런트엔드 동작 원칙**: 프런트엔드는 기존처럼 SERanking 사이트를 선택하는 흐름을 유지하되, 선택된 `site_id`를 서버에 전달하면 백엔드가 레지스트리에서 해당 클라이언트의 GA4 property를 찾아 매칭하는 방식으로 동작하도록 설계했습니다.
        
    -   **백엔드 API 설계**:
        
        -   `/api/clients`는 레지스트리 파일 기반의 클라이언트 목록을 반환합니다.
            
        -   `/api/ga4_data`는 `client_id`를 받거나 `site_id`를 받아 레지스트리에서 `ga4_property_id`를 찾아 데이터를 조회합니다.
            
        -   `/api/seranking_data`는 `site_id`를 기준으로 동작하고, `generate-pdf-report`는 `client_id`를 통해 모든 식별자를 일괄 처리하도록 변경했습니다.
            
2.  **시스템 전반의 개선 방향 정리**
    
    -   **WordPress-Flask 보안**: `HttpOnly` 쿠키 기반의 JWT 세션 유지 방식을 표준으로 확립하고, WordPress는 "인증 게이트 + 링크 허브" 역할만 하도록 단순화했습니다. 세션 만료 등의 이슈를 점검할 체크리스트도 수립했습니다.
        
    -   **PDF 품질 기준**: A3 가로(404×281mm) 콘텐츠 박스에 맞춘 최적 이미지 픽셀 규격(예: 300DPI 기준 4,772×3,319px)을 확정했습니다. 이미지 업스케일링 대신, 생성 단계에서 목표 픽셀로 바로 만드는 운영 방침을 세웠습니다.
        
    -   **`pdf_generator.py` 개선**: `xhtml2pdf`의 `link_callback`을 확장해 로컬 이미지도 안전하게 처리하고, Matplotlib의 안정성을 강화하며, 에러 로깅을 상세히 기록하는 등의 개선안을 구체화했습니다.

## 🧠 배운 핵심 개념

-   **멀티테넌시 구조 설계**: 서비스 확장성을 고려할 때, 외부 API의 식별자(GA4 `property_id`, SERanking `site_id`)를 코드에 하드코딩하는 대신, **별도의 레지스트리 파일로 중앙 집중화하여 관리하는 방식**이 유지보수와 확장성 측면에서 훨씬 유리하다는 것을 배웠습니다.
    
-   **시스템 분리와 단순화**: WordPress와 Flask 간의 복잡한 연동 문제를 해결하기 위해 **각 시스템의 역할을 "인증 게이트"와 "데이터 처리 엔진"으로 명확히 분리**하고, 불필요한 기능(WP의 서버 파일 직접 읽기 등)을 제거하여 전체 구조를 단순화하는 것이 안정성을 높이는 핵심 전략임을 깨달았습니다.

## 💡 실전 시행착오 및 팁

-   **프런트-백엔드 데이터 매칭**: 프런트엔드가 SERanking `site_id`만으로 GA4 데이터를 요청해야 하는 상황에서, 서버가 레지스트리를 통해 **`site_id`에서 `client_id`로 역방향 매핑**하는 유틸리티 함수를 추가함으로써, 프런트엔드 로직의 복잡성을 최소화할 수 있었습니다.
    
-   **환경변수와 설정 파일의 역할 분담**: 서비스에 따라 달라지는 동적 데이터(클라이언트 ID)는 환경변수 대신 **버전 관리에서 제외되는 설정 파일(`.gitignore`)**로 관리하고, 시스템 전반에 영향을 미치는 정적 설정(예: `GA4_MULTI_TENANT` 플래그)만 환경변수로 관리하는 것이 안전하고 유연한 방식임을 정리했습니다.

## 🔜 다음 계획

-   `instance/clients.json` 파일을 생성하고 초기 클라이언트 데이터를 시드한 후, `.env` 파일을 설정하여 멀티테넌트 모드를 활성화할 것입니다.
    
-   백엔드 API 엔드포인트에 레지스트리 기반 패치를 반영하고, 프런트엔드 드롭다운과 연동하는 작업을 진행할 것입니다.
    
-   커버/백커버 원본 이미지 리소스를 확정된 고품질 픽셀(4,772×3,319px)로 재생성하고, 문서 동기화 작업을 완료할 것입니다.

