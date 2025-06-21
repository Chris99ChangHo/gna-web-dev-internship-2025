# 📅 Day 02 (2025-06-19, Thu)

## 🎓 What I Did Today

**📌 Practiced Cron job and established an automation structure**   
**📌 Explored directions for REST API utilization**   
**📌 Gained experience in automated article collection and publishing using Python, WP REST API, and Cron**   
**📌 Integrated Google Social Login with WordPress**   
**📌 Prepared WordPress for external data integration via REST API**   
**📌 Improved Login/Signup UI and troubleshooted related issues**   
**📌 Adjusted DevNewsHub site layout and resolved search result display**  
**📌 Worked on Isaac Painting client site's font and mobile optimization**  

### Detailed Activities

**1. Cron Job Practice and Automation Structure:** 
- Conducted a practical exercise for Cron jobs with a simple example. 
- Modified portions of the Python code for scraping and upload automation to ensure articles are uploaded in a **private** status. 
- Configured a scheduled Cron event to **publish** these privately uploaded articles daily, confirming its successful operation today.

**2. Exploring REST API Utilization:** 
- Received advice from a senior developer to gain experience not only in fetching data via REST API but also in **sending data externally**. 
- Discussed examples where, in addition to bringing data into a WordPress (WP) website, app developers utilize this data for broader services or applications. 
- Directed to the official WordPress REST API documentation: `https://developer.wordpress.org/rest-api/`.

**3. Current Experience Overview (from previous day's discussion):** 
- Gained hands-on experience in **automating article scraping from external sites using Python and uploading them to the DevNewsHub site via the WP REST API**. This encompassed the entire flow of automated article collection and publishing. 
- Successfully implemented data collection and publishing using Cron jobs and the REST API. 
- **Currently, these operations are in the manual execution phase**. For regular automation, additional **system cron** configuration is required (needs verification: possibly due to lack of permission for wp-cron to execute Python code).
- Furthermore, regular automation isn't fully implemented yet, as **scraping code needs to be adapted to work across various platforms**.

**4. WordPress Social Login Integration:** 
- Completed Google Social Login integration using the **Nextend Social Login plugin**. 
- Process included: creating a Google OAuth client, registering redirect URIs, entering Client ID/Secret into the plugin, and enabling the feature. 
- Tested the use of shortcodes and widgets to ensure social login buttons were properly displayed on the Login/Signup UI.

**5. REST API Practice and External Integration Preparation:** 
- Designed a structure for external web/app data utilization using the WordPress REST API. 
- Organized examples and practice methods for custom endpoints, such as personalized article feeds and article statistics/analysis data. 
- Confirmed endpoint design and authentication methods (e.g., JWT, OAuth) for external services to genuinely retrieve and utilize WordPress data.

**6. Login/Signup UI Improvement:** 
- Standardized button text to "Sign in / Sign up" for consistent user experience (UX). 
- Practiced various methods (shortcodes, widgets, Elementor custom code) to add social login buttons to the UI when they didn't appear by default.

**7. Problem Solving and Practice Feedback:** 
- Resolved `redirect_uri_mismatch` errors during Google OAuth integration by accurately registering the actual requested `redirect_uri` in the Google Console. 
- Confirmed normal operation after enabling a social login Provider that was in a Disabled state. 
- Verified methods for implementing custom registration forms using plugins and shortcodes due to the absence of a default WordPress registration widget.

**8. DevNewsHub Site Layout and Search Result Display:** 
- Made various adjustments to the overall layout of the DevNewsHub website. 
- Successfully implemented the search functionality to display results within the homepage (not in a new window). However, the search results currently default to the theme's default structure, not applying the theme builder's layout, which requires further layout modification.

**9. Isaac Painting Client Site Work:** 
- Realized the previously completed Isaac Painting client site was actually a migration task similar to the past "dentalcore" project. 
- Spent time finalizing font adjustments and optimizing for mobile responsiveness until the end of the workday.

## 🧠 Key Concepts Learned

-   **Cron Job Implementation**: Practical application of Cron for scheduling and automating tasks.
-   **WordPress Private/Publish Status Control**: Utilizing WordPress post statuses to manage content visibility via automated processes.
-   **REST API for Bi-directional Data Flow**: Understanding that REST API is not just for fetching but also for sending data, enabling broader application integration.
-   **System Cron vs. WP-Cron**: Recognizing the distinction and potential permission considerations between system-level cron jobs and WordPress-specific cron.
-   **WordPress Social Login Integration**: Practical steps for connecting WordPress with external authentication providers like Google using plugins.
-   **OAuth 2.0 Flow (Client Creation, Redirect URIs, Client ID/Secret)**: Hands-on experience with the key components of OAuth for secure third-party authentication.
-   **WordPress REST API Custom Endpoints**: Designing and preparing custom API endpoints for specific data needs (e.g., personalized feeds, analytics).
-   **API Authentication Methods (JWT, OAuth)**: Awareness of different security mechanisms for controlling API access.
-   **WordPress UI Customization (Shortcodes, Widgets, Elementor)**: Methods for dynamically inserting and managing content/functionality in WordPress interfaces.
-   **Responsive Web Design**: Importance of font consistency and mobile optimization for client sites.

## 💡 Practical Trial-and-Error and Tips

-   **Automating Content Lifecycle with Cron**: Successfully set up a Cron event to transition articles from private to public, demonstrating a basic but effective content automation pipeline.
-   **Exploring REST API for External Data Transfer**: Realized the broader potential of REST API for data distribution beyond just data ingestion into WordPress. This opens up possibilities for integrating with other services or applications.
-   **Identifying Automation Gaps**: Pinpointing that current automation is manual and requires further setup (system cron, cross-platform scraping) for true regular automation. This helps in prioritizing next steps.
-   **Debugging OAuth Redirect URI Mismatches**: Practical experience in resolving common OAuth errors by meticulously matching redirect URIs.
-   **Enabling Plugin Providers**: A simple yet crucial step to ensure social login functionality works after initial setup.
-   **Client Site Migration Considerations**: Realizing that a "completion" might evolve into a migration or optimization task, requiring further attention to details like font and mobile responsiveness.

## 🔜 Next Steps

-   **Expand Scraping Capabilities to New Platforms**: Begin developing specialized code for scraping articles from other news platforms like **BBC** and **NBC**, tailoring the scraping logic to their unique website structures.
-   **Install and Test Translation Plugin**: Integrate and test a translation plugin to implement English-Korean translation functionality, which is a core feature of this mini-project.
-   **Investigate System Cron vs. WP-Cron Python Execution**: Research the best practices and permissions required for running Python scripts as scheduled tasks, especially in the context of WordPress.
-   **Further Optimize Isaac Painting Site**: Continue to refine font consistency and ensure full mobile responsiveness across various devices.
-   **Explore Custom REST API Endpoint Implementation**: Begin actual implementation of custom REST API endpoints for features like personalized article feeds or analytics data.

----------

# 📅 2일차 (2025-06-19, 목)

## 🎓 오늘 한 일

**📌 크론 작업 실습 및 자동화 구조 확립** 
**📌 REST API 활용 방향 탐색** 
**📌 Python, WP REST API, 크론을 활용한 기사 자동 수집 및 게시 경험 습득** 
**📌 워드프레스 구글 소셜 로그인 연동** 
**📌 REST API를 활용한 워드프레스 외부 데이터 연동 준비** 
**📌 로그인/회원가입 UI 개선 및 관련 문제 해결** 
**📌 DevNewsHub 사이트 레이아웃 조정 및 검색 결과 표시 문제 해결**  
**📌 Isaac Painting 클라이언트 사이트 폰트 및 모바일 최적화 작업 진행**  

### 상세 활영

**1. 크론 작업 실습 및 자동화 구조:** 
- 간단한 예시를 통해 크론 작업 실습을 진행함. 
- 스크래핑 및 업로드 자동화 Python 코드를 일부 수정하여, 기사들이 **비공개(private)** 상태로 업로드되도록 변경함. 
- 예약된 크론 이벤트를 통해, 매일 비공개 상태로 업로드된 기사들을 **공개(publish)**하는 구조로 크론 이벤트를 설정하고, 오늘 정상적으로 동작하는 것을 확인함.

**2. REST API 활용 방향 탐색:** 
- 개발 선임으로부터 REST API를 통해 데이터를 가져오는 것뿐만 아니라, **외부로 데이터를 보내는 경험**도 해보라는 조언을 받음. 
- 외부에서 데이터를 받아와 워드프레스(WP) 웹에 올리는 것 외에, 앱 개발자들이 이 데이터를 앱으로 옮겨 **다른 서비스로 확장하거나 활용하는 사례**를 언급함. 
- 공식 문서(`https://developer.wordpress.org/rest-api/`)를 참고하라고 안내받음.

**3. 현재까지의 경험 (이전 논의 내용 반영):** 
- Python 코드로 외부 사이트에서 뉴스 기사를 스크랩하여, WP REST API를 활용해 DevNewsHub 사이트에 업로드하는 **자동화 경험**을 쌓음. (자동화된 기사 수집 및 게시의 전체 흐름을 경험) 
- 크론 작업과 REST API를 활용해 **데이터 수집 및 게시를 성공적으로 구현**함. 
- **현재는 수동 실행 단계**이며, 정기적으로 자동화하려면 **시스템 크론(system cron)을 추가로 설정**해야 함. (WP-Cron으로 Python 코드를 실행시키는 권한이 없는지 사실 확인 필요) - 또한, 다양한 플랫폼에서 동작할 수 있는 스크래핑 코드 작성이 필요하므로, **정기적 자동화는 아직 구현되지 않은 상태**임.

**4. 워드프레스 소셜 로그인 연동:** 
- **Nextend Social Login 플러그인**을 사용하여 구글 소셜 로그인 연동을 완료함. 
- **구글 OAuth 클라이언트 생성, 리디렉션 URI 등록, 플러그인에 Client ID/Secret 입력, 활성화(Enable)**까지 진행함. 
- 로그인/회원가입 UI에서 소셜 로그인 버튼이 정상적으로 표시되도록 **숏코드 및 위젯 활용법**을 테스트함.

**5. REST API 실습 및 외부 연동 준비:** 
- 워드프레스 REST API를 활용해 **외부 웹/앱에서 데이터 활용이 가능한 구조를 설계**함. 
- 사용자별 맞춤 기사 피드, 기사 통계/분석 데이터 등 **커스텀 엔드포인트 예시와 실습 방법을 정리**함. 
- 외부 서비스에서 워드프레스 데이터를 실제로 가져오거나 활용할 수 있도록 **엔드포인트 설계 및 인증 방식(예: JWT, OAuth 등)을 확인**함.

**6. 로그인/회원가입 UI 개선:** 
- "Sign in / Sign up" 조합으로 버튼 텍스트를 통일하고, 사용자 경험(UX) 관점에서 일관성 있게 적용함. 
- 소셜 로그인 버튼이 나타나지 않는 경우, **숏코드/위젯/Elementor 커스텀 코드** 등 다양한 방법으로 UI에 추가하는 방법을 실습함.

**7. 문제 해결 및 실습 피드백:** 
- 구글 OAuth 연동 과정에서 **`redirect_uri_mismatch` 오류 발생 시, 실제 요청된 redirect_uri를 구글 콘솔에 정확히 등록**해 해결함. 
- 소셜 로그인 Provider가 Disabled 상태일 때 **활성화(Enable) 처리로 정상 작동**을 확인함. 
- 워드프레스의 기본 회원가입 위젯 부재를 인지하고, **플러그인 및 숏코드 활용을 통한 커스텀 회원가입 폼 구현 방법**을 확인함.

**8. DevNewsHub 사이트 레이아웃 및 검색 결과 표시:** 
- DevNewsHub 사이트의 전반적인 레이아웃을 수정함. 
- 검색창에서 검색 시 결과가 새 창이 아닌 홈페이지 내부에서 뜨도록 구현을 성공함. 하지만, 검색 결과가 테마 빌더가 아닌 워드프레스 기본 구조로 출력되어 레이아웃 추가 수정이 필요함을 파악함.

**9. Isaac Painting 클라이언트 사이트 작업:** 
- 이전에 완료했다고 생각했던 Isaac Painting 클라이언트 사이트가 사실 dentalcore 마이그레이션과 유사한 작업임을 인지함. 
- 최종적으로 **폰트를 맞추고 모바일 최적화 작업**을 진행하다 퇴근함.

## 🧠 배운 핵심 개념

-   **크론 작업 구현**: 작업을 스케줄링하고 자동화하기 위한 크론의 실제 적용.
-   **워드프레스 비공개/공개 상태 제어**: 자동화된 프로세스를 통해 콘텐츠 가시성을 관리하기 위한 워드프레스 게시물 상태 활용.
-   **양방향 데이터 흐름을 위한 REST API**: REST API가 데이터를 가져오는 것뿐만 아니라 외부로 보내는 데에도 사용될 수 있음을 이해하여, 더 광범위한 애플리케이션 통합 가능성 인지.
-   **시스템 크론 vs. WP-Cron**: 시스템 수준의 크론 작업과 워드프레스 특정 크론 간의 차이점 및 잠재적인 권한 고려사항 인지.
-   **워드프레스 소셜 로그인 연동**: Nextend Social Login 플러그인을 활용한 구글 소셜 로그인 연동 경험.
-   **OAuth 2.0 기본 이해**: 구글 OAuth 클라이언트 생성, 리디렉션 URI 등록 등 OAuth 연동의 핵심 절차 숙지.
-   **워드프레스 REST API 커스텀 엔드포인트 설계**: 특정 데이터(사용자별 맞춤 피드, 통계 등)를 위한 맞춤형 API 엔드포인트 설계 개념.
-   **API 인증 방식**: JWT, OAuth 등 외부 서비스와의 안전한 데이터 연동을 위한 인증 방식에 대한 이해.
-   **워드프레스 UI 커스터마이징**: 숏코드, 위젯, Elementor 커스텀 코드를 활용한 UI 요소 추가 및 관리.
-   **반응형 웹 디자인**: 폰트 일관성 유지 및 모바일 환경 최적화의 중요성 재확인.

## 💡 Practical Trial-and-Error and Tips

-   **크론을 활용한 콘텐츠 수명 주기 자동화**: 기사를 비공개에서 공개로 전환하는 크론 이벤트를 성공적으로 설정하여, 간단하지만 효과적인 콘텐츠 자동화 파이프라인을 시연함.
-   **외부 데이터 전송을 위한 REST API 탐색**: REST API의 잠재력이 워드프레스에 데이터를 가져오는 것을 넘어 데이터 배포에도 확장될 수 있음을 깨달음. 이는 다른 서비스나 애플리케이션과의 통합 가능성을 열어줌.
-   **자동화 격차 식별**: 현재 자동화가 수동 단계이며, 진정한 정기적 자동화를 위해서는 추가 설정(시스템 크론, 크로스 플랫폼 스크래핑)이 필요함을 파악함. 이는 다음 단계의 우선순위를 정하는 데 도움을 줌.
-   **OAuth `redirect_uri_mismatch` 오류 해결**: 구글 콘솔에 실제 요청된 URI를 정확히 등록함으로써 흔히 발생하는 OAuth 오류를 해결한 경험.
-   **플러그인 활성화의 중요성**: 소셜 로그인 Provider가 Disabled 상태일 때 이를 활성화(Enable) 처리하여 기능이 정상 작동함을 확인.
-   **클라이언트 작업의 유동성**: 프로젝트가 완료된 후에도 추가적인 최적화나 마이그레이션 작업이 발생할 수 있음을 경험하며, 작업의 범위가 확장될 수 있음을 인지.

## 🔜 다음 단계

-   **다른 플랫폼 스크래핑 기능 확장**: **BBC**, **NBC**와 같은 다른 뉴스 플랫폼에 특화된 스크래핑 코드를 개발하여 스크랩 대상 확장을 시작할 계획.
-   **번역 플러그인 설치 및 테스트**: 이번 미니 프로젝트의 핵심 기능인 영한 번역 기능 구현을 위해 번역 플러그인을 설치하고 테스트할 계획.
-   **시스템 크론 vs. WP-Cron Python 실행 조사**: 워드프레스 환경에서 Python 스크립트를 예약된 작업으로 실행하기 위한 최적의 방법과 필요한 권한에 대해 조사.
-   **Isaac Painting 사이트 추가 최적화**: 폰트 일관성을 더욱 정교하게 맞추고, 다양한 기기에서 완전한 모바일 반응성을 확보하기 위한 작업을 계속 진행.
-   **커스텀 REST API 엔드포인트 구현 탐색**: 개인 맞춤 기사 피드 또는 분석 데이터와 같은 기능을 위한 커스텀 REST API 엔드포인트의 실제 구현을 시작할 계획.
