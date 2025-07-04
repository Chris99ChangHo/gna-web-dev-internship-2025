# 📅 Day 04 (2025-07-03, Thu)

## 🎓 What I Did Today

**📌 Participated in the morning development meeting, shared yesterday's progress, and received new directives.**   
**📌 Obtained necessary Shopify backend access from the senior developer and began updating Shopify product descriptions with Wix product information.**   
**📌 Manually updated product information to verify Shopify's data structure and description field behavior.**   
**📌 Developed a Python web scraping script for direct import into Shopify, collecting image URLs and detailed product information (HTML).**    
**📌 Organized scraped product data into separate CSV files based on information availability.**  
**📌 Researched using Shopify's API to automate product description uploads.**  

### Detailed Activities

**1. Morning Development Meeting & Task Review:** The day started with the usual development meeting.

-   **Progress Share & New Directives:** I shared the progress from yesterday, particularly on the client website finalization and the start of product info scraping. New tasks and clarifications for existing ones were received.
    

**2. Shopify Access & Product Data Update Initiation:** A critical step for product migration began today.

-   **Obtained Shopify Backend Access:** I successfully received the necessary backend access to the Shopify store from the senior developer. This access is crucial for migrating product information from the existing Wix site to the description fields of each product in Shopify.
    
-   **Initiated Scraped Product Information Update:** With access granted, I immediately began the process of updating product information on the Shopify store using scraped data.
    

**3. Manual Updates for Shopify Structure & Data Behavior Verification:** Prior to automated uploads, manual work was performed to understand the Shopify platform's characteristics.

-   **Manual Update for Structure Verification:** After gaining Shopify backend access from the senior developer, I manually updated Shopify product descriptions to directly verify and test how the platform processes data and applies HTML content. This served as a crucial foundation for future scraping code development and automation strategy planning.
    

**4. Web Scraping Script Development & Strategy Evolution:** I developed automation code to efficiently collect product info and improved the script to align with the upload strategy.

-   **Scraping Tools & Purpose:** I began writing the scraping automation code using **Python's Selenium and BeautifulSoup (bs4)** for product information collection and description updates.
    
-   **Evolution of Scraping Strategy:** Initially, the plan was to scrape and upload images only. However, I realized that detailed text-based product information (product info) was also necessary. Considering Shopify's limitation of single image uploads, I'm now modifying the scraping structure to retrieve the entire product info, including its HTML structure, directly from Wix. The goal is to insert this raw HTML content as a code block into the `body_html` field (product description) of each Shopify product.
    
-   **Data Categorization & CSV Export:** Currently, the collected product info data (including URLs) is being organized into separate CSV files based on whether the information is complete or missing. (Target site: **[https://www.melbmarket.com.au/](https://www.melbmarket.com.au/)**)
    

**5. Shopify API Utilization Research:** In parallel with manual testing and scraping code improvements, I explored more efficient automation methods.

-   **API Utilization Research:** I conducted in-depth research into whether the Shopify Admin REST API can be used to automate the upload of scraped HTML content into the description field of each product. I'm still exploring how to set up the specific pipeline for this.

## 🧠 Key Concepts Learned

-   **Developing and Executing Shopify Product Description Migration Strategies:** Gained practical experience in the end-to-end process of migrating specific product information (descriptions) to Shopify, including access, data structuring, and manual testing.
    
-   **Advanced Web Scraping Techniques for Complex HTML Content and Images:** Learned advanced scraping methods for maintaining HTML structure and efficiently processing image URLs to transform data for the target platform.
    
-   **Exploring Technical Workarounds for Platform Limitations (e.g., Single Image Uploads):** Understood how to identify limitations of target platforms and sought creative and practical technical solutions to overcome them (e.g., scraping entire HTML for direct insertion).

## 💡 Practical Trial-and-Error and Tips

-   **Importance of Understanding and Testing Shopify's HTML Rendering in Description Fields:** When inserting scraped HTML into Shopify's `body_html` field, it's crucial to understand how Shopify renders HTML (e.g., CSS style application, allowed tags) and thoroughly test with small datasets beforehand.
    
-   **Pre-research and Strategy Planning for Large-Scale Image/HTML Uploads via API:** Recognizing the limitations of CSV imports, it's important to research the possibilities of large-scale data (especially HTML content or images) uploads via REST API in advance to establish the most efficient migration strategy.
    
-   **Flexible Structuring of Automation Scraping Code:** As platform constraints or new requirements (e.g., need for text info beyond images) may arise, it's beneficial to design scraping code flexibly so that data extraction methods (e.g., image URLs only -> full HTML) can be easily changed.

## 🔜 Next Steps

-   **Complete Upload of Scraped HTML Content to Shopify Product Description Fields:** Finalize the refinement of the current scraped data and its upload to Shopify's `body_html` fields.
    
-   **Implement Automated Description Updates using Shopify Admin REST API:** Research further into automating bulk description updates via the Shopify API and attempt to implement it.
    
-   **Client One-Page Website Go-Live:** Coordinate with the team for the final deployment of the "Kisa Sikdang" website.
    
-   **Research and Prepare PPT on AI Security Threats:** Continue in-depth research and preparation for the presentation titled "The Evolution of Hacking, Scams, and Spamming Using AI — and Its Impact on Server Security," scheduled for **Thursday, July 10, 2025**.
    
-   **Continue DevNewsHub Mini-Project:** DevNewsHub mini-project is currently paused due to other client tasks, but I will **resume development as time permits**, continuing with additional feature implementation and improvements for both the WordPress website and the React Native/Expo app.
    
----------

# 📅 4일차 (2025-07-03, 목)

## 🎓 오늘 한 일

**📌 오전 개발 미팅에 참여하여 어제 업무 진행 상황을 공유하고, 새로운 업무 지시를 받았습니다.**   
**📌 선임 개발자로부터 Shopify 백엔드 접근 권한을 획득하고, Wix 상품 정보를 Shopify 각 상품의 description 항목으로 업데이트하는 작업을 시작했습니다.**   
**📌 수동으로 Shopify 상품 정보를 업데이트하며 데이터 구조 및 description 항목의 동작 방식을 확인했습니다.**   
**📌 Shopify로의 직접 임포트를 위한 Python 웹 스크래핑 스크립트를 개발하여 이미지 URL 및 상세 상품 정보(HTML)를 수집했습니다.**   
**📌 스크래핑한 상품 데이터를 정보 유무에 따라 각각 별도의 CSV 파일로 분류하고 정리했습니다.**   
**📌 Shopify의 API를 활용하여 상품 description 업로드를 자동화할 수 있는지 리서치했습니다.**  

### 상세 활동

**1. 오전 개발 미팅 및 업무 검토:** 하루는 평소와 같이 개발 미팅으로 시작되었습니다.

-   **진행 상황 공유 및 새로운 지시:** 어제 진행했던 클라이언트 웹사이트 최종 마무리 및 상품 정보 스크래핑 시작 등의 진행 상황을 공유했습니다. 이어서 기존 업무에 대한 명확화 및 새로운 지시사항을 받았습니다.
    

**2. Shopify 접근 권한 확보 및 상품 데이터 업데이트 작업 시작:** 상품 마이그레이션을 위한 중요한 단계가 오늘 시작되었습니다.

-   **Shopify 계정 백엔드 접근 권한 획득:** 선임 개발자로부터 Shopify 스토어의 백엔드 접근 권한을 성공적으로 부여받았으며, 이는 기존 Wix 사이트의 상품 정보를 Shopify 각 상품의 description 항목으로 마이그레이션하는 데 필수적이었습니다.
    
-   **초기 스크래핑한 상품 정보 데이터 업데이트 작업 시작:** 권한 획득 후, 스크래핑한 상품 정보를 Shopify에 업데이트하는 작업을 시작했습니다.
    

**3. 수동 업데이트를 통한 Shopify 구조 및 데이터 동작 확인:** 자동화된 업로드에 앞서 Shopify 플랫폼의 특성을 이해하기 위해 수동 작업을 수행했습니다.

-   **수동 업데이트를 통한 구조 확인:** 선임 개발자로부터 Shopify 백엔드 접근 권한을 획득한 후, 수동으로 Shopify 상품 description을 업데이트하며 플랫폼의 데이터 처리 방식과 HTML 콘텐츠 적용 방식을 직접 확인하고 테스트했습니다. 이는 향후 스크래핑 코드 개발 및 자동화 전략 수립에 중요한 기반이 되었습니다.
    

**4. 웹 스크래핑 스크립트 개발 및 전략 진화:** 상품 info 데이터 수집을 효율적으로 진행하기 위해 자동화 코드를 작성했으며, 업로드 전략에 맞춰 스크립트를 개선했습니다.

-   **스크래핑 툴 및 목적:** 상품 정보 수집 및 description 업데이트 자동화를 위해 **Python의 Selenium과 BeautifulSoup(bs4)**를 활용한 스크래핑 자동화 코드를 작성하기 시작했습니다.
    
-   **스크래핑 전략의 진화:** 초기에는 이미지만 스크래핑하여 업로드할 계획이었으나, 텍스트 기반의 상세 상품 정보(product info)도 필요함을 파악했습니다. 이에 따라 Shopify의 단일 이미지 업로드 제약을 고려하여, 기존 Wix에 있던 product info 전체를 HTML 구조 그대로 가져와 Shopify의 각 상품 description 항목(`body_html`)에 코드 블록 형태로 직접 삽입하기 위해 스크래핑 구조를 변경 중입니다.
    
-   **데이터 분류 및 CSV 정리:** 현재 수집한 상품 info 데이터(URL 포함)는 정보 유무에 따라 각각 별도의 CSV 파일로 정리하고 있습니다. (대상 사이트: **[https://www.melbmarket.com.au/](https://www.melbmarket.com.au/)**)
    

**5. Shopify API 활용 가능성 리서치:** 수동 테스트 및 스크래핑 코드 개선과 병행하여, 더 효율적인 자동화 방안을 모색했습니다.

-   **API 활용 가능성 리서치:** Shopify Admin REST API를 활용하여 스크래핑한 HTML 콘텐츠를 각 상품의 description 필드에 자동화하여 업로드할 수 있는지에 대한 심층적인 리서치를 진행했습니다. 아직 구체적인 파이프라인 구성 방법은 탐색 중입니다.

## 🧠 배운 핵심 개념

-   **Shopify 상품 Description 마이그레이션 전략 수립 및 실행:** 계정 접근, 데이터 구조화, 수동 테스트를 포함하여 Shopify로 특정 상품 정보(description)를 마이그레이션하는 전반적인 프로세스에 대한 실제 경험을 얻었습니다.
    
-   **복잡한 HTML 콘텐츠 및 이미지 처리 스크래핑 기법:** 웹 스크래핑 시 HTML 구조를 유지하고, 이미지 URL을 효율적으로 처리하여 대상 플랫폼에 맞게 데이터를 변환하는 고급 스크래핑 기법을 학습했습니다.
    
-   **플랫폼 제약(예: 단일 이미지 업로드)에 대한 기술적 우회 방안 모색:** 대상 플랫폼의 한계점을 파악하고, 이를 극복하기 위한 창의적이고 실용적인 기술적 해결책(예: HTML 통째로 가져와 삽입)을 모색하는 방법을 배웠습니다.

## 💡 실전 시행착오 및 팁

-   **Shopify Description 필드의 HTML 렌더링 특성 이해 및 테스트의 중요성:** 스크래핑한 HTML을 Shopify의 `body_html` 필드에 삽입할 때는 Shopify가 HTML을 어떻게 렌더링하는지(CSS 스타일 적용, 태그 허용 범위 등) 미리 이해하고 소량의 데이터로 충분히 테스트하는 것이 필수적입니다.
    
-   **대량 이미지/HTML 업로드 시 API 활용을 위한 사전 리서치 및 전략 수립:** CSV 임포트의 한계를 인지하고, REST API를 통한 대량 데이터(특히 HTML 콘텐츠나 이미지) 업로드의 가능성을 미리 조사하여 가장 효율적인 마이그레이션 전략을 수립하는 것이 중요합니다.
    
-   **스크래핑 자동화 코드의 유연한 구조화:** 플랫폼의 제약사항이나 새로운 요구사항(예: 이미지 외 텍스트 정보 필요)이 발생할 수 있으므로, 스크래핑 코드를 유연하게 설계하여 데이터 추출 방식(예: 이미지 URL만 -> 전체 HTML)을 쉽게 변경할 수 있도록 준비하는 것이 좋습니다.

## 🔜 이후 학습 방향

-   **Shopify 각 상품의 description 필드에 스크래핑한 HTML 콘텐츠 업로드 완료:** 현재 진행 중인 스크래핑 데이터의 최종 정제 및 Shopify `body_html` 필드로의 업로드를 완료할 것입니다.
    
-   **Shopify Admin REST API를 활용한 description 자동 업데이트 구현:** Shopify API를 통한 대량의 description 업데이트 자동화 방안을 추가 리서치하고 실제 구현을 시도할 것입니다.
    
-   **클라이언트 원페이지 웹사이트 최종 배포:** "기사식당" 웹사이트의 최종 배포를 위해 팀과 조율할 것입니다.
    
-   **AI 보안 위협 관련 PPT 리서치 및 준비:** "AI를 활용한 해킹, 스캠, 스팸의 진화 — 그리고 서버 보안에 미치는 영향"이라는 주제로 발표 자료 심층 리서치 및 준비를 계속할 것입니다. CPanel/WHM 서버 관리자 관점에서 AI 기반 보안 위협과 잠재적 대응책을 이해하는 것이 목표이며, 발표는 **2025년 7월 10일 목요일**에 예정되어 있습니다.
    
-   **DevNewsHub 미니 프로젝트 지속:** DevNewsHub 미니 프로젝트는 현재 다른 클라이언트 업무로 인해 잠시 중단되었지만, **시간이 허락하는 대로 개발을 이어가며** 워드프레스 웹사이트 및 React Native/Expo 앱의 추가 기능 구현 및 개선 작업을 진행할 것입니다.
