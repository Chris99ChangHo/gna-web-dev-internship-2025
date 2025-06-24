# 📅 Day 03 (2025-06-20, Fri)

## 🎓 What I Did Today

**📌 Participated in development meeting**   
**📌 Optimized responsive layout for ISAAC Painting client site**   
**📌 Attempted to apply scraping code to new news sites**   
**📌 Integrated and configured a translation plugin (GTranslate)**  

### Detailed Activities

**1. Development Meeting Participation:** 
- Reported progress on the mini-project (DevNewsHub), including site layout, search functionality, and Google login integration (via plugin). - Confirmed that scheduled Cron jobs were functioning correctly. 
- Mentioned ongoing mobile optimization work for the Isaac Painting site (assigned yesterday afternoon). 
- Received feedback to explore utilizing REST API to send data from WordPress externally for broader service applications in the future mini-project work.

**2. ISAAC Painting (Client Site) Work:** 
- **Responsive Layout Review and Improvement (Mobile/PC):** Reviewed and improved the responsive layout of the header, footer, and main content areas of the ISAAC Painting client site. 
- **Header/Menu Alignment Issue Resolution:** Repeatedly modified Flexbox structures and Elementor settings to align the logo and hamburger menu on a single line in mobile view. 
- Set Elementor Pro containers to Flexbox: Direction `Row`, Justify Content `Space Between`, Align Items `Center`. - Ensured Flex Direction remained `Row` at mobile breakpoints. 
- Resolved hamburger menu sizing by adjusting the toggle align option. 
- **Image Sizing for Alignment Stability:** Fixed alignment issues by setting image sizes with fixed `px` units instead of responsive units (`%`). 
- Specifically, fixed the logo image size in `px` to completely resolve Flexbox alignment problems on mobile. 
- **Thorough Breakpoint Setting Review and Adjustment:** Carefully checked and adjusted breakpoint settings (mobile/tablet). - Corrected mobile editor's breakpoint from tablet to mobile. 
- This breakpoint change successfully applied the mobile layout, aligning the logo and hamburger menu on one line. 
- **Client Site Migration Optimization (Actual Work Priority):** Prioritized and executed migration optimization tasks for the ISAAC Painting site, focusing on improving site performance and stability.

**3. DevNewsHub (Personal/Side Project) Work:** 
- **Attempted Scraping Code Application:** Tried to apply the scraping code to other news sites, specifically BBC. 
- Encountered strong anti-bot security on BBC, preventing article scraping despite attempting various selectors. 
- **Translation Plugin (GTranslate) Integration:** Installed and configured the GTranslate plugin for multilingual support. 
- Reviewed translation quality and responsive layout. 
- Used multiple language selector shortcodes (e.g., flag, name) to create links/buttons and applied them to the footer, providing a direct language selection UI to users.

## 🧠 Key Concepts Learned

-   **Elementor Flexbox for Responsive Design**: Advanced application of Elementor Pro's Flexbox containers for precise responsive layout control (including `Direction`, `Justify Content`, `Align Items`, and breakpoint-specific settings).
-   **Impact of Image Sizing Units on Responsiveness**: Understanding how fixed `px` vs. relative `%` units affect responsive image alignment, particularly within Flexbox layouts.
-   **WordPress Breakpoint Management**: The importance of correctly setting and adjusting breakpoints in page builders for accurate mobile rendering.
-   **Client Site Migration Best Practices**: Real-world application of migration optimization for improving site performance and stability.
-   **Anti-Bot Mechanisms in Web Scraping**: Encountering and understanding advanced anti-bot technologies (e.g., those used by BBC), which necessitate more sophisticated scraping techniques (e.g., headless browsers, CAPTCHA solving, IP rotation).
-   **Multilingual Website Implementation**: Practical experience with translation plugins (GTranslate) for offering language selection to users via shortcodes and UI elements.
-   **REST API for External Data Distribution**: Reinforcement of the concept that REST API can be used to send data outwards from WordPress for integration with other services/applications.

## 💡 Practical Trial-and-Error and Tips

-   **Iterative Responsive Design Process**: Realized that achieving pixel-perfect responsive design often requires iterative adjustments of Flexbox properties and breakpoint settings.
-   **Debugging Elementor Flexbox Layouts**: Specific issues like logo/hamburger menu alignment on mobile often boil down to correctly applying `Flex Direction: Row` and `Justify Content: Space Between` at the mobile breakpoint.
-   **Choosing Image Sizing Units**: For critical alignment elements like logos, fixed `px` sizing can sometimes be more reliable than percentage-based sizing in complex responsive layouts.
-   **Addressing Web Scraping Challenges**: Acknowledged that popular news sites frequently employ robust anti-scraping measures, necessitating more advanced strategies beyond simple `requests` and `BeautifulSoup`. This will require further research into dynamic content rendering and bot detection bypass.
-   **Enhancing User-Friendly Translation UI**: Providing clear language selection options (flags, text links) in accessible locations like the footer improves user experience for multilingual sites.
-   **Importance of Real-World Client Work**: Gaining practical experience with migration optimization on an actual client site offers valuable insights into performance and stability considerations.
-   **Proactive REST API Exploration**: The advice to explore sending data externally via REST API is a forward-looking step towards building more interconnected services, moving beyond just data ingestion.
-   **WordPress Search Result Customization Challenges**: Faced the challenge where search results, when displayed within the same page (not a new window), revert to the theme's default structure instead of applying the Elementor Pro theme builder's layout. This implies that custom coding will be needed to ensure the desired layout is applied to internal search results, as widget-based solutions might not suffice.

## 🔜 Next Steps

-   **Expand Scraping Capabilities to New Platforms (Advanced)**: Research and implement more advanced scraping techniques (e.g., using Selenium for headless Browse, rotating proxies) to bypass anti-bot security on challenging sites like BBC.
-   **Customize DevNewsHub Internal Search Result Layout (Code-Based)**: Address the issue of internal search results displaying in the default theme structure. This will involve custom coding to ensure the search results inherit the intended theme builder's design, as widget-based solutions are insufficient.
-   **Further Optimize Isaac Painting Site**: Continue to refine font consistency and ensure full mobile responsiveness across various devices.
-   **Explore Custom REST API Endpoint Implementation for External Data Sending**: Begin actual implementation of custom REST API endpoints for features like personalized article feeds or analytics data, focusing on sending data outwards from WordPress.

----------

# 📅 3일차 (2025-06-20, 금)

## 🎓 오늘 한 일

**📌 개발 미팅 참여**   
**📌 ISAAC Painting 클라이언트 사이트 반응형 레이아웃 최적화 작업 진행**   
**📌 새로운 뉴스 사이트 스크래핑 코드 적용 시도**   
**📌 번역 플러그인(GTranslate) 설치 및 설정**  

### 상세 활동

**1. 개발 미팅 참여:** 
- 미니 프로젝트(DevNewsHub)와 관련하여 사이트 레이아웃, 검색 기능, 구글 로그인 연동(플러그인 활용) 등의 진행 상황을 보고함. 
- 예약해둔 크론(Cron) 작업들이 정상적으로 작동하고 있음을 보고함. 
- 어제 오후에 지시받았던 Isaac Painting 모바일 최적화 업무 진행 상황을 공유함. 
- 선임 개발자로부터 다음 미니 프로젝트 작업 시 REST API를 활용하여 워드프레스 내부 데이터를 외부로 보내거나, 이를 활용하는 서비스를 구상해 볼 것을 조언받음.

**2. ISAAC Painting (클라이언트 사이트) 작업:** 
- **모바일/PC 반응형 레이아웃 점검 및 개선**: 클라이언트 사이트 ISAAC Painting의 헤더, 푸터, 메인 콘텐츠 영역 전반의 반응형 레이아웃을 점검하고 구조를 개선함. 
- **로고 및 햄버거 메뉴 정렬 문제 해결**: 로고와 햄버거 메뉴가 모바일에서 한 줄에 정렬되도록 Flexbox 구조와 Elementor 설정을 반복적으로 수정함. 
- Elementor Pro에서 컨테이너를 Flexbox로 설정하고, Direction을 `Row`, Justify Content를 `Space Between`, Align Items를 `Center`로 조정함. - 모바일 브레이크포인트에서도 Flex Direction이 `Row`로 유지되도록 설정함.
- 햄버거 메뉴 크기 조절은 토글 얼라인 옵션을 변경하여 해결함. 
- **이미지 크기 고정을 통한 정렬 문제 해결**: 이미지 크기를 반응형 단위(%) 대신 `px`로 고정하여 정렬 문제를 해결함. 
- 특히 로고 이미지를 `px` 단위로 고정하여 모바일에서 Flexbox 정렬 문제를 완전히 해결함. 
- **브레이크포인트(모바일/태블릿) 설정 꼼꼼히 점검 및 조정**: 모바일 에디터에서 브레이크포인트가 태블릿으로 설정되어 있어 모바일로 변경함. 
- 브레이크포인트 변경으로 모바일 레이아웃이 정상적으로 적용되어 로고와 햄버거 메뉴가 한 줄에 정렬됨을 확인함. 
- **클라이언트 사이트 마이그레이션 최적화(실제 업무)**: ISAAC Painting 사이트의 마이그레이션 최적화 작업을 실제 업무 우선순위로 진행하며 사이트 성능 및 안정성 향상에 기여함.

**3. DevNewsHub (개인/사이드 프로젝트) 작업:** 
- **스크래핑 코드 적용 시도**: 다른 뉴스 사이트(예: BBC)에서 스크래핑 코드를 적용하려고 시도함. 
- BBC의 안티봇(anti-bot) 보안이 강하여 여러 선택자를 시도했음에도 불구하고 기사를 긁어오지 못하는 상황에 직면함. 
- **번역 플러그인(GTranslate) 적용**: 다국어 지원을 위해 GTranslate 플러그인을 설치하고 설정함. 
- 번역 품질 및 반응형 레이아웃을 점검함. 
- 언어 선택기 숏코드 여러 개를 사용하여 (깃발, 이름) 형태로 링크/버튼을 만들어 푸터에 적용, 사용자에게 직접 선택 가능한 UI를 제공함.

## 🧠 배운 핵심 개념

-   **Elementor Flexbox를 활용한 반응형 디자인**: Elementor Pro의 Flexbox 컨테이너를 활용한 정밀한 반응형 레이아웃 제어(Direction, Justify Content, Align Items 및 브레이크포인트별 설정 포함)에 대한 고급 적용 방법.
-   **이미지 크기 단위의 반응형 영향**: Flexbox 레이아웃 내에서 고정 `px` 단위와 상대 `%` 단위가 반응형 이미지 정렬에 미치는 영향 이해.
-   **워드프레스 브레이크포인트 관리**: 정확한 모바일 렌더링을 위해 페이지 빌더에서 브레이크포인트를 올바르게 설정하고 조정하는 것의 중요성.
-   **클라이언트 사이트 마이그레이션 모범 사례**: 성능 및 안정성을 위한 마이그레이션 최적화의 실제 적용.
-   **웹 스크래핑의 안티봇 메커니즘**: BBC와 같은 웹사이트에서 사용되는 강력한 안티봇 기술을 접하고 이해하며, 더 정교한 스크래핑 기술(예: 헤드리스 브라우저, CAPTCHA 해결, IP 로테이션)의 필요성 인지.
-   **다국어 웹사이트 구현**: 숏코드 및 UI 요소를 통해 사용자에게 언어 선택을 제공하기 위한 번역 플러그인(GTranslate)의 실제 사용 경험.
-   **REST API를 활용한 외부 데이터 분배**: REST API가 워드프레스에서 외부로 데이터를 전송하여 다른 서비스/앱과 통합하는 데 사용될 수 있다는 개념의 재확인.

## 💡 실습 시 시행착오 및 팁

-   **반복적인 반응형 디자인 과정**: 완벽한 반응형 디자인을 달성하려면 Flexbox 속성과 브레이크포인트 설정을 반복적으로 조정해야 함을 깨달음.
-   **Elementor Flexbox 레이아웃 디버깅**: 모바일에서 로고/햄버거 메뉴 정렬과 같은 특정 문제는 모바일 브레이크포인트에서 `Flex Direction: Row` 및 `Justify Content: Space Between`을 올바르게 적용하는 것으로 해결될 수 있음.
-   **이미지 크기 단위 선택**: 로고와 같은 중요한 정렬 요소의 경우, 복잡한 반응형 레이아웃에서는 고정 `px` 크기 지정이 백분율 기반 크기 지정보다 더 안정적일 수 있음.
-   **웹 스크래핑 도전 과제**: 인기 뉴스 사이트들이 강력한 안티 스크래핑 조치를 사용하는 경우가 많으므로, 단순 `requests` 및 `BeautifulSoup` 이상의 고급 전략이 필요함을 인지함. 동적 콘텐츠 렌더링 및 봇 감지 우회에 대한 추가 조사가 필요할 것임.
-   **사용자 친화적인 번역 UI 개선**: 푸터와 같은 접근하기 쉬운 위치에 명확한 언어 선택 옵션(깃발, 텍스트 링크)을 제공하는 것이 다국어 사이트의 사용자 경험을 향상시킴.
-   **실제 클라이언트 작업의 중요성**: 실제 클라이언트 사이트의 마이그레이션 최적화 작업을 통해 성능 및 안정성 고려사항에 대한 귀중한 통찰력을 얻음.
-   **선제적인 REST API 탐색**: REST API를 통해 외부로 데이터를 전송하는 것을 탐색하라는 조언은 더 상호 연결된 서비스를 구축하기 위한 미래 지향적인 단계이며, 단순히 데이터 수집을 넘어선다.
-   **워드프레스 검색 결과 커스터마이징의 어려움**: 검색 결과가 (새 창이 아닌) 홈페이지 내부에서 표시될 때 Elementor Pro 테마 빌더의 레이아웃이 적용되지 않고 테마의 기본 구조로 돌아가는 문제에 직면함. 이는 위젯 기반 솔루션만으로는 부족하며, 원하는 레이아웃을 내부 검색 결과에 적용하려면 **코드 기반의 추가적인 사용자 정의**가 필요함을 의미함.

## 🔜 이후 학습 방향

-   **다른 플랫폼 스크래핑 기능 확장 (고급)**: BBC와 같은 까다로운 사이트의 안티봇 보안을 우회하기 위한 고급 스크래핑 기술(예: 헤드리스 브라우징을 위한 Selenium 사용, 프록시 로테이션)을 조사하고 구현할 계획.
-   **DevNewsHub 내부 검색 결과 레이아웃 사용자 정의 (코드 기반)**: 내부 검색 결과가 기본 테마 구조로 표시되는 문제를 해결하고, 원하는 테마 빌더의 디자인과 일치하도록 레이아웃을 **코드 기반으로** 수정할 예정.
-   **Isaac Painting 사이트 추가 최적화**: 폰트 일관성을 더욱 정교하게 맞추고, 다양한 기기에서 완전한 모바일 반응성을 확보하기 위한 작업을 계속 진행.
-   **커스텀 REST API 엔드포인트 구현 탐색**: 개인 맞춤 기사 피드 또는 분석 데이터와 같은 기능을 위한 커스텀 REST API 엔드포인트의 실제 구현을 시작할 계획. (워드프레스에서 외부로 데이터 전송에 중점).
