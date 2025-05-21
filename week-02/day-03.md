# 📅 Day 03 (2025-05-21, Wed)

## 🎓 What I Did Today

**📌 Attended daily development meeting at 9 AM.**  
**📌 Received a new practical assignment: building an e-commerce site using WooCommerce, referencing gangnamsyrup.com.au.**  
**📌 Completed WooCommerce initial setup and product registration.**  
**📌 Started and significantly progressed on the header section, focusing on logo, navigation menu, and utility icons (Search, My Account, Cart).**  
**📌 Investigated and applied methods for mobile and tablet optimization, specifically for banners and embedded videos.**  
**📌 Explored using Elementor's Product widget with queries to organize specific product displays.**  
**📌 Investigated how WooCommerce handles user registration and login processes on the My Account page.**  
**📌 Explored how the default Shop page displays all products and how to organize them using queries.**  
**📌 Reviewed and summarized common WooCommerce and Elementor development challenges and their solutions from today's practice.**  

### WooCommerce E-commerce Client Site Practice
- **Project Goal:** Begin building an e-commerce site, replicating design and functionality from [gangnamsyrup.com.au](https://gangnamsyrup.com.au/).
- **WooCommerce Initial Setup & Product Registration:** Completed the foundational WooCommerce settings and uploaded initial product data.
- **Header Implementation:**
    - Structured header using 3 Elementor containers: Site Logo, Navigation Menu, and a section for utility icons (Search, My Account, Cart).
    - **Search Icon:** Explored Elementor's `Search` widget functionalities, noting its current limitations for built-in overlay or dropdown skin options. Understood that achieving such advanced search UIs now likely requires custom CSS/JavaScript or third-party Elementor add-ons.
    - **Cart Icon:** Integrated WooCommerce's cart functionality, aiming for a mini-cart display (likely using Elementor's `Menu Cart` widget).
- **Product Display Exploration (WooCommerce & Elementor):**
    - Explored how Elementor's `Products` widget uses 'Query' parameters (categories, tags, IDs) to filter and display specific product sets on custom pages, rather than showing all products.
    - Understood that the default WooCommerce Shop page typically displays all registered products.
    - Began investigating methods to categorize and organize products on the shop page itself or on other custom product display pages.
- **My Account Page & User Management Investigation:**
    - Investigated the default WooCommerce pages for user login, registration, and basic account management (e.g., dashboard, orders).
    - Focused on understanding how these forms and functionalities are inherently provided by WooCommerce and how they interact with user sessions.
- **Mobile & Tablet Optimization:**
    - Analyzed the responsiveness of banners and YouTube videos on `gangnamsyrup.com.au` using Chrome DevTools.
    - Researched and understood core principles of responsive web design within WordPress/WooCommerce: responsive themes, CSS media queries, fluid images/media (e.g., `max-width: 100%; height: auto;` for images, and `padding-bottom` trick for `iframes`), Elementor's responsive settings, and the `viewport` meta tag.
    - Consolidated these findings for `extracurricular/Study-Responsive-Web/Responsive-Design-Methods.md` and `Responsive-Design-Beginner-Guide.md`.

## 🧠 Key Concepts Learned

- **Header Customization with Elementor Theme Builder:** How to create a custom header layout with multiple containers for various elements.
- **Interactive Search Implementation:** Understood the concept of an interactive search bar (e.g., overlay or dropdown) and the current state of Elementor's `Search` widget. Acknowledged that Elementor's `Search` widget no longer offers built-in skin options (like overlay/dropdown) as it did in older versions. Realized that achieving these dynamic search UIs now requires custom CSS/JavaScript or reliance on external Elementor add-ons that provide such functionalities.
- **WooCommerce Core Widgets: `Products` vs. `Archive Products`:**
    - **`Products` Widget:** This widget is versatile and can be used on *any page*. You manually control *which* products are displayed using its 'Query' settings (e.g., show only products from 'Electronics' category, or 'featured' products, or specific product IDs). It fetches products based on your explicit instructions.
    - **`Archive Products` Widget:** This widget is specifically designed for WooCommerce *archive pages* (like the main Shop page, Category pages, or Tag pages). It automatically displays products that are *relevant to the current page's context*. For example, on a 'T-shirts' category page, it will automatically show only T-shirts without you having to set a query. You typically use Elementor Theme Builder to design these archive pages.
- **WooCommerce User Authentication Flow (Login/Registration):** Understood that WooCommerce provides built-in pages and shortcodes (`[woocommerce_my_account]`) for user login, registration, and password reset. These forms handle the user authentication process and automatically create/manage user accounts. The default behavior often involves redirection to the 'My Account' dashboard after successful login/registration.
- **WooCommerce Shop Page & Product Query Basics:**
    - The main 'Shop' page in WooCommerce is a special page designated to list *all* products by default.
    - While the Shop page itself lists everything, the `Products` widget allows you to create *custom product displays* on other pages (e.g., a "Best Sellers" section on your homepage) by using its 'Query' options to filter by categories, tags, specific products, or product attributes. This gives you control over *what* products appear *where*.
- **WooCommerce Basic Settings:** Importance of configuring product display (shop page, product images), 'Add to Cart' button behavior, and other core settings for a functional store.
- **Product Image Management:** Criticality of WooCommerce image settings (`Appearance > Customize > WooCommerce > Product Images`), 'Thumbnail Cropping', and using `Regenerate Thumbnails` plugin for optimal image display. Also, Elementor's 'Image Size' and 'Object-fit' options for `Products` widget.
- **Cache Management:** The absolute necessity of clearing various caches (browser, WordPress plugins, server) after making changes to see immediate results, preventing old content from being displayed.
- **Responsive Design Fundamentals:** Re-emphasizing the role of responsive themes, CSS media queries, and flexible elements (fluid images/media, proper use of `viewport` meta tag) in achieving cross-device compatibility and an optimal viewing experience on mobile and tablet devices.
- **Problem Solving Approach:** The importance of clear problem definition, step-by-step verification (e.g., checking settings, clearing cache, inspecting elements), and utilizing official documentation/community resources for efficient troubleshooting.

## 🔜 Future Study Direction

- Continue practicing WooCommerce e-commerce site building, focusing on completing My Account and Shop pages, likely considering custom solutions or add-ons for advanced search UI.
- Deep dive into customizing specific WooCommerce template files for product, cart, and checkout pages.
- Explore more advanced Elementor Pro features for complex WooCommerce page designs and conditional displays.
- Implement more dynamic JavaScript interactions if Elementor's built-in options are insufficient for desired functionalities (e.g., custom pop-ups, dynamic content loading).
- Begin populating the `extracurricular/Study-Responsive-Web/` folder with the detailed responsive design guides.

---

# 📅 Day 03 (2025-05-21, 수)

## 🎓 오늘 한 일

**📌 오전 9시 일일 개발 미팅 참석.**  
**📌 `gangnamsyrup.com.au`를 참고하여 WooCommerce를 활용한 이커머스 사이트 구축 실습 과제 부여받음.**  
**📌 우커머스 초기 설정 및 상품 등록 완료.**  
**📌 헤더 섹션 구현을 시작하여 로고, 내비게이션 메뉴, 유틸리티 아이콘(검색, 내 계정, 장바구니)에 집중하며 상당 부분 진척.**  
**📌 모바일 및 태블릿 최적화 방법, 특히 배너와 삽입된 비디오에 대해 조사하고 적용.**  
**📌 엘리멘터 상품 위젯의 쿼리를 사용하여 특정 상품 진열 방식을 탐색.**  
**📌 우커머스에서 사용자 회원가입 및 로그인 과정이 어떻게 이루어지는지 조사.**  
**📌 기본 Shop 페이지에 모든 상품이 표시되는 방식과 쿼리를 사용하여 상품을 정리하는 방법을 탐색.**  
**📌 오늘 실습에서 겪었던 일반적인 WooCommerce 및 Elementor 개발 문제점과 해결 방안을 검토하고 요약.**  

### WooCommerce 이커머스 클라이언트 사이트 실습
- **프로젝트 목표:** `gangnamsyrup.com.au`의 디자인과 기능을 복제하여 이커머스 사이트 구축 시작.
- **우커머스 초기 설정 및 상품 등록:** 기본적인 우커머스 설정 및 초기 상품 데이터 업로드 완료.
- **헤더 구현:**
    - 엘리멘터 컨테이너 3개를 사용하여 헤더 구조화: 사이트 로고, 내비게이션 메뉴, 유틸리티 아이콘(검색, 내 계정, 장바구니) 섹션.
    - **검색 아이콘:** 엘리멘터의 `Search` 위젯 기능을 탐색하면서, 내장된 오버레이 또는 드롭다운 스킨 옵션에 대한 현재 제한 사항을 확인했습니다. 이러한 고급 검색 UI를 구현하려면 이제 사용자 정의 CSS/JavaScript 또는 서드파티 엘리멘터 애드온이 필요하다는 점을 이해했습니다.
    - **장바구니 아이콘:** 우커머스의 장바구니 기능을 통합하여 미니 카트 표시를 목표로 함 (엘리멘터의 `Menu Cart` 위젯 활용 가능성 높음).
- **상품 진열 탐색 (우커머스 & 엘리멘터):**
    - 엘리멘터의 `상품` 위젯이 '쿼리' 매개변수(카테고리, 태그, ID)를 사용하여 모든 상품 대신 특정 상품 세트를 사용자 정의 페이지에 필터링하고 표시하는 방법을 탐색.
    - 기본 우커머스 Shop 페이지가 일반적으로 등록된 모든 상품을 표시한다는 점을 이해.
    - Shop 페이지 자체 또는 다른 사용자 정의 상품 진열 페이지에서 상품을 분류하고 정리하는 방법을 조사하기 시작.
- **내 계정 페이지 및 사용자 관리 조사:**
    - 사용자 로그인, 회원가입 및 기본 계정 관리(예: 대시보드, 주문)를 위한 우커머스의 기본 페이지를 조사.
    - 이러한 양식과 기능이 우커머스에 의해 본질적으로 어떻게 제공되며 사용자 세션과 어떻게 상호 작용하는지 이해하는 데 중점.
- **모바일 및 태블릿 최적화:**
    - `gangnamsyrup.com.au`에서 배너와 YouTube 비디오의 반응형 동작을 크롬 개발자 도구를 사용하여 분석.
    - 워드프레스/우커머스 내 반응형 웹 디자인의 핵심 원리 연구 및 이해: 반응형 테마, 특정 조정을 위한 CSS 미디어 쿼리, 유연한 이미지/미디어(예: 이미지에 `max-width: 100%; height: auto;`, iframe에 `padding-bottom` 트릭), 엘리멘터의 반응형 설정, 그리고 `viewport` 메타 태그.
    - 이 발견 사항들을 `extracurricular/Study-Responsive-Web/Responsive-Design-Methods.md` 및 `Responsive-Design-Beginner-Guide.md`에 정리.

## 🧠 배운 핵심 개념

- **엘리멘터 테마 빌더를 활용한 헤더 커스터마이징:** 다양한 요소를 위한 여러 컨테이너를 포함하는 맞춤형 헤더 레이아웃을 만드는 방법.
- **인터랙티브 검색 구현:** 인터랙티브 검색 바(예: 오버레이 또는 드롭다운)의 개념과 엘리멘터 `Search` 위젯의 현재 상태를 이해했습니다. 엘리멘터 `Search` 위젯이 이전 버전에서 제공했던 내장 스킨 옵션(오버레이/드롭다운 등)을 더 이상 제공하지 않는다는 점을 인지했습니다. 이러한 동적 검색 UI를 구현하려면 이제 사용자 정의 CSS/JavaScript 또는 해당 기능을 제공하는 외부 엘리멘터 애드온에 의존해야 한다는 점을 깨달았습니다.
- **우커머스 핵심 위젯: `상품` (Products) vs. `아카이브 상품` (Archive Products):**
    - **`상품` 위젯:** 이 위젯은 다재다능하며 *어떤 페이지*에서든 사용할 수 있습니다. 위젯의 '쿼리' 설정을 사용하여 *어떤 상품*이 표시될지 수동으로 제어합니다(예: '전자제품' 카테고리의 상품만 표시, '추천' 상품, 특정 상품 ID 등). 명시적인 지침에 따라 상품을 가져옵니다.
    - **`아카이브 상품` 위젯:** 이 위젯은 우커머스 *아카이브 페이지*(예: 메인 상점 페이지, 카테고리 페이지, 태그 페이지)를 위해 특별히 설계되었습니다. 현재 페이지의 *컨텍스트와 관련된* 상품을 자동으로 표시합니다. 예를 들어, '티셔츠' 카테고리 페이지에 있을 때, 쿼리를 설정할 필요 없이 자동으로 티셔츠만 표시합니다. 일반적으로 엘리멘터 테마 빌더를 사용하여 이러한 아카이브 페이지를 디자인합니다.
- **우커머스 사용자 인증 흐름 (로그인/회원가입):** 우커머스가 사용자 로그인, 회원가입, 비밀번호 재설정을 위한 내장 페이지와 쇼트코드(`[woocommerce_my_account]`)를 제공한다는 점을 이해했습니다. 이러한 양식은 사용자 인증 프로세스를 처리하고 사용자 계정을 자동으로 생성/관리합니다. 기본 동작은 종종 성공적인 로그인/회원가입 후 '내 계정' 대시보드로 리디렉션하는 것을 포함합니다.
- **우커머스 상점 페이지 및 상품 쿼리 기본:**
    - 우커머스의 메인 '상점' 페이지는 기본적으로 *모든 상품*을 나열하도록 지정된 특별한 페이지입니다.
    - 상점 페이지 자체는 모든 것을 나열하지만, `상품` 위젯은 다른 페이지(예: 홈페이지의 "베스트 셀러" 섹션)에 *사용자 정의 상품 진열*을 만들 수 있도록 허용하며, 카테고리, 태그, 특정 상품 또는 상품 속성별로 필터링하는 '쿼리' 옵션을 사용합니다. 이는 *어떤* 상품이 *어디에* 나타날지 제어할 수 있게 합니다.
- **우커머스 기본 설정:** 상품 진열(상점 페이지, 상품 이미지), '장바구니 추가' 버튼 동작 및 기능적인 상점을 위한 기타 핵심 설정 구성의 중요성.
- **상품 이미지 관리:** 우커머스 이미지 설정(`외모 > 사용자 정의하기 > WooCommerce > Product Images`), '썸네일 자르기', `Regenerate Thumbnails` 플러그인 사용의 중요성. 또한 엘리멘터 '상품' 위젯의 '이미지 크기' 및 '객체 맞춤' 옵션.
- **캐시 관리:** 변경 사항을 즉시 반영하기 위해 다양한 캐시(브라우저, 워드프레스 플러그인, 서버)를 지우는 것의 절대적인 필요성, 오래된 콘텐츠가 표시되는 것을 방지.
- **반응형 디자인 기본:** 반응형 테마, CSS 미디어 쿼리, 유연한 요소(유동적인 이미지/미디어, `viewport` 메타 태그의 올바른 사용)가 다양한 기기 호환성 및 모바일/태블릿 장치에서 최적의 보기 경험을 달성하는 데 미치는 역할 재강조.
- **문제 해결 접근 방식:** 명확한 문제 정의, 단계별 확인(예: 설정 확인, 캐시 지우기, 요소 검사), 그리고 효율적인 문제 해결을 위한 공식 문서 및 커뮤니티 자료 활용의 중요성.

## 🔜 이후 학습 방향

- 계속해서 우커머스 이커머스 사이트 구축 실습을 진행하며 내 계정 및 상점 페이지 완성을 목표로 하고, 고급 검색 UI를 위한 사용자 정의 솔루션 또는 애드온 고려.
- 상품, 장바구니, 결제 페이지를 위한 특정 우커머스 템플릿 파일 커스터마이징에 대해 심층 학습.
- 복잡한 우커머스 페이지 디자인 및 조건부 표시를 위한 고급 엘리멘터 프로 기능 탐색.
- 엘리멘터 내장 옵션이 원하는 기능(예: 맞춤 팝업, 동적 콘텐츠 로딩)에 불충분할 경우, 더 동적인 JavaScript 상호작용 구현.
- `extracurricular/Study-Responsive-Web/` 폴더에 반응형 디자인 상세 가이드들을 채워나가기 시작.
