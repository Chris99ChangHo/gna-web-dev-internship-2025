# 🛒 WooCommerce Comprehensive Guide

## 1. ✅ What is WooCommerce?
WooCommerce is the most widely used open-source eCommerce plugin for WordPress. It allows users to create and operate online stores directly within the WordPress environment.

* **Developer**: Originally developed by WooThemes, acquired by Automattic (parent company of WordPress.com) in 2015.
* **License**: Open-source (GPLv3).
* **Integration**: Designed to work seamlessly with WordPress themes and admin dashboard.

## 2. 🧱 Core Features
WooCommerce provides a robust set of features essential for any online store.

### 2.1. 🛍️ Product Management
* **Simple Products**: Single items without variations.
* **Variable Products**: Products with multiple variations (e.g., size, color), each with its own SKU, price, and stock.
* **Grouped Products**: Bundles of related, standalone products.
* **Virtual/Downloadable Products**: Ideal for services or digital goods that don't require shipping.

### 2.2. 🛒 Cart and Checkout
* Built-in cart and checkout pages for a seamless buying process.
* Ajax-powered cart for quantity adjustments without page reloads.
* Customizable checkout fields (via plugin or custom code).

### 2.3. 💳 Payment Gateways
* **Built-in**: PayPal, Stripe, Bank Transfer, Cash on Delivery.
* **Extensible**: Supports additional payment methods via plugins (e.g., Toss, Kakaopay in Korea).

### 2.4. 🚚 Shipping Options
* Flat Rate, Free Shipping, Local Pickup.
* Configurable **Shipping Zones** and **Shipping Classes** for flexible pricing based on location and product type.

### 2.5. 🧾 Tax Configuration
* Automatic tax calculation (often with plugin assistance).
* Ability to set tax rates and control whether prices are shown with or without tax.

## 3. 🧠 WooCommerce Core Concepts
To truly master WooCommerce customization, it's crucial to understand its underlying architecture and how it integrates with WordPress.

### 3.1. ⚙️ WordPress Core Concepts (Foundation of WooCommerce)
WooCommerce builds heavily on WordPress's core functionalities.

* **Post Types**: In WordPress, most content is managed as 'posts'. WooCommerce extends this with **Custom Post Types** for its specific data.
    * **Products**: A custom post type named `product`.
    * **Orders**: A custom post type named `shop_order`.
    * *Why it matters*: Product and order main data (like title, description, status) are stored in the standard `wp_posts` table.
* **Meta Data**: Additional, detailed information attached to posts.
    * **`wp_postmeta` Table**: Most specific product details (e.g., price, SKU, stock, attributes, variations) and order details (e.g., customer address, payment method, line items) are stored here as key-value pairs, linked to their respective `post_id` in `wp_posts`.
* **Hooks (Actions & Filters)**: WordPress's powerful extensibility mechanism, fully leveraged by WooCommerce.
    * **Actions**: Allow you to **insert or execute code** at specific predefined points in the execution flow.
    * **Filters**: Allow you to **modify or filter data** before it's displayed or saved.
    * *Why it matters*: These are the primary methods for customizing WooCommerce without directly editing core files.

### 3.2. 🛒 WooCommerce-Specific Concepts
Beyond the WordPress core, WooCommerce introduces its own set of unique concepts for e-commerce.

* **Database Schema**: WooCommerce introduces its own dedicated database tables for specific e-commerce data.
    * Examples include `woocommerce_order_items` (for individual items within an order), `woocommerce_order_itemmeta`, `wc_product_meta_lookup` (for faster product filtering), `wc_download_log`, etc.
    * *Why it matters*: Understanding where data resides helps in debugging and complex custom queries.
* **Product Types**: Built-in product types that cater to various selling scenarios.
    * **Simple Product**: Standard, single item.
    * **Variable Product**: Product with attributes (like color, size) creating different variations, each with its own SKU, price, and stock.
    * **Grouped Product**: Collection of simple, standalone products.
    * **External/Affiliate Product**: Links to an external URL for purchase.
    * **Virtual Product**: Non-physical product, no shipping required.
    * **Downloadable Product**: Digital product customers can download after purchase.
    * *Why it matters*: Choosing the correct product type is crucial for inventory, pricing, and customer experience.
* **Template Hierarchy & Overrides**: WooCommerce's front-end appearance is rendered using template files located in `wp-content/plugins/woocommerce/templates/`.
    * **Template Overrides**: To customize these, you **never directly edit the plugin's template files**. Instead, create a `woocommerce` folder within your **child theme** (e.g., `wp-content/themes/your-child-theme/woocommerce/`), then copy the specific template file you want to modify (maintaining its original subfolder structure) into that `woocommerce` folder. WooCommerce will then use your custom version.
    * *Why it matters*: This ensures your customizations are safe from being overwritten during WooCommerce plugin updates.
* **WooCommerce Hooks (Actions & Filters)**: Similar to WordPress hooks, but specific to WooCommerce. These are the most flexible and update-safe ways to modify WooCommerce's behavior and output.
    * The **WooCommerce Code Reference** (`developer.woocommerce.com`) is essential for discovering available hooks and their parameters.
    * *Why it matters*: For most customizations (adding content, altering fields, changing logic), using hooks is preferred over template overrides, as they are less intrusive and more resilient to updates.

## 4. 🌐 WooCommerce Operational Flow at a Glance
To fully understand WooCommerce's structure and practical operational flow, here's an overview of the essential steps.

1.  **Product Setup**: Understand **Simple** and **Variable Products**, set up **Product Categories/Tags** for classification. Register products with consistent image ratios/sizes, descriptions, options, prices, and stock levels.
2.  **Template Understanding**: Recognize **Archive Template** (product lists for categories/tags), **Single Product Template** (individual product details), and **Search Results Template** (displays products matching search queries).
3.  **Shipping & Tax Configuration**: Define **Shipping Zones** with specific methods and costs. Set up **Tax** policies (e.g., VAT) and decide if prices include or exclude tax.
4.  **Payment Integration**: Utilize basic WooCommerce payments (test payments) or integrate local/international Payment Gateway (PG) plugins for live operations. The flow is **Cart → Checkout → Payment → Order Completion**.
5.  **Order & Customer Management**: Use the admin panel to view **Order Management** details, change statuses (e.g., pending, completed, in transit), and process refunds. Manage **Customer Management** including member info, shipping addresses, and purchase history.
6.  **Design & Customization**: Customize templates (archive, single product, search results) using builders like Elementor. Refine headers, footers, banners, and product cards with CSS/JS.
7.  **Plugins & Extensions**: Extend functionality with plugins for features like coupons, reviews, filters, recommended products, and sliders.
8.  **Responsiveness & Optimization**: Ensure layouts, buttons, text, and images display well on mobile, tablet, and PC. Focus on **Accessibility** (alt text, font contrast) and **Speed Optimization**.
9.  **Live Operation & Testing**: Conduct test orders/payments, manage orders, and check email notifications to experience the actual flow. Identify and improve any issues.

## 5. 🛠️ Development & Maintenance Best Practices
Following these best practices ensures your WooCommerce site is robust, maintainable, and update-proof.

* **Use Child Themes (Crucial!)**: Always create and activate a child theme. Place all your custom PHP code, CSS, and JavaScript within this child theme to protect customizations from being lost during parent theme or plugin updates.
* **Never Modify Core Files**: Absolutely avoid directly editing any files within the `wp-content/plugins/woocommerce/` directory or your parent theme's files. Use hooks, filters, or template overrides within your child theme instead.
* **Prioritize Hooks Over Template Overrides**: If a desired change can be achieved with a hook, use the hook. Template overrides should be reserved for more extensive structural or layout changes. Hooks are generally more resilient to future updates.
* **Debugging**: Learn basic WordPress and PHP debugging. Enable `WP_DEBUG` in `wp-config.php` and monitor the `debug.log` file. Tools like `var_dump()` and `error_log()` are invaluable.
* **Consult Official Documentation**: The official WooCommerce documentation and especially the **WooCommerce Code Reference** (`developer.woocommerce.com`) are your best friends. They provide authoritative information on hooks, functions, classes, and best practices.

---

# 🛒 WooCommerce 종합 가이드

## 1. ✅ WooCommerce란?
WooCommerce는 WordPress에서 가장 널리 사용되는 오픈소스 전자상거래 플러그인입니다. 사용자는 WordPress 환경 내에서 온라인 쇼핑몰을 직접 구축하고 운영할 수 있습니다.

* **개발사**: WooThemes가 처음 개발하였으며, 2015년에 WordPress.com의 모회사인 Automattic에 인수됨.
* **라이선스**: 오픈소스(GPLv3).
* **통합성**: WordPress 테마 및 관리자 대시보드와 완벽하게 연동되도록 설계됨.

## 2. 🧱 핵심 기능
WooCommerce는 모든 온라인 상점에 필수적인 강력한 기능 세트를 제공합니다.

### 2.1. 🛍️ 상품 관리
* **단순 상품 (Simple Products)**: 옵션이 없는 단일 상품.
* **가변 상품 (Variable Products)**: 색상, 사이즈 등 다양한 옵션이 있는 상품으로, 각 옵션은 자체 SKU, 가격 및 재고를 가질 수 있습니다.
* **그룹 상품 (Grouped Products)**: 관련된 독립적인 여러 상품을 묶은 형태.
* **가상/다운로드 상품 (Virtual/Downloadable Products)**: 배송이 필요 없는 서비스 또는 디지털 상품에 적합합니다.

### 2.2. 🛒 장바구니 및 결제
* 원활한 구매 과정을 위한 기본 제공 장바구니 및 결제 페이지.
* 페이지 새로고침 없이 수량 조절이 가능한 Ajax 기반 장바구니 기능.
* 결제 단계 필드 커스터마이징 가능 (플러그인 또는 커스텀 코드 활용).

### 2.3. 💳 결제 수단
* **기본 내장**: PayPal, Stripe, 계좌이체, 현장결제 등.
* **확장 가능**: 다양한 결제 게이트웨이 플러그인 지원 (예: 국내의 Toss, 카카오페이 등).

### 2.4. 🚚 배송 옵션
* 고정 배송비, 무료 배송, 매장 수령 등.
* 위치 및 상품 유형에 따라 유연한 가격 책정을 위한 **배송 지역 (Shipping Zones)** 및 **배송 클래스 (Shipping Classes)** 설정 가능.

### 2.5. 🧾 세금 설정
* 자동 세금 계산 가능 (주로 플러그인 지원 필요).
* 세율 설정 및 가격에 세금 포함/제외 여부 제어 가능.

## 3. 🧠 WooCommerce 핵심 개념
WooCommerce 커스터마이징을 진정으로 마스터하려면, 기본 아키텍처와 WordPress와의 통합 방식을 이해하는 것이 중요합니다.

### 3.1. ⚙️ 워드프레스 코어 개념 (WooCommerce의 기반)
WooCommerce는 WordPress의 핵심 기능을 기반으로 구축되었습니다.

* **포스트 타입 (Post Types)**: 워드프레스에서 대부분의 콘텐츠는 '포스트'로 관리됩니다. WooCommerce는 특정 데이터를 위해 **커스텀 포스트 타입**을 도입하여 이를 확장합니다.
    * **상품 (Products)**: `product`라는 커스텀 포스트 타입입니다.
    * **주문 (Orders)**: `shop_order`라는 커스텀 포스트 타입입니다.
    * *왜 중요할까요?*: 상품 및 주문의 주요 데이터(제목, 설명, 상태 등)는 표준 `wp_posts` 테이블에 저장됩니다.
* **메타 데이터 (Meta Data)**: 포스트에 첨부되는 추가적이고 상세한 정보입니다.
    * **`wp_postmeta` 테이블**: 대부분의 상세 상품 정보(예: 가격, SKU, 재고, 속성, 변형) 및 주문 세부 정보(예: 고객 주소, 결제 수단, 품목)는 여기에 키-값 쌍으로 저장되며, 해당 `post_id`와 연결됩니다.
* **훅 (Hooks - 액션 & 필터)**: 워드프레스의 강력한 확장성 메커니즘이며, WooCommerce가 이를 완전히 활용합니다.
    * **액션 (Actions)**: 실행 흐름의 미리 정의된 특정 지점에 **코드를 삽입하거나 실행**할 수 있도록 합니다.
    * **필터 (Filters)**: 데이터가 표시되거나 저장되기 전에 **데이터를 수정하거나 필터링**할 수 있도록 합니다.
    * *왜 중요할까요?*: 코어 파일을 직접 편집하지 않고 WooCommerce를 커스터마이징하는 주요 방법입니다.

### 3.2. 🛒 WooCommerce 고유 개념
WordPress 코어 외에도 WooCommerce는 전자 상거래를 관리하기 위한 자체적인 고유 개념을 도입합니다.

* **데이터베이스 스키마 (Database Schema)**: WooCommerce는 특정 전자 상거래 데이터를 위한 자체 전용 데이터베이스 테이블을 추가합니다.
    * 예시로는 `woocommerce_order_items` (주문 내 개별 품목), `woocommerce_order_itemmeta`, `wc_product_meta_lookup` (빠른 상품 필터링용), `wc_download_log` 등이 있습니다.
    * *왜 중요할까요?*: 어떤 데이터가 어디에 있는지 이해하는 것은 디버깅 및 복잡한 커스텀 쿼리에 도움이 됩니다.
* **상품 타입 (Product Types)**: 다양한 판매 시나리오에 맞춰 내장된 상품 유형입니다.
    * **단순 상품 (Simple Product)**: 표준 단일 품목.
    * **가변 상품 (Variable Product)**: 색상, 사이즈와 같은 속성을 가지며, 각 변형은 자체 SKU, 가격 및 재고를 가질 수 있습니다.
    * **그룹 상품 (Grouped Product)**: 단순 상품들의 묶음.
    * **외부/제휴 상품 (External/Affiliate Product)**: 외부 URL로 연결되어 구매가 이루어지는 상품.
    * **가상 상품 (Virtual Product)**: 배송이 필요 없는 비물리적 상품.
    * **다운로드 상품 (Downloadable Product)**: 구매 후 고객이 다운로드할 수 있는 디지털 상품.
    * *왜 중요할까요?*: 정확한 재고, 가격 책정 및 고객 경험을 위해 올바른 상품 유형을 선택하는 것이 중요합니다.
* **템플릿 계층 구조 및 오버라이드 (Template Hierarchy & Overrides)**: WooCommerce의 프론트엔드 외관은 `wp-content/plugins/woocommerce/templates/` 경로에 있는 템플릿 파일을 사용하여 렌더링됩니다.
    * **템플릿 오버라이드**: 이를 커스터마이징하려면 플러그인의 템플릿 파일을 **직접 편집해서는 절대 안 됩니다.** 대신, **차일드 테마** 안에 `woocommerce` 폴더(예: `wp-content/themes/your-child-theme/woocommerce/`)를 만들고, 수정하려는 특정 템플릿 파일(원본 하위 폴더 구조를 유지하며)을 해당 `woocommerce` 폴더 안에 복사합니다. 그러면 WooCommerce는 사용자 지정 버전을 사용합니다.
    * *왜 중요할까요?*: 이렇게 하면 WooCommerce 플러그인 업데이트 시 사용자 지정 사항이 덮어쓰여지는 것으로부터 안전하게 보호됩니다.
* **WooCommerce 훅 (Actions & Filters)**: WordPress 훅과 유사하지만, WooCommerce에 특화되어 있습니다. 이는 WooCommerce의 동작 및 출력을 수정하는 가장 유연하고 업데이트에 안전한 방법입니다.
    * **WooCommerce Code Reference**(`developer.woocommerce.com`)는 사용 가능한 훅과 그 매개변수를 발견하는 데 필수적입니다.
    * *왜 중요할까요?*: 대부분의 커스터마이징(콘텐츠 추가, 필드 변경, 로직 변경)에는 템플릿 오버라이드보다 훅 사용이 선호됩니다. 훅은 침해적이지 않고 업데이트에 더 강하기 때문입니다.

## 4. 🌐 WooCommerce 운영 흐름 한눈에 보기
WooCommerce의 구조와 실전 운영 흐름을 완전히 이해하기 위해 필수적인 단계들을 요약했습니다.

1.  **상품 설정**: **단순 상품** 및 **가변 상품**을 이해하고, 분류를 위해 **상품 카테고리/태그**를 설정합니다. 일관된 이미지 비율/크기, 설명, 옵션, 가격, 재고 수준으로 상품을 등록합니다.
2.  **템플릿 이해**: **아카이브 템플릿** (카테고리/태그별 상품 목록), **싱글 상품 템플릿** (개별 상품 상세 정보), **검색 결과 템플릿** (검색어와 일치하는 상품 표시)을 파악합니다.
3.  **배송 및 세금 설정**: 특정 방법 및 비용으로 **배송 지역**을 정의합니다. **세금** 정책 (예: 부가세)을 설정하고 가격에 세금 포함/제외 여부를 결정합니다.
4.  **결제 통합**: 기본 WooCommerce 결제(테스트 결제)를 활용하거나, 실제 운영을 위해 국내/해외 결제 게이트웨이(PG) 플러그인을 통합합니다. 흐름은 **장바구니 → 결제 → 결제 완료 → 주문 완료**입니다.
5.  **주문 및 고객 관리**: 관리자 패널을 사용하여 **주문 관리** 세부 정보를 확인하고, 상태(예: 입금 대기, 완료, 배송 중)를 변경하며, 환불을 처리합니다. 회원 정보, 배송지, 구매 내역을 포함한 **고객 관리**를 수행합니다.
6.  **디자인 및 커스터마이징**: Elementor와 같은 빌더를 사용하여 템플릿 (아카이브, 단일 상품, 검색 결과)을 커스터마이징합니다. CSS/JS로 헤더, 푸터, 배너 및 상품 카드 등을 다듬습니다.
7.  **플러그인 및 확장 기능**: 쿠폰, 리뷰, 필터, 추천 상품, 슬라이더와 같은 기능을 위한 플러그인을 사용하여 기능을 확장합니다.
8.  **반응형 및 최적화**: 모바일, 태블릿, PC에서 레이아웃, 버튼, 텍스트, 이미지가 잘 표시되도록 확인합니다. **접근성** (alt 텍스트, 폰트 대비) 및 **속도 최적화**에 중점을 둡니다.
9.  **실제 운영 및 테스트**: 실제 흐름을 경험하기 위해 테스트 주문/결제를 수행하고, 주문을 관리하며, 이메일 알림을 확인합니다. 모든 문제점을 식별하고 개선합니다.

## 5. 🛠️ 개발 및 유지보수 모범 사례
다음 모범 사례를 따르면 WooCommerce 사이트가 견고하고 유지보수가 용이하며 업데이트에도 강해집니다.

* **차일드 테마 사용 (필수!)**: 항상 차일드 테마를 생성하고 활성화하세요. 모든 커스텀 PHP 코드, CSS, JavaScript를 이 차일드 테마 안에 배치하여 부모 테마 또는 플러그인 업데이트 시 커스터마이징이 손실되는 것을 방지합니다.
* **코어 파일 절대 수정 금지**: `wp-content/plugins/woocommerce/` 디렉토리 또는 부모 테마 파일 내의 어떤 파일도 직접 편집하는 것을 절대 피하세요. 대신 차일드 테마 내에서 훅, 필터 또는 템플릿 오버라이드를 사용하세요.
* **템플릿 오버라이드보다 훅 우선**: 원하는 변경 사항을 훅으로 달성할 수 있다면 훅을 사용하세요. 템플릿 오버라이드는 더 광범위한 구조적 또는 레이아웃 변경에 한정해야 합니다. 훅은 일반적으로 향후 업데이트에 더 탄력적입니다.
* **디버깅**: 기본적인 WordPress 및 PHP 디버깅 기술을 익히세요. `wp-config.php`에서 `WP_DEBUG`를 활성화하고 `debug.log` 파일을 모니터링하세요. `var_dump()` 및 `error_log()`와 같은 도구는 매우 유용합니다.
* **공식 문서 참조**: 공식 WooCommerce 문서, 특히 **WooCommerce Code Reference**(`developer.woocommerce.com`)는 최고의 자료입니다. 훅, 함수, 클래스 및 모범 사례에 대한 신뢰할 수 있는 정보를 제공합니다.
