# 📅 Day 05 (2025-07-04, Fri)

## 🎓 What I Did Today

**📌 Participated in the morning development meeting, providing updates on the Melbourne Market data migration and the Kisa Sikdang project.**   
**📌 Developed and refined Python scripts for scraping `outerHTML` of product descriptions from external sites and automating their upload to Shopify.**   
**📌 Implemented a crucial feature to parse all image URLs within the scraped HTML, upload these images to Shopify's backend media files, and replace original URLs with Shopify CDN links.**   
**📌 Identified the need for code improvements to preserve original text styling, such as color, from the scraped HTML and included this in the next steps.**  

### Detailed Activities

**1. Morning Development Meeting & Project Updates:** The day began with the development meeting where the status of ongoing projects was discussed and plans were confirmed.

-   **Melbourne Market Product Data Migration Update:** I reported on the active migration of product data from the existing Wix site ([https://www.melbmarket.com.au/](https://www.melbmarket.com.au/)) to Shopify. Given the large volume of products, it was decided that **data scraping and uploading would proceed concurrently**. A technical issue was raised: while image scraping code is in place, the need to **also scrape product text information** necessitates code modification. This was communicated to the team, and a follow-up report will be given upon completion.
    
-   **Kisa Sikdang Project Development Status:** It was confirmed that the Kisa Sikdang project is nearing completion, with **only design feedback remaining**. No further development issues are anticipated for this project.
    

**2. Shopify Product Description Migration Script Development:** Following the meeting, a significant portion of the day was dedicated to advancing the Shopify product data migration tool.

-   **`outerHTML` Scraping Implementation:** I developed and refined a Python script (using libraries like `requests`, `BeautifulSoup`, and potentially `Selenium` for dynamic content) to extract the full `outerHTML` of product description sections. This method ensures that the original formatting, styling, and embedded content are preserved during migration.
    
-   **HTML Content Cleaning and Standardization (Considering Style Preservation):** The extracted `outerHTML` underwent a cleaning process to remove any unnecessary tags or attributes that might interfere with Shopify's rendering. During this, I observed that **original text colors and other styles might be lost or revert to default values**, indicating a need for further improvement to preserve these elements.
    
-   **Local Storage and Naming Conventions:** The scraped HTML content is now systematically saved into local folders, with folder names normalized to match Shopify product titles. This organization is critical for later matching and uploading.
    

**3. Automated Shopify Image and Description Upload (Including Full Media Processing):** A crucial focus was placed on handling images within the descriptions, a vital requirement for maintaining visual fidelity and functionality on Shopify.

-   **Shopify API Integration and Pagination:** The script uses the **`shopify-python-api` library** to interact with the Shopify store. To handle a large number of products efficiently and avoid API rate limits, I implemented **`since_id` based pagination** for retrieving product lists. This ensures all products are processed without hitting API call limits or experiencing data duplication.
    
-   **Image Extraction and Upload to Shopify Backend Media:**
    
    -   The script now actively **parses the scraped `outerHTML` to identify all image (`<img>`) tags and their source (`src`) URLs.**
        
    -   For **every identified image**, the script **downloads the image content** and then **uploads it directly to Shopify's backend media files (Files section)**. This step is critical as it completely migrates image hosting from the original site to Shopify, ensuring stable image display regardless of the source site's status, and leveraging Shopify's CDN.
        
    -   Upon successful upload, Shopify provides a new CDN-hosted URL for the image. The script then **replaces the original image `src` URL within the `outerHTML`** with this new Shopify CDN URL.
        
-   **Conditional Description Update:** To prevent accidental overwrites, the script is designed to update a product's `body_html` (description) **only if it's currently empty or contains only whitespace**. This allows for safe, incremental updates.
    
-   **Error Handling and Logging:** Robust error handling is in place for API calls, network issues, and file operations. Detailed logging provides clear feedback on which products were updated, skipped, or encountered issues, offering a comprehensive overview of the migration progress.

## 🧠 Key Concepts Learned

-   **Strategic Data Migration Planning:** Gained insight into planning large-scale data migrations, specifically understanding the need for concurrent scraping and uploading when dealing with high volumes of items.
    
-   **Advanced Web Scraping for Dynamic HTML (Style Preservation):** Deepened practical experience in using `outerHTML` extraction to preserve complex layouts and handle nested content. Now, understanding extends to the critical importance of dynamically adapting and preserving **original text styles (like color)** during the scraping and import process.
    
-   **Shopify API for Content & Media Management (Complete Media Asset Migration):** Enhanced understanding of Shopify's Admin API, particularly for bulk product `body_html` updates and the vital process of programmatically **uploading all scraped images directly to the media backend** and referencing them via CDN.
    
-   **Robust Pagination Strategies (`since_id`):** Solidified knowledge of efficient API pagination techniques to handle large datasets, ensuring complete and reliable data retrieval while respecting API rate limits.

## 💡 Practical Trial-and-Error and Tips

-   **Anticipating Evolving Scraping Requirements and Style Preservation:** Initial scraping efforts might focus on one type of data (e.g., images), but it's crucial to anticipate and quickly adapt to broader data requirements (e.g., text descriptions, **original styling**). Specifically, when importing `outerHTML` directly, **inline styles or specific CSS classes might not be correctly applied in the Shopify environment, potentially leading to loss of text color (e.g., red) or reversion to default styles**. To address this, further work on HTML sanitization to preserve style attributes or convert them for Shopify's environment will be necessary.
    
-   **Challenges of `outerHTML` Image Handling (Importance of Full Backend Hosting):** While `outerHTML` is great for preserving layout, it includes original image URLs. The key challenge was realizing that **all these images** also needed to be migrated to Shopify's hosting. Simply embedding the `outerHTML` doesn't host the images on Shopify, which can lead to broken links if the source site changes or goes down. Therefore, **the process of directly uploading all images to Shopify's media backend is essential for long-term data stability.**
    
-   **Shopify Media API Nuances:** Directly uploading to Shopify's 'Files' (media backend) often requires specific API calls (sometimes via GraphQL or direct REST calls using `requests`, as `shopify-python-api` might not have direct wrappers for all 'Files' functionalities). For this project, a conceptual approach of uploading images to get a Shopify CDN URL for replacement in `body_html` was adopted, emphasizing the importance of getting images properly hosted.
    
-   **Rate Limit Management for Large Migrations:** For large-scale data migrations, incorporating `time.sleep()` between API calls is non-negotiable. Consistent, slight delays (e.g., 0.5-0.7 seconds) are crucial for staying within Shopify's rate limits and ensuring stable, uninterrupted processing.

## 🔜 Next Steps

-   **Refine Melbourne Market Scraping Code (Including Text and Styles):** Implement the necessary code modifications for the Melbourne Market product data migration to ensure that both images and **text content are correctly scraped, and that original text colors and other crucial style information are preserved as much as possible**. This will involve researching HTML sanitization logic and style attribute handling.
    
-   **Complete Shopify Product Description and Image Migration (Verify All Images Backend Hosted):** Finalize the script and execute the full migration of all remaining product descriptions and their associated images to the Shopify store. **Crucially, I will thoroughly verify that all scraped images are successfully uploaded to Shopify's media backend and that their CDN links are correctly replaced.**
    
-   **Validate Migrated Data:** Thoroughly review a sample of migrated products on Shopify to ensure descriptions render correctly, images are displayed, and links function as expected.
    
-   **Client One-Page Website Finalization:** Address any remaining feedback from the designer and senior developer for the "Kisa Sikdang" website and prepare for its final deployment.
    
-   **Research and Prepare PPT on AI Security Threats:** Continue in-depth research and preparation for the presentation on "The Evolution of Hacking, Scams, and Spamming Using AI — and Its Impact on Server Security," scheduled for **Thursday, July 10, 2025**.
    
----------


# 📅 Day 05 (2025-07-04, 금)

## 🎓 오늘 한 일

**📌 오전 개발 미팅에 참여하여 멜번 마켓 데이터 마이그레이션 및 기사식당 프로젝트 진행 상황을 공유했습니다.**   
**📌 외부 사이트에서 상품 설명의 `outerHTML`을 스크래핑하여 Shopify로 자동 업로드하는 Python 스크립트를 개발하고 개선했습니다.**   
**📌 스크래핑된 HTML 내의 모든 이미지 URL을 파싱하여 Shopify 미디어 백엔드에 업로드하고, 원본 URL을 Shopify CDN 링크로 교체하는 핵심 기능을 구현했습니다.**   
**📌 스크래핑된 HTML의 텍스트 색상 등 원본 스타일을 최대한 보존하는 방향으로 코드 개선 필요성을 확인하고, 이를 다음 작업 방향에 포함했습니다.**  

### 상세 활동

**1. 오전 개발 미팅 및 프로젝트 업데이트:** 하루는 개발 미팅으로 시작되었고, 진행 중인 프로젝트의 현황을 논의하고 계획을 확정했습니다.

-   **멜번 마켓 상품 데이터 마이그레이션 업데이트:** 기존 Wix 사이트([https://www.melbmarket.com.au/)](https://www.melbmarket.com.au/))에서 Shopify로 상품 데이터를 활발히 마이그레이션 중임을 보고했습니다. 방대한 상품 수량을 고려하여 **데이터 스크래핑과 업로드를 동시에 병행**하기로 결정했습니다. 기술적 이슈로, 이미지 스크래핑 코드는 준비되었으나 **상품 텍스트 정보도 함께 스크래핑해야 하는 상황이 발생하여 코드 수정이 필요**함을 제기했습니다. 이 내용은 팀에 공유되었고, 모든 작업 완료 후 추가 보고를 하기로 했습니다.
    
-   **기사식당 프로젝트 개발 현황:** 기사식당 프로젝트는 거의 완료 단계에 있으며, **디자인 피드백만 남아있음**이 확인되었습니다. 이 프로젝트와 관련하여 추가적인 개발 이슈는 없을 것으로 예상됩니다.
    

**2. Shopify 상품 설명 마이그레이션 스크립트 개발:** 미팅 이후, 하루의 상당 부분을 Shopify 상품 데이터 마이그레이션 도구 개발에 할애했습니다.

-   **`outerHTML` 스크래핑 구현:** Python 스크립트(`requests`, `BeautifulSoup` 및 동적 콘텐츠 처리를 위한 `Selenium`과 같은 라이브러리 사용)를 개발하고 개선하여 상품 설명 섹션의 전체 `outerHTML`을 추출했습니다. 이 방식은 마이그레이션 시 원본 포맷팅, 스타일 및 포함된 콘텐츠를 보존하는 데 효과적입니다.
    
-   **HTML 콘텐츠 정리 및 표준화 (스타일 보존 고려):** 추출된 `outerHTML`은 Shopify 렌더링을 방해할 수 있는 불필요한 태그나 속성을 제거하는 클리닝 과정을 거쳤습니다. 이 과정에서 **원본 텍스트 색상과 같은 스타일이 유실되거나 기본값으로 변경될 가능성을 확인했으며, 이를 보존하는 방안에 대한 추가 개선이 필요함**을 인지했습니다.
    
-   **로컬 저장 및 명명 규칙:** 스크래핑된 HTML 콘텐츠는 이제 Shopify 상품명과 일치하도록 폴더 이름이 정규화되어 로컬 폴더에 체계적으로 저장됩니다. 이러한 구성은 나중에 매칭 및 업로드에 매우 중요합니다.
    

**3. Shopify 이미지 및 설명 자동 업로드 (완전한 미디어 처리 포함):** 설명 내 이미지 처리에 상당한 중점을 두었으며, 이는 Shopify에서 시각적 무결성 및 기능을 유지하는 데 필수적인 요구사항이었습니다.

-   **Shopify API 통합 및 페이지네이션:** 스크립트는 **`shopify-python-api` 라이브러리**를 사용하여 Shopify 스토어와 통신합니다. 많은 수의 상품을 효율적으로 처리하고 API 요청 제한을 피하기 위해, 상품 목록을 가져올 때 **`since_id` 기반 페이지네이션**을 구현했습니다. 이는 API 호출 제한을 넘지 않고 데이터 중복 없이 모든 상품을 처리하는 견고한 방법입니다.
    
-   **이미지 추출 및 Shopify 미디어 백엔드에 전체 업로드:**
    
    -   스크립트는 이제 스크래핑된 `outerHTML`을 적극적으로 **파싱하여 모든 이미지(`<img>`) 태그와 해당 `src` (소스) URL을 식별합니다.**
        
    -   식별된 **모든 이미지**에 대해, 스크립트는 **이미지 콘텐츠를 다운로드**한 다음, **Shopify 미디어 백엔드 (Files)에 직접 업로드**합니다. 이 단계는 이미지 호스팅을 원본 사이트에서 Shopify로 완전히 옮겨 원본 사이트의 상태와 관계없이 안정적인 이미지 표시를 보장하며, Shopify의 CDN을 활용하는 데 매우 중요합니다.
        
    -   업로드가 성공하면, Shopify는 해당 이미지에 대한 새로운 CDN 호스팅 URL을 제공합니다. 스크립트는 이 새로운 Shopify CDN URL로 **`outerHTML` 내의 원본 이미지 `src` URL을 교체**합니다.
        
-   **조건부 설명 업데이트:** 우발적인 덮어쓰기를 방지하기 위해, 스크립트는 Shopify 상품의 `body_html` (설명) 필드가 **현재 비어 있거나 공백만 포함된 경우에만** 업데이트하도록 설계되었습니다. 이를 통해 안전하고 점진적인 업데이트가 가능합니다.
    
-   **오류 처리 및 로깅:** API 호출, 네트워크 문제, 파일 작업에 대한 강력한 오류 처리가 구현되어 있습니다. 상세한 로깅은 어떤 상품이 업데이트되었는지, 건너뛰어졌는지, 또는 문제가 발생했는지에 대한 명확한 피드백을 제공하여 마이그레이션 진행 상황을 종합적으로 보여줍니다.

## 🧠 배운 핵심 개념

-   **전략적 데이터 마이그레이션 계획:** 대규모 데이터 마이그레이션을 계획하는 데 대한 통찰력을 얻었으며, 특히 많은 양의 항목을 다룰 때 동시 스크래핑 및 업로드의 필요성을 이해했습니다.
    
-   **동적 HTML을 위한 고급 웹 스크래핑 (스타일 유지 고려):** 복잡한 레이아웃을 보존하고 중첩된 콘텐츠를 처리하기 위해 `outerHTML` 추출을 사용하는 실용적인 경험을 심화했으며, 이제 텍스트 콘텐츠 및 그 **스타일(색상 등)**을 동적으로 적응시켜 가져오는 중요성을 파악했습니다.
    
-   **콘텐츠 및 미디어 관리를 위한 Shopify API (완전한 미디어 자산 마이그레이션):** Shopify Admin API, 특히 대량 상품 `body_html` 업데이트와 스크래핑한 **모든 이미지를 미디어 백엔드에 프로그래밍 방식으로 업로드**하고 CDN을 통해 참조하는 중요한 프로세스에 대한 이해를 심화했습니다.
    
-   **견고한 페이지네이션 전략 (`since_id`):** 대량의 데이터 세트를 처리하고 API 요청 제한을 준수하면서 완전하고 신뢰할 수 있는 데이터 검색을 보장하는 효율적인 API 페이지네이션 기술에 대한 지식을 확고히 했습니다.

## 💡 실전 시행착오 및 팁

-   **변화하는 스크래핑 요구사항 예측 및 스타일 보존:** 초기 스크래핑은 한 가지 유형의 데이터(예: 이미지)에 집중할 수 있지만, 더 넓은 데이터 요구사항(예: 텍스트 설명, **원본 스타일**)에 대한 예측과 신속한 적응이 중요합니다. 특히 `outerHTML`을 그대로 가져올 때 **인라인 스타일이나 특정 CSS 클래스가 Shopify 환경에서 올바르게 적용되지 않아 텍스트 색상(예: 빨간색) 등이 유실되거나 기본값으로 변경될 수 있음**을 확인했습니다. 이를 해결하기 위해 HTML 정제 단계에서 스타일 속성을 유지하거나 Shopify 환경에 맞게 변환하는 추가적인 작업이 필요합니다.
    
-   **`outerHTML` 이미지 처리의 과제 (완전한 백엔드 호스팅의 중요성):** `outerHTML`은 레이아웃 보존에 탁월하지만, 원본 이미지 URL을 포함합니다. 핵심 과제는 이러한 **모든 이미지**도 Shopify 호스팅으로 마이그레이션해야 한다는 것을 깨닫는 것이었습니다. 단순히 `outerHTML`을 삽입하는 것만으로는 이미지가 Shopify에 호스팅되지 않아, 원본 사이트가 변경되거나 다운될 경우 링크가 깨지는 문제가 발생할 수 있습니다. 따라서 **Shopify 미디어 백엔드에 모든 이미지를 직접 업로드하는 과정은 데이터의 장기적 안정성을 위해 필수적**입니다.
    
-   **Shopify 미디어 API의 미묘한 차이:** Shopify의 'Files' (미디어 백엔드)에 직접 업로드하는 것은 종종 특정 API 호출(때로는 GraphQL 또는 `requests`를 사용한 직접 REST 호출)을 필요로 합니다. `shopify-python-api`가 모든 'Files' 기능에 대한 직접적인 래퍼를 제공하지 않을 수 있기 때문입니다. 이 프로젝트에서는 `body_html` 내의 이미지 교체를 위해 Shopify CDN URL을 얻기 위한 이미지 업로드 개념적 접근 방식을 채택했으며, 이미지를 올바르게 호스팅하는 것의 중요성을 강조했습니다.
    
-   **요청 제한 관리를 위한 대규모 마이그레이션:** 대규모 데이터 마이그레이션의 경우, API 호출 사이에 `time.sleep()`을 사용하는 것은 필수적입니다. 일관되고 약간의 지연(예: 0.5-0.7초)은 Shopify의 요청 제한 내에서 유지하고 안정적이며 중단 없는 처리를 보장하는 데 매우 중요합니다.

## 🔜 이후 학습 방향

-   **멜번 마켓 스크래핑 코드 개선 (텍스트 및 스타일 포함):** 멜번 마켓 상품 데이터 마이그레이션을 위해 이미지와 **텍스트 콘텐츠 모두 올바르게 스크래핑될 뿐만 아니라, 원본 텍스트 색상 및 기타 중요한 스타일 정보도 최대한 유지되도록** 필요한 코드 수정을 구현할 것입니다. 이를 위해 HTML 정제 로직 및 스타일 속성 처리 방안을 연구할 것입니다.
    
-   **Shopify 상품 설명 및 이미지 마이그레이션 완료 (모든 이미지 백엔드 호스팅 확인):** Shopify 스토어로 나머지 모든 상품 설명 및 관련 이미지의 전체 마이그레이션을 위한 스크립트를 최종적으로 다듬고 실행할 것입니다. **특히, 스크랩된 모든 이미지가 Shopify 미디어 백엔드에 성공적으로 업로드되고 해당 CDN 링크로 교체되었는지 철저히 확인할 것입니다.**
    
-   **마이그레이션된 데이터 유효성 검사:** Shopify에서 마이그레이션된 상품 샘플을 철저히 검토하여 설명이 올바르게 렌더링되고, 이미지가 표시되며, 링크가 예상대로 작동하는지 확인할 것입니다.
    
-   **클라이언트 원페이지 웹사이트 최종 마무리:** "기사식당" 웹사이트에 대한 디자이너 및 선임 개발자의 남은 피드백을 반영하고 최종 배포를 준비할 것입니다.
    
-   **AI 보안 위협 관련 PPT 리서치 및 준비:** "AI를 활용한 해킹, 스캠, 스팸의 진화 — 그리고 서버 보안에 미치는 영향"이라는 주제로 발표 자료에 대한 심층 리서치 및 준비를 계속할 것입니다. 발표는 **2025년 7월 10일 목요일**에 예정되어 있습니다.
