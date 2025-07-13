# 📅 Day 04 (2025-07-10, Thu)

## 🎓 What I Did Today

**📌 Participated in the morning development meeting, reporting on the progress of the report project and stating the plan to prioritize Wix element removal in Melbourne Market after presentation prep.**     
**📌 Confirmed task priorities with the development lead: PPT presentation → Melbourne Market migration → Report project.**   
**📌 In the morning, I completed the originally scheduled PPT, then revised the 'Open-Source CMS vs. Web Builders Script: Comparative Analysis & Practical AI Integration' presentation after a schedule change.**     
**📌 In the afternoon, I modified and immediately began executing the Melbourne Market product information migration code, reaching 68% completion before pausing the process to resume and finalize it the following day.**    

### Detailed Activities

**1. Today's Development Meeting Highlights:**

-   **Report Project Status:** Reported that the report-related project is currently progressing without significant issues, with actual testing planned to commence after presentation preparations are complete.
    
-   **Wix Element Removal Priority:** Shared the plan to immediately begin the task of removing Wix elements from Melbourne Market product information once the presentation preparation is finalized, as it's the top priority.
    
-   **Confirmed Task Priorities:** Following the development lead's instruction, the work sequence was confirmed as:
    
    1.  **PPT Presentation Preparation** (for the 'Open-Source CMS vs. Web Builders' topic, which had received previous feedback)
        
    2.  **Melbourne Market** (product migration and Wix element removal)
        
    3.  **Report Project**
        
-   **Progress Communication Request:** Was asked to promptly communicate any issues that arise or the completion status for both the Melbourne Market and Report projects.
    

**2. Today's Work and Progress:**

-   **Morning:** Completed the **'The Evolution of Hacking, Scams, and Spamming Using AI — and Its Impact on Server Security'** PPT, which was originally scheduled for presentation today (July 10th). Afterwards, I confirmed that this PPT presentation was postponed to a later research assignment slot. Consequently, I focused on revising the **'Open-Source CMS vs. Web Builders Script: Comparative Analysis & Practical AI Integration'** presentation, which I had received manager feedback on yesterday (July 9th). This presentation is scheduled for tomorrow (July 11th).
    
-   **Afternoon:** After finalizing the revised presentation, I immediately began modifying and executing the **Melbourne Market product information migration code**. By the end of the day, I had reached approximately **68% completion** before pausing the execution (using Ctrl+C) and planning to complete the remaining portion the following day.
    

**3. Melbourne Market Product Information Migration Code Improvement Summary:**

-   **Overview of Wix Element Filtering (Cleaning) Function:**
    
    -   The `clean_html_content` function primarily serves to remove or modify unnecessary or problematic HTML tags, attributes, and styles from HTML content scraped from Wix, ensuring it's clean and compatible for Shopify product descriptions.
        
    -   **Necessity:** Wix uses its own HTML structures, classes, inline styles, and scripts. If these elements are directly transferred to Shopify, it can cause **platform dependency issues** like disappearing images or broken styles upon Wix service termination, CSS conflicts with Shopify themes, layout disruptions, or inclusion of unnecessary JavaScript functionalities.
        
    -   When processing each product's HTML, the script uploads internal images to Shopify and replaces their `src` URLs with Shopify CDN URLs.
        
-   **Improved Image Upload and URL Acquisition Logic:**
    
    -   **Staged Uploads (Temporary Upload):** The script first calls Shopify's `stagedUploadsCreate` API to obtain a **signed URL** for uploading files to a temporary storage location (e.g., Shopify's area on Google Cloud Storage).
        
    -   **Actual File Upload:** It then uses the obtained signed URL to upload local images to Shopify's temporary storage.
        
    -   **Shopify Files Registration Request:** Once the temporary upload is complete, it calls the `fileCreate` API to formally request registration of the file in Shopify Files (identified by a `gid://shopify/MediaImage/...` style ID).
        
    -   **Shopify CDN URL Acquisition and Retry Logic:** Immediately after `fileCreate`, Shopify often doesn't return the permanent CDN URL (`https://cdn.shopify.com/...` format) right away. This is because Shopify's internal systems take some time to process the file and distribute it to the CDN. The script detects this delay, and if `originalSource.url` (or now `image { url }`) is `None`, it **retries up to 5 times with an exponential backoff (`time.sleep(2 ** attempt)`)** to query for the Shopify CDN URL. This retry mechanism ensures stable acquisition of the permanent CDN URL.

## 🧠 Key Concepts Learned

-   **Importance of Development Priority Setting:** Reconfirmed the necessity of **efficient priority setting and flexible task switching** between urgent immediate tasks (like presentation preparation) and ongoing project work (Melbourne Market, Report).
    
-   **Precision in Cross-Platform Migration:** Gained a deep understanding of the **importance of cleaning and optimizing content** when migrating from platforms with unique elements (like Wix) to another (Shopify). This goes beyond simple data transfer, focusing on removing unnecessary dependencies and ensuring compatibility.
    
-   **Advanced Shopify API for Image Management:** Learned the **complex workflow of reliably uploading and managing external images to Shopify CDN** through Shopify's `stagedUploadsCreate` and `fileCreate` APIs. Gained practical experience on how critical **exponential backoff-based retry logic** is for stable system integration, especially for asynchronous API responses like CDN URL acquisition.
    
-   **Role of CDN (Content Delivery Network):** Understood the concept of CDN as a geographically distributed network of servers designed to deliver web content (images, videos, etc.) to users faster and more efficiently, recognizing its essential role in improving website loading speeds, distributing server load, and enhancing overall stability.

## 💡 Practical Trial-and-Error and Tips

-   **Asynchronous Processing and Retry Strategy in API Integration:** For API responses that aren't immediate, like Shopify CDN URL acquisition, using an **exponential backoff retry mechanism** with `time.sleep` is an effective way to ensure **API stability and data integrity**. This approach is more robust than a fixed `sleep` time.
    
-   **Importance of Proactive Code Cleaning:** When migrating data that may contain unnecessary or incompatible elements (like Wix tags) from the source, **applying a cleaning function beforehand** is crucial. This preempts potential issues and significantly saves debugging time and resources later.
    
-   **Segmented Task Planning and Reporting:** Breaking down large projects (like Melbourne Market migration) into smaller, manageable units (code modification, execution, progress reporting) and clearly communicating progress is highly effective for **self-management and team communication**.
    
-   **Flexible Adjustment of Presentation Content:** When unexpected schedule changes occur and a different presentation topic becomes immediate, it's essential to have the **flexibility to quickly incorporate previous feedback and re-structure content** for the new presentation.

## 🔜 Next Steps

-   **Deliver Presentation:** Successfully present **'Open-Source CMS vs. Web Builders Script: Comparative Analysis & Practical AI Integration'** tomorrow (July 11th).
    
-   **Complete Melbourne Market Product Migration:** Finish the remaining 68% of the Melbourne Market product information migration tomorrow morning and prepare it for final deployment.
    
-   **Initiate Report Project Testing:** Immediately after the Melbourne Market migration is complete, move into the actual testing phase for the report project to identify and resolve any issues.
    
-   **Continuous Communication with Development Lead and Team:** Promptly communicate any issues that arise and report the completion status for both the Melbourne Market and Report projects.

----------

# 📅 4일차 (2025-07-10, 목)

## 🎓 오늘 한 일

**📌 오전 개발 미팅에서 리포트 프로젝트 진행 현황을 공유하고, PPT 준비 후 멜번마켓 Wix 요소 제거 작업을 우선 진행하겠다고 보고했습니다.**   
**📌 개발 선임의 요청에 따라 업무 우선순위를 PPT 발표 → 멜번마켓 마이그레이션 → 리포트 프로젝트 순으로 확정했습니다.**   
**📌 오전에 당초 예정된 PPT를 완성한 뒤, 발표 일정 변경을 확인하고 **'Open-Source CMS vs. Web Builders Script: Comparative Analysis & Practical AI Integration'** 발표 자료를 수정했습니다.**   
**📌 오후에는 멜번마켓 상품정보 마이그레이션 코드를 수정하고 바로 실행하여 퇴근 전까지 68% 진행도를 보였으며, 일단 중단한 뒤 다음 날 이어서 실행하여 마무리할 예정입니다.**  

### 상세 활동

**1. 오늘 개발 미팅 주요 내용:**

-   **Report 프로젝트 현황:** 현재까지 리포트 관련 프로젝트에서는 별다른 문제가 없으며, PPT 발표 준비 후에 실제 테스트를 진행할 계획임을 보고했습니다.
    
-   **Wix 요소 제거 작업 우선순위:** PPT 발표 준비가 최우선이므로, 발표를 마치는 즉시 멜번마켓 상품 정보 내 Wix 요소 제거 작업을 바로 시작할 계획임을 공유했습니다.
    
-   **업무 우선순위 확정:** 개발 선임의 지시에 따라 다음과 같은 순서로 업무를 진행하기로 확정했습니다.
    
    1.  **PPT 발표 준비** (이전에 피드백 받았던 'Open-Source CMS vs. Web Builders' 주제)
        
    2.  **멜번마켓** (상품 마이그레이션 및 Wix 요소 제거)
        
    3.  **Report 프로젝트**
        
-   **진행 상황 공유 요청:** 멜번마켓과 Report 관련 프로젝트는 진행 중 문제가 발생하거나 완료되는 시점에 바로 공유해 달라는 지시를 받았습니다.
    

**2. 오늘 작업 및 진행률:**

-   **오전:** 당초 오늘(7월 10일) 발표 예정이었던 **'AI를 활용한 해킹, 스캠, 스팸의 진화 — 그리고 서버 보안에 미치는 영향'** 관련 PPT를 완성했습니다. 이후, 이 PPT 발표가 다음 리서치 과제 일정으로 미뤄진 것을 확인했습니다. 곧바로 어제(7월 9일) 매니저님께 피드백을 받았던 **'Open-Source CMS vs. Web Builders Script: Comparative Analysis & Practical AI Integration' 발표 자료를 수정**하는 데 집중했습니다. 이 발표는 내일(7월 11일) 진행될 예정입니다.
    
-   **오후:** 수정된 발표 자료 작업을 마무리한 후, 곧바로 **멜번마켓 상품정보 마이그레이션 코드 수정 및 실행**에 착수했습니다. 퇴근 전까지 약 **68%의 진행률**을 보였으며, 일단 실행을 중단하고 다음 날 오전 출근하여 나머지 작업을 이어서 마무리할 예정입니다.
    

**3. 멜번마켓 상품정보 마이그레이션 코드 개선 요약:**

-   **Wix 요소 필터링(클리닝) 함수 개요:**
    
    -   `clean_html_content` 함수는 주로 Wix에서 스크래핑된 HTML 내용을 Shopify 상품 Description에 깔끔하고 호환성 있게 적용되도록 불필요하거나 문제가 될 수 있는 HTML 태그나 속성, 스타일을 제거하거나 수정하는 역할을 수행합니다.
        
    -   **필요성:** Wix는 자체적인 HTML 구조, 클래스, 인라인 스타일, 스크립트 등을 사용하는데, 이 요소들이 Shopify로 그대로 옮겨지면 Wix 서비스 종료 시 마이그레이션한 상품 이미지들이 사라지거나 Shopify 테마의 CSS와 충돌, 레이아웃 깨짐, 불필요한 JavaScript 기능 포함 등 **플랫폼 종속성 문제**가 발생할 수 있기 때문에 이 필터링 작업이 필수적입니다.
        
    -   각 상품 HTML을 처리할 때, 내부에 있는 이미지들을 Shopify에 업로드하고 해당 이미지의 `src` URL을 Shopify CDN URL로 교체하는 작업을 수행합니다.
        
-   **개선된 이미지 업로드 및 URL 처리 로직:**
    
    -   **Staged Uploads (임시 업로드):** 스크립트는 먼저 Shopify의 `stagedUploadsCreate` API를 호출하여 파일을 임시 저장소(예: Google Cloud Storage의 Shopify 영역)에 업로드할 수 있는 **서명된 URL**을 획득합니다.
        
    -   **실제 파일 업로드:** 획득한 서명된 URL을 사용하여 로컬 이미지를 Shopify 임시 저장소에 업로드합니다.
        
    -   **Shopify Files 등록 요청:** 임시 업로드가 완료되면 `fileCreate` API를 호출하여 해당 파일을 Shopify Files(`gid://shopify/MediaImage/...` 형태의 ID)에 정식으로 등록 요청합니다.
        
    -   **Shopify CDN URL 획득 및 재시도 로직:** `fileCreate` 직후 Shopify는 이미지에 대한 영구적인 CDN URL(`https://cdn.shopify.com/...` 형태)을 바로 반환해주지 않는 경우가 많습니다. 이는 Shopify 내부 시스템이 파일 처리를 완료하고 CDN에 배포하는 데 약간의 시간이 걸리기 때문입니다. 스크립트는 이 지연을 감지하고 `originalSource.url` (혹은 이제 `image { url }`)이 `None`일 경우, **최대 5회까지 지수 백오프(`time.sleep(2 ** attempt)`) 방식으로 재시도**하며 Shopify CDN URL을 조회합니다. 이 재시도를 통해 안정적으로 영구 CDN URL을 확보하게 됩니다.

## 🧠 배운 핵심 개념

-   **개발 우선순위 설정의 중요성:** 긴급한 발표 준비와 같이 당면한 과제와 지속적인 프로젝트 진행(멜번마켓, 리포트) 사이에서 **효율적인 우선순위 설정과 유연한 업무 전환**이 필수적임을 다시 한번 확인했습니다.
    
-   **크로스 플랫폼 마이그레이션의 정교함:** Wix와 같이 고유한 요소가 많은 플랫폼에서 다른 플랫폼(Shopify)으로 콘텐츠를 마이그레이션할 때, 단순히 데이터를 옮기는 것을 넘어 **불필요한 종속성 요소를 제거하고 대상 플랫폼에 최적화된 형식으로 클리닝하는 작업의 중요성**을 깊이 이해했습니다.
    
-   **Shopify API를 활용한 이미지 관리의 심화:** Shopify의 `stagedUploadsCreate` 및 `fileCreate` API를 통해 **외부 이미지를 Shopify CDN으로 안정적으로 업로드하고 관리하는 복잡한 워크플로우**를 배웠습니다. 특히 CDN URL 획득 시의 비동기적 특성과 이를 극복하기 위한 **지수 백오프(Exponential Backoff) 기반의 재시도 로직** 구현이 안정적인 시스템 구축에 얼마나 중요한지 실질적으로 경험했습니다.
    
-   **CDN(Content Delivery Network)의 역할:** 웹 콘텐츠(이미지, 비디오 등)를 사용자에게 더 빠르고 효율적으로 전송하기 위해 지리적으로 분산된 서버 네트워크인 CDN의 개념과, 웹사이트 로딩 속도 개선, 서버 부하 분산, 안정성 향상에 필수적인 역할을 이해했습니다.

## 💡 실전 시행착오 및 팁

-   **API 연동 시 비동기 처리 및 재시도 전략:** Shopify CDN URL 획득처럼 API 응답이 즉각적이지 않은 경우, `time.sleep`을 활용한 지수 백오프 방식의 재시도 로직은 **API 안정성과 데이터 무결성을 보장하는 효과적인 방법**입니다. 단순히 `sleep` 시간을 고정하는 것보다 더 견고한 처리가 가능합니다.
    
-   **코드 클리닝의 선행 중요성:** 데이터 마이그레이션 시 원본 데이터에 불필요하거나 호환되지 않는 요소(Wix 태그)가 포함되어 있다면, **미리 클리닝 함수를 적용하여 잠재적인 문제를 사전에 방지**하는 것이 추후 디버깅 시간과 리소스(resource)를 크게 절약할 수 있습니다.
    
-   **세분화된 작업 계획 및 보고:** 큰 프로젝트(멜번마켓 마이그레이션)를 작은 단위(코드 수정, 실행, 진행률 보고)로 나누어 실행하고, 진행률을 명확히 보고하는 방식은 **자기 관리 및 팀과의 소통에 매우 효과적**입니다.
    
-   **발표 내용의 유연한 조정:** 예상치 못한 일정 변경으로 인해 준비된 발표 자료가 아닌 다른 자료를 발표하게 되었을 때, **기존 피드백을 신속히 반영하여 내용을 재구성하는 유연성**이 필요합니다.
    

## 🔜 이후 학습 방향

-   **발표 진행:** 내일(7월 11일) **'Open-Source CMS vs. Web Builders Script: Comparative Analysis & Practical AI Integration'** 주제로 발표를 성공적으로 마칠 것입니다.
    
-   **멜번마켓 상품정보 마이그레이션 완료:** 내일 오전 중으로 남은 멜번마켓 상품정보 마이그레이션 작업(68%)을 마무리하고, 최종적으로 배포될 수 있도록 준비할 것입니다.
    
-   **리포트 프로젝트 테스트 시작:** 멜번마켓 마이그레이션이 완료되는 즉시, 리포트 프로젝트의 실제 테스트 단계로 진입하여 문제점을 파악하고 해결할 것입니다.
    
-   **개발 선임 및 팀과의 지속적인 소통:** 멜번마켓과 리포트 프로젝트에서 문제 발생 시 즉시 공유하고, 각 프로젝트의 완료 시점도 정기적으로 보고할 것입니다.
