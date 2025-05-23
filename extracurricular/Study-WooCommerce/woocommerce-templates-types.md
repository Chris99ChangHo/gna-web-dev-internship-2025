# Understanding WooCommerce + Elementor Templates: Archive vs. Single Product

This document clarifies the differences between Archive Templates and Single Product Templates, when to use each, and summarizes key aspects of WooCommerce + Elementor templating.

## 1. Differences Between Archive Template and Single Product Template

### Archive (Product Archive) Template

* **When to Use?**
    * Used for pages that display multiple products at once in a list or grid format.
    * Examples include Product Category pages, Product Tag pages, the main Shop page, etc.
* **Examples:**
    * `/shop`
    * `/product-category/drinks`
    * `/product-tag/fruit`
* **What to Customize in the Template:**
    * Product card design (thumbnail, name, price, button, etc.)
    * Product list/grid layout (number of columns, spacing, hover effects, etc.)
    * Top section elements like category title, description, filters, banners, etc.

### Single Product Template

* **When to Use?**
    * Used for individual product detail pages.
* **Examples:**
    * `/product/green-grape-ade`
    * `/product/mango-syrup`
* **What to Customize in the Template:**
    * Product image(s), product name, price, description, options, add-to-cart button.
    * Tabs for detailed description/reviews, related products section.
    * The entire layout of the product detail page.

## 2. Key Summary of WooCommerce + Elementor Templating

Using Elementor Pro's Theme Builder allows you to create "templates" for WooCommerce product category (archive) pages and single product detail pages, applying desired layouts and designs consistently across relevant content.

### Archive Template

* **Application:** Applied to pages where multiple products are exposed at once (e.g., category pages, tag pages, main shop page).
* **Customization:** Customize product card designs, grid/list layouts, filters, banners, and more.

### Single Product Template

* **Application:** Applied to the detailed page of each individual product.
* **Customization:** Freely arrange product images, descriptions, options, add-to-cart buttons, detail/review tabs, related products, and more.

### Where to Create Templates

* WordPress Admin Dashboard > `Templates` > `Theme Builder`
    * `Product Archive` (for archive pages)
    * `Single Product` (for single product pages)

### How to Apply Templates

* After creating a template, you can define its application scope using "Display Conditions."
* You can set conditions to apply to all products/categories, specific categories/products, and so on.

## 3. At a Glance (Table)

| Template Type     | Applied Page Example      | When/What for?                                     |
| :---------------- | :------------------------ | :------------------------------------------------- |
| Archive           | `/shop`, `/product-category/...` | For customizing pages that display multiple products at once |
| Single Product    | `/product/product-name`   | For customizing individual product detail pages' design |

## 4. Conclusion / Recommendation

* If you want to change the design of your category/product listing pages → Use an **Archive Template**.
* If you want to change the design of your individual product detail pages (images, description, options, etc.) → Use a **Single Product Template**.

Both types of templates can be created separately as needed, and Elementor Pro's Theme Builder allows you to add and manage as many templates as you desire!

---

# WooCommerce + Elementor 템플릿 이해: 아카이브 vs. 싱글 상품

이 문서는 아카이브 템플릿과 싱글 상품 템플릿의 차이점, 각각 언제 사용되는지, 그리고 WooCommerce + Elementor 템플릿의 핵심 내용을 요약하여 정리합니다.

## 1. 아카이브(Archive) 템플릿과 싱글 상품(Single Product) 템플릿의 차이

### 아카이브(Archive) 템플릿

* **언제 사용?**
    * 상품 카테고리 페이지, 상품 태그 페이지, 메인 쇼핑몰(Shop) 페이지 등 여러 개의 상품이 한 번에 리스트/그리드 형태로 나오는 페이지에 사용합니다.
* **예시:**
    * `/shop`
    * `/product-category/음료`
    * `/product-tag/과일`
* **템플릿에서 주로 커스터마이즈하는 것:**
    * 상품 카드(썸네일, 이름, 가격, 버튼 등) 디자인
    * 상품 리스트/그리드 레이아웃(몇 칼럼, 간격, hover 효과 등)
    * 상단 카테고리 제목, 설명, 필터, 배너 등

### 싱글 상품(Single Product) 템플릿

* **언제 사용?**
    * 개별 상품 상세 페이지에서 사용합니다.
* **예시:**
    * `/product/green-grape-ade`
    * `/product/mango-syrup`
* **템플릿에서 주로 커스터마이즈하는 것:**
    * 상품 이미지, 상품명, 가격, 설명, 옵션, 장바구니 버튼
    * 상세설명/리뷰 탭, 관련상품 섹션
    * 상품 상세 레이아웃 전체

## 2. 지금까지 Woocommerce + Elementor 템플릿 관련 핵심 요약

Elementor Pro의 Theme Builder를 사용하면 WooCommerce의 상품 카테고리(아카이브) 페이지와 상품 상세(싱글 상품) 페이지를 각각 원하는 레이아웃/디자인으로 "템플릿"을 만들어 일괄 적용할 수 있습니다.

### 아카이브 템플릿

* **적용:** 여러 상품이 한 번에 노출되는 페이지(카테고리, 태그, 쇼핑몰 메인 등)에 적용됩니다.
* **커스터마이즈:** 상품 카드 디자인, 그리드/리스트 레이아웃, 필터/배너 등을 커스터마이즈합니다.

### 싱글 상품 템플릿

* **적용:** 각 상품의 상세 페이지에 적용됩니다.
* **커스터마이즈:** 상품 이미지, 설명, 옵션, 카트 버튼, 상세/리뷰 탭, 관련상품 등을 자유롭게 배치합니다.

### 템플릿 만드는 위치

* 워드프레스 관리자 > `Templates`(템플릿) > `Theme Builder`(테마 빌더)
    * `Product Archive`(상품 아카이브)
    * `Single Product`(싱글 상품)

### 템플릿 적용 방식

* 템플릿을 만들고 "Display Conditions"(적용 조건)에서 적용 범위를 지정할 수 있습니다.
* 전체 상품/카테고리, 특정 카테고리/상품 등 적용 범위 지정이 가능합니다.

## 3. 한눈에 정리 (표)

| 템플릿 종류           | 적용 페이지 예시                | 언제/무엇을 위해 사용?                                       |
| :------------------ | :------------------------------ | :----------------------------------------------------------- |
| 아카이브(Archive)   | `/shop`, `/product-category/...` | 여러 상품을 한 번에 보여주는 페이지 디자인 커스텀용        |
| 싱글 상품(Single Product) | `/product/상품명`               | 개별 상품 상세 페이지 디자인 커스텀용                        |

## 4. 결론 / 추천

* 카테고리/상품 리스트 페이지 디자인을 바꾸고 싶으면 → **아카이브 템플릿**을 사용하세요.
* 상품 상세페이지(이미지, 설명, 옵션 등) 디자인을 바꾸고 싶으면 → **싱글 상품 템플릿**을 사용하세요.

둘 다 필요에 따라 따로따로 만들 수 있으며, Elementor Pro Theme Builder에서 원하는 만큼 템플릿을 추가/관리할 수 있습니다!
