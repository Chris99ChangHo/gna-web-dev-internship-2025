# 📅 Day 03 (2025-05-21, Wed)

## 🎓 What I Did Today

**📌 Attended daily development meeting at 9 AM.**  
**📌 Received a new practical assignment: building an e-commerce site using WooCommerce, referencing gangnamsyrup.com.au.**  
**📌 Started implementing the header section, focusing on logo, navigation menu, and utility icons (Search, My Account, Cart).**  
**📌 Investigated methods for mobile and tablet optimization, specifically for banners and embedded videos.**  
**📌 Reviewed and summarized common WooCommerce and Elementor development challenges and their solutions from today's practice.**  

### WooCommerce E-commerce Client Site Practice
- **Project Goal:** Begin building an e-commerce site, replicating design and functionality from [gangnamsyrup.com.au](https://gangnamsyrup.com.au/).
- **Header Implementation:**
    - Structured header using 3 Elementor containers: Site Logo, Navigation Menu, and a section for utility icons (Search, My Account, Cart).
    - **Search Icon:** Explored methods to create a toggle search bar (like the overlay/dropdown seen on the reference site) using Elementor's `Search` widget.
    - **My Account Icon:** Linked to WooCommerce's default 'My Account' page.
    - **Cart Icon:** Integrated WooCommerce's cart functionality, aiming for a mini-cart display (likely using Elementor's `Menu Cart` widget).
- **Mobile & Tablet Optimization:**
    - Analyzed the responsiveness of banners and YouTube videos on `gangnamsyrup.com.au` using Chrome DevTools.
    - Researched and understood core principles of responsive web design within WordPress/WooCommerce: responsive themes, CSS media queries, fluid images/media (e.g., `max-width: 100%; height: auto;` for images, `padding-bottom` trick for `iframes`), Elementor's responsive settings, and the `viewport` meta tag.
    - Consolidated these findings for `extracurricular/Study-Responsive-Web/Responsive-Design-Methods.md` and `Responsive-Design-Beginner-Guide.md`.

## 🧠 Key Concepts Learned

- **Header Customization with Elementor Theme Builder:** How to create a custom header layout with multiple containers for various elements.
- **Interactive Search Implementation:** Understanding the concept of toggling a search bar (overlay/dropdown) via Elementor widgets or custom JavaScript/CSS.
- **WooCommerce Core Widgets:**
    - **`Products` Widget:** Its primary use for displaying specific products based on queries on any page.
    - **`Archive Products` Widget:** Its exclusive use within Theme Builder's Product Archive templates, and why it shouldn't be used on general pages.
- **WooCommerce Basic Settings:** Importance of configuring product display, 'Add to Cart' button behavior, and 'My Account' settings.
- **Product Image Management:** Criticality of WooCommerce image settings (`Appearance > Customize > WooCommerce > Product Images`), 'Thumbnail Cropping', and using `Regenerate Thumbnails` plugin. Also, Elementor's 'Image Size' and 'Object-fit' options for `Products` widget.
- **Cache Management:** The absolute necessity of clearing various caches (browser, WordPress plugins, server) after making changes to see immediate results.
- **Responsive Design Fundamentals:** Re-emphasizing the role of responsive themes, media queries, and flexible elements in achieving cross-device compatibility.
- **Problem Solving Approach:** The importance of clear problem definition, step-by-step verification, and utilizing official documentation/community resources.

## 🔜 Future Study Direction

- Continue practicing WooCommerce e-commerce site building, moving beyond the header.
- Deep dive into customizing specific WooCommerce template files for product, cart, and checkout pages.
- Explore more advanced Elementor Pro features for complex WooCommerce page designs and conditional displays.
- Implement more dynamic JavaScript interactions if Elementor's built-in options are insufficient for desired functionalities (e.g., custom pop-ups, dynamic content loading).
- Begin populating the `extracurricular/Study-Responsive-Web/` folder with the detailed responsive design guides.

---

# 📅 Day 03 (2025-05-21, 수)

## 🎓 오늘 한 일

**📌 오전 9시 일일 개발 미팅 참석.**  
**📌 `gangnamsyrup.com.au`를 참고하여 WooCommerce를 활용한 이커머스 사이트 구축 실습 과제 부여받음.**  
**📌 헤더 섹션 구현 시작: 로고, 내비게이션 메뉴, 유틸리티 아이콘(검색, 내 계정, 장바구니)에 집중.**  
**📌 모바일 및 태블릿 최적화 방법, 특히 배너와 삽입된 비디오에 대해 조사 및 적용.**  
**📌 오늘 실습에서 겪었던 일반적인 WooCommerce 및 Elementor 개발 문제점과 해결 방안을 검토하고 요약.**  

### WooCommerce 이커머스 클라이언트 사이트 실습
- **프로젝트 목표:** `gangnamsyrup.com.au`의 디자인과 기능을 복제하여 이커머스 사이트 구축 시작.
- **헤더 구현:**
    - 엘리멘터 컨테이너 3개를 사용하여 헤더 구조화: 사이트 로고, 내비게이션 메뉴, 유틸리티 아이콘(검색, 내 계정, 장바구니) 섹션.
    - **검색 아이콘:** 엘리멘터의 `Search` 위젯 기능을 활용하여 (참고 사이트에서 보이는 오버레이/드롭다운과 같은) 토글 검색 바를 만드는 방법 탐색.
    - **내 계정 아이콘:** 우커머스의 기본 '내 계정' 페이지에 링크.
    - **장바구니 아이콘:** 우커머스의 장바구니 기능을 통합하여 미니 카트 표시를 목표로 함 (엘리멘터의 `Menu Cart` 위젯 활용 가능성 높음).
- **모바일 및 태블릿 최적화:**
    - `gangnamsyrup.com.au`에서 배너와 YouTube 비디오의 반응형 동작을 크롬 개발자 도구를 사용하여 분석.
    - 워드프레스/우커머스 내 반응형 웹 디자인의 핵심 원리 연구 및 이해: 반응형 테마, 특정 조정을 위한 CSS 미디어 쿼리, 유연한 이미지/미디어(예: 이미지에 `max-width: 100%; height: auto;`, iframe에 `padding-bottom` 트릭), 엘리멘터의 반응형 설정, 그리고 `viewport` 메타 태그.
    - 이 발견 사항들을 `extracurricular/Study-Responsive-Web/Responsive-Design-Methods.md` 및 `Responsive-Design-Beginner-Guide.md`에 정리.

## 🧠 배운 핵심 개념

- **엘리멘터 테마 빌더를 활용한 헤더 커스터마이징:** 다양한 요소를 위한 여러 컨테이너를 포함하는 맞춤형 헤더 레이아웃을 만드는 방법.
- **인터랙티브 검색 구현:** 엘리멘터 위젯 또는 커스텀 JavaScript/CSS를 통해 검색 바를 토글(오버레이/드롭다운)하는 개념 이해.
- **우커머스 핵심 위젯:**
    - **`상품` (Products) 위젯:** 어떤 페이지에서든 쿼리(카테고리, 태그, ID 등)에 따라 특정 상품을 표시하기 위한 주된 용도.
    - **`아카이브 상품` (Archive Products) 위젯:** 테마 빌더의 상품 아카이브 템플릿 내에서만 독점적으로 사용되며, 일반 페이지에 사용해서는 안 되는 이유.
- **우커머스 기본 설정:** 상품 진열, '장바구니 추가' 버튼 동작, '내 계정' 설정 구성의 중요성.
- **상품 이미지 관리:** 우커머스 이미지 설정(`외모 > 사용자 정의하기 > WooCommerce > Product Images`), '썸네일 자르기', `Regenerate Thumbnails` 플러그인 사용의 중요성. 또한 엘리멘터 '상품' 위젯의 '이미지 크기' 및 '객체 맞춤' 옵션.
- **캐시 관리:** 변경 사항을 즉시 반영하기 위해 다양한 캐시(브라우저, 워드프레스 플러그인, 서버)를 지우는 것의 절대적인 필요성.
- **반응형 디자인 기본:** 다양한 기기 호환성을 달성하기 위한 반응형 테마, 미디어 쿼리, 유연한 요소의 역할 재강조.
- **문제 해결 접근 방식:** 명확한 문제 정의, 단계별 확인, 공식 문서 및 커뮤니티 자료 활용의 중요성.

## 🔜 이후 학습 방향

- 계속해서 우커머스 이커머스 사이트 구축 실습을 진행하며 헤더 이후의 부분을 작업.
- 상품, 장바구니, 결제 페이지를 위한 특정 우커머스 템플릿 파일 커스터마이징에 대해 심층 학습.
- 복잡한 우커머스 페이지 디자인 및 조건부 표시를 위한 고급 엘리멘터 프로 기능 탐색.
- 엘리멘터 내장 옵션이 원하는 기능(예: 맞춤 팝업, 동적 콘텐츠 로딩)에 불충분할 경우, 더 동적인 JavaScript 상호작용 구현.
- `extracurricular/Study-Responsive-Web/` 폴더에 반응형 디자인 상세 가이드들을 채워나가기 시작.
