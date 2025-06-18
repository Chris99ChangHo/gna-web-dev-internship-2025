# 📅 Day 01 (2025-06-18, WED)

## 🎓 What I Did Today

**📌 Participated in a development meeting and discussed Cron-related topics**   
**📌 Improved Python scraping code: Implemented duplicate article skipping logic**   **📌 Removed the function for previewing scraped content in HTML and refactored related code**   
**📌 Attempted to implement DevNewsHub search functionality for Posts widget**  

### Detailed Activities

**1. Attended Development Meeting:** - Received a question about using Cron during the progress update. - Shared my current lack of experience with Cron and uncertainty about its practical applications. - Learned about the WP-Crontrol plugin and its connection to REST API/AJAX knowledge. - Received the plugin link: `https://wordpress.org/plugins/wp-crontrol/`.

**2. Explored WP Crontrol Plugin:** - Understood the plugin's overview and key functionalities (e.g., viewing, editing, adding events, managing schedules). - Grasped practical application examples, such as managing Cron events via the `Tools → Cron Events` menu.

**3. Improved Python Scraping Code:** - **Implemented duplicate article skipping logic**: Added logic to compare newly collected links with previously saved links in a CSV file, effectively skipping already scraped articles. - **Removed the function for previewing scraped content in HTML and refactored code**: Decided that the function used to preview parsed article results in HTML was unnecessary for the actual WordPress upload/automation pipeline. Removed it and refactored other functions and the overall codebase that were affected, confirming its utility was limited to development and debugging stages.

**4. Attempted DevNewsHub Search Integration:** - Tried to implement a feature where searching in the DevNewsHub homepage search bar would directly synchronize with and display only news search results in the Posts widget below. - The implementation was unsuccessful today, and the root cause of the issue remains unknown.

## 🧠 Key Concepts Learned

-   **Concept and Necessity of Cron**: Understood its role as a scheduling tool for performing repetitive tasks at set times.
-   **WordPress Cron (WP-Cron)**: Learned about the mechanism within WordPress for scheduling and executing periodic tasks.
-   **WP Crontrol Plugin**: Explored this tool that provides a visual interface for managing and controlling WP-Cron events from the WordPress admin panel, offering features like viewing, editing, adding, and deleting events.
-   **Scraping Duplicate Handling Logic**: Gained insights into efficient data collection methods, such as using CSV files to check for and skip duplicates from previously collected data.

## 💡 Practical Trial-and-Error and Tips

-   **Considering Python Scraping Code and WP-Cron Integration**: Began to think about how to integrate a Python-based scraping script with the PHP-based WP-Cron (e.g., running the Python script as a server cronjob, or calling the Python script via a WP-Cron event). Further exploration is needed.
-   **WP-Cron Use Cases**: Conceived an automation scenario where "uploaded content is kept private and then made public at a specific time via WP-Cron," and drafted experimental code for it (to be checked tomorrow at 9:30 AM). This suggests WP-Cron's utility extends beyond simple data collection automation to content management automation.
-   **Separating Development/Production Code**: Reconfirmed the importance of removing functions only necessary during development/debugging from the production environment to enhance code efficiency and stability.
-   **Troubleshooting Search Widget Synchronization**: Encountered an issue where the DevNewsHub search bar couldn't directly synchronize results with the Posts widget. This highlights the need for debugging and understanding WordPress query loops or widget filtering mechanisms when custom search functionalities are implemented.

## 🔜 Next Steps

-   **Test WP-Cron Integration Practice Code**: Verify the functionality of the experimental code for automated content publishing via WP-Cron tomorrow (June 19th) at 9:30 AM.
-   **Deep Dive into Python Script and WP-Cron Integration Methods**: Further research and learn about efficient ways to periodically run Python scripts and reflect their results in WordPress (e.g., using server `crontab`, sending Python script results via WordPress REST API).
-   **Install and Explore WP Crontrol Plugin**: Plan to install the plugin directly and explore its features in detail from the admin panel.
-   **Expand Scraping Capabilities to New Platforms**: Begin developing specialized code for scraping articles from other news platforms like **BBC** and **NBC**, tailoring the scraping logic to their unique website structures.
-   **Debug DevNewsHub Search Functionality**: Investigate the cause of the failed search bar to Posts widget synchronization on the DevNewsHub homepage and implement a solution.
- **Install and Test Translation Plugin**: Integrate and test a translation plugin to implement English-Korean translation functionality, which is a core feature of this mini-project.

----------

# 📅 1일차 (2025-06-18, 수)

## 🎓 오늘 한 일

**📌 개발 미팅 참여 및 크론(Cron) 관련 논의**   
**📌 Python 스크래핑 코드 개선: 중복 기사 건너뛰기 로직 구현**   
**📌 스크랩 결과물 HTML 미리보기 함수 제거 및 관련 코드 수정**   
**📌 DevNewsHub 검색창 기능 구현 시도**  

### 상세 활영

**1. 개발 미팅 진행:** - 프로그레스 업데이트 중 크론(Cron) 활용 여부에 대한 질문 받음. - 현재 크론 미경험 및 활용처에 대한 고민 공유. - WP-Crontrol 플러그인 추천 및 REST API/AJAX 지식 연관성 설명 청취. - `https://wordpress.org/plugins/wp-crontrol/` 플러그인 링크 공유 받음.

**2. WP Crontrol 플러그인 기능 파악:** - 플러그인 개요 및 주요 기능(이벤트 확인, 편집, 추가, 스케줄 관리 등) 학습. - 실무 활용 예시(크론 이벤트 관리 메뉴) 이해.

**3. Python 스크래핑 코드 개선:** - **중복 기사 건너뛰기 로직 구현**: 기존에 스크랩된 기사를 건너뛰기 위해 CSV 파일에 저장된 이전 링크와 새로 수집한 링크를 비교하는 로직을 추가함. - **스크랩 결과물 HTML 미리보기 함수 제거 및 코드 전반 수정**: 실제 워드프레스 업로드/자동화 파이프라인에서 불필요하다고 판단되는, 파싱된 기사 결과를 HTML로 미리 볼 수 있게 하는 함수를 삭제하고, 이에 따라 영향을 받는 다른 함수들을 포함한 코드 전반을 수정함. 개발 및 디버깅 단계에서만 유용한 함수임을 확인.

**4. DevNewsHub 검색 기능 구현 시도:** - DevNewsHub 홈페이지 검색창에서 검색 시 하단의 Posts 위젯에 바로 동기화되어 뉴스 검색 기록만 뜨도록 구현을 시도함. - 오늘 시도에서는 실패했으며, 원인은 아직 파악하지 못함.

## 🧠 Key Concepts Learned

-   **크론(Cron)의 개념 및 필요성**: 정해진 시간에 반복 작업을 수행하는 스케줄링 도구의 역할 이해.
-   **워드프레스 크론(WP-Cron)**: 워드프레스 내에서 주기적인 작업을 예약하고 실행하는 메커니즘.
-   **WP Crontrol 플러그인**: 워드프레스 관리자 페이지에서 WP-Cron 이벤트를 시각적으로 관리하고 제어할 수 있는 도구. 이벤트 확인, 수정, 추가, 삭제 등 다양한 기능 제공.
-   **스크래핑 중복 처리 로직**: CSV 파일 등을 활용하여 이전에 수집한 데이터와의 중복을 검사하고 건너뛰는 효율적인 데이터 수집 방법.

## 💡 Practical Trial-and-Error and Tips

-   **Python 스크래핑 코드와 WP-Cron 연동 방안 고민**: PHP 기반의 WP-Cron과 Python으로 구현된 스크래핑 코드를 어떻게 연동할지에 대한 초기 고민 시작. (ex. Python 스크립트를 서버에서 cronjob으로 돌리고, 그 결과물을 워드프레스가 읽어들이는 방식 또는 WP-Cron 이벤트를 통해 Python 스크립트를 호출하는 방식 등 추가 탐색 필요)
-   **WP-Cron 활용 아이디어 구상**: "업로드된 내용을 비공개로 유지하다가 WP-Cron을 통해 특정 시간에 공개 처리"와 같은 자동화 시나리오 구상 및 실습 코드 작성 (내일 오전 9시 30분 확인 예정). 이는 WP-Cron이 단순한 데이터 수집 자동화를 넘어 콘텐츠 관리 자동화에도 활용될 수 있음을 시사함.
-   **개발/운영 환경 코드 분리**: 개발/디버깅 단계에서만 필요한 함수는 운영 환경에서 제거하여 코드의 효율성과 안정성을 높이는 것이 중요함을 재확인.
-   **검색 위젯 동기화 문제 해결**: DevNewsHub 검색창이 Posts 위젯과 직접 동기화되지 않는 문제에 직면함. 이는 사용자 정의 검색 기능 구현 시 워드프레스 쿼리 루프나 위젯 필터링 메커니즘에 대한 디버깅 및 이해가 필요함을 시사함.

## 🔜 Next Steps

-   **WP-Cron 연동 실습 코드 테스트**: 내일(6월 19일) 오전 9시 30분에 WP-Cron을 활용한 콘텐츠 공개 처리 자동화 실습 코드 동작 여부 확인.
-   **Python 스크립트와 WP-Cron 연동 방식 심층 탐색**: Python 스크립트를 주기적으로 실행하고 그 결과를 워드프레스에 반영하는 효율적인 방법에 대해 추가적으로 자료 조사 및 학습 (예: 서버 `crontab` 활용, 워드프레스 REST API를 통한 Python 스크립트 결과 전송 등).
-   **WP Crontrol 플러그인 실제 설치 및 탐색**: 플러그인을 직접 설치하여 관리자 화면에서 제공하는 기능들을 더 자세히 살펴볼 계획.
-   **다른 플랫폼 스크래핑 기능 확장**: **BBC**, **NBC**와 같은 다른 뉴스 플랫폼에 특화된 스크래핑 코드를 개발하여 스크랩 대상 확장을 시작할 계획.
-   **DevNewsHub 검색 기능 디버깅**: DevNewsHub 홈페이지 검색창과 Posts 위젯 간 동기화 실패 원인을 파악하고 해결책을 구현할 예정.
- **번역 플러그인 설치 및 테스트**: 이번 미니 프로젝트의 핵심 기능인 영한 번역 기능 구현을 위해 번역 플러그인을 설치하고 테스트할 계획.
