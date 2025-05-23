# 🛒 WooCommerce Core Concepts

## 1. 🧱 Core Concepts

To truly master WooCommerce customization, it's crucial to understand the underlying architecture and how it integrates with WordPress.

### 1.1. ⚙️ WordPress Core Concepts (Foundation of WooCommerce)

WooCommerce builds heavily on the core functionalities of WordPress. Understanding these basics is fundamental.

* **Post Types**: In WordPress, almost all content is managed as 'posts'. WooCommerce extends this concept by introducing **Custom Post Types** to handle its specific data.
    * **Products**: Are a custom post type named `product`.
    * **Orders**: Are a custom post type named `shop_order`.
    * *Why it matters*: This means product and order main data (like title, description, status) are stored in the standard `wp_posts` table.
* **Meta Data**: This is how additional, detailed information is attached to posts (including custom post types like products and orders).
    * **`wp_postmeta` Table**: Most specific product details (e.g., price, SKU, stock quantity, product attributes, variations) and order details (e.g., customer address, payment method, line item details) are stored here as key-value pairs, linked to their respective `post_id` in `wp_posts`.
* **Hooks (Actions & Filters)**: WordPress's powerful extensibility mechanism, fully leveraged by WooCommerce.
    * **Actions**: Allow you to **insert or execute code** at specific predefined points in WordPress or WooCommerce's execution flow. For example, you can use an action hook to add extra content *below* the product summary.
    * **Filters**: Allow you to **modify or filter data** before it's displayed or saved. For example, you can use a filter hook to change how product prices are formatted or to alter checkout fields.
    * *Why it matters*: These are the primary methods for customizing WooCommerce without directly editing core files.

### 1.2. 🛒 WooCommerce-Specific Concepts

Beyond the WordPress core, WooCommerce introduces its own set of unique concepts to manage e-commerce functionalities.

* **Database Schema**: While heavily relying on `wp_posts` and `wp_postmeta`, WooCommerce also introduces its own dedicated database tables for specific e-commerce data management.
    * Examples include `woocommerce_order_items` (for individual items within an order), `woocommerce_order_itemmeta` (meta for order items), `wc_product_meta_lookup` (for faster product filtering), `wc_download_log`, etc.
    * *Why it matters*: Understanding which data resides where helps in debugging and complex custom queries.
* **Product Types**: WooCommerce offers built-in product types that cater to various selling scenarios, impacting how products are set up and displayed.
    * **Simple Product**: A standard, single item with no variations.
    * **Variable Product**: A product with multiple attributes (like color, size) that create different variations, each potentially having its own SKU, price, and stock. (This is very common and important to understand for e-commerce sites).
    * **Grouped Product**: A collection of simple, standalone products presented as a group.
    * **External/Affiliate Product**: A product listed on your site but linked to an external URL for purchase.
    * **Virtual Product**: A non-physical product that doesn't require shipping (e.g., a service, membership).
    * **Downloadable Product**: A product that customers can download after purchase (e.g., e-books, software).
    * *Why it matters*: Choosing the correct product type is crucial for accurate inventory, pricing, and customer experience.
* **Template Hierarchy & Overrides**: WooCommerce's front-end appearance (product pages, cart, checkout) is rendered using a structured set of template files.
    * These core template files are located in `wp-content/plugins/woocommerce/templates/`.
    * **Template Overrides**: To customize these views, you **never** directly edit the plugin's template files. Instead, you create a `woocommerce` folder within your **child theme** (e.g., `wp-content/themes/your-child-theme/woocommerce/`), then copy the specific template file you want to modify (maintaining its original subfolder structure) into that `woocommerce` folder. WooCommerce will then use your custom version instead of the plugin's default.
    * *Why it matters*: This ensures your customizations are safe from being overwritten during WooCommerce plugin updates.
* **WooCommerce Hooks (Actions & Filters)**: Similar to WordPress hooks, but specific to WooCommerce. These are the most flexible and update-safe ways to modify WooCommerce's behavior and output.
    * You'll find hundreds of WooCommerce-specific hooks. Learning to use the official **WooCommerce Code Reference** (`developer.woocommerce.com`) is essential to discover available hooks and their parameters.
    * *Why it matters*: For most customizations (adding content, altering fields, changing logic), using hooks is preferred over template overrides, as they are less intrusive and more resilient to updates.

---

## 2. 🛠️ Development & Maintenance Best Practices

Following these best practices will ensure your WooCommerce site is robust, maintainable, and update-proof.

* **Use Child Themes (Crucial!)**: This is non-negotiable. Always create and activate a child theme, and place all your custom PHP code, CSS, and JavaScript within this child theme. This protects your customizations from being lost when the parent theme or WooCommerce plugin is updated.
* **Never Modify Core Files**: Absolutely avoid directly editing any files within the `wp-content/plugins/woocommerce/` directory or your parent theme's files. Any direct changes will be overwritten during updates. Always use hooks, filters, or template overrides within your child theme.
* **Prioritize Hooks Over Template Overrides**: If a desired change can be achieved with a hook (action or filter), use the hook. Template overrides should be reserved for more extensive structural or layout changes that hooks cannot easily accommodate. Hooks are generally more resilient to future updates.
* **Debugging**: Learn basic WordPress and PHP debugging techniques. Enable `WP_DEBUG` in `wp-config.php` and monitor the `debug.log` file. Tools like `var_dump()` and `error_log()` are invaluable for understanding data flow and identifying issues in your custom code.
* **Consult Official Documentation**: The official WooCommerce documentation and especially the **WooCommerce Code Reference** (`developer.woocommerce.com`) are your best friends. They provide authoritative information on hooks, functions, classes, and best practices.

---

# 🛒 WooCommerce 핵심 개념

## 1. 🧱 핵심 개념

WooCommerce 커스터마이징을 진정으로 마스터하려면, 기본 아키텍처와 WordPress와의 통합 방식을 이해하는 것이 중요합니다.

### 1.1. ⚙️ 워드프레스 코어 개념 (WooCommerce의 기반)

WooCommerce는 WordPress의 핵심 기능을 기반으로 구축되었습니다. 이러한 기본 사항을 이해하는 것이 매우 중요합니다.

* **포스트 타입 (Post Types)**: 워드프레스에서 거의 모든 콘텐츠는 '포스트'라는 개념으로 관리됩니다. WooCommerce는 특정 데이터를 처리하기 위해 **커스텀 포스트 타입**을 도입하여 이 개념을 확장합니다.
    * **상품(Products)**: `product`라는 커스텀 포스트 타입입니다.
    * **주문(Orders)**: `shop_order`라는 커스텀 포스트 타입입니다.
    * *왜 중요할까요?*: 이는 상품 및 주문의 주요 데이터(제목, 설명, 상태 등)가 표준 `wp_posts` 테이블에 저장됨을 의미합니다.
* **메타 데이터 (Meta Data)**: 포스트(상품 및 주문과 같은 커스텀 포스트 타입 포함)에 추가적이고 상세한 정보를 첨부하는 방법입니다.
    * **`wp_postmeta` 테이블**: 대부분의 상세 상품 정보(예: 가격, SKU, 재고 수량, 상품 속성, 변형) 및 주문 세부 정보(예: 고객 주소, 결제 수단, 품목 세부 정보)가 여기에 키-값(Key-Value) 쌍으로 저장되며, 해당 `post_id`와 연결됩니다.
* **훅 (Hooks - 액션 & 필터)**: 워드프레스의 강력한 확장성 메커니즘이며, WooCommerce가 이를 완전히 활용합니다.
    * **액션 (Actions)**: 워드프레스 또는 WooCommerce의 실행 흐름에서 미리 정의된 특정 지점에 **코드를 삽입하거나 실행**할 수 있도록 합니다. 예를 들어, 액션 훅을 사용하여 상품 요약 *아래*에 추가 콘텐츠를 넣을 수 있습니다.
    * **필터 (Filters)**: 데이터가 표시되거나 저장되기 전에 **데이터를 수정하거나 필터링**할 수 있도록 합니다. 예를 들어, 필터 훅을 사용하여 상품 가격 표시 형식을 변경하거나 결제 필드를 변경할 수 있습니다.
    * *왜 중요할까요?*: 이는 코어 파일을 직접 편집하지 않고 WooCommerce를 커스터마이징하는 주요 방법입니다.

### 1.2. 🛒 WooCommerce 고유 개념

WordPress 코어 외에도 WooCommerce는 전자 상거래 기능을 관리하기 위한 자체적인 고유 개념을 도입합니다.

* **데이터베이스 스키마 (Database Schema)**: `wp_posts` 및 `wp_postmeta`에 크게 의존하지만, WooCommerce는 특정 전자 상거래 데이터 관리를 위한 자체 전용 데이터베이스 테이블도 추가합니다.
    * 예시로는 `woocommerce_order_items` (주문 내 개별 품목), `woocommerce_order_itemmeta` (주문 품목 메타), `wc_product_meta_lookup` (빠른 상품 필터링용), `wc_download_log` 등이 있습니다.
    * *왜 중요할까요?*: 어떤 데이터가 어디에 있는지 이해하는 것은 디버깅 및 복잡한 커스텀 쿼리에 도움이 됩니다.
* **상품 타입 (Product Types)**: WooCommerce는 다양한 판매 시나리오에 맞춰 다양한 상품 유형을 내장하고 있으며, 이는 상품 설정 및 표시 방식에 영향을 미칩니다.
    * **단순 상품 (Simple Product)**: 변형이 없는 표준 단일 품목입니다.
    * **가변 상품 (Variable Product)**: 색상, 사이즈와 같은 여러 속성을 가지고 있어 다양한 변형을 만들고, 각 변형은 자체 SKU, 가격 및 재고를 가질 수 있습니다. (전자 상거래 사이트에서 매우 흔하고 중요합니다.)
    * **그룹 상품 (Grouped Product)**: 단순 상품들의 묶음으로, 그룹으로 묶여서 표시됩니다.
    * **외부/제휴 상품 (External/Affiliate Product)**: 사이트에 나열되어 있지만 외부 URL로 연결되어 구매가 이루어지는 상품입니다.
    * **가상 상품 (Virtual Product)**: 배송이 필요 없는 비물리적 상품입니다 (예: 서비스, 멤버십).
    * **다운로드 상품 (Downloadable Product)**: 구매 후 고객이 다운로드할 수 있는 상품입니다 (예: 전자책, 소프트웨어).
    * *왜 중요할까요?*: 정확한 재고, 가격 책정 및 고객 경험을 위해 올바른 상품 유형을 선택하는 것이 중요합니다.
* **템플릿 계층 구조 및 오버라이드 (Template Hierarchy & Overrides)**: WooCommerce의 프론트엔드 외관(상품 페이지, 장바구니, 결제 등)은 구조화된 템플릿 파일 세트를 사용하여 렌더링됩니다.
    * 이러한 핵심 템플릿 파일은 `wp-content/plugins/woocommerce/templates/` 경로에 있습니다.
    * **템플릿 오버라이드**: 이 뷰를 커스터마이징하려면 플러그인의 템플릿 파일을 **직접 편집해서는 안 됩니다.** 대신, **차일드 테마** 안에 `woocommerce` 폴더(예: `wp-content/themes/your-child-theme/woocommerce/`)를 만들고, 수정하려는 특정 템플릿 파일(원본 하위 폴더 구조를 유지하며)을 해당 `woocommerce` 폴더 안에 복사합니다. 그러면 WooCommerce는 플러그인의 기본 템플릿 대신 사용자 지정 버전을 사용합니다.
    * *왜 중요할까요?*: 이렇게 하면 WooCommerce 플러그인 업데이트 시 사용자 지정 사항이 덮어쓰여지는 것으로부터 안전하게 보호됩니다.
* **WooCommerce 훅 (Actions & Filters)**: 워드프레스 훅과 유사하지만, WooCommerce에 특화되어 있습니다. 이는 WooCommerce의 동작 및 출력을 수정하는 가장 유연하고 업데이트에 안전한 방법입니다.
    * 수백 개의 WooCommerce 특정 훅을 찾을 수 있습니다. 사용 가능한 훅과 그 매개변수를 발견하려면 공식 **WooCommerce Code Reference**(`developer.woocommerce.com`)를 사용하는 방법을 배우는 것이 필수적입니다.
    * *왜 중요할까요?*: 대부분의 커스터마이징(콘텐츠 추가, 필드 변경, 로직 변경)에는 템플릿 오버라이드보다 훅 사용이 선호됩니다. 훅은 침해적이지 않고 업데이트에 더 강하기 때문입니다.

---

## 2. 🛠️ 개발 및 유지보수 모범 사례

이러한 모범 사례를 따르면 WooCommerce 사이트가 견고하고 유지보수가 용이하며 업데이트에도 강해질 수 있습니다.

* **차일드 테마 사용 (필수!)**: 이것은 협상할 수 없는 사항입니다. 항상 차일드 테마를 생성하고 활성화한 다음, 모든 커스텀 PHP 코드, CSS, JavaScript를 이 차일드 테마 안에 배치하세요. 이렇게 하면 부모 테마나 WooCommerce 플러그인이 업데이트될 때 커스터마이징이 손실되는 것을 방지할 수 있습니다.
* **코어 파일 절대 수정 금지**: `wp-content/plugins/woocommerce/` 디렉토리 또는 부모 테마 파일 내의 어떤 파일도 직접 편집하는 것을 절대 피하세요. 직접 변경한 내용은 업데이트 시 덮어쓰여집니다. 항상 차일드 테마 내에서 훅, 필터 또는 템플릿 오버라이드를 사용하세요.
* **템플릿 오버라이드보다 훅 우선**: 원하는 변경 사항을 훅(액션 또는 필터)으로 달성할 수 있다면 훅을 사용하세요. 템플릿 오버라이드는 훅으로는 쉽게 처리할 수 없는 더 광범위한 구조적 또는 레이아웃 변경에 한정해야 합니다. 훅은 일반적으로 향후 업데이트에 더 탄력적입니다.
* **디버깅**: 기본적인 WordPress 및 PHP 디버깅 기술을 익히세요. `wp-config.php`에서 `WP_DEBUG` 모드를 활성화하고 `debug.log` 파일을 모니터링하세요. `var_dump()` 및 `error_log()`와 같은 도구는 사용자 지정 코드의 데이터 흐름을 이해하고 문제를 식별하는 데 매우 유용합니다.
* **공식 문서 참조**: 공식 WooCommerce 문서, 특히 **WooCommerce Code Reference**(`developer.woocommerce.com`)는 최고의 자료입니다. 훅, 함수, 클래스 및 모범 사례에 대한 신뢰할 수 있는 정보를 제공합니다.
