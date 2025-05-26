# 📅 Day 01 (2025-05-26, Mon)

## 🎓 What I Did Today

**📌 Researched and Understood WooCommerce Core Feature Structures for `gangnamsyrup.com.au` practical application.**  
**📌 Explored Elementor Addon concepts and confirmed their necessity for enhanced functionality.**  
**📌 Studied WooCommerce Default Page Customization methods (PHP Template Override) and explored application possibilities.**  
**📌 Reviewed core e-commerce operational elements (Shipping, Permalinks) and considered systematic management via Git.**  

### Detailed Activities

* **WooCommerce Core Feature Structure Analysis & Practical Research for `gangnamsyrup.com.au`:**
    * Analyzed the structure of key WooCommerce features and researched practical application methods for the `gangnamsyrup.com.au` project. This process aims to build a foundation for flexibly responding to various requirements that may arise during actual e-commerce operations.
    * **Product Management (Products):** Reconfirmed the importance of setting attributes for various product types (simple, variable) on `gangnamsyrup.com.au`, stock management, and product visibility settings.
    * **Order Management (Orders):** Understood the order status flow (pending, processing, completed, canceled, etc.) in conjunction with `gangnamsyrup.com.au`'s shipping and inventory systems, and considered ways to improve customer communication and internal management efficiency using order notes.
    * **Customer Management (Customers):** Reviewed the need for user data management and potential group-based access control for `gangnamsyrup.com.au` users.
    * **Payments & Shipping:** Based on Stripe integration experience, explored suitable payment gateway (PG) integration methods for `gangnamsyrup.com.au`. Specifically, **thoroughly checked the Shipping structure (flat rate, free, regional shipping zone settings), found the content valuable, and planned to apply a similar methodology to other core concepts for detailed organization.** Through this, acquired knowledge necessary for implementing `gangnamsyrup.com.au`'s shipping policies.
    * **Taxes & Coupons:** Understood the basic principles of country/region-specific tax settings and reviewed strategic applications of various coupon types (fixed discount, percentage discount, free shipping) that can be utilized on `gangnamsyrup.com.au`.
    * **Analytics:** Explored ways to use sales reports and stock reports to derive business insights and establish growth strategies for `gangnamsyrup.com.au`.
    * **Extensions & Customization:** Confirmed that WooCommerce can be infinitely extended through its plugin ecosystem, and additional requirements beyond core functions can be addressed through custom development (PHP/CSS/JS) or addon utilization for `gangnamsyrup.com.au`.

* **Elementor Addon Concept Understanding & Necessity Confirmation (Applied to `gangnamsyrup.com.au`):**
    * Upon LLM's recommendation, **researched "what" Elementor addons are and understood their necessity** as tools to extend Elementor's functionality and reduce time for specific design/feature implementations. This was considered a way to enhance the efficiency of the `gangnamsyrup.com.au` project.
    * **Addon Concept & Necessity:** Understood that addons are essential tools for extending Elementor's capabilities and shortening the time for specific design/feature implementations, which can improve the efficiency of the `gangnamsyrup.com.au` project.
    * **Research on Key Addon Types & Features:** Researched Elementor Pro (Theme Builder, Pop-up Builder, Form Builder, dynamic content, conditional display, etc.), ElementsKit, Essential Addons, Ultimate Addons, and other third-party addons that offer unique widgets, templates, and conditional display features (some available only in Pro versions) to meet specific requirements for `gangnamsyrup.com.au`.
    * **Review of Practical Application Strategies:** For the `gangnamsyrup.com.au` project, reviewed code-free customization (confirming the possibility of implementing dynamic UI/UX with drag-and-drop instead of complex PHP/CSS code, e.g., displaying buttons based on login/logout status), utilizing template and section libraries (reducing development time using pre-built design elements), and **understanding the importance of Conditional Display features and exploring application methods for `gangnamsyrup.com.au`** (the importance of hiding or showing sections/widgets based on specific user roles, login status, pages, etc.).

* **WooCommerce Default Page Customization Methods (feat. PHP Template Override) Study & `gangnamsyrup.com.au` Application Possibilities:**
    * Studied various methods for customizing WooCommerce's default pages (cart, checkout, my account, shop pages, etc.) when they don't align with brand identity and user experience. Understood that PHP template override is the most powerful and flexible method in practice, and deeply organized this method for application to `gangnamsyrup.com.au`.
    * **Necessity of Customization:** Implementing brand-specific UI/UX for `gangnamsyrup.com.au` beyond the limitations of default designs/functions.
    * **Key Customization Methods:**
        * **Using Page Builders/Plugins:** Visually modifying with page builders like Elementor or specific customization plugins (convenient without code knowledge, but with functional limitations; already applied to some `gangnamsyrup.com.au` layouts).
        * **WooCommerce Template Override (PHP-based):**
            * **Concept:** A method of copying and modifying default template files within the WooCommerce plugin to a child theme, ensuring changes persist even during plugin updates. Understood that this is a powerful and detailed customization method, essential for key pages like `gangnamsyrup.com.au`'s My Account page, and requires PHP knowledge.
            * **Practical Procedure (Example for `gangnamsyrup.com.au` My Account Page):**
                1.  **Identify Original File Location:** Check the template path within the WooCommerce plugin, such as `/wp-content/plugins/woocommerce/templates/myaccount/`.
                2.  **Create Identical Path in Child Theme:** E.g., `/wp-content/themes/your-child-theme/woocommerce/myaccount/` (This path will be used to manage `gangnamsyrup.com.au`'s customization files).
                3.  **Copy Template Files to Modify:** E.g., copy `form-login.php`, `dashboard.php`, `my-account.php` from the original location to the child theme.
                4.  **Review Copied File Modifications:** `form-login.php` (review modifying login/registration form titles, notices, inserting additional fields to reflect `gangnamsyrup.com.au`'s registration policy), `dashboard.php` (review modifying dashboard greetings, links, descriptions for `gangnamsyrup.com.au` user experience optimization), `my-account.php` (review possibilities for overall layout changes such as adjusting the position of navigation and content output (`do_action`)).
                5.  **Core Principle:** Maintain the original structure (comments, functions, `do_action`, etc.) and only add/modify desired parts for `gangnamsyrup.com.au` application.
                6.  **Save and Verify:** Save files and refresh browser (expected).
            * **Caution:** Understood the importance of not directly modifying original files and ensuring exact file/folder structure matching for override to work, which is essential for `gangnamsyrup.com.au`'s stable operation.
        * **Using Specialized Plugins:** Extending functionality using plugins specialized for specific pages (e.g., Checkout) (to be considered for future `gangnamsyrup.com.au` expansion).
        * **Using WordPress Customizer:** Modifying design within limited scope through the default WordPress Customizer (applied for simple style adjustments on `gangnamsyrup.com.au`).

* **WooCommerce Permalink Settings Understanding & Optimization Review:**
    * Studied the impact of WooCommerce permalink settings on Search Engine Optimization (SEO) and User Experience (UX). Understood how to set up `gangnamsyrup.com.au`'s product and category URL structures to be more SEO-friendly.
    * **Setting Path:** `WordPress Admin > Settings > Permalinks` and `WooCommerce > Settings > Products > General > Permalinks`.
    * **Key Options:** Understood the differences between various options like default, product name, product category, and established criteria for selecting the most suitable structure for `gangnamsyrup.com.au` (e.g., clear URL structures like `domain/product/product-name`, `domain/product-category/category-name`).

* **Git for WooCommerce Customization File Management (`gangnamsyrup.com.au` Project):**
    * Established a systematic method for managing `gangnamsyrup.com.au`'s WooCommerce customization files via Git. This is essential for collaboration, version control, and preventing conflicts during future updates.
    * **Recommended Folder Structure (within `your-child-theme`):**
        ```text
        your-child-theme/
        ├── functions.php
        ├── style.css
        ├── woocommerce/
        │   └── myaccount/
        │       ├── form-login.php
        │       ├── dashboard.php
        │       └── my-account.php
        ├── ... (other theme files)
        ```
    * **Management Principle:** Only overridden template files should be copied and modified within the `woocommerce/myaccount/` folder, and custom code in `functions.php` and `style.css` should also be managed there.
    * **Git Upload/Management Tips:** Considered uploading the entire child theme to Git or managing custom files in a separate folder. The importance of clear documentation of customization details and application methods in a `README.md` file was confirmed for efficient management of `gangnamsyrup.com.au`'s development history.

## 🧠 Key Concepts Learned

* **Integrated Understanding of WooCommerce End-to-End System Structure:** Through `gangnamsyrup.com.au` practice, gained a comprehensive understanding of the overall flow of the WooCommerce e-commerce system and the interaction of each function, from product registration to order processing, customer management, payment/shipping settings (especially Shipping Zone), and analytics. **During the Shipping structure review process, recognizing its detail and flexibility, gained the motivation to apply the same methodology to deeply understand other core concepts.**
* **Understanding Elementor Addon Functionality Expansion & Necessity:** Through LLM's recommendation, **researched the concept of Elementor Pro and third-party addons and understood their functional extensibility.** Especially recognized the high utility of **Conditional Display features** for dynamically controlling content or UI elements based on user status (logged-in/logged-out) or page characteristics (categories, specific products), which is considered a key competency for building a personalized user experience on `gangnamsyrup.com.au`.
* **Learning PHP-based WooCommerce Template Override Methodology for Practical Application:** With `gangnamsyrup.com.au`'s specific page (My Account, Login, etc.) customization in mind, thoroughly learned the concept, necessity, and **practical procedure of safely modifying original files by copying them to a child theme** using the PHP template override method. This is a crucial methodology for maintaining `gangnamsyrup.com.au`'s brand identity while ensuring updates are robust.
* **Understanding SEO and UX Optimization Elements for E-commerce Websites (Permalinks):** Understood the importance of WooCommerce permalink settings for Search Engine Optimization (SEO) and User Experience (UX), and learned how to set up `gangnamsyrup.com.au`'s URL structure to be clear and consistent.
* **Recognizing the Importance of Project Version Control and Collaboration using Git:** Reconfirmed that systematically managing all changes, including WooCommerce customization code, for a real project like `gangnamsyrup.com.au` via Git, and documenting it in a `README.md` file, is essential for improving development productivity and collaboration efficiency.

## 🔜 Future Study Direction

* **Applying Customization to `gangnamsyrup.com.au` Live Project:** Aim to apply the learned PHP template override methods to `gangnamsyrup.com.au`'s My Account page and other default pages to improve actual UI/UX and strengthen practical capabilities.
* **Deepening Elementor Dynamic Feature Application & Testing:** Plan to apply Elementor's conditional display features, such as dynamic header icon display based on login/logout status, to various scenarios on `gangnamsyrup.com.au` and test their actual operation to enhance advanced UI/UX implementation skills.
* **In-depth WooCommerce Shipping & Tax Settings:** Plan to thoroughly study and apply advanced WooCommerce settings such as Shipping Zones, Shipping Classes, and Tax Rates to match `gangnamsyrup.com.au`'s actual shipping and tax policies, building a complete e-commerce operational foundation.
* **Deepening PHP and WordPress Hooks Utilization:** Beyond WooCommerce template overrides, continue learning and practicing PHP coding skills by utilizing WordPress and WooCommerce action and filter hooks via the `functions.php` file for extending functionality.
* **Creating Pre-Deployment and Launch Checklist for `gangnamsyrup.com.au`:** Before the actual deployment of `gangnamsyrup.com.au`, plan to create and master a final checklist for site stability and performance, including final permalink structure verification, cache settings, and basic SEO configurations.

---

# 📅 Day 01 (2025-05-26, 월)

## 🎓 오늘 한 일

**📌 WooCommerce 핵심 기능 구조 파악 및 `gangnamsyrup.com.au` 실무 적용 방안 리서치.**  
**📌 Elementor 애드온(Addon)의 개념 이해 및 활용 필요성 확인.**  
**📌 WooCommerce 기본 페이지 커스터마이징 (PHP 템플릿 오버라이드) 방법 학습 및 적용 가능성 탐색.**  
**📌 이커머스 핵심 운영 요소(Shipping, Permalinks) 구조 확인 및 Git을 통한 체계적 관리 방안 검토.**  

### 상세 활동

* **`gangnamsyrup.com.au` WooCommerce 핵심 기능별 구조 파악 및 실무 리서치:**
    * `gangnamsyrup.com.au` 프로젝트에 WooCommerce를 적용하기 위해 주요 기능별 구조를 분석하고, 실무 적용 방안을 리서치했습니다. 이는 실제 이커머스 운영 시 발생할 수 있는 다양한 요구사항에 유연하게 대처하기 위한 기반을 다지는 과정입니다.
    * **상품 관리 (Products):** `gangnamsyrup.com.au`의 다양한 제품 유형(단순, 가변)에 따른 속성(Attributes) 설정, 재고 관리(Stock Management) 및 제품 가시성(Visibility) 설정의 중요성을 확인했습니다.
    * **주문 관리 (Orders):** 주문 상태(Order Status) 흐름(대기, 처리 중, 완료, 취소 등)을 `gangnamsyrup.com.au`의 배송 및 재고 시스템과 연동하여 이해하고, 주문 노트(Order Notes)를 활용한 고객 커뮤니케이션 및 내부 관리 효율화 방안을 고려했습니다.
    * **고객 관리 (Customers):** `gangnamsyrup.com.au` 사용자들의 회원 정보(User Data) 관리 및 잠재적인 그룹별 접근 권한 설정의 필요성을 검토했습니다.
    * **결제 (Payments) & 배송 (Shipping):** Stripe와의 연동 경험을 바탕으로 `gangnamsyrup.com.au`에 적합한 결제 게이트웨이(PG) 연동 방안을 모색하고, 특히 **Shipping 구조(정액, 무료, 지역별 배송 존 설정)를 상세히 확인하며 그 내용이 괜찮아 다른 핵심 개념에도 동일한 방법론을 적용하여 정리해봐야겠다는 계획을 수립**했습니다. 이를 통해 `gangnamsyrup.com.au`의 배송 정책을 구현하는 데 필요한 지식을 습득했습니다.
    * **세금 (Taxes) & 쿠폰 (Coupons):** 국가/지역별 세금 설정의 기본 원리를 이해하고, `gangnamsyrup.com.au`에서 활용할 수 있는 다양한 쿠폰 유형(정액 할인, 정률 할인, 무료 배송)의 전략적 적용을 검토했습니다.
    * **분석 (Analytics):** 판매 보고서(Sales Report) 및 재고 보고서(Stock Report)를 통해 `gangnamsyrup.com.au`의 비즈니스 인사이트를 도출하고 성장 전략을 수립하는 데 활용할 방안을 모색했습니다.
    * **확장 및 커스터마이징 (Extensions & Customization):** WooCommerce는 플러그인 생태계를 통해 무한히 확장 가능하며, `gangnamsyrup.com.au`의 핵심 기능 외 추가 요구사항은 맞춤형 개발 (PHP/CSS/JS) 또는 애드온 활용을 통해 해결할 수 있음을 확인했습니다.

* **Elementor 애드온(Addon) 개념 이해 및 활용 필요성 확인 (`gangnamsyrup.com.au` 적용):**
    * Elementor의 기능을 확장하고, 특정 디자인/기능 구현 시간을 단축하는 도구인 애드온에 대해 LLM의 추천을 받아 **"무엇인지"를 검색하고 그 필요성을 파악**했습니다. 이는 `gangnamsyrup.com.au` 프로젝트의 효율성을 높일 수 있는 방안으로 검토했습니다.
    * **애드온의 개념 및 필요성:** Elementor의 기능을 확장하고, 특정 디자인/기능 구현 시간을 단축하는 핵심 도구로서 `gangnamsyrup.com.au` 프로젝트의 효율성을 높일 수 있음을 파악했습니다.
    * **주요 애드온 종류 및 특징 리서치:** Elementor Pro (테마 빌더, 팝업 빌더, 양식 빌더, 동적 콘텐츠, 조건부 표시 등), ElementsKit, Essential Addons, Ultimate Addons 등 각기 다른 독점 위젯, 템플릿, 조건부 표시 기능 (일부 Pro 버전에서만 제공) 등을 제공하여 `gangnamsyrup.com.au`의 특정 요구사항에 대응하는 방법을 리서치했습니다.
    * **실무 활용 전략 검토:** `gangnamsyrup.com.au` 프로젝트에 코드 없는 커스터마이징 (복잡한 PHP/CSS 코드 없이 드래그 앤 드롭으로 동적인 UI/UX 구현 가능성 확인, 예: 로그인/로그아웃 상태에 따른 버튼 표시), 템플릿 및 섹션 라이브러리 활용 (미리 만들어진 디자인 요소를 활용하여 개발 시간 단축), **조건부 표시 (Conditional Display) 기능의 중요성 및 `gangnamsyrup.com.au`에 적용 방안 검토** (특정 사용자 역할, 로그인 상태, 페이지 등에 따라 섹션/위젯을 숨기거나 보여주는 기능의 중요성).

* **WooCommerce 디폴트 페이지 커스터마이징 방법 (feat. PHP 템플릿 오버라이드) 학습 및 `gangnamsyrup.com.au` 적용 가능성 탐색:**
    * WooCommerce의 기본 페이지(장바구니, 결제, 내 계정, 상점 페이지 등)가 브랜드 아이덴티티와 사용자 경험에 맞지 않을 때 커스터마이징하는 다양한 방법을 학습했습니다. 특히 PHP 템플릿 오버라이드 방식이 실무에서 가장 강력하고 유연하다는 점을 이해하고, `gangnamsyrup.com.au`에 적용하기 위한 이 방법에 대해 깊이 있게 정리했습니다.
    * **커스터마이징의 필요성:** `gangnamsyrup.com.au`의 기본 디자인/기능의 한계를 넘어선 브랜드 맞춤형 UI/UX 구현.
    * **주요 커스터마이징 방법:**
        * **페이지 빌더/플러그인 활용:** Elementor와 같은 페이지 빌더나 특정 커스터마이징 플러그인을 사용하여 시각적으로 수정 (코드 지식 없이 간편하나, 기능적 한계 존재, `gangnamsyrup.com.au`의 일부 레이아웃에 이미 적용 중).
        * **WooCommerce 템플릿 오버라이드 (PHP 기반):**
            * **개념:** WooCommerce 플러그인 내의 기본 템플릿 파일을 차일드 테마로 복사하여 수정함으로써, 플러그인 업데이트 시에도 변경 사항이 유지되도록 하는 방법. `gangnamsyrup.com.au`의 My Account 페이지와 같이 핵심적인 페이지의 세밀한 커스터마이징에 활용할 수 있으며, PHP 지식이 필수적임을 파악했습니다.
            * **실무 절차 (`gangnamsyrup.com.au` My Account 페이지 예시):**
                1.  **원본 파일 위치 파악:** `/wp-content/plugins/woocommerce/templates/myaccount/` 와 같이 WooCommerce 플러그인 내 템플릿 경로를 확인.
                2.  **차일드 테마에 동일 경로 생성:** 예: `/wp-content/themes/your-child-theme/woocommerce/myaccount/` (이 경로에 `gangnamsyrup.com.au`의 커스터마이징 파일들을 관리할 예정).
                3.  **수정할 템플릿 파일 복사:** 예: `form-login.php`, `dashboard.php`, `my-account.php` 등을 원본에서 차일드 테마로 복사.
                4.  **복사한 파일 수정 검토:** `form-login.php` (로그인/회원가입 폼 타이틀 문구, 안내문구, 추가 필드 삽입 등 `gangnamsyrup.com.au`의 회원가입 정책 반영 검토), `dashboard.php` (대시보드 인사말, 링크, 설명 수정, `gangnamsyrup.com.au` 사용자 경험 최적화 검토), `my-account.php` (내비게이션 및 콘텐츠 출력(`do_action`) 위치 조정 등 전체 레이아웃 변경 가능성 검토).
                5.  **핵심 원칙:** 원본 파일의 주석, 함수, `do_action` 등 핵심 구조는 그대로 유지하고, 원하는 부분만 추가/수정하여 `gangnamsyrup.com.au`에 적용할 방안을 탐색.
                6.  **저장 및 확인:** 파일 저장 후 브라우저 새로고침 및 캐시 삭제하여 변경 사항 확인 (예상).
            * **주의사항:** 원본 파일을 직접 수정하지 않도록 주의하고, 파일/폴더 구조를 정확히 일치시켜야 오버라이드가 작동하며, 이는 `gangnamsyrup.com.au`의 안정적인 운영에 필수적임을 이해했습니다.
        * **특화 플러그인 활용:** 특정 페이지(예: Checkout)에 특화된 플러그인을 사용하여 기능 확장 (향후 `gangnamsyrup.com.au` 확장 시 검토).
        * **워드프레스 커스터마이저 활용:** 제한적인 범위 내에서 워드프레스 기본 커스터마이저를 통해 디자인 변경 (간단한 스타일 조정에 `gangnamsyrup.com.au`에 적용).

* **WooCommerce 퍼머링크(Permalinks) 설정 이해 및 최적화 방안 검토:**
    * WooCommerce 퍼머링크 설정이 검색 엔진 최적화(SEO) 및 사용자 경험(UX)에 미치는 영향을 학습했습니다. `gangnamsyrup.com.au`의 제품 및 카테고리 URL 구조를 보다 SEO 친화적으로 설정하는 방법을 파악했습니다.
    * **설정 경로:** `워드프레스 관리자 > 설정 > 고유주소 (Permalinks)` 및 `WooCommerce > 설정 > 상품 > 일반 > 고유주소`.
    * **주요 옵션:** 기본, 상품 이름, 상품 카테고리 등 다양한 옵션의 차이를 이해하고 `gangnamsyrup.com.au`에 가장 적합한 구조를 선택하는 기준을 마련했습니다. (예: `도메인/상품/상품명`, `도메인/product-category/카테고리명`과 같이 명확한 URL 구조).

* **Git을 통한 WooCommerce 커스터마이징 파일 관리 (`gangnamsyrup.com.au` 프로젝트):**
    * `gangnamsyrup.com.au` 프로젝트의 WooCommerce 커스터마이징 파일들을 Git을 통해 체계적으로 관리하는 방법을 확립했습니다. 이는 협업 및 버전 관리, 그리고 향후 업데이트 시 충돌 방지를 위해 필수적입니다.
    * **권장 폴더 구조 (`your-child-theme` 내):**
        ```text
        your-child-theme/
        ├── functions.php
        ├── style.css
        ├── woocommerce/
        │   └── myaccount/
        │       ├── form-login.php
        │       ├── dashboard.php
        │       └── my-account.php
        ├── ... (other theme files)
        ```
    * **관리 원칙:** 오직 오버라이드된 템플릿 파일만 `woocommerce/myaccount/` 폴더 내에 복사하여 수정하며, `functions.php`와 `style.css` 내의 커스텀 코드도 함께 관리합니다.
    * **Git 업로드/관리 팁:** 전체 차일드 테마를 Git에 업로드하거나, 커스텀 파일만 별도 폴더에서 관리하는 방안을 고려합니다. `README.md` 파일을 통해 커스터마이징 내용과 적용 방법을 명확히 문서화하여 `gangnamsyrup.com.au`의 개발 이력을 효율적으로 관리합니다.

## 🧠 배운 핵심 개념

* **WooCommerce 엔드투엔드(End-to-End) 시스템 구조 파악:** `gangnamsyrup.com.au` 실습을 통해 상품 등록부터 주문 처리, 고객 관리, 결제/배송 설정(특히 Shipping Zone), 그리고 분석에 이르는 WooCommerce 이커머스 시스템의 전반적인 흐름과 각 기능의 상호작용을 통합적으로 이해했습니다. **Shipping 구조 확인 과정에서 그 상세함과 유연성을 보고 다른 핵심 개념에도 동일한 방법론을 적용하여 깊이 있게 파악해야겠다는 학습 의지를 갖게 되었습니다.**
* **Elementor 애드온의 기능 확장 및 필요성 인식:** LLM의 추천을 통해 Elementor Pro 및 서드파티 애드온의 개념을 **검색하고 그 기능적 확장성**을 파악했습니다. 특히 **조건부 표시(Conditional Display) 기능**이 사용자 상태나 페이지 특성에 따라 동적으로 UI를 제어하는 데 매우 유용함을 이해했으며, 이는 `gangnamsyrup.com.au`의 개인화된 사용자 경험 구축에 핵심적인 역량으로 검토됩니다.
* **PHP 기반 WooCommerce 템플릿 오버라이드 방법론 학습:** `gangnamsyrup.com.au`의 특정 페이지(My Account, Login 등) 커스터마이징을 염두에 두고, PHP 템플릿 오버라이드 방식의 개념, 필요성, 그리고 **원본 파일을 직접 수정하지 않고 차일드 테마에 복사하여 안전하게 수정하는 실무 절차**를 명확히 학습했습니다. 이는 `gangnamsyrup.com.au`의 브랜드 아이덴티티를 유지하면서도 업데이트에 강건한 커스터마이징을 가능하게 하는 중요한 방법론입니다.
* **이커머스 웹사이트의 SEO 및 UX 최적화를 위한 Permalinks 설정:** WooCommerce의 퍼머링크 설정이 검색 엔진 최적화(SEO) 및 사용자 경험(UX)에 미치는 중요성을 이해하고, `gangnamsyrup.com.au`의 URL 구조를 명확하고 일관성 있게 설정하는 방법을 학습했습니다.
* **Git을 활용한 프로젝트 버전 관리 및 협업의 중요성 인식:** `gangnamsyrup.com.au`와 같은 실제 프로젝트에서 WooCommerce 커스터마이징 코드를 포함한 모든 변경 사항을 Git을 통해 체계적으로 관리하고, `README.md`를 통해 문서화하는 것이 개발 생산성 및 협업 효율성을 높이는 데 필수적임을 재확인했습니다.

## 🔜 이후 학습 방향

* **`gangnamsyrup.com.au` 실제 프로젝트에 커스터마이징 적용 및 테스트:** 학습한 PHP 템플릿 오버라이드 방법을 `gangnamsyrup.com.au` 프로젝트의 My Account 페이지 및 기타 디폴트 페이지에 적용하여 실제 UI/UX를 개선하고 실무 역량을 강화하는 것을 목표로 합니다.
* **Elementor 동적 기능 심화 적용 및 테스트:** 로그인/비로그인 상태에 따른 헤더 아이콘 동적 표시와 같은 Elementor의 조건부 표시 기능을 `gangnamsyrup.com.au`의 다양한 시나리오에 적용하고 실제 동작을 테스트하며 고급 UI/UX 구현 능력을 향상시킬 예정입니다.
* **WooCommerce Shipping 및 Tax 심층 설정:** `gangnamsyrup.com.au`의 실제 배송 및 세금 정책에 맞춰 WooCommerce의 Shipping Zone, Shipping Class, Tax Rate 등의 고급 설정을 심층적으로 학습하고 적용하여 완벽한 이커머스 운영 기반을 구축합니다.
* **PHP 및 WordPress Hooks 활용 심화:** WooCommerce 템플릿 오버라이드 외에 `functions.php` 파일을 활용하여 WordPress 및 WooCommerce의 액션(Action)과 필터(Filter) 훅(Hook)을 이용한 기능 확장을 학습하고 실습하며 PHP 코딩 실력을 향상시킵니다.
* **사이트 배포 및 출시 전 최종 점검 리스트 작성:** `gangnamsyrup.com.au`의 실제 배포를 앞두고, 퍼머링크 구조 최종 확인, 캐시 설정, SEO 기본 설정 등 사이트 안정성과 성능을 위한 최종 점검 체크리스트를 만들고 숙달합니다.

  
