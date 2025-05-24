# 📝 Week 02 Reflection (2025.05.19 ~ 05.23)

This second week of my internship offered deep insights into practical web development and operations. I moved between a **real client project (Dentalcore)** and **practice projects (Oppa Painting, gangnamsyrup.com.au)**. I significantly enhanced my skills building and optimizing websites with WordPress, Elementor, and WooCommerce.

## ✅ Key Tasks This Week

* **📌 Applied Client Feedback**: Interpreted and applied client feedback for content updates and restructuring on the Dentalcore site.  
* **📌 Managed & Optimized Multiple Websites**: Progressed Oppa Painting's layout and content, focusing on template reuse and responsive design.  
* **📌 Deepened WooCommerce E-commerce Skills**: Built core e-commerce functionality for `gangnamsyrup.com.au`, including Stripe payment integration and various operational scenarios.  
* **📌 Enhanced Functional Testing & Troubleshooting**: Documented errors for Airhome's new features and resolved Elementor/WooCommerce issues.  

## 🧠 What I Learned

* **Elementor Theme Builder Mastery**: Practicing dynamic creation of product/post archive and single page templates, and applying them conditionally, helped me grasp Theme Builder's core structure. I especially appreciated the **convenience of archive templates, eliminating the need for individual page creation**.
* **WooCommerce Payment Flow & Stripe Integration**: Hands-on experience with Stripe Payment Gateway in test mode provided a comprehensive understanding of the end-to-end payment process, from cart to final order management. This highlighted the critical role of robust payment system integration in e-commerce operations.
* **Understanding Diverse Order Scenarios**: Practicing various e-commerce scenarios—coupon application, shipping changes, stock reduction, and manual order status updates—deepened my understanding of WooCommerce's flexible order management capabilities.
* **Mobile Responsive Design Best Practices**: Continuous practice adapting layouts for mobile, including headers, icons, and cards, and using Elementor's show/hide features for device-specific menus, reinforced that responsive layout adjustment is an ongoing skill.
* **Criticality of Image Optimization for E-commerce**: I identified the impact of inconsistent product image ratios on layout integrity and the limitations of WordPress's default customizer. Through research and validation from senior developers/designers, I confirmed that **pre-resizing and standardizing original images with external tools like Canva is the most reliable method** for stable responsive layouts. Image handling is consistently a complex aspect of web development.

## 🔧 Technical Problem-Solving Experience

* **Responsive Two-Column Layout (Image vs. Background Image)**
    * **Problem**: When creating a two-column section with an image on one side (often as a background with `cover`) and text on the other, the image often stretched, cropped incorrectly, or broke its aspect ratio on mobile/tablet. Relying solely on padding for text positioning also made responsive optimization challenging.
    * **Cause**: Using background images with `object-fit: cover` within container elements makes controlling their display ratio and alignment across different viewports difficult. Padding alone is insufficient for robust responsive alignment.
    * **Solution**:
        * **Preferred "Image Widget" over "Background Image"**: For explicit image content, embedding an "Image Widget" and controlling its size/ratio using `object-fit: cover; width: 100%; height: 100%;` within its container proved more reliable.
        * **Utilized Elementor's Flexbox Containers**: I actively employed Flexbox properties (`align-items`, `justify-content`, `gap`) within containers for precise vertical/horizontal centering and automatic spacing, minimizing reliance on fixed padding/margins.
        * **Pre-sized Images**: Emphasized pre-processing and uploading images with consistent aspect ratios using tools like Canva/Photoshop to ensure predictable display across devices.

## 💡 Reflections

* **Efficiency Through Template Reuse**: Reusing existing templates and components is crucial for significantly reducing development time and maintaining consistency across multiple client sites or projects.
* **Real-world Challenges in Responsive Design**: Beyond simple width adjustments, I experienced the critical importance of fine-tuning responsive layouts. This included flexible container element alignment, adapting to specific device breakpoints (e.g., iPad), and maintaining image aspect ratios. My hands-on experience showed that **using "Image Widgets + Flexbox" for responsive two-column layouts is far more stable** than relying on background images.
* **E-commerce Development as a Core Skill**: I realized **e-commerce functionality constitutes a significant portion of practical web development**, especially for sites beyond simple informational posters. Deeply learning and practicing WooCommerce is essential for my progression as a full-stack developer, and I now see the potential to create truly sophisticated e-commerce websites with continued practice.
* **Interplay of Design and Development**: Translating client design requirements into code, I found that **design elements are surprisingly subjective and can introduce unpredictable variables**. This experience underscored that **design sensibility and robust structural design capabilities are as critical as technical implementation for a full-stack developer**. Cultivating a strong intuition for design-conscious structural design will further solidify my potential as an independent full-stack developer.
* **Continuous Learning Imperative**: Despite two weeks of GUI-based web development, I realize there's still a vast amount to learn. Beyond additional coding knowledge, comprehensive understanding of functional testing, front-end/back-end principles, and payment system flows is crucial. I actively research and organize these areas to further my learning journey.

## 🌱 Points of Improvement & Next Week's Goals

* **Elementor Widget Limitations & Customization Necessity**: While Elementor widgets are powerful, I experienced their **limitations in fully meeting all design and functional requirements** due to Pro-only features or changes over time (deletion, merging, becoming free). Customization offers an alternative, but it's not a panacea. I realized the importance of **understanding widget limitations and finding appropriate points for custom development**.
* **Incomplete Full Page Flow for gangnamsyrup.com.au**: It's a missed opportunity that I couldn't complete the full page flow for the `gangnamsyrup.com.au` practice project due to the large volume of products/posts.
* **Guest Checkout Testing Pending**: The inability to complete guest checkout testing due to development environment limitations is also a task to address next week.

In Week 3, I'll focus on addressing these areas and deepening my learning:

* **Image Standardization and Application**: I'll use external tools like Canva to **standardize product image ratios and sizes**, then apply them to `gangnamsyrup.com.au`. This will let me directly observe their impact on page layouts and truly grasp the **practical importance of image optimization**.
* **Advanced Mobile/Tablet Optimization**: Beyond basic responsive settings, I aim to develop an intuition for **designing layouts with mobile/tablet optimization in mind from the structural design phase**, ensuring a refined layout across various devices. This involves deepening my understanding of Elementor's advanced responsive features and Flexbox utilization.
* **Complex Header Layout Implementation & Deeper WooCommerce Features**: I'll attempt to implement complex header layouts to enhance my proficiency in Elementor and CSS. I'll also delve deeper into WooCommerce's advanced settings and conditional display features (e.g., dynamic menu changes based on login status) to achieve a more complete web development skill set.
* **Thorough Guest Checkout Flow Practice**: Once the environment permits, I'll **thoroughly test all payment scenarios, including guest checkout flows**, preparing for actual service operation.
* **Strengthening Site Structure Design Capability**: I'll cultivate the intuition to **pre-consider which site structure (Full Width/Boxed) is appropriate** before starting development, solidifying the design phase.

---

# 📝 2주차 회고 (2025.05.19 ~ 05.23)

이번 2주차 인턴십 기간 동안, 저는 **실제 클라이언트 프로젝트(Dentalcore)**와 **실습 프로젝트(Oppa Painting, gangnamsyrup.com.au)**를 오가며 웹 개발의 실질적인 측면과 운영 노하우를 깊이 이해했습니다. WordPress, Elementor, 그리고 WooCommerce를 활용한 웹사이트 구축 및 최적화 과정에서 많은 것을 배우고 적용하며 역량을 한층 더 강화했습니다.

## ✅ 이번 주 주요 작업

* **📌 클라이언트 프로젝트 피드백 반영**: Dentalcore 사이트의 콘텐츠와 구조를 조정하며 실무적인 피드백 반영 경험을 쌓았습니다.  
* **📌 다수 웹사이트 레이아웃 및 콘텐츠 최적화**: Oppa Painting 실습 프로젝트의 기획부터 완성까지 진행하며 템플릿 재사용과 반응형 디자인 감각을 익혔습니다.  
* **📌 WooCommerce 이커머스 기능 심화 실습**: `gangnamsyrup.com.au` 실습 프로젝트를 통해 이커머스 핵심 기능을 구현하고, Stripe 연동 결제 및 다양한 운영 시나리오를 경험했습니다.  
* **📌 기능 테스트 및 실무적 문제 해결**: Airhome 기능 테스트를 진행하며 체계적인 에러 리포트 작성법을 익혔고, Elementor/WooCommerce 관련 여러 이슈들을 해결하며 Troubleshooting 역량을 강화했습니다.  

## 🧠 배운 핵심 개념

* **Elementor Theme Builder 활용**: 상품 및 포스트의 아카이브(목록) 및 싱글(상세) 페이지 템플릿을 동적으로 생성하고, Display Condition을 통해 조건부 적용하는 방법을 실습하며 Elementor Theme Builder의 핵심 구조를 이해했습니다. 특히, **개별 페이지를 일일이 생성하지 않아도 되는 아카이브 템플릿의 편리함**을 체감했습니다.
* **WooCommerce 결제 흐름 실습 (Stripe 연동)**: Stripe Payment Gateway 플러그인을 테스트 모드로 설정하고, 장바구니 담기부터 실제 테스트 카드 결제, 주문 완료 및 관리자 페이지에서의 주문 관리까지의 엔드투엔드(End-to-End) 결제 흐름을 직접 경험했습니다. 이를 통해 결제 시스템 연동 및 운영의 중요성을 체감했습니다.
* **다양한 주문 시나리오 이해**: 쿠폰 적용, 배송 주소 변경, 재고 자동 감소, 관리자 페이지에서의 주문 상태 변경(예: 보류, 처리 중, 완료, 환불) 등 실제 이커머스 운영에서 발생할 수 있는 다양한 주문 시나리오를 실습하며 WooCommerce의 유연한 주문 관리 기능을 학습했습니다.
* **모바일 반응형 레이아웃 실습**: 모바일 환경에 맞는 헤더, 아이콘, 카드 레이아웃을 직접 조정하고 Elementor의 표시/숨김 기능을 활용하여 기기별 최적화된 메뉴를 구성하는 실무적인 반응형 디자인 기법을 지속적으로 실습했습니다. 이를 통해 반응형 레이아웃 조정이 꾸준한 연습을 통해 발전하는 영역임을 이해했습니다.
* **이커머스 이미지 최적화의 중요성**: 다운로드된 상품 이미지들의 일관성 부족이 레이아웃에 미치는 영향을 파악하고, 워드프레스 기본 커스터마이즈 기능의 한계를 인지했습니다. 조사를 통해 선임 개발자 및 디자이너로부터 이미지 처리가 항상 까다로운 부분이며, Canva와 같은 외부 툴을 통한 원본 이미지의 사전 리사이징 및 비율 통일이 반응형 레이아웃의 안정성을 위한 가장 확실한 방법이라는 점을 확인했습니다.

## 🔧 기술적 문제 해결 경험

* **반응형 2단 레이아웃 (이미지 vs. 배경 이미지)**
    * **문제**: 2단 섹션에서 한쪽에 이미지를 (종종 배경으로 `cover` 설정하여) 다른 쪽 텍스트와 함께 배치할 때, 모바일/태블릿에서 이미지가 찌그러지거나, 잘못 잘리거나, 비율이 깨지는 현상이 자주 발생했습니다. 텍스트 위치를 오직 패딩에만 의존하는 방식 또한 반응형 최적화를 매우 어렵게 만들었습니다.
    * **원인**: 컨테이너 내에서 `object-fit: cover`를 사용하는 배경 이미지는 다양한 뷰포트에서 비율 및 정렬 제어가 어렵습니다. 또한, 견고한 반응형 정렬에는 패딩만으로는 한계가 있습니다.
    * **해결**:
        * **"배경 이미지" 대신 "이미지 위젯" 선호**: 명시적인 이미지 콘텐츠의 경우, "이미지 위젯"을 직접 삽입하고, 컨테이너 내에서 `object-fit: cover; width: 100%; height: 100%;` 등으로 크기와 비율을 제어하는 것이 훨씬 안정적임을 확인했습니다.
        * **Elementor의 Flexbox 컨테이너 적극 활용**: 컨테이너 내에서 `align-items`, `justify-content`, `gap` 등 Flexbox 속성을 적극 활용하여 정확한 수직/수평 중앙 정렬과 자동 간격 조절을 구현했습니다. 고정된 패딩/마진에 대한 의존도를 최소화했습니다.
        * **이미지 사전 크기 조정**: Canva/Photoshop과 같은 도구를 사용하여 일관된 비율의 이미지를 사전 처리하고 업로드하는 것이 디바이스 간 예측 가능한 이미지 표시를 보장함을 강조했습니다.

## 💡 느낀 점

* **템플릿 재사용과 효율성**: 다수 클라이언트 사이트나 프로젝트를 관리할 때, 기존 템플릿과 컴포넌트의 재사용이 개발 시간을 크게 단축시키고 전체적인 일관성을 유지하는 데 핵심적임을 깨달았습니다.
* **반응형 디자인의 실질적 도전**: 단순한 너비 조정이 아닌, 컨테이너 내 요소의 반응형 정렬, 특정 디바이스 브레이크포인트(예: iPad) 대응, 그리고 이미지의 비율 유지 등 세밀한 조정의 중요성을 체감했습니다. 저의 경험을 통해 **"배경 이미지"보다는 "이미지 위젯 + Flexbox"를 활용한 반응형 2단 레이아웃 구성이 훨씬 안정적**이라는 실무적 노하우를 습득했습니다.
* **이커머스 개발의 중요성과 잠재력**: 단순히 정보를 전달하는 웹사이트가 아닌 이상, **이커머스 기능이 웹 개발 실무의 상당 부분을 차지**한다는 것을 절실히 깨달았습니다. WooCommerce를 깊이 있게 학습하고 실습하는 것이 풀스택 개발자로 나아가는 데 필수적이며, 앞으로 더 연습하다 보면 정말 세련된 이커머스 웹사이트를 직접 구축할 수 있을 것이라는 가능성을 보았습니다.
* **디자인과 개발의 상호작용 및 주관성**: 클라이언트의 요구사항을 개발로 구현하는 과정에서, **디자인적 요소가 생각보다 주관적이고 때로는 예측 불가능한 변수로 작용할 수 있음**을 체감했습니다. 이는 기술적 구현만큼이나 **디자인 감각과 이를 뒷받침하는 견고한 구조 설계 능력이 풀스택 개발자에게 필수적인 역량**임을 일깨워주었습니다. 향후 디자인적 요소를 고려한 견고한 구조 설계 감각을 함양한다면, **독립적인 1인 풀스택 개발자로서의 성장 가능성**을 더욱 확고히 할 수 있다는 확신을 얻었습니다.
* **끝없는 학습의 필요성**: 2주간 GUI 기반 웹 개발을 경험했음에도 불구하고, 여전히 배워야 할 것이 많음을 깨달았습니다. 코딩에 대한 추가 학습 외에도 기능 테스트, 프론트엔드/백엔드 지식, 결제 시스템 흐름 등 다양한 분야의 심층적인 이해가 필요하며, 이를 위해 꾸준히 리서치하고 정리하며 학습에 매진하고 있습니다.

## 🌱 아쉬운 점 및 다음 주 목표

* **Elementor 위젯의 한계 및 커스터마이징의 필요성**: Elementor 위젯은 강력하지만, Pro 전용 위젯이나 시간의 흐름에 따른 기능 변화(삭제, 통합, 무료 전환 등)로 인해 **모든 디자인 및 기능 요구사항을 위젯만으로 충족하기 어렵습니다.** 커스터마이징이 대안이 될 수 있지만, 이 역시 만능이 아니므로 **위젯의 한계를 인지하고 적절한 커스터마이징 포인트를 찾는 능력**이 중요함을 깨달았습니다.
* **gangnamsyrup.com.au 실습 프로젝트 전체 흐름 미완**: 대량의 상품/포스트로 인해 `gangnamsyrup.com.au` 실습 프로젝트의 모든 페이지 흐름을 완성하지 못했습니다.
* **비회원 주문 실습 보류**: 개발 환경 제약으로 비회원 주문 테스트를 완료하지 못했습니다. 이는 다음 주에 보완할 과제입니다.

3주차에는 이러한 아쉬운 점들을 보완하고 심화 학습에 집중합니다.

* **이미지 표준화 및 적용**: Canva 등 외부 툴을 활용해 **상품 이미지의 비율과 크기를 표준화**하고, `gangnamsyrup.com.au` 프로젝트에 적용해 페이지 레이아웃에 미치는 영향을 직접 확인하며 **이미지 최적화의 실질적 중요성**을 체득합니다.
* **고도화된 모바일/태블릿 최적화**: 단순히 반응형 설정을 넘어, **다양한 디바이스에서 세련된 레이아웃을 유지하도록 구조 설계 단계부터 모바일/태블릿 최적화를 염두에 두는 감각**을 기릅니다. Elementor의 고급 반응형 기능 및 Flexbox 활용을 심화합니다.
* **복잡한 헤더 레이아웃 구현 및 WooCommerce 고급 기능 탐구**: 복잡한 헤더 레이아웃 구현을 시도하며 Elementor와 CSS 숙련도를 높입니다. WooCommerce의 고급 설정 및 조건부 표시 기능(예: 로그인 상태에 따른 메뉴 변화)을 더 깊이 탐구해 완성도 높은 웹 개발 역량을 갖춥니다.
* **비회원 주문 흐름 완벽 실습**: 환경이 허락하는 대로 **비회원 주문 플로우를 완벽하게 테스트**하여 실제 서비스 운영 이해도를 높입니다.
* **사이트 구조 설계 역량 강화**: 어떤 사이트에 어떤 구조(Full Width/Boxed)가 적합할지에 대한 고민을 선행하여 개발 착수 전 설계를 더욱 탄탄히 하는 감각을 키웁니다.
