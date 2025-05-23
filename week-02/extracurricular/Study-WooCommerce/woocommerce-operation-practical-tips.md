# 🛒 WooCommerce Operation: Practical Tips & Best Practices

This document summarizes key practical tips and best practices for managing a WooCommerce site, covering essential aspects from content structure to payment and inventory management.

## 1. ⚙️ Understanding Product/Post Structure & Automated Templates

* **Automated Classification & Output:**
    * By accurately assigning categories and tags when registering products or posts, you can leverage Elementor Theme Builder's Display Conditions.
    * Templates can be automatically applied and content classified/displayed based solely on these template conditions.

## 2. 🖼️ Image & Card Layout Best Practices

* **Consistent Image Ratios:**
    * The most reliable way to prevent image distortion in layouts is to ensure consistent aspect ratios and sizes for product images *before* uploading them.
    * **Recommendation:** Utilize the Image widget instead of background images. CSS properties like `object-fit: cover` or `aspect-ratio` can be used for responsive scaling.
* **Card Overlay Layouts:**
    * For card-style overlays, a practical approach involves placing Heading and Button widgets on top of a Container/Column background image.
    * Design elements like `min-height`, `align-items`, and `background overlay` are crucial for a polished look.
    * **Note:** If the original image has rounded corners, it's essential to precisely match the container's aspect ratio.

## 3. 📦 Inventory Management Tips

* **Understanding Stock Input:**
    * WooCommerce's stock field requires direct input of the "current remaining quantity."
    * **Crucial:** When receiving new stock, do *not* add to the existing number; instead, directly enter the *final total quantity* in the field (e.g., if you had 10 and received 50, enter '60', not '+50').
* **Preventing Negative Stock:**
    * It's generally recommended to disable the "Allow orders even if out of stock" option under WooCommerce > Settings > Products > Inventory to prevent stock levels from going into negative.
* **Bulk Stock Management (Optional):**
    * For sites with many products or frequent stock movements, using plugins like **Stock Manager for WooCommerce (free)** is highly recommended for efficiency.
        * Allows managing stock, price, and status for multiple products/variations on a single screen, similar to an Excel sheet.
        * Supports CSV export/import for bulk stock updates.
    * **Developer Insight:** Understanding how these plugins manipulate WooCommerce DB (especially `wp_postmeta` table for keys like `_stock`, `_manage_stock`) is beneficial for custom development.

## 4. 💳 Payment & Order Management Workflow

* **Payment Gateway Integration:**
    * Install and set up payment gateway plugins like Stripe in **test mode** for practical experience.
* **Workflow Practice:**
    * Repeatedly check the practical flow: changing order status, processing refunds, checking email notifications, and verifying automatic stock reduction after payment.

## 5. 🔑 Login/Guest Order & UX Considerations

* **Conditional Menu Display:**
    * The site menu (e.g., "Login/Register" vs. "My Account/Logout") should dynamically change based on the user's login status. This often requires advanced Elementor addons or WordPress menu-specific plugins.
* **Guest Checkout Functionality:**
    * Guest purchases are only possible if the "Allow orders without an account" option is enabled in WooCommerce > Settings > Accounts & Privacy.

## 6. 🚧 Site Access Restrictions (Pre-Launch)

* **Understanding Restrictions:**
    * Before a site officially launches, non-member access may be restricted by plugins, theme settings, or hosting configurations.
* **Testing Recommendation:**
    * It's advisable to disable these restrictions only immediately before launch or during specific external testing periods to verify site functionality for all users.

---

# 🛒 WooCommerce 운영: 실무 팁 및 모범 사례

이 문서는 WooCommerce 사이트를 운영하는 데 필요한 핵심 실무 팁과 모범 사례를 콘텐츠 구조부터 결제 및 재고 관리까지 필수적인 측면들을 다룹니다.

## 1. ⚙️ 상품/포스트 구조 및 템플릿 자동화 이해

* **자동 분류 및 출력:**
    * 상품 또는 포스트 등록 시 카테고리와 태그만 정확히 지정하면, Elementor Theme Builder의 Display Condition을 활용할 수 있습니다.
    * 오직 템플릿 조건에 따라 콘텐츠가 자동으로 분류되고 출력될 수 있습니다.

## 2. 🖼️ 이미지 및 카드 레이아웃 모범 사례

* **일관된 이미지 비율:**
    * 레이아웃에서 이미지 찌그러짐을 방지하는 가장 확실한 방법은 상품 이미지를 업로드하기 *전에* 일관된 비율과 크기로 맞추는 것입니다.
    * **권장 사항:** 배경 이미지 대신 Image 위젯을 사용하는 것을 권장합니다. 반응형 스케일링을 위해 `object-fit: cover` 또는 `aspect-ratio`와 같은 CSS 속성을 활용할 수 있습니다.
* **카드형 오버레이 레이아웃:**
    * 카드 스타일 오버레이의 경우, 컨테이너/컬럼의 배경 이미지 위에 Heading 및 Button 위젯을 배치하는 것이 실무적인 접근 방식입니다.
    * `min-height`, `align-items`, `background overlay`와 같은 디자인 요소는 깔끔한 시각적 효과를 위해 중요합니다.
    * **참고:** 원본 이미지에 둥근 모서리가 있다면 컨테이너의 비율과 정확하게 일치시키는 것이 필수적입니다.

## 3. 📦 재고 관리 팁

* **재고 입력 방식 이해:**
    * WooCommerce의 재고 필드는 "현재 남은 수량"을 직접 입력하는 방식입니다.
    * **매우 중요:** 신규 입고 시 기존 수량에 더하는 방식이 아니라, 필드에 *최종 총 수량*을 직접 입력해야 합니다 (예: 기존 10개에 50개가 입고되었다면 '60'을 입력하고 '+50'이 아님).
* **재고 음수 방지:**
    * WooCommerce > 설정 > 상품 > 재고에서 "재고 없음 시에도 주문 허용" 옵션을 비활성화하여 재고 수량이 음수로 내려가는 것을 방지하는 것이 일반적입니다.
* **대량 재고 관리 (선택 사항):**
    * 상품 수가 많거나 입출고가 잦은 사이트의 경우, 효율성을 위해 **Stock Manager for WooCommerce (무료)**와 같은 플러그인 사용을 강력히 권장합니다.
        * 단일 화면에서 여러 상품/옵션의 재고, 가격, 상태를 엑셀처럼 관리하고 대량 수정이 가능합니다.
        * CSV 내보내기/가져오기 기능을 통해 재고 데이터를 일괄 업데이트할 수 있습니다.
    * **개발자 인사이트:** 이러한 플러그인들이 WooCommerce DB(특히 `wp_postmeta` 테이블의 `_stock`, `_manage_stock` 등)의 재고 관련 메타 키를 어떻게 조작하는지 이해하는 것은 사용자 정의 개발 시 유용합니다.

## 4. 💳 결제 및 주문 관리 워크플로우

* **결제 게이트웨이 연동:**
    * Stripe와 같은 결제 게이트웨이 플러그인을 설치하고 **테스트 모드**에서 설정하여 실질적인 경험을 쌓습니다.
* **워크플로우 실습:**
    * 주문 상태 변경, 환불 처리, 이메일 알림 확인, 결제 후 재고 자동 감소 등 실무 플로우를 반복적으로 점검합니다.

## 5. 🔑 로그인/비회원 주문 및 UX 고려 사항

* **조건부 메뉴 표시:**
    * 사이트 메뉴 (예: "로그인/회원가입" vs. "내 계정/로그아웃")는 사용자 로그인 상태에 따라 동적으로 변경되어야 합니다. 이는 종종 고급 Elementor 애드온이나 워드프레스 메뉴 전용 플러그인을 필요로 합니다.
* **비회원 주문 기능:**
    * 비회원 구매는 WooCommerce > 설정 > 계정 및 개인정보 보호에서 "계정 없이 주문 허용" 옵션이 켜져 있어야만 가능합니다.

## 6. 🚧 사이트 접근 제한 (출시 전)

* **제한 사항 이해:**
    * 사이트가 공식적으로 출시되기 전에는 플러그인, 테마 설정 또는 호스팅 구성으로 인해 비회원 접근이 제한될 수 있습니다.
* **테스트 권장 사항:**
    * 모든 사용자를 위한 사이트 기능을 검증하려면, 출시 직전이나 특정 외부 테스트 기간에만 이러한 제한을 해제하는 것이 좋습니다.
