# 📅 Day 02 (2025-06-17, Tue)

## 🎓 What I Did Today

**📌 Participated in the morning development meeting, briefing on the DevNewsHub scraping project and discussing dashboard customization with hooks, actions, and filters. Received advice on WP-Cron for automation with the WP REST API.**   
**📌 Explored and studied WP-Cron and System Cron (Linux) as part of a broader understanding of automated task scheduling.**   
**📌 Debugged and refined the ABC News scraping script, particularly addressing issues with dynamic content loading via Selenium and HTML parsing with Beautiful Soup.**   
**📌 Conducted additional study on Python's logging module, recognizing its importance in scraping code.**  

### Detailed Activities

**1. Morning Development Meeting & Task Review** The day started with a development meeting where I provided updates on ongoing projects and received key advice.

-   **Project Progress Briefing**: I briefed the team on the progress of the **DevNewsHub Python code for automated WordPress uploads using the WP REST API**. I also discussed efforts to customize the WordPress dashboard using **hooks, actions, and filters** to enhance development utility.
-   **WP-Cron Recommendation for Automation (WP REST API context)**: When discussing the DevNewsHub scraping script and its integration with the **WP REST API for data transfer**, I mentioned my interest in achieving full automation. My senior then advised me to look into **WP-Cron** as a method for automating such data delivery.

**2. Study on WP-Cron, System Cron (Linux), and Python Logging** Following the senior's advice and recognizing the need for robust automation, I studied WP-Cron and also revisited the concept of system cron. Additionally, I reviewed Python's logging module, which I encountered during yesterday's scraping work.

-   **WP-Cron**: Explored `WP-Cron` (via `https://developer.wordpress.org/plugins/cron/`), understanding it as WordPress's built-in task scheduler. It simulates a cron job and is typically executed when someone visits the WordPress site.
-   **System Cron (Linux)**: Revisited the concept of `system cron` from Linux studies, noting its more robust, system-level approach to scheduling commands or scripts to run automatically at precise intervals, independent of website traffic. This study further contributed to my understanding of operating systems.
-   **Python Logging Module**: Reviewed the Python `logging` module, which I encountered during yesterday's scraping code development. This study focused on its benefits for structured output, improved debugging, and maintainability compared to simple `print()` statements.

**3. ABC News Scraping Work Summary & Problem Identification** Today's primary focus was on the ABC News scraping script, aiming to collect article links from the 'Computer Science' topic page and parse their detailed content for WordPress publication.

-   **Attempted Work Today**:
    -   **Article Link Collection using Selenium**: Attempted to collect article links from the topic page using Selenium to handle the "Load more" button's AJAX loading.
    -   **Individual Article Content Parsing**: Worked on parsing content (title, author, date, topics, body HTML, first media URL) from collected article links, strengthening the purification logic to remove unwanted elements.

**4. Key Problems and Errors Encountered Today** The day was largely spent debugging issues arising from the website's dynamic nature and HTML structure changes.

-   **Dynamic Loading Issues**: Experienced problems finding and clicking the "Load more" button, suggesting changes in its CSS selector or loading behavior.
-   **Parsing Failures**: Encountered difficulties in consistently extracting article details (title, body, etc.) due to changes in the website's HTML structure.
-   **Thumbnail Extraction Problems**: Faced issues with extracting the primary image/video thumbnail URL, indicating changes in meta tags or embedded media structures.
-   **Content Purification Imperfections**: Noted that some unwanted elements (like bullet points or specific phrases) were still present in the purified body, or essential content was sometimes over-removed. I attempted to refine `elements_to_remove_selectors` to address this.

**5. Conclusion of Today's Work**: The entire day was dedicated to debugging and adjusting selectors for dynamic elements and HTML structure changes within the scraping script. Progress was limited due to these ongoing challenges.

## 🧠 Key Concepts Learned

-   **WP-Cron vs. System Cron for Task Automation**: Understood **WP-Cron** as WordPress's site-visit-triggered scheduler, suitable for periodic WordPress-dependent tasks. Contrasted this with **System Cron (Linux)**, a more robust, system-level utility for precise, independent task scheduling. This distinction is crucial for selecting the appropriate automation tool for different scenarios, especially for off-site processes like scraping.
-   **Python `logging` Module Fundamentals**: Studied the `logging` module as a superior alternative to `print()` for debugging and operational monitoring. Learned its benefits for structured output, varying log levels (DEBUG, INFO, ERROR), and improving the maintainability and readability of script execution.
-   **Dynamic Nature of Web Scraping**: Reaffirmed that web scraping is a highly dynamic task, constantly requiring adjustments to selectors and logic due to frequent changes in website structures and loading mechanisms (e.g., AJAX).
-   **Importance of Robust Error Handling in Scraping**: Learned the necessity of implementing comprehensive error handling and logging (as seen with `logging` module) to efficiently diagnose and troubleshoot issues like `404 Not Found` errors or selector failures.
-   **Selenium for Dynamic Content**: Gained practical experience using Selenium to interact with dynamic web elements like "Load more" buttons, which are inaccessible via simple HTTP requests.
-   **Iterative Debugging in Web Scraping**: Understood that debugging web scraping scripts is an iterative process, involving constant checking of browser developer tools, adjusting selectors, and re-running the script to verify changes.
-   **Data Purification Challenges**: Recognized the ongoing challenge of thoroughly purifying scraped HTML content to remove all "noise" while preserving essential information, and the need for continuous refinement of removal logic.

## 💡 Practical Trial-and-Error and Tips

-   **Browser Developer Tools are Essential**: For debugging scraping issues, consistently use browser developer tools (especially the Network and Elements tabs) to inspect how dynamic content loads and to identify correct, stable CSS selectors.
-   **Anticipate Website Changes**: Always assume that website structures will change. Design scraping scripts with modularity and clear logging to make future maintenance and adaptation easier.
-   **Refine Selectors Systematically**: When selectors fail, don't just guess. Systematically inspect the target HTML, identify unique attributes or parent-child relationships, and test new selectors incrementally.
-   **Validate Purified Content Locally**: Before uploading to WordPress, save the purified HTML content to a local file and visually inspect it to ensure all unwanted elements are removed and the core content is intact.
-   **Consider Task Schedulers for Automation**: For future automation tasks, evaluate whether **WP-Cron** (for WordPress-dependent tasks) or **system cron** (for independent, robust scheduling) is more appropriate based on reliability and execution frequency requirements.

## 🔜 Next Steps

-   **Implement Existing Article Skipping Logic**: Add a duplicate check feature to prevent already published articles from being re-scraped or re-published on WordPress. After this, I'll re-run the modified code to verify if unwanted elements like bullet points are correctly removed.
-   **Review Existing WordPress Articles**: Consider whether to modify the 8 existing articles on WordPress to align with the automated upload structure (e.g., addressing title duplication issues when the title is part of the body in the single post type).
-   **Troubleshoot Taxonomy Display on Dashboard**: Investigate why taxonomies are not visible on the WordPress dashboard despite code additions, ensuring elements are properly imported and displayed in real-time.

----------

# 📅 2일차 (2025-06-17, 화)

## 🎓 오늘 한 일

**📌 오전 개발 미팅에서 프로젝트 진행 상황을 브리핑하고, 훅, 액션, 필터를 활용한 대시보드 커스터마이즈에 대해 논의했습니다. WP REST API를 통한 자동화를 위해 WP-Cron 활용에 대한 조언을 받았습니다.**   
**📌 향후 작업 자동화를 위한 WP-Cron 및 리눅스 시스템 Cron에 대한 학습을 진행했습니다.**   
**📌 Selenium을 통한 동적 콘텐츠 로딩 및 Beautiful Soup을 통한 HTML 파싱 관련 문제를 해결하며 ABC 뉴스 스크래핑 스크립트를 디버깅하고 개선했습니다.**   
**📌 어제 스크래핑 코드 진행 중에 발견했던 파이썬 로깅 모듈에 대해 추가적으로 학습하고 정리했습니다.**  

### 상세 활동

**1. 오전 개발 미팅 및 업무 점검** 하루는 개발 미팅으로 시작되었고, 진행 중인 프로젝트에 대한 업데이트를 공유하고 중요한 조언을 받았습니다.

-   **프로젝트 진행 상황 브리핑**: **DevNewsHub 파이썬 코드**를 활용하여 **WP REST API를 통해 워드프레스에 자동으로 콘텐츠를 업로드하는 진행 상황**을 브리핑했습니다. 또한, 개발에 유용한 대시보드 커스터마이즈를 위해 **훅(hooks), 액션(actions), 필터(filters)를 활용하는 방안**에 대해 논의했습니다.
-   **자동화를 위한 WP-Cron 권장 (WP REST API 컨텍스트)**: DevNewsHub 스크래핑 스크립트와 **WP REST API를 통한 데이터 전달**에 대해 논의하면서, 완전한 자동화 솔루션 구현에 관심이 있다고 언급했습니다. 선임은 이러한 데이터 전달 자동화를 위해 **WP-Cron**을 활용해보라고 조언했습니다.

**2. WP-Cron, 시스템 Cron (Linux), 파이썬 로깅 학습** 선임의 조언에 따라, 그리고 견고한 자동화를 위해 필요하다고 판단하여 WP-Cron 및 시스템 Cron에 대한 학습을 진행했습니다. 또한, 어제 스크래핑 코드 진행 중에 발견했던 파이썬 로깅 모듈에 대해서도 공부했습니다.

-   **WP-Cron**: `WP-Cron` (참고: `https://developer.wordpress.org/plugins/cron/`)을 탐색하며, 워드프레스 내장 작업 스케줄러로, 사이트 방문 시 실행되는 크론 잡을 시뮬레이션함을 이해했습니다.
-   **시스템 Cron (Linux)**: 리눅스 학습 시 들었던 `system cron` 개념을 재정리하며, WP-Cron과 달리 사이트 트래픽에 의존하지 않고 정확한 간격으로 명령어나 스크립트를 자동으로 실행하도록 예약하는 더 견고한 시스템 수준의 접근 방식임을 파악했습니다. 이는 운영체제에 대한 이해를 넓히는 데 도움이 되었습니다.
-   **파이썬 로깅 모듈**: 어제 스크래핑 코드 개발 중 접했던 파이썬 `logging` 모듈을 검토했습니다. 이 학습은 간단한 `print()` 문 대신 구조화된 출력, 향상된 디버깅 및 유지보수성 측면에서 로깅 모듈이 제공하는 이점에 중점을 두었습니다.

**3. ABC 뉴스 스크래핑 작업 요약 및 문제점 정리** 오늘의 주요 초점은 ABC 뉴스 스크래핑 스크립트에 있었으며, '컴퓨터 과학' 토픽 페이지에서 기사 링크를 수집하고 워드프레스 게시용으로 상세 내용을 파싱하는 것을 목표로 했습니다.

-   **오늘 작업 시도 내용**:
    -   **Selenium을 이용한 기사 링크 수집**: "Load more" 버튼의 AJAX 로딩을 처리하기 위해 Selenium을 사용하여 토픽 페이지에서 기사 링크를 수집하려고 시도했습니다.
    -   **개별 기사 내용 파싱**: 수집된 기사 링크에서 콘텐츠(제목, 작성자, 날짜, 토픽, 본문 HTML, 첫 미디어 URL)를 파싱하는 작업을 진행했으며, 불필요한 요소를 제거하기 위한 정화 로직을 강화했습니다.

**4. 오늘 발생했던 주요 문제점 및 에러** 하루는 주로 웹사이트의 동적인 부분과 HTML 구조 변화에서 발생하는 오류를 디버깅하는 데 사용되었습니다.

-   **동적 로딩 문제**: "Load more" 버튼을 찾고 클릭하는 데 문제가 발생했으며, 이는 해당 버튼의 CSS 셀렉터나 로딩 동작이 변경되었음을 시사합니다.
-   **파싱 실패**: 웹사이트의 HTML 구조가 변경되어 기사 세부 정보(제목, 본문 등)를 일관되게 추출하는 데 어려움을 겪었습니다.
-   **썸네일 추출 문제**: `og:image` 메타 태그나 내장 미디어 구조 변경으로 인해 대표 이미지/비디오 썸네일 URL을 추출하는 데 문제가 발생했습니다.
-   **콘텐츠 정화 불완전**: 일부 불필요한 요소(예: 글머리 기호 또는 특정 문구)가 여전히 정화된 본문에 남아 있거나, 때로는 필수 콘텐츠가 과도하게 제거되는 문제가 있었습니다. 이를 해결하기 위해 `elements_to_remove_selectors`를 수정하여 개선을 시도했습니다.

**5. 오늘 작업 결론**: 결론적으로, 오늘은 웹사이트의 동적인 요소(Selenium으로 링크 가져오기)와 HTML 구조 변화(Beautiful Soup으로 내용 파싱)로 인해 발생하는 오류를 디버깅하고 셀렉터를 조정하는 데 하루 종일 집중했습니다. 이로 인해 상당한 진전은 제한적이었습니다.

## 🧠 배운 핵심 개념

-   **WP-Cron vs. 시스템 Cron을 통한 작업 자동화**: **WP-Cron**은 워드프레스 사이트 방문 시 트리거되는 예약 작업 방식으로, 워드프레스 종속적인 주기적 작업에 적합합니다. 이와 대조적으로 **시스템 Cron (Linux)**은 웹사이트 트래픽과 독립적으로 정밀하게 작업을 예약하는 더 견고한 시스템 수준의 유틸리티임을 이해했습니다. 이러한 구별은 스크래핑과 같은 외부 프로세스를 포함한 다양한 시나리오에 적합한 자동화 도구를 선택하는 데 중요합니다.
-   **파이썬 `logging` 모듈 기본 사항**: 디버깅 및 운영 모니터링을 위한 `print()` 문의 우수한 대안으로 `logging` 모듈을 학습했습니다. 구조화된 출력, 다양한 로그 레벨(DEBUG, INFO, ERROR), 스크립트 실행의 유지보수성 및 가독성 향상 측면에서의 이점을 배웠습니다.
-   **웹 스크래핑의 동적인 특성**: 웹 스크래핑은 웹사이트 구조 및 로딩 방식(예: AJAX)의 빈번한 변경으로 인해 셀렉터와 로직을 지속적으로 조정해야 하는 매우 동적인 작업임을 재확인했습니다.
-   **스크래핑에서 견고한 오류 처리의 중요성**: `404 Not Found` 오류나 셀렉터 실패와 같은 문제를 효율적으로 진단하고 해결하기 위해 포괄적인 오류 처리 및 로깅(`logging` 모듈 사용)을 구현하는 것의 필요성을 배웠습니다.
-   **동적 콘텐츠를 위한 Selenium 활용**: 단순 HTTP 요청으로는 접근할 수 없는 "더보기" 버튼과 같은 동적 웹 요소와 상호작용하기 위해 Selenium을 활용하는 실질적인 경험을 얻었습니다.
-   **웹 스크래핑의 반복적인 디버깅**: 웹 스크래핑 스크립트 디버깅은 브라우저 개발자 도구 확인, 셀렉터 조정, 변경 사항 확인을 위한 스크립트 재실행 등 반복적인 과정임을 이해했습니다.
-   **데이터 정화의 도전 과제**: 필수 정보를 보존하면서 모든 "노이즈"를 제거하기 위해 스크래핑된 HTML 콘텐츠를 철저히 정화하는 지속적인 도전과제와 제거 로직의 지속적인 개선 필요성을 인식했습니다.

## 💡 실전 시행착오 및 팁

-   **브라우저 개발자 도구의 필수성**: 스크래핑 문제 디버깅 시, 브라우저 개발자 도구(특히 Network 및 Elements 탭)를 일관되게 사용하여 동적 콘텐츠가 로드되는 방식과 올바르고 안정적인 CSS 셀렉터를 식별해야 합니다.
-   **웹사이트 변경 예측**: 웹사이트 구조는 언제든지 변경될 수 있다고 항상 가정해야 합니다. 향후 유지보수 및 적응을 용이하게 하기 위해 모듈성과 명확한 로깅을 갖춘 스크래핑 스크립트를 설계해야 합니다.
-   **셀렉터 체계적 개선**: 셀렉터가 실패할 경우, 단순히 추측하지 말고 대상 HTML을 체계적으로 검사하여 고유한 속성이나 부모-자식 관계를 식별하고 새로운 셀렉터를 점진적으로 테스트해야 합니다.
-   **정화된 콘텐츠 로컬에서 검증**: 워드프레스에 업로드하기 전에 정화된 HTML 콘텐츠를 로컬 파일로 저장하고 시각적으로 검사하여 모든 불필요한 요소가 제거되고 핵심 콘텐츠가 온전히 남아 있는지 확인해야 합니다.
-   **자동화를 위한 작업 스케줄러 고려**: 향후 자동화 작업을 위해 **WP-Cron** (워드프레스 의존적 작업용) 또는 **시스템 Cron** (독립적이고 견고한 예약용) 중 어떤 것이 신뢰성과 실행 빈도 요구 사항에 더 적합한지 평가해야 합니다.

## 🔜 Next Steps

-   **기존 기사 건너뛰기 로직 구현 및 불릿 포인트 제거 확인**: 이미 워드프레스에 게시된 기사는 다시 스크래핑하거나 게시하지 않도록 중복 체크 기능을 추가할 것입니다. 이어서 수정된 코드를 다시 실행하여 글머리 기호 및 기타 불필요한 요소들이 기사 본문에서 올바르게 제거되었는지 확인할 예정입니다.
-   **기존 워드프레스 기사 검토**: 기존에 업로드된 8개의 기사를 자동화된 업로드 구조에 맞게 수정해야 할지 고민할 것입니다 (예: 단일 포스트 타입에서 제목이 본문과 함께 표시되어 제목이 중복되는 현상 해결).
-   **대시보드 텍소노미 표시 문제 해결**: 코드 추가에도 불구하고 워드프레스 대시보드에 텍소노미가 보이지 않는 문제를 조사하여, 요소들이 실시간으로 올바르게 가져와지고 표시되는지 확인할 필요가 있습니다.
