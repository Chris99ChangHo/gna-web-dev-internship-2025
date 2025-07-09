# 📅 Day 01 (2025-07-07, Mon)

## 🎓 What I Did Today

**📌 Participated in the morning development meeting, providing updates on the Shopify product data migration project, specifically addressing the need for automated image uploads.**  
**📌 Received a new directive to link a previously proposed marketing strategy idea with the company's existing marketing material creation program, with a mandate to develop an automated prototype.**  
**📌 Integrated and refined Python scripts for automated Shopify product description migration, covering `outerHTML` scraping, Shopify product description updates, and Shopify Files image uploads, ensuring a robust, self-contained migration workflow.**    
**📌 Progressed significantly on the Google Analytics 4 (GA4) dashboard project, successfully authenticating with the GA4 Data API, resolving metric naming errors, and setting up a personal GA4 property for data collection, verifying live data flow.**   

### Detailed Activities

**1. Morning Development Meeting & New Project Directives:** The day started with a development meeting where ongoing project statuses were reviewed and new, strategic tasks were assigned.

-   **Shopify Product Data Migration Update:**
    
    -   Reported that all **product data (text, price, etc.) from `www.melbmarket.com.au` (Wix) has been successfully scraped (`outerHTML`) and migrated to Shopify via API.**
        
    -   Identified a critical issue: **images were not automatically saved to Shopify's media backend** as initially expected when only product descriptions were migrated.
        
    -   Confirmed the necessity for **dedicated automated image upload code** to transfer images directly to Shopify's CDN. The development team concurred that this is a standard and essential process, and the immediate priority is to complete this image upload automation.
        
-   **New Marketing Strategy & Automation Project:**
    
    -   Received a directive to **link a marketing strategy idea** I previously presented with the company's **existing client marketing material creation program.**
        
    -   The CEO specifically mandated the development of an **automated prototype** that incorporates my ideas and adds automation features to the existing program.
        
    -   This new project is scheduled to **commence immediately after the completion of the Shopify image upload automation.**
        

**2. Consolidated Shopify Product Information Migration Automation:** A significant portion of the day was dedicated to structuring and refining the Python scripts for the Melbourne Market Shopify migration.

-   **Integrated Migration Workflow:** Consolidated three key Python scripts (`melb-scrape-html-images.py`, `upload-description-automation.py`, `upload-image-automation.py`) to create a comprehensive, automated workflow for migrating product information (text descriptions and images) from Wix-based websites like `melbmarket.com.au` to a Shopify store.
    
-   **Ensuring Data Integrity:** This integrated system is designed to ensure product information and images remain fully intact on the Shopify store, even if the original Wix site becomes unavailable.
    
-   **Core Functionality Breakdown:**
    
    -   **`melb-scrape-html-images.py` (Web Scraping):**
        
        -   **Purpose:** Extracts detailed text descriptions and embedded images from Wix product pages.
            
        -   **Technology:** Python, Selenium, ChromeDriver, BeautifulSoup, requests.
            
        -   **Key Features:** Handles **dynamic content loading** (PageDown, scroll to bottom) to ensure all elements are captured. Implements **robust HTML cleaning** (removing unnecessary `<br>` tags, specific `<span>` elements, duplicate text content inherent to Wix structures, preserving `style` attributes like font color). Downloads images locally and generates Shopify-compatible HTML. Tracks URL scraping success/failure. Allows for targeted re-scraping of specific URLs.
            
    -   **`upload-description-automation.py` (Shopify Product Description Update):**
        
        -   **Purpose:** Applies scraped HTML descriptions to the `body_html` field of Shopify products.
            
        -   **Technology:** Python, `shopify` (Shopify REST Admin API client), `tqdm`.
            
        -   **Key Features:** Integrates with Shopify Admin API. Efficiently retrieves large product lists using **`since_id` based pagination**. Filters products by inventory quantity (non-zero) to prevent unnecessary API calls. Matches products based on normalized names for accurate updates. Provides detailed logging.
            
    -   **`upload-image-automation.py` (Shopify Files Image Upload):**
        
        -   **Purpose:** Uploads locally saved images to Shopify's CDN (Content Delivery Network) via Shopify Files for stable image hosting.
            
        -   **Technology:** Python, `gql` (GraphQL client), `requests`, `tenacity`, `tqdm`.
            
        -   **Key Features:** Utilizes **Shopify GraphQL Admin API** for efficient image uploads. Implements a **two-step "Staged Upload" process**: requesting a signed URL from Shopify for direct cloud storage upload, then uploading the image to that URL, and finally registering it with Shopify Files. Includes **retry logic (`tenacity`)** for network stability and **duplicate upload prevention** via a tracking CSV. Processes images in batches to respect API rate limits.
            

**3. GA4 Dashboard Project Problem Solving & Progress:** Focused on resolving critical issues blocking the GA4 dashboard data retrieval.

-   **GA4 API Authentication Success:**
    
    -   Resolved the persistent `API Error: The file ... client_secret.json does not have a valid type. Type is None` by explicitly passing authentication information via `InstalledAppFlow` to `BetaAnalyticsDataClient` in `app.py`.
        
    -   Overcame the `403 access_denied` error by adding my Google account as a 'test user' in the Google Cloud Console's OAuth consent screen.
        
    -   Successfully completed the browser authentication process when the Flask server ran, leading to correct `credentials.json` file generation and usage.
        
    -   Confirmed successful backend communication with the GA4 API via `GET /api/ga4_data ... 200` log messages.
        
-   **GA4 API Metric Name Correction:**
    
    -   Addressed the `API Error: 400 Did you mean newUsers? Field views is not a valid metric.` by correcting the metric name from `Metric(name="views")` to `Metric(name="screenPageViews")` in `app.py`, which is the correct GA4 metric for page/screen views.
        
-   **GA4 Demo Account API Access Restriction:**
    
    -   Encountered a `429 This property is denied access to the API.` error due to API access policy limitations on GA4 demo accounts (e.g., Google Merchandise Store).
        
    -   **Strategized to switch to a personal GA4 property** to bypass this restriction.
        
-   **Personal GA4 Property Setup & Tag Configuration:**
    
    -   Created a simple HTML test webpage (`my_test_site/index.html`) to collect GA4 data.
        
    -   Created a new GA4 property and accurately embedded its 'Measurement ID (G-XXXXXXXXXX)' into the HTML file.
        
    -   Configured the website URL as `http://localhost:5500` in the GA4 admin data stream settings.
        
    -   **Crucially, verified successful data collection** as 'Realtime Report' in Google Analytics detected traffic (2 active users) from my test webpage, confirming correct GA4 tag setup.
        
-   **Current Issue: Dashboard Displays Zeroes:**
    
    -   Despite real-time GA4 data, the frontend dashboard still showed 'Total Sessions 0', 'Total Users 0'.
        
    -   Suspected causes: `GA4_PROPERTY_ID` in `.env` not updated to the new personal GA4 property's numerical ID, or the dashboard's date range being set too far in the past (e.g., 2025-05-31 ~ 2025-06-29), as data only started accumulating today.
        
    -   **Next Steps for Resolution:** Full Flask server restart (for env variable application) and adjusting the frontend dashboard's date range to reflect current data (e.g., today or last 7 days).
        

## 🧠 Key Concepts Learned

-   **Advanced Web Scraping for Dynamic Content:** Deepened expertise in using Selenium for dynamic content loading, specifically handling Wix's complex JavaScript-driven page structures (e.g., repeated `PAGE_DOWN`, scroll to bottom logic) and performing in-browser HTML cleaning via injected JavaScript.
    
-   **Robust Shopify API Integration for Data & Media:** Gained comprehensive understanding of Shopify's Admin API for bulk product updates and, more critically, its **GraphQL Staged Uploads for direct image hosting to Shopify Files (CDN)**. This involved mastering a multi-step upload process and handling different HTTP request types (PUT vs. POST).
    
-   **API Rate Limit Management & Pagination:** Solidified practical techniques for managing API rate limits through strategic `time.sleep()` intervals and efficient data retrieval using `since_id` based pagination for large datasets.
    
-   **GA4 Data API Authentication & Metrics:** Successfully navigated complex Google API authentication flows (OAuth, `InstalledAppFlow`, test users), corrected GA4 metric naming conventions, and understood the nuances of GA4 demo account API access policies versus personal property data collection.
    
-   **Full-Stack Data Flow Validation:** Practiced end-to-end data validation from frontend GA4 tag setup (verified by Realtime reports) to backend API calls, troubleshooting common issues at each stage.
    

## 💡 Practical Trial-and-Error and Tips

-   **Dynamic Content Scraping - Persistence is Key:** When dealing with heavily JavaScript-driven sites like Wix, simply loading the page is insufficient. Persistent scrolling (e.g., `PAGE_DOWN` loops until no new content loads) and strategic waits (`time.sleep`, `WebDriverWait`) are crucial for complete data capture.
    
-   **In-Browser HTML Cleaning:** For complex or messy HTML structures (like Wix's), injecting JavaScript via `driver.execute_script()` for direct DOM manipulation and cleaning can be far more effective and precise than post-processing with BeautifulSoup in Python. This is especially true for removing duplicate text nodes or specific problematic elements.
    
-   **Shopify Image Hosting is Non-Negotiable:** Never assume images within scraped HTML will automatically be hosted by Shopify. A dedicated process to upload all images directly to Shopify's backend (via GraphQL Staged Uploads) and update `src` links to Shopify's CDN is vital for long-term data stability and avoiding broken images.
    
-   **GA4 API - Own Your Data:** For development and testing, relying on GA4 demo accounts for API access is often problematic due to restrictions. Creating and using your own GA4 property (even with a simple test page) is the most reliable way to develop and test GA4 data integration.
    
-   **Environment Variable Best Practices:** Always remember to fully restart your server application (e.g., Flask) after updating environment variables (`.env` file) to ensure changes are correctly loaded and applied.
    

## 🔜 Next Steps

-   **Complete Shopify Image Upload Automation:** Finalize and execute the dedicated image upload script for the Melbourne Market migration, ensuring all images are successfully transferred to Shopify Files and their CDN links are correctly updated in product descriptions.
    
-   **Begin Marketing Automation Prototype Development:** Immediately commence work on the new project to link marketing strategy ideas with the existing marketing material creation program, focusing on automation and prototype development.
    
-   **Finalize GA4 Dashboard Data Display:** Debug the current issue of zero data on the dashboard by ensuring correct `GA4_PROPERTY_ID` in `.env` and adjusting the frontend date range to reflect recent data from the personal GA4 property.
    
-   **Client One-Page Website Finalization:** Address any remaining feedback for the "Kisa Sikdang" website and prepare for its final deployment.
    
-   **Continue DevNewsHub Mini-Project Development:** As time permits, resume further development on both the WordPress website and the React Native/Expo app, based on previous feedback.
    
-   **Intensify AI Security Threat Research & PPT Preparation:** Continue in-depth research and preparation for the presentation on "The Evolution of Hacking, Scams, and Spamming Using AI — and Its Impact on Server Security," scheduled for **Thursday, July 10, 2025**.
    

----------

# 📅 1일차 (2025-07-07, 월)

## 🎓 오늘 한 일

**📌 오전 개발 미팅에 참여하여 Shopify 상품 정보 마이그레이션 진행 상황을 공유하고, 이미지 업로드 자동화의 필요성을 보고했습니다.**   
**📌 과거 발표에서 제안했던 마케팅 전략 아이디어와 현재 회사에서 제공 중인 마케팅 자료 제작 프로그램을 연계하여 자동화된 프로토타입을 개발하라는 새로운 지시를 받았습니다.**  
**📌 Wix 사이트 상품 정보를 Shopify로 마이그레이션하는 자동화된 Python 스크립트(outerHTML 스크래핑, Shopify 상품 설명 업데이트, Shopify Files 이미지 업로드)를 통합하고 개선하여 견고한 마이그레이션 워크플로우를 구축했습니다.**   
**📌 Google Analytics 4 (GA4) 대시보드 프로젝트에서 중요한 진전을 이루어, GA4 Data API 인증에 성공하고 지표 이름 오류를 해결했으며, 개인 GA4 속성을 설정하여 실시간 데이터 흐름을 확인했습니다.**   

### 상세 활동

**1. 오전 개발 미팅 및 신규 프로젝트 지시:** 하루는 개발 미팅으로 시작되었고, 진행 중인 프로젝트 현황을 검토하고 새로운 전략적 업무를 배정받았습니다.

-   **Shopify 상품 데이터 마이그레이션 업데이트:**
    
    -   `www.melbmarket.com.au` (Wix) 사이트의 **모든 상품 정보(텍스트, 가격 등)가 스크래핑(outer HTML)되어 Shopify API로 성공적으로 마이그레이션되었음**을 보고했습니다.
        
    -   중요한 문제점을 확인했습니다: 상품 설명만 마이그레이션했을 때 **이미지가 Shopify의 미디어 백엔드에 자동으로 저장되지 않았습니다.**
        
    -   이미지를 Shopify CDN으로 직접 전송하기 위한 **전용 자동 이미지 업로드 코드의 필요성**을 확인했습니다. 개발팀에서도 이것이 표준적이고 필수적인 프로세스라고 동의했으며, 이 이미지 업로드 자동화를 최우선으로 완료하기로 결정했습니다.
        
-   **새로운 마케팅 전략 및 자동화 프로젝트:**
    
    -   과거에 제가 제안했던 **마케팅 전략 아이디어**를 회사에서 현재 제공 중인 **클라이언트 마케팅 자료 제작 프로그램과 연계**하라는 지시를 받았습니다.
        
    -   사장님께서 직접, 제 아이디어를 반영하고 자동화 기능을 추가하여 **프로토타입을 개발**하라고 지시하셨습니다.
        
    -   이 새로운 프로젝트는 **Shopify 이미지 업로드 자동화 작업 완료 즉시 착수**할 예정입니다.
        

**2. Shopify 상품 정보 마이그레이션 자동화 코드 통합 정리:** 하루의 상당 부분을 멜번 마켓 Shopify 마이그레이션을 위한 Python 스크립트 구조화 및 개선에 할애했습니다.

-   **통합된 마이그레이션 워크플로우:** 세 가지 핵심 Python 스크립트(`melb-scrape-html-images.py`, `upload-description-automation.py`, `upload-image-automation.py`)를 통합하여 `melbmarket.com.au`와 같은 Wix 기반 웹사이트에서 Shopify 스토어로 상품 정보(텍스트 설명 및 이미지)를 마이그레이션하는 포괄적인 자동화 워크플로우를 구축했습니다.
    
-   **데이터 무결성 보장:** 이 통합 시스템은 원본 Wix 사이트가 사라지더라도 Shopify 스토어의 상품 정보와 이미지가 온전히 유지되도록 설계되었습니다.
    
-   **핵심 기능 요약:**
    
    -   **`melb-scrape-html-images.py` (웹 스크래핑):**
        
        -   **목적:** Wix 상품 페이지에서 상세 텍스트 설명 및 포함된 이미지를 추출합니다.
            
        -   **기술:** Python, Selenium, ChromeDriver, BeautifulSoup, requests.
            
        -   **주요 기능:** **동적 콘텐츠 로딩**을 처리하여(PageDown, 최하단 스크롤 로직) 모든 요소를 캡처합니다. **정교한 HTML 클리닝**을 구현합니다(불필요한 `<br>` 태그, 특정 `<span>` 요소, Wix 구조의 특성상 중복되는 텍스트 콘텐츠 제거, 글자 색상과 같은 `style` 속성 유지). 이미지를 로컬에 다운로드하고 Shopify 호환 HTML을 생성합니다. URL 스크래핑 성공/실패를 추적합니다. 특정 URL만 선택적으로 다시 스크래핑할 수 있습니다.
            
    -   **`upload-description-automation.py` (Shopify 상품 설명 업데이트):**
        
        -   **목적:** 스크래핑된 HTML 설명을 Shopify 상품의 `body_html` 필드에 적용합니다.
            
        -   **기술:** Python, `shopify` (Shopify REST Admin API 클라이언트), `tqdm`.
            
        -   **주요 기능:** Shopify Admin API와 연동합니다. **`since_id` 기반 페이지네이션**을 사용하여 대량의 상품 목록을 효율적으로 가져옵니다. 재고 수량(0이 아닌)으로 상품을 필터링하여 불필요한 API 호출을 방지합니다. 정규화된 상품명을 기반으로 상품을 매칭하여 업데이트 대상을 식별합니다. 상세 로깅을 제공합니다.
            
    -   **`upload-image-automation.py` (Shopify Files 이미지 업로드):**
        
        -   **목적:** 로컬에 저장된 이미지를 Shopify Files를 통해 Shopify CDN(콘텐츠 전송 네트워크)에 업로드하여 안정적인 이미지 호스팅을 확보합니다.
            
        -   **기술:** Python, `gql` (GraphQL 클라이언트), `requests`, `tenacity`, `tqdm`.
            
        -   **주요 기능:** 효율적인 이미지 업로드를 위해 **Shopify GraphQL Admin API**를 활용합니다. **두 단계 "Staged Upload" 프로세스**를 구현합니다: Shopify로부터 클라우드 스토리지 직접 업로드용 서명된 URL을 요청하고, 해당 URL로 이미지를 업로드한 다음, Shopify Files에 등록합니다. 네트워크 안정성을 위한 **재시도 로직(`tenacity`)**을 포함하고, 추적 CSV를 통해 **중복 업로드를 방지**합니다. API 요청 제한을 준수하기 위해 이미지를 배치 단위로 처리합니다.
            

**3. GA4 대시보드 프로젝트 문제 해결 및 진행 상황:** GA4 대시보드 데이터 검색을 방해하는 중요한 문제 해결에 집중했습니다.

-   **GA4 API 인증 성공:**
    
    -   기존의 `API Error: The file ... client_secret.json does not have a valid type. Type is None` 오류를 `app.py`에서 `InstalledAppFlow`를 통해 `BetaAnalyticsDataClient`에 인증 정보를 명시적으로 전달하여 해결했습니다.
        
    -   Google Cloud Console의 OAuth 동의 화면에서 제 Google 계정을 '테스트 사용자'로 추가하여 `403 access_denied` 오류를 극복했습니다.
        
    -   Flask 서버 실행 시 브라우저 인증 과정이 성공적으로 완료되었고, `credentials.json` 파일도 정상적으로 생성 및 사용되었습니다.
        
    -   `GET /api/ga4_data ... 200` 터미널 로그 메시지를 통해 백엔드가 GA4 API와 성공적으로 통신했음을 확인했습니다.
        
-   **GA4 API 지표 이름 오류 수정:**
    
    -   `API Error: 400 Did you mean newUsers? Field views is not a valid metric.` 오류를 해결하기 위해 `app.py`에서 지표 이름을 `Metric(name="views")`에서 GA4의 올바른 페이지/화면 조회수 지표인 `Metric(name="screenPageViews")`로 수정했습니다.
        
-   **GA4 데모 계정 API 접근 제한 문제 직면:**
    
    -   GA4 데모 계정(예: Google Merchandise Store)의 API 접근 정책 제한으로 인해 `429 This property is denied access to the API.` 오류가 발생했습니다.
        
    -   이 제한을 우회하기 위해 **개인 GA4 속성으로 전환하는 전략**을 세웠습니다.
        
-   **개인 GA4 속성 설정 및 태그 구성:**
    
    -   GA4 데이터를 수집할 간단한 HTML 테스트 웹페이지(`my_test_site/index.html`)를 생성했습니다.
        
    -   새로운 GA4 속성을 만들고, 해당 속성의 '측정 ID (G-XXXXXXXXXX)'를 HTML 파일에 정확히 삽입하여 웹페이지에서 데이터가 수집되도록 설정했습니다.
        
    -   GA4 관리자 페이지의 데이터 스트림 설정에서 웹사이트 URL을 `http://localhost:5500`으로 설정하도록 안내했습니다.
        
    -   **결정적으로, Google Analytics '실시간 보고서'에서 제 테스트 웹페이지의 트래픽(활성 사용자 2명)이 성공적으로 감지됨을 확인하여 GA4 태그 설정이 완벽하게 작동함을 확인했습니다.**
        
-   **현재 문제: 대시보드에 0 표시:**
    
    -   GA4 실시간 보고서에는 데이터가 보이지만, 프론트엔드 대시보드에는 여전히 '총 세션 0', '총 사용자 0'으로 표시되고 있습니다.
        
    -   가장 유력한 원인은 `.env` 파일의 `GA4_PROPERTY_ID`가 새로 만든 개인 GA4 속성의 '속성 ID(순수 숫자)'로 정확히 업데이트되지 않았거나, 대시보드의 날짜 범위가 너무 과거로 설정되어 데이터가 0으로 나올 가능성입니다(예: 2025-05-31 ~ 2025-06-29).
        
    -   **해결을 위한 다음 단계:** Flask 서버를 완전히 종료했다가 다시 시작하고(환경 변수 적용을 위해), 프론트엔드 대시보드의 날짜 범위를 현재 데이터가 쌓이고 있는 시점(예: 오늘 또는 최근 7일)으로 조정하는 것입니다.
        

## 🧠 배운 핵심 개념

-   **동적 콘텐츠를 위한 고급 웹 스크래핑:** Wix의 복잡한 JavaScript 기반 페이지 구조(예: 반복적인 `PAGE_DOWN`, 최하단 스크롤 로직)를 처리하고, 주입된 JavaScript를 통해 브라우저 내 HTML 클리닝을 수행하는 등 Selenium 사용에 대한 전문성을 심화했습니다.
    
-   **데이터 및 미디어를 위한 견고한 Shopify API 통합:** 대량 상품 업데이트를 위한 Shopify Admin API와 특히 **Shopify Files(CDN)에 직접 이미지를 호스팅하기 위한 GraphQL Staged Uploads**에 대한 포괄적인 이해를 얻었습니다. 이는 다단계 업로드 프로세스 및 다른 HTTP 요청 유형(PUT vs. POST) 처리를 포함합니다.
    
-   **API 요청 제한 관리 및 페이지네이션:** 전략적인 `time.sleep()` 간격 및 대규모 데이터 세트를 위한 `since_id` 기반 페이지네이션을 사용한 효율적인 데이터 검색을 통해 API 요청 제한을 관리하는 실용적인 기술을 확고히 했습니다.
    
-   **GA4 Data API 인증 및 지표:** 복잡한 Google API 인증 흐름(OAuth, `InstalledAppFlow`, 테스트 사용자)을 성공적으로 탐색하고, GA4 지표 명명 규칙을 수정했으며, GA4 데모 계정 API 접근 정책과 개인 속성 데이터 수집의 미묘한 차이를 이해했습니다.
    
-   **풀스택 데이터 흐름 유효성 검사:** 프론트엔드 GA4 태그 설정(실시간 보고서로 확인)부터 백엔드 API 호출에 이르기까지 종단 간 데이터 유효성 검사를 수행하고, 각 단계에서 발생하는 일반적인 문제를 해결하는 연습을 했습니다.
    

## 💡 실전 시행착오 및 팁

-   **동적 콘텐츠 스크래핑 - 끈기가 핵심:** Wix와 같이 JavaScript에 크게 의존하는 사이트를 다룰 때는 단순히 페이지를 로드하는 것만으로는 불충분합니다. 숨겨진 콘텐츠가 로드될 때까지 페이지를 계속 스크롤하는 것(예: `PAGE_DOWN` 루프)과 전략적인 대기 시간(`time.sleep`, `WebDriverWait`)이 완전한 데이터 캡처에 필수적입니다.
    
-   **브라우저 내 HTML 클리닝:** Wix와 같이 복잡하거나 지저분한 HTML 구조의 경우, `driver.execute_script()`를 통해 JavaScript를 주입하여 직접 DOM을 조작하고 클리닝하는 것이 Python에서 BeautifulSoup으로 후처리하는 것보다 훨씬 효과적이고 정밀할 수 있습니다. 이는 중복 텍스트 노드나 특정 문제 요소를 제거하는 데 특히 그렇습니다.
    
-   **Shopify 이미지 호스팅은 필수:** 스크래핑된 HTML 내의 이미지가 Shopify에 자동으로 호스팅될 것이라고 가정해서는 안 됩니다. 모든 이미지를 Shopify 백엔드에 직접 업로드(GraphQL Staged Uploads를 통해)하고 `src` 링크를 Shopify CDN으로 업데이트하는 전용 프로세스는 장기적인 데이터 안정성과 깨진 이미지 방지를 위해 필수입니다.
    
-   **GA4 API - 자신의 데이터를 소유하라:** 개발 및 테스트를 위해 GA4 데모 계정에 API 접근을 의존하는 것은 제한으로 인해 문제가 되는 경우가 많습니다. 자신만의 GA4 속성(간단한 테스트 페이지라도)을 만들고 사용하는 것이 GA4 데이터 통합을 개발하고 테스트하는 가장 신뢰할 수 있는 방법입니다.
    
-   **환경 변수 모범 사례:** 환경 변수(`.env` 파일)를 업데이트한 후에는 변경 사항이 올바르게 로드되고 적용되도록 항상 서버 애플리케이션(예: Flask)을 완전히 다시 시작해야 합니다.
    

## 🔜 다음 학습 방향

-   **Shopify 이미지 업로드 자동화 완료:** 멜번 마켓 마이그레이션을 위한 전용 이미지 업로드 스크립트를 최종적으로 다듬고 실행하여, 모든 이미지가 Shopify Files로 성공적으로 전송되고 상품 설명 내 CDN 링크가 올바르게 업데이트되도록 할 것입니다.
    
-   **마케팅 자동화 프로토타입 개발 착수:** 마케팅 전략 아이디어를 기존 마케팅 자료 제작 프로그램과 연계하는 새로운 프로젝트에 즉시 착수하여, 자동화 및 프로토타입 개발에 집중할 것입니다.
    
-   **GA4 대시보드 데이터 표시 최종 마무리:** `.env` 파일의 `GA4_PROPERTY_ID`를 확인하고 프론트엔드 날짜 범위를 개인 GA4 속성의 최신 데이터를 반영하도록 조정하여 대시보드에 0이 표시되는 현재 문제를 디버깅할 것입니다.
    
-   **클라이언트 원페이지 웹사이트 최종 마무리:** "기사식당" 웹사이트에 대한 남은 피드백을 반영하고 최종 배포를 준비할 것입니다.
    
-   **Continue DevNewsHub Mini-Project Development:** 시간이 허락하는 대로 워드프레스 웹사이트 및 React Native/Expo 앱의 추가 개발을 이전 피드백을 바탕으로 계속 이어나갈 것입니다.
    
-   **AI 보안 위협 리서치 및 PPT 준비 심화:** 2025년 7월 10일 마감일을 앞두고 CPanel/WHM 서버 보안 영향을 중심으로 "AI를 활용한 해킹, 스캠, 스팸의 진화 — 그리고 서버 보안에 미치는 영향" 발표 자료에 대한 심층 리서치 및 준비를 계속할 것입니다.
