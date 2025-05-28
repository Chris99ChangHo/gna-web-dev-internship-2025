# ✨ WooCommerce Practical Development: A Language-Specific Guide

### **1. HTML: WooCommerce Template Structure & Overrides**

This section covers how to leverage HTML for understanding and customizing the visual structure of your WooCommerce frontend. WooCommerce renders most of its HTML through PHP template files.

* **WooCommerce Template File Structure:**
    WooCommerce stores various PHP template files in the `wp-content/plugins/woocommerce/templates/` directory. These files generate the actual **HTML structure** for your store pages (e.g., product listings, single product pages, cart, checkout).
    * **Key Template Examples:**
        * `archive-product.php`: Product archive/listing page
        * `single-product.php`: Individual product detail page
        * `cart/cart.php`: Cart page
        * `checkout/form-checkout.php`: Checkout page form
        * `myaccount/my-account.php`: My Account page
* **Practical HTML Customization (Template Overrides):**
    * **Using a Child Theme:** When modifying WooCommerce template files, it's crucial to **create and use a child theme**. Directly editing the parent theme can lead to your changes being overwritten during theme updates.
    * **Override Rule:** To override a template, copy the desired file from `wp-content/plugins/woocommerce/templates/` to a new `woocommerce/` folder within your **child theme's directory**, maintaining the exact same sub-path as the original.
        * **Example:** To modify `single-product/product-image.php`, copy it to `wp-content/themes/your-child-theme/woocommerce/single-product/product-image.php`.
    * **Leveraging Action/Filter Hooks:** WooCommerce embeds numerous action (`do_action()`) and filter (`apply_filters()`) hooks directly within its templates. These hooks allow you to add content or modify existing content at specific points in the HTML structure without directly altering the template files. This method is often preferred over direct template overrides for minor adjustments.
        * **Example:** The `do_action('woocommerce_before_single_product_summary');` hook allows you to inject content just before the product summary on a single product page.
    * **Organization Example (Modifying HTML within a Template File):**
        Below is an example of modifying `wp-content/plugins/woocommerce/templates/single-product/title.php` after copying it to your child theme's `woocommerce/single-product/title.php` path.
        ```php
        <?php
        /**
         * Template File: single-product/title.php (Displays Product Title)
         * This file renders the product title on individual product pages.
         */

        // Default product title display
        the_title( '<h1 class="product_title entry-title">', '</h1>' );

        // Use a specific hook to add custom HTML below the title (controlled by PHP's add_action)
        do_action( 'woocommerce_single_product_summary_after_title' );

        /*
         * If you want to change the HTML output by the_title() function itself,
         * you can override this template file and directly modify the <h1 class="product_title entry-title">...</h1> part.
         *
         * For example, to add "Product Name: " before the title:
         * <h1 class="product_title entry-title">Product Name: <?php the_title(); ?></h1>
         *
         * Or you could change it to an entirely different HTML structure.
         */
        ?>
        ```

        * **Explanation:** This example illustrates how to control HTML markup within a WooCommerce template file. The `the_title()` function generates the default HTML, while `do_action()` hooks provide points for inserting additional content via PHP. By overriding the template, you gain the freedom to **modify the HTML structure itself**, like the `<h1>` tag in this example.

### **2. CSS: WooCommerce Styling Guide**

This section outlines how to effectively control and manage the visual elements of WooCommerce using CSS.

* **WooCommerce Official Guidelines:**
    * Most WooCommerce-related CSS classes use the **`.woocommerce-` prefix**.
    * CSS naming predominantly follows the **BEM (Block__Element--Modifier) methodology**.
        * **Example:** `.woocommerce-loop-product__title` (product title in product loops), `.woocommerce-cart__item--active` (active item in the cart).
* **Practical CSS Organization:**
    * **File Management:** It's best practice to **manage WooCommerce-specific CSS separately**, typically in `css/woocommerce.css` or within a `css/components/woocommerce/` folder. This approach enhances code modularity and maintainability.
    * **Common Elements/Classes:** Familiarizing yourself with classes related to key WooCommerce pages and components allows for efficient styling.
        * **Examples:** `.woocommerce-cart` (entire cart page), `.woocommerce-checkout` (entire checkout page), `.woocommerce-MyAccount-navigation` (My Account menu), `.woocommerce-product-attributes` (product attributes table).
    * **Configuration/Patterns:** Common styling patterns (e.g., box model, buttons, forms, tables, navigation, tabs) should be separated into distinct sections, with comments to improve readability.
    * **Organization Example:**
        ```css
        /* WooCommerce Buttons */
        .woocommerce .button, .woocommerce .woocommerce-button {
            background-color: #007bff;
            color: #fff;
            padding: 10px 20px;
            border-radius: 5px;
            /* ... other button styles ... */
        }

        /* WooCommerce Cart Table */
        .woocommerce-cart table.shop_table {
            width: 100%;
            border-collapse: collapse;
            margin-bottom: 20px;
            /* ... other table styles ... */
        }

        /* WooCommerce Product Attributes Table */
        .woocommerce-product-attributes th {
            font-weight: bold;
            padding: 8px;
            text-align: left;
            /* ... other attribute table header styles ... */
        }
        ```

    * **CSS Property Sorting:** For better readability, it's recommended to sort CSS properties according to a specific convention.
        * **Example:** Group properties by type (e.g., box model, color, font, miscellaneous).

### **3. JavaScript: Controlling WooCommerce Interactions**

This section covers how to use JavaScript to manage dynamic features and user interactions within WooCommerce.

* **WooCommerce Official JavaScript Naming Conventions:**
    * **Functions:** Use the `wc_` prefix (e.g., `wcFunctionName()`).
    * **Classes:** Use the `WC_` prefix (e.g., `WCClassName`).
    * **Events/Hooks:** Use the `woocommerce_` prefix (e.g., `woocommerceEventName`), often used with jQuery's `trigger` and `on` methods for custom events.
* **Practical JavaScript Organization:**
    * **File Management:** WooCommerce-related JavaScript should be **managed separately**, typically in `js/woocommerce.js` or within a `js/components/woocommerce/` folder. This minimizes conflicts with other scripts and simplifies maintenance.
    * **Common Events/Patterns:** WooCommerce fires various custom events, allowing you to add or modify functionality at specific points in time.
        * **Examples:** Use `added_to_cart` (when a product is added to the cart), `updated_cart_totals` (when cart totals are updated), `found_variation` (when a variable product option is selected) to implement dynamic UI elements like DOM manipulation, Ajax calls, and real-time notifications.
    * **Organization Example:**
        ```javascript
        // WooCommerce: Add to cart event
        jQuery(document.body).on('added_to_cart', function(event, fragments, cart_hash, $button){
            // Code to execute after a product is added to the cart
            console.log('Product has been added to the cart!');
            // E.g., update mini cart, display notification
        });

        // WooCommerce: Checkout update
        jQuery(document.body).on('updated_checkout', function(){
            // Code to execute when the checkout page is updated (e.g., shipping method changed)
            console.log('Checkout information has been updated.');
            // E.g., change specific field values, adjust UI
        });
        ```

    * **jQuery Dependency:** WooCommerce's built-in JavaScript relies heavily on **jQuery**. Therefore, it's generally convenient to use jQuery for custom scripts as well. If you need to use vanilla JS or other frameworks due to modern development trends, additional work might be required to ensure compatibility with existing WooCommerce scripts.

### **4. PHP: WooCommerce Backend & Template Control**

This section focuses on using PHP to control WooCommerce's core functionality, data processing, and template structure.

* **WooCommerce Official PHP Naming Conventions:**
    * **Functions:** Use the `wc_` prefix (e.g., `wc_get_product()`).
    * **Classes:** Use the `WC_` prefix (e.g., `WC_Product`).
    * **Hooks (Actions/Filters):** Use the `woocommerce_` prefix (e.g., `woocommerce_before_cart`).
* **Practical PHP Organization:**
    * **File Management:** Instead of directly adding code to your theme's (or child theme's) `functions.php` file, it's a good practice to **organize WooCommerce-related functions and hooks into separate files or folders**, such as `inc/woocommerce.php`. This improves maintainability. You would then `require` or `include` this file from `functions.php`.
    * **Common Hooks/Filters:** WooCommerce provides a vast array of action hooks (`add_action()`) and filter hooks (`add_filter()`) that allow you to extend or modify functionality without directly altering core plugin code.
        * **Examples:**
            * `woocommerce_before_cart`: Before the cart page content starts.
            * `woocommerce_after_checkout_form`: After the checkout form ends.
            * `woocommerce_account_menu_items`: To modify My Account menu items.
            * `woocommerce_product_tabs`: To add/remove tabs on the single product page.
    * **Organization Example:**
        ```php
        <?php
        // WooCommerce: Customize My Account menu items
        // Used to add new menu items or reorder existing ones
        add_filter('woocommerce_account_menu_items', function($items) {
            $items['custom-link'] = 'My Custom Link'; // Add a new menu item
            // $items['orders'] = 'My Order History'; // Change text of an existing item
            return $items;
        });

        // WooCommerce: Add a custom message to the cart page
        // Used to display a specific message above the cart table
        add_action('woocommerce_before_cart', function() {
            if (WC()->cart->is_empty()) {
                echo '<p class="woocommerce-info">Your cart is empty.</p>';
            } else {
                echo '<p class="custom-cart-message">Free shipping on all orders!</p>';
            }
        });

        // WooCommerce: Modify product price display format (Filter example)
        add_filter('woocommerce_price_format', function($format, $currency_pos) {
            // For example, to prepend "Price: " to the price
            return 'Price: %1$s%2$s'; // %1$s is currency symbol, %2$s is price
        }, 10, 2);
        ```

    * **Template Overrides:** As mentioned in the HTML section, WooCommerce renders frontend HTML via `.php` template files. By copying these files into a `woocommerce/` folder within your theme and maintaining the original path, you can modify them without losing changes during plugin updates.

### **5. Other Practical Considerations: Version Control & Stability**

These are crucial additional considerations for enhancing code stability and maintainability in WooCommerce development.

* **Importance of Child Themes:**
    * As mentioned, **always use a child theme when modifying WooCommerce template files or adding custom code to `functions.php`**. Direct modifications to the parent theme risk being overwritten during theme updates.
    * A child theme safely inherits the parent theme's functionalities while allowing you to add your own styles and features.
* **Version Control Systems (e.g., Git):**
    * Utilizing a **version control system like Git** is essential for any WooCommerce project.
    * Managing your customized code, theme files, and plugin configurations with Git allows you to track changes, collaborate with team members, and easily revert to previous versions if issues arise.
* **WooCommerce Update Management:**
    * WooCommerce receives regular updates for feature enhancements and security patches. Always **perform a backup** before updating, and test in a development environment first to check for conflicts with your custom code or other plugins.
    * When overriding templates, check if the original template files have changed with a WooCommerce update (often indicated by 'template outdated' warnings) and update your overridden files accordingly.

---

# ✨ WooCommerce 실무 개발: 언어별 가이드라인

### **1. HTML: WooCommerce 템플릿 구조 및 오버라이드**

이 섹션에서는 WooCommerce 프론트엔드의 시각적 구조를 이해하고 커스터마이징하기 위해 HTML을 어떻게 활용하는지 다룹니다. WooCommerce는 대부분의 HTML을 PHP 템플릿 파일을 통해 렌더링합니다.

* **WooCommerce 템플릿 파일 구조:**
    WooCommerce는 `wp-content/plugins/woocommerce/templates/` 경로에 다양한 PHP 템플릿 파일들을 가지고 있습니다. 이 파일들이 실제 상점 페이지(제품 목록, 상세 페이지, 장바구니, 결제 등)의 **HTML 구조를 생성**합니다.
    * **주요 템플릿 예시:**
        * `archive-product.php`: 제품 아카이브/목록 페이지
        * `single-product.php`: 개별 제품 상세 페이지
        * `cart/cart.php`: 장바구니 페이지
        * `checkout/form-checkout.php`: 결제 페이지 폼
        * `myaccount/my-account.php`: 마이 어카운트 페이지
* **실무적인 HTML 커스터마이징 방법 (템플릿 오버라이드):**
    * **자식 테마(Child Theme) 사용:** WooCommerce 템플릿 파일을 직접 수정하는 대신, 반드시 **자식 테마**를 생성하여 커스터마이징해야 합니다. 부모 테마를 직접 편집하면 테마 업데이트 시 변경사항이 덮어쓰여 사라질 수 있습니다.
    * **오버라이드 규칙:** 수정하고 싶은 템플릿 파일을 `wp-content/plugins/woocommerce/templates/`에서 복사하여, 자신의 **자식 테마 폴더 내에 `woocommerce/`라는 새 폴더를 만들고 원본과 동일한 하위 경로에 붙여넣기** 합니다.
        * **예시:** `single-product/product-image.php` 파일을 수정하려면, `wp-content/themes/your-child-theme/woocommerce/single-product/product-image.php` 경로에 복사합니다.
    * **액션/필터 훅 활용:** WooCommerce는 템플릿 내에 수많은 액션(`do_action()`) 및 필터(`apply_filters()`) 훅을 심어두어, HTML 구조 자체를 직접 수정하지 않고도 특정 위치에 콘텐츠를 추가하거나 기존 콘텐츠를 변경할 수 있게 합니다. 이 방법은 사소한 조정을 위해 직접적인 템플릿 오버라이드보다 권장됩니다.
        * **예시:** `do_action('woocommerce_before_single_product_summary');` 훅은 개별 제품 상세 페이지의 요약 정보 시작 전에 콘텐츠를 추가할 수 있게 합니다.
    * **정리 예시 (템플릿 파일 내에서 HTML 구조 변경 시):**
        아래는 `wp-content/plugins/woocommerce/templates/single-product/title.php` 파일을 자식 테마의 `woocommerce/single-product/title.php`로 복사한 후 수정하는 예시입니다.
        ```php
        <?php
        /**
         * 템플릿 파일: single-product/title.php (제품 제목 표시)
         * 이 파일은 개별 제품 페이지에서 제품 제목을 렌더링합니다.
         */

        // 기본 제품 제목 표시
        the_title( '<h1 class="product_title entry-title">', '</h1>' );

        // 특정 훅을 사용하여 제목 아래에 커스텀 HTML 추가 (PHP의 add_action으로 제어)
        do_action( 'woocommerce_single_product_summary_after_title' );

        /*
         * 만약 위 `the_title()` 함수로 출력되는 HTML 자체를 변경하고 싶다면,
         * 이 템플릿 파일을 오버라이드하여 <h1 class="product_title entry-title">...</h1> 부분을 직접 수정합니다.
         *
         * 예를 들어, 제목 앞에 '상품명: '이라는 텍스트를 추가하려면:
         * <h1 class="product_title entry-title">상품명: <?php the_title(); ?></h1>
         *
         * 또는 완전히 다른 HTML 구조로 변경할 수도 있습니다.
         */
        ?>
        ```

        * **설명:** 이 예시는 WooCommerce 템플릿 파일 내부에서 HTML 마크업을 어떻게 제어하는지 보여줍니다. `the_title()` 함수로 기본 HTML이 생성되며, `do_action()` 훅은 PHP 코드를 통해 추가 콘텐츠를 삽입할 수 있는 지점을 제공합니다. 템플릿 파일을 오버라이드하면 이 `<h1>` 태그와 같은 **HTML 구조 자체를 자유롭게 변경**할 수 있습니다.

### **2. CSS: WooCommerce 스타일링 가이드**

이 섹션에서는 WooCommerce의 시각적인 요소를 효과적으로 제어하고 관리하기 위해 CSS를 어떻게 활용하는지 설명합니다.

* **WooCommerce 공식 가이드라인:**
    * 대부분의 WooCommerce 관련 CSS 클래스는 **`.woocommerce-` 접두사**를 사용합니다.
    * CSS 네이밍은 주로 **BEM(Block__Element--Modifier) 방식**을 따릅니다.
        * **예시:** `.woocommerce-loop-product__title` (상품 목록 내 상품 제목), `.woocommerce-cart__item--active` (장바구니 활성 항목).
* **실무적인 CSS 정리법:**
    * **파일 관리:** WooCommerce 전용 CSS는 일반적으로 **`css/woocommerce.css`** 또는 **`css/components/woocommerce/` 폴더 내에 별도로 관리**하는 것이 좋습니다. 이 접근 방식은 코드의 모듈성과 유지보수성을 향상시킵니다.
    * **자주 쓰는 요소/클래스:** WooCommerce의 주요 페이지나 컴포넌트와 관련된 클래스들을 파악해두면 효율적인 스타일링이 가능합니다.
        * **예시:** `.woocommerce-cart` (장바구니 페이지 전체), `.woocommerce-checkout` (결제 페이지 전체), `.woocommerce-MyAccount-navigation` (마이 어카운트 메뉴), `.woocommerce-product-attributes` (제품 속성 테이블) 등.
    * **설정값/패턴:** 공통적으로 사용되는 스타일 패턴(예: 박스 모델, 버튼, 폼, 표, 내비게이션, 탭 등)은 별도의 섹션으로 구분하여 관리하고, 주석을 활용해 가독성을 높입니다.
    * **정리 예시:**
        ```css
        /* WooCommerce Buttons */
        .woocommerce .button, .woocommerce .woocommerce-button {
            background-color: #007bff;
            color: #fff;
            padding: 10px 20px;
            border-radius: 5px;
            /* ... 기타 버튼 스타일 ... */
        }

        /* WooCommerce Cart Table */
        .woocommerce-cart table.shop_table {
            width: 100%;
            border-collapse: collapse;
            margin-bottom: 20px;
            /* ... 기타 테이블 스타일 ... */
        }

        /* WooCommerce Product Attributes Table */
        .woocommerce-product-attributes th {
            font-weight: bold;
            padding: 8px;
            text-align: left;
            /* ... 기타 속성 테이블 헤더 스타일 ... */
        }
        ```

    * **CSS 속성 정렬:** 가독성을 위해 CSS 속성을 특정 규칙에 따라 정렬하는 것을 권장합니다.
        * **예시:** 타입별로 속성을 그룹화합니다 (예: 박스 모델, 색상, 글꼴, 기타).

### **3. JavaScript: WooCommerce 인터랙션 제어**

이 섹션에서는 WooCommerce 내에서 동적인 기능과 사용자 인터랙션을 관리하기 위해 JavaScript를 어떻게 사용하는지 다룹니다.

* **WooCommerce 공식 JavaScript 네이밍 규칙:**
    * **함수:** `wc` 접두사를 사용합니다 (예: `wcFunctionName()`).
    * **클래스:** `WC` 접두사를 사용합니다 (예: `WCClassName`).
    * **이벤트/훅:** `woocommerce` 접두사를 사용하며 (예: `woocommerceEventName`), 주로 jQuery의 `trigger` 및 `on` 메서드와 함께 커스텀 이벤트에 사용됩니다.
* **실무적인 JavaScript 정리법:**
    * **파일 관리:** WooCommerce 관련 JavaScript는 일반적으로 **`js/woocommerce.js`** 또는 **`js/components/woocommerce/` 폴더 내에 별도로 관리**하는 것이 좋습니다. 이는 다른 스크립트와의 충돌을 최소화하고 유지보수를 간소화합니다.
    * **자주 쓰는 이벤트/패턴:** WooCommerce는 다양한 커스텀 이벤트를 발생시켜 특정 시점에 기능을 추가하거나 수정할 수 있도록 합니다.
        * **예시:** `added_to_cart` (상품이 장바구니에 추가될 때), `updated_cart_totals` (장바구니 합계가 업데이트될 때), `found_variation` (가변 상품의 옵션이 선택될 때) 등을 활용하여 DOM 조작, Ajax 호출, 실시간 알림 등 동적인 UI 요소를 구현합니다.
    * **정리 예시:**
        ```javascript
        // WooCommerce: Add to cart event
        jQuery(document.body).on('added_to_cart', function(event, fragments, cart_hash, $button){
            // 상품이 장바구니에 추가된 후 실행될 코드
            console.log('상품이 장바구니에 추가되었습니다!');
            // 예: 미니 카트 업데이트, 알림 표시 등
        });

        // WooCommerce: Checkout update
        jQuery(document.body).on('updated_checkout', function(){
            // 결제 페이지가 업데이트될 때 실행될 코드 (예: 배송 방법 변경 시)
            console.log('결제 정보가 업데이트되었습니다.');
            // 예: 특정 필드 값 변경, UI 조정 등
        });
        ```

    * **jQuery 의존성:** WooCommerce의 내장 JavaScript 스크립트는 주로 **jQuery를 사용**합니다. 따라서 커스텀 스크립트도 jQuery를 활용하는 것이 일반적으로 편리합니다. 최신 개발 트렌드에 따라 바닐라 JS 또는 다른 프레임워크를 사용해야 하는 경우, 기존 WooCommerce 스크립트와의 호환성을 고려한 추가적인 작업이 필요할 수 있습니다.

### **4. PHP: WooCommerce 백엔드 및 템플릿 제어**

이 섹션에서는 WooCommerce의 핵심 기능, 데이터 처리, 그리고 템플릿 구조를 제어하기 위해 PHP를 어떻게 사용하는지 다룹니다.

* **WooCommerce 공식 PHP 네이밍 규칙:**
    * **함수:** `wc_` 접두사를 사용합니다 (예: `wc_get_product()`).
    * **클래스:** `WC_` 접두사를 사용합니다 (예: `WC_Product`).
    * **훅 (액션/필터):** `woocommerce_` 접두사를 사용합니다 (예: `woocommerce_before_cart`).
* **실무적인 PHP 정리법:**
    * **파일 관리:** 테마(또는 자식 테마)의 `functions.php` 파일에 직접 코드를 추가하기보다, **`inc/woocommerce.php`와 같은 별도의 파일 또는 폴더에 WooCommerce 관련 함수와 훅을 분리하여 관리**하는 것이 유지보수성을 높이는 좋은 방법입니다. 이 파일은 `functions.php`에서 `require` 또는 `include`합니다.
    * **자주 쓰는 훅/필터:** WooCommerce는 방대한 액션 훅(`add_action()`)과 필터 훅(`add_filter()`)을 제공하여 핵심 코드를 직접 수정하지 않고도 기능을 확장하거나 변경할 수 있도록 합니다.
        * **예시:**
            * `woocommerce_before_cart`: 장바구니 페이지 내용 시작 전.
            * `woocommerce_after_checkout_form`: 결제 폼 종료 후.
            * `woocommerce_account_menu_items`: 마이 어카운트 메뉴 항목 변경.
            * `woocommerce_product_tabs`: 제품 상세 페이지 탭 추가/제거.
    * **정리 예시:**
        ```php
        <?php
        // WooCommerce: 마이 어카운트 메뉴 커스터마이즈
        // 메뉴 항목을 추가하거나 순서를 변경할 때 사용
        add_filter('woocommerce_account_menu_items', function($items) {
            $items['custom-link'] = '내 커스텀 링크'; // 새 메뉴 항목 추가
            // $items['orders'] = '내 주문 내역'; // 기존 항목 텍스트 변경
            return $items;
        });

        // WooCommerce: 카트 페이지에 커스텀 메시지 추가
        // 장바구니 테이블 상단에 특정 메시지를 표시할 때 사용
        add_action('woocommerce_before_cart', function() {
            if (WC()->cart->is_empty()) {
                echo '<p class="woocommerce-info">장바구니가 비어 있습니다.</p>';
            } else {
                echo '<p class="custom-cart-message">지금 구매하시면 무료 배송!</p>';
            }
        });

        // WooCommerce: 제품 가격 표시 형식 변경 (필터 예시)
        add_filter('woocommerce_price_format', function($format, $currency_pos) {
            // 예를 들어, 가격 앞에 '가격: ' 이라는 텍스트를 붙이려면
            return '가격: %1$s%2$s'; // %1$s는 통화 기호, %2$s는 가격
        }, 10, 2);
        ```

    * **템플릿 오버라이드:** HTML 섹션에서 언급했듯이, WooCommerce는 `.php` 템플릿 파일을 통해 프론트엔드 HTML을 렌더링합니다. 테마 내 `woocommerce/` 폴더에 원본 템플릿 파일과 동일한 경로로 파일을 복사하여 수정하면, 플러그인 업데이트 시에도 변경사항이 유지됩니다.

### **5. 기타 실무 고려사항: 버전 관리 및 안정성**

이 섹션은 WooCommerce 개발 시 코드의 안정성과 유지보수성을 높이기 위한 중요한 추가적인 고려사항입니다.

* **자식 테마(Child Theme)의 중요성:**
    * 앞서 언급했듯이, **WooCommerce 템플릿 파일을 수정하거나 `functions.php`에 커스텀 코드를 추가할 때는 반드시 자식 테마를 사용**해야 합니다. 부모 테마를 직접 수정하면, 테마 업데이트 시 모든 변경사항이 덮어쓰여 사라질 수 있습니다.
    * 자식 테마는 부모 테마의 기능을 안전하게 상속받으면서도, 자신만의 스타일과 기능을 추가할 수 있는 환경을 제공합니다.
* **버전 관리 시스템 (Git 등):**
    * **Git과 같은 버전 관리 시스템을 활용**하는 것이 필수적입니다.
    * 커스터마이징된 코드, 테마 파일, 플러그인 설정 등을 Git으로 관리하면, 변경 이력을 추적하고, 팀원들과 협업하며, 문제가 발생했을 때 이전 버전으로 쉽게 되돌릴 수 있습니다.
* **WooCommerce 업데이트 대응:**
    * WooCommerce는 기능 개선 및 보안 취약점 패치를 위해 주기적으로 업데이트됩니다. 업데이트 전에 항상 **백업**을 수행하고, 개발 환경에서 먼저 테스트하여 커스터마이징된 코드나 플러그인과의 충돌 여부를 확인해야 합니다.
    * 템플릿 오버라이드 시에는 WooCommerce 업데이트로 인해 원본 템플릿 파일에 변경사항이 생겼는지 확인하고, 필요한 경우 자신의 오버라이드 파일을 업데이트된 내용에 맞춰 수정해야 합니다. (이를 'template outdated' 경고로 확인할 수 있습니다.)
