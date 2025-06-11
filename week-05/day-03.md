
# 📅 Day 03 (2025-06-11, Wed)

## 🎓 ## What I Did Today

**📌 Completed the "Open-Source CMS vs. Web Builders" research and presentation materials.**  
**📌 Discussed mini-project progress in the development meeting, focusing on a "Development News Hub" site.**  
**📌 In Progress the Python script for automated news article scraping from ABC News and seamless upload to WordPress via REST API, evolving from initial Docscraper goals.**  

### Detailed Activities

**1. Research Assignment & Presentation Material Completion****I finalized the research assignment on "Open-Source CMS vs. Web Builders: Comparative Analysis & Practical AI Integration" and successfully completed the presentation materials.**

-   **Research Completion**: I thoroughly completed the data collection for the comparative analysis of Open-Source CMS and Web Builders, focusing on their practical advantages and disadvantages, especially regarding AI integration.
-   **Presentation Material Production**: Based on the extensive research, I organized the findings into a clear and concise presentation (PPT) format, making it ready for delivery.

**2. Development Meeting & Mini-Project Discussion** Today's development meeting focused on the progress of my mini-project, the "Development News Hub" (Dev News Hub) site.

-   **Progress Review**: I presented my intention to develop the Dev News Hub mini-project for practical skill enhancement.
-   **Feedback on Time Allocation**: It was acknowledged that I couldn't dedicate significant time to this mini-project due to the ongoing CMS and Web Builder Tools research assignment (due Thursday).
-   **Next Steps & Confidence Building**: The feedback was positive, encouraging me to continue once I complete the PPT. The team emphasized that once I feel confident and proficient in custom post types, hooks, actions, and filters through practical exercises, we'll proceed to the next steps.

**3. Automated News Article Scraping & WordPress Upload Script Development** Following the meeting, I dedicated my time to **completing the presentation materials and, most importantly, developed a Python script to automatically scrape news articles and upload them to a custom post type (`news`) in WordPress via the REST API. This development evolved from the initial goals of the Docscraper program.**

-   **Project Goal**: The primary goal was to develop a Python script to scrape specific "computer-science" articles from the ABC News website and automatically publish them as posts on a pre-designated WordPress site (`dev.gnasolutions.com.au/intern02`). This included uploading thumbnail images and assigning appropriate categories/tags. A key focus was to extract clean HTML content by removing unnecessary elements (ads, share buttons, related article sections) from the article body.
    
-   **Key Features & Implementation**:
    
    -   **Article Link Collection (`get_article_links_by_load_more`)**:
        -   Initially, I attempted to collect links using standard pagination (`?page=X`), but identified that ABC News's "Load More" button uses AJAX API calls.
        -   The script was modified to directly call the relevant API endpoint (`https://www.abc.net.au/news/api/news-story-list-data/topic/{TOPIC_SLUG}`) instead of visually clicking the button.
        -   It iteratively calls the API using `offset` and `count` parameters, fetching `articles_per_request` (currently 8) links at a time.
        -   A `target_article_count` variable allows setting the total number of articles to collect, with the script repeating API calls until this count is reached or no new links are returned.
    -   **Article Content Parsing (`parse_article_with_html`)**:
        -   For each article URL, Beautiful Soup is used to extract the title, author, date, and topic information.
        -   Article body HTML is extracted, with unnecessary elements (ads, share buttons, "Related topics," "More Just In," footer links) identified via F12 developer tools and removed to ensure clean content.
        -   The URL of the first image within the article is also extracted for use as a thumbnail.
    -   **Data Storage (`save_to_csv`)**:
        -   Scraped and parsed article data is saved to `abc_articles_with_html.csv` in CSV format.
    -   **Preview Generation (`preview_article_html`)**:
        -   An HTML preview file (`article_preview.html`) is generated to allow web browser verification of scraped content, aiding in reviewing parsing and cleaning.
    -   **WordPress Upload (`upload_to_wordpress`)**:
        -   The script uses the WordPress REST API to upload scraped articles as new posts.
        -   Authentication is handled via Basic Authentication using `WP_USERNAME` and `WP_APPLICATION_PASSWORD`.
        -   Parsed article topic information is dynamically mapped to WordPress category and tag IDs, which are fetched from the WordPress API at script initialization.
        -   If a first image is extracted, it's uploaded to the WordPress Media Library and set as the post's featured image.
        -   Original author, date, and URL are stored as WordPress post metadata.
-   **Key Challenges & Solutions**:
    
    -   **"Load More" Logic**: Identified the AJAX nature of the "Load More" button and efficiently switched from attempted pagination link finding to direct API calls using `requests` (avoiding Selenium), which is more efficient.
    -   **WordPress Category/Tag Mapping**: Addressed the need for dynamic mapping by fetching WordPress category and tag IDs via the WordPress API at runtime.
    -   **Unnecessary HTML Element Removal**: Continuously reviewed and improved the logic for removing extraneous elements from the article body using the preview file to ensure accuracy.
-   **Next Steps & Verification Needs**:
    
    -   **API URL & Response Structure Confirmation**: Crucially, I need to use developer tools (Network tab) to confirm that the `api_url_template` within `get_article_links_by_load_more` is indeed the exact API address called by ABC News's "Load More" button. I also need to verify that the API's JSON response structure (e.g.,  `data` key containing the article list,  `url` or `link` key for article URL) matches the script's expectations.
    -   **Script Execution Testing**: I must execute the script to verify that articles are correctly uploaded to WordPress, content is properly parsed, and thumbnails, categories, and tags are correctly assigned.

## 🧠 Key Concepts Learned

-   **Practical Client-Side Interaction & Business Acumen**: My first direct client meeting provided invaluable experience in real-world client communication, requirement elicitation, and understanding the business decision-making process for IT services from a non-developer perspective.
-   **API-Driven Web Scraping**: Gained significant practical experience in identifying and directly interacting with AJAX-powered API endpoints for efficient data collection, a more robust method than traditional HTML parsing for dynamic content.
-   **Automated WordPress Content Management**: Mastered the use of the WordPress REST API for programmatic content creation, including post creation, media uploads, and dynamic taxonomy/metadata assignment, demonstrating a powerful way to automate site updates.
-   **Robust Data Cleaning & Preprocessing**: Understood the critical importance of cleaning scraped HTML content by removing unnecessary elements to ensure the quality and usability of data uploaded to WordPress.

## 💡 Practical Trial-and-Error and Tips

-   **Observing Network Traffic for API Discovery**: Using browser developer tools (Network tab) was crucial for discovering the underlying AJAX API calls of the "Load More" button, leading to a much more efficient scraping strategy. This is a vital skill for dynamic web content.
-   **Iterative HTML Cleaning**: The `preview_article_html` feature was highly effective for iterative debugging and refinement of the HTML cleaning logic, enabling me to visually confirm the output and remove unwanted elements systematically.
-   **Dynamic WordPress Object Mapping**: Dynamically fetching WordPress category/tag IDs via the REST API at runtime is a robust approach, ensuring the script adapts to changes in WordPress taxonomy structures without manual updates to the script itself.
-   **Client Empathy in Tech**: The client meeting highlighted that successful IT solutions require not just technical skills but also a deep understanding of non-technical users' needs and pain points, emphasizing empathy in communication.

## 🔜 Next Steps

-   **Finalize Research Presentation**: Complete the "Open-Source CMS vs. Web Builders" PPT and prepare thoroughly for the upcoming presentation.
-   **Thorough Testing of WordPress Auto-Upload Script**: Conduct comprehensive testing of the Python script to ensure seamless and accurate automated article uploads to WordPress, verifying content, images, categories, and tags.
-   **Refine Docscraper Program Logic**: Continue to improve the `Docscraper` program, focusing on data selection and structuring for effective LLM learning, as outlined in the ongoing update.

----------

# 📅 3일차 (2025-06-11, 수)

## 🎓 오늘 한 일

**📌 "Open-Source CMS vs. Web Builders" 리서치 및 발표 자료 완성.**  
**📌 개발 미팅에서 '개발 뉴스 허브' 미니 프로젝트 진행 상황 논의.**  
**📌 초기 Docscraper 목표에서 확장되어 ABC 뉴스 기사 자동 스크래핑 및 워드프레스 REST API를 통한 원활한 업로드 파이썬 스크립트 개발 진.**  

### 상세 활동

**1. 리서치 과제 및 발표 자료 완성****"Open-Source CMS vs. Web Builders: Comparative Analysis & Practical AI Integration" 리서치 과제를 최종 완료하고 발표 자료를 성공적으로 제작했습니다.**

-   **리서치 완료**: 오픈소스 CMS와 웹 빌더의 비교 분석, 특히 AI 통합과 관련하여 실무적인 장단점에 대한 자료 조사를 철저히 마무리했습니다.
-   **발표 자료 제작**: 방대한 리서치 내용을 바탕으로 명확하고 간결한 발표(PPT) 자료 형태로 정리하여 발표 준비를 마쳤습니다.

**2. 개발 미팅 및 미니 프로젝트 논의** 오늘 개발 미팅에서는 제가 진행하려는 '개발 뉴스 허브(Dev News Hub)' 미니 프로젝트의 진행 상황에 대해 논의했습니다.

-   **진행 상황 보고**: 실무 역량 강화를 위한 데브 뉴스 허브 미니 프로젝트 개발 의사를 밝혔습니다.
-   **시간 할애에 대한 피드백**: 목요일에 있을 CMS 및 웹 빌더 툴 리서치 과제로 인해 미니 프로젝트에 많은 시간을 할애하지 못했음을 인정했습니다.
-   **다음 단계 및 자신감 고취**: 긍정적인 피드백을 받으며, PPT 발표가 끝난 후 커스텀 포스트 타입, 훅, 액션, 필터 관련 스킬이 능숙해지고 자신감이 생기면 다음 단계로 넘어가자고 독려받았습니다.

**3. 뉴스 기사 자동 스크래핑 및 워드프레스 업로드 스크립트 개발** 미팅 후에는 발표 자료를 완성하는 데 시간을 할애했으며, 가장 중요하게는 **파이썬 코드를 사용하여 뉴스 기사를 자동으로 스크래핑하고 워드프레스 REST API를 통해 `news` 커스텀 포스트 타입에 자동으로 업로드하는 코드를 작성했습니다. 이 개발은 초기 Docscraper 프로그램의 목표에서 확장된 것입니다.**

-   **프로젝트 목표**: ABC News 웹사이트에서 특정 토픽('computer-science')의 기사를 스크래핑하여 미리 지정된 워드프레스 사이트(`dev.gnasolutions.com.au/intern02`)에 게시물로 자동 업로드하는 파이썬 스크립트를 개발하는 것이 주 목표였습니다. 썸네일 이미지도 함께 업로드하고, 적절한 카테고리/태그를 할당하며, 기사 본문에서 불필요한 요소(광고, 공유 버튼, 관련 기사 섹션 등)를 제거하여 깔끔한 HTML을 추출하는 데 중점을 두었습니다.
    
-   **주요 기능 및 구현**:
    
    -   **기사 링크 수집 (`get_article_links_by_load_more`)**:
        -   초기에는 일반적인 페이지네이션(`?page=X`) 방식으로 링크를 수집하려 했으나, ABC News의 "더보기" 버튼이 AJAX API 호출을 통해 새로운 기사를 로드하는 것을 확인했습니다.
        -   따라서 스크립트는 웹 페이지의 "더보기" 버튼을 시각적으로 클릭하는 대신, 해당 버튼이 실제로 호출하는 API 엔드포인트(`https://www.abc.net.au/news/api/news-story-list-data/topic/{TOPIC_SLUG}`)를 직접 호출하여 기사 링크를 수집하도록 수정되었습니다.
        -   `offset`과 `count` 파라미터를 사용하여 API를 반복적으로 호출하며, 한 번에 `articles_per_request` (현재 8개)씩 기사 링크를 가져옵니다.
        -   `target_article_count` 변수를 통해 수집할 총 기사 목표 개수를 설정할 수 있으며, 스크립트는 이 목표 개수에 도달하거나 더 이상 새로운 기사 링크가 반환되지 않을 때까지 API 호출을 반복합니다.
    -   **기사 내용 파싱 (`parse_article_with_html`)**:
        -   각 기사 URL에 접속하여 Beautiful Soup을 사용하여 제목, 작성자, 날짜, 토픽 정보를 추출합니다.
        -   기사 본문 HTML을 추출하며, 이 과정에서 F12 개발자 도구를 통해 확인된 불필요한 HTML 요소(광고, 공유 버튼, "Related topics", "More Just In", 푸터 링크 등)들을 제거하여 깔끔한 본문만 남깁니다.
        -   기사 내의 첫 번째 이미지 URL도 찾아내어 썸네일로 활용할 수 있도록 준비합니다.
    -   **데이터 저장 (`save_to_csv`)**:
        -   수집 및 파싱된 기사 데이터는 `abc_articles_with_html.csv` 파일에 CSV 형태로 저장됩니다.
    -   **미리보기 생성 (`preview_article_html`)**:
        -   스크랩된 기사의 내용을 웹 브라우저에서 확인할 수 있도록 HTML 미리보기 파일(`article_preview.html`)을 생성합니다. 이는 파싱 및 정화 작업이 제대로 이루어졌는지 검토하는 데 유용합니다.
    -   **워드프레스 업로드 (`upload_to_wordpress`)**:
        -   워드프레스 REST API를 사용하여 스크랩된 기사를 새 게시물로 업로드합니다.
        -   `WP_USERNAME`과 `WP_APPLICATION_PASSWORD`를 사용하여 Basic Authentication 방식으로 인증합니다.
        -   파싱된 기사의 `topics` 정보를 기반으로 워드프레스의 카테고리 및 태그 ID를 매핑하여 게시물에 할당합니다. 이 매핑은 스크립트 시작 시 워드프레스 API로부터 동적으로 가져와 초기화됩니다.
        -   추출된 첫 번째 이미지가 있다면, 이를 워드프레스 미디어 라이브러리에 업로드한 후 해당 게시물의 대표 이미지(`featured media`)로 설정합니다.
        -   기사의 원본 작성자, 날짜, URL 등은 워드프레스 게시물의 메타 데이터로 저장됩니다.
-   **주요 해결 과제 및 논의**:
    
    -   **"더보기" 버튼 로직**: 초기에는 웹 페이지의 페이지네이션 링크를 찾으려 했으나, 실제로는 AJAX 호출로 동작하는 것을 파악하고, Selenium 사용 없이 `requests`로 직접 API를 호출하는 방식으로 전환했습니다. 이 방식은 더 효율적이고 빠릅니다.
    -   **워드프레스 카테고리/태그 매핑**: 워드프레스에서 카테고리와 태그를 미리 생성하고 그 ID를 스크립트에 매핑하는 것이 필요하며, 현재는 스크립트 실행 시 워드프레스 API를 통해 이를 동적으로 가져오도록 구현했습니다.
    -   **불필요한 HTML 요소 제거**: 미리보기 파일을 통해 기사 본문에 남아있는 불필요한 요소들을 지속적으로 확인하고, 제거 로직을 개선하여 본문 내용의 정확성을 높였습니다.
-   **다음 단계 및 검증 필요 사항**:
    
    -   **API URL 및 응답 구조 확인**:  `get_article_links_by_load_more` 함수 내의 `api_url_template`가 실제로 ABC News의 "더보기" 버튼이 호출하는 정확한 API 주소인지, 그리고 해당 API의 JSON 응답 구조(`data` 키 안에 기사 목록이 있는지, 각 기사의 URL 키가 `url` 또는 `link`인지 등)가 스크립트가 예상하는 것과 일치하는지 반드시 개발자 도구(Network 탭)를 통해 최종 확인해야 합니다.
    -   **스크립트 실행 테스트**: 스크립트를 실행하여 워드프레스에 실제 게시물이 잘 업로드되고, 내용이 제대로 파싱되며, 썸네일과 카테고리/태그가 올바르게 할당되는지 테스트해야 합니다.

## 🧠 배운 핵심 개념

-   **실무적 고객 소통 및 비즈니스 통찰**: 첫 고객사 대면 미팅을 통해 실제 비즈니스 맥락에서 고객 소통, 요구사항 도출, IT 서비스 제안 과정의 현실을 경험했습니다. 비개발자 관점에서 IT 서비스가 어떻게 진행되는지 이해하는 귀중한 시간이었습니다.
-   **API 기반 웹 스크래핑**: AJAX 기반의 API 엔드포인트를 식별하고 직접 상호작용하여 효율적으로 데이터를 수집하는 실질적인 경험을 얻었습니다. 이는 동적 콘텐츠를 위한 전통적인 HTML 파싱보다 훨씬 강력한 방법입니다.
-   **워드프레스 자동 콘텐츠 관리**: 워드프레스 REST API를 사용하여 게시물 생성, 미디어 업로드, 동적 텍소노미/메타데이터 할당 등 프로그래밍 방식으로 콘텐츠를 관리하는 방법을 숙달했습니다. 이는 사이트 업데이트를 자동화하는 강력한 방법입니다.
-   **강력한 데이터 클리닝 및 전처리**: 스크래핑된 HTML 콘텐츠에서 불필요한 요소를 제거하여 워드프레스에 업로드될 데이터의 품질과 유용성을 보장하는 것이 얼마나 중요한지 이해했습니다.

## 💡 실전 시행착오 및 팁

-   **API 발견을 위한 네트워크 트래픽 관찰**: 브라우저 개발자 도구(Network 탭)를 사용하여 "더보기" 버튼의 기본 AJAX API 호출을 발견한 것은 훨씬 효율적인 스크래핑 전략으로 이어졌습니다. 이는 동적 웹 콘텐츠를 다루는 데 필수적인 기술입니다.
-   **반복적인 HTML 클리닝**:  `preview_article_html` 기능은 HTML 클리닝 로직을 반복적으로 디버깅하고 개선하는 데 매우 효과적이었습니다. 이를 통해 출력물을 시각적으로 확인하고 원치 않는 요소를 체계적으로 제거할 수 있었습니다.
-   **동적인 워드프레스 객체 매핑**: 스크립트 실행 시 워드프레스 REST API를 통해 카테고리/태그 ID를 동적으로 가져오는 방식은 견고한 접근 방식입니다. 이를 통해 스크립트가 워드프레스 텍소노미 구조의 변경에 수동 업데이트 없이도 적응할 수 있습니다.
-   **기술 솔루션에서의 고객 공감**: 고객 미팅을 통해 성공적인 IT 솔루션은 기술적 능력뿐만 아니라, 비기술적인 사용자의 필요와 고충에 대한 깊은 이해, 즉 소통에서의 공감 능력이 중요함을 깨달았습니다.

## 🔜 Next Steps

-   **리서치 발표 자료 최종 완성**: "Open-Source CMS vs. Web Builders" PPT를 완성하고 다가오는 발표를 철저히 준비할 계획입니다.
-   **워드프레스 자동 업로드 스크립트 철저한 테스트**: 파이썬 스크립트의 포괄적인 테스트를 수행하여 워드프레스에 기사가 원활하고 정확하게 자동 업로드되는지, 콘텐츠, 이미지, 카테고리 및 태그가 올바른지 검증할 것입니다.
-   **Docscraper 프로그램 로직 정교화**: 지속적인 업데이트에 명시된 대로 `Docscraper` 프로그램의 데이터 선별 및 구조화에 중점을 두어, 효과적인 LLM 학습을 위한 고품질의 목표 지향적 데이터를 확보할 것입니다.
