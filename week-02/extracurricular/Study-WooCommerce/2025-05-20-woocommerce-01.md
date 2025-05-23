# 🛒 WooCommerce Research (2025-05-20)

## ✅ What is WooCommerce?

WooCommerce is the most widely used open-source eCommerce plugin for WordPress. It allows users to create and operate online stores directly within the WordPress environment.

- **Developer**: Originally developed by WooThemes, acquired by Automattic (parent company of WordPress.com) in 2015
- **License**: Open-source (GPLv3)
- **Integration**: Designed to work seamlessly with WordPress themes and admin dashboard

---

## 🧱 Core Features

### 1. 🛍️ Product Management
- **Simple Products**: Single items without variations
- **Variable Products**: Products with multiple variations (e.g., size, color)
- **Grouped Products**: Bundles of related products
- **Virtual/Downloadable Products**: Ideal for services or digital goods

### 2. 🛒 Cart and Checkout
- Built-in cart and checkout pages
- Ajax-powered cart (quantity adjustments without page reload)
- Customizable checkout fields (via plugin or custom code)

### 3. 💳 Payment Gateways
- **Built-in**: PayPal, Stripe, Bank Transfer, Cash on Delivery
- **Extensible**: Support for additional payment methods (e.g., Toss, Kakaopay in Korea) via plugins

### 4. 🚚 Shipping Options
- Flat Rate, Free Shipping, Local Pickup
- Shipping zones and classes for flexible pricing

### 5. 🧾 Tax Configuration
- Auto tax calculation (with plugin help)
- Set tax rates and control whether prices are shown with or without tax

---

## 🌐 WooCommerce Structure & Operations at a Glance

To fully understand WooCommerce's structure and practical operational flow, here are the overall structure and essential elements organized step-by-step.

### Overall Flow to Understand WooCommerce's Structure

1.  **Product Structure Understanding**
    * **Simple Product**: A standard product without options.
    * **Variable Product**: A product with multiple options (attributes/variations) like color, size, or flavor.
        * Requires understanding product attributes and how to set prices, stock, and images per option.
    * **Product Categories/Tags**: Basic units for product classification.
        * Automatically sorts/displays products by category or tag.
2.  **Template/Page Structure**
    * **Archive Template**: The product list page for categories/tags.
        * Products are automatically classified and displayed based on specified conditions.
    * **Single Product Template**: The individual product detail page.
        * Customizable elements include product images, descriptions, options, prices, and add-to-cart buttons.
    * **Search Results Template**: Automatically displays products matching the search query.
3.  **Product Registration & Image Management**
    * When registering products, standardize image ratios/sizes beforehand (e.g., square, rectangular, as appropriate for your store).
    * Input product descriptions, options, prices, and stock levels.
4.  **Shipping & Tax Settings**
    * **Shipping**: Set up shipping zones and specify shipping methods/costs for each zone.
    * **Tax**: Configure tax policies (e.g., VAT) and specify whether prices include or exclude tax per product.
5.  **Payment Flow/Integration**
    * Use basic WooCommerce payments (test payments, WooPayments) or integrate domestic/international PG (card payment) plugins for live operations.
    * The payment flow is: Cart → Checkout → Payment → Order Completion.
6.  **Order & Customer Management**
    * **Order Management**: View order details, change statuses (e.g., pending payment, completed, in transit), and process refunds.
    * **Customer Management**: Manage member information, shipping addresses, and purchase history.
7.  **Design/Customization**
    * Customize archive/single product/search results templates using builders like Elementor.
    * Design headers, footers, banners, product cards, and refine styles/behaviors with CSS/JS.
8.  **Plugins/Extensions**
    * Extend functionality with necessary plugins for features like coupons, reviews, filters, recommended products, and sliders.
9.  **Responsiveness/Accessibility/Optimization**
    * Ensure layout, buttons, text, and images display well on mobile/tablet/PC through responsive settings.
    * Focus on accessibility (alt text, font contrast) and speed optimization.
10. **Actual Operation/Testing**
    * Conduct test orders/payments, manage orders, and check email notifications to experience the actual flow.
    * Identify and improve any issues or inconveniences.

### WooCommerce Structure Key Elements at a Glance

* Product Structure (Simple/Variable/Category/Tag)
* Template Structure (Archive/Single/Search)
* Product Image/Option/Description Management
* Shipping/Tax/Payment Settings
* Order/Customer Management
* Design/Customization (CSS/JS/Plugins)
* Responsiveness/Accessibility/Optimization
* Actual Operation/Testing

By following this flow step-by-step, you can gain a comprehensive understanding of WooCommerce's overall structure and practical operational methods.

---

# 🛒 WooCommerce 리서치 (2025-05-20)

## ✅ WooCommerce란?

WooCommerce는 WordPress에서 가장 널리 사용되는 오픈소스 전자상거래 플러그인입니다. 사용자는 WordPress 환경 내에서 온라인 쇼핑몰을 직접 구축하고 운영할 수 있습니다.

- **개발사**: WooThemes가 처음 개발하였으며, 2015년에 WordPress.com의 모회사인 Automattic에 인수됨
- **라이선스**: 오픈소스(GPLv3)
- **통합성**: WordPress 테마 및 관리자 대시보드와 완벽하게 연동되도록 설계됨

---

## 🧱 핵심 기능

### 1. 🛍️ 상품 관리
- **단순 상품(Simple Product)**: 옵션이 없는 단일 상품
- **가변 상품(Variable Product)**: 색상, 사이즈 등 다양한 옵션이 있는 상품
- **그룹 상품(Grouped Product)**: 관련된 여러 상품을 묶은 형태
- **가상/디지털 상품(Virtual/Downloadable)**: 서비스 또는 디지털 콘텐츠 판매에 적합

### 2. 🛒 장바구니 및 결제
- 기본적으로 제공되는 장바구니(Cart) 및 결제(Checkout) 페이지
- Ajax 기반 장바구니 기능 (페이지 새로고침 없이 수량 변경 가능)
- 결제 단계 필드 커스터마이징 가능 (플러그인 또는 코드 활용)

### 3. 💳 결제 수단
- **기본 내장**: PayPal, Stripe, 계좌이체, 현장결제 등
- **확장 가능**: 다양한 결제 게이트웨이 플러그인 지원 (예: Toss, 카카오페이 등 국내 결제 모듈도 설치 가능)

### 4. 🚚 배송 옵션
- 고정 배송비, 무료 배송, 매장 수령 등 기본 옵션 제공
- 배송 지역(Shipping Zones) 및 배송 클래스 설정 가능

### 5. 🧾 세금 설정
- 자동 세금 계산 가능 (추가 플러그인 설치 시)
- 세금 클래스 설정, 가격에 세금 포함/제외 여부 선택 가능

---

## 🌐 WooCommerce 구조 및 운영 흐름 한눈에 보기

WooCommerce의 구조와 실전 운영 흐름을 한 번에 이해할 수 있도록 전체적인 구조와 꼭 알아야 할 핵심 요소를 단계별로 정리해 드릴게요.

### WooCommerce 구조를 이해하기 위한 전체적인 흐름

1.  **상품 구조 이해**
    * **단일 상품(Simple Product)**: 옵션이 없는 일반 상품.
    * **가변 상품(Variable Product)**: 색상, 사이즈, 맛 등 여러 옵션(속성/Variations)이 있는 상품.
        * 상품 속성(Attributes)과 옵션별 가격/재고/이미지 설정법 이해 필요.
    * **상품 카테고리/태그**: 상품을 분류하는 기본 단위.
        * 카테고리별, 태그별로 상품을 자동 정렬/출력.
2.  **템플릿/페이지 구조**
    * **아카이브(Archive) 템플릿**: 카테고리/태그별 상품 리스트 페이지.
        * 조건만 지정하면 해당 카테고리 상품이 자동으로 분류되어 보여짐.
    * **싱글 상품(Single Product) 템플릿**: 개별 상품 상세 페이지.
        * 상품 이미지, 설명, 옵션, 가격, 장바구니 등 커스터마이즈.
    * **검색 결과(Search Results) 템플릿**: 검색어에 맞는 상품만 자동으로 출력.
3.  **상품 등록 및 이미지 관리**
    * 상품 등록 시 이미지 비율/크기를 미리 통일해서 업로드 (정사각형, 직사각형 등 쇼핑몰에 맞게).
    * 상품 설명, 옵션, 가격, 재고 등 입력.
4.  **배송 및 세금 설정**
    * **배송(Shipping)**: 배송 구역(Zone) 설정. 각 구역별 배송 방법/배송비 지정.
    * **세금(Tax)**: 부가세 등 세금 정책 설정. 상품별 세금 포함/별도 여부 지정.
5.  **결제 플로우/연동**
    * WooCommerce 기본 결제(테스트 결제, WooPayments 등) 또는 실제 운영 시 국내/해외 PG(카드결제) 플러그인 연동.
    * 결제 흐름: 장바구니 → 주문서 작성 → 결제 → 주문 완료.
6.  **주문 및 고객 관리**
    * **주문 관리**: 주문 내역 확인, 상태 변경(입금대기, 결제완료, 배송중 등), 환불 처리.
    * **고객 관리**: 회원 정보, 배송지, 구매 이력 등 관리.
7.  **디자인/커스터마이즈**
    * Elementor 등 빌더로 아카이브/싱글/검색 결과 등 템플릿 커스터마이즈.
    * 헤더, 푸터, 배너, 상품 카드 등 디자인 및 CSS/JS로 세부 스타일, 동작 보완.
8.  **플러그인/확장 기능**
    * 쿠폰, 리뷰, 필터, 추천상품, 슬라이더 등 필요한 기능은 플러그인으로 확장.
9.  **반응형/접근성/최적화**
    * 모바일/태블릿/PC에서 레이아웃, 버튼, 텍스트, 이미지가 잘 보이도록 반응형 세팅.
    * 접근성(alt 텍스트, 폰트 대비 등), 속도 최적화.
10. **실제 운영/테스트**
    * 테스트 주문/결제, 주문 관리, 이메일 알림 등 실제 플로우를 경험해보고 문제점/불편한 점을 개선.

### 한눈에 보는 WooCommerce 구조 핵심

* 상품 구조(단일/가변/카테고리/태그)
* 템플릿 구조(아카이브/싱글/검색)
* 상품 이미지/옵션/설명 관리
* 배송/세금/결제 설정
* 주문/고객 관리
* 디자인/커스터마이즈(CSS/JS/플러그인)
* 반응형/접근성/최적화
* 실제 운영/테스트

이 흐름을 따라가며 하나씩 익히면 WooCommerce의 전체 구조와 실무 운영 방식을 한 번에 이해할 수 있습니다!
