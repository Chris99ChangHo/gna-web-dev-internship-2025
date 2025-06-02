# 📝 Week 03 Reflection (2025.05.26 ~ 05.30)

This third week of my internship was a period of focused learning on **WooCommerce customization and WordPress backend development, complemented by a significant deep dive into AI's impact on marketing.** I gained practical skills in design customization, understood the critical role of hooks in extending WordPress functionality, and prepared and delivered a comprehensive presentation on AI.

## ✅ Key Tasks This Week

-   **📌 Comprehensive WooCommerce Core Feature Understanding**: Researched and understood WooCommerce's end-to-end system, from product management to shipping and payments, for practical application.
-   **📌 Elementor Addon Exploration**: Explored Elementor addon concepts and confirmed their necessity for enhanced design and functionality.
-   **📌 WooCommerce Default Page Customization**: Studied and practiced PHP template override methods for safely customizing WooCommerce default pages (`My Account`, `Cart`, `Checkout`).
-   **📌 CSS-First Design Approach**: Prioritized CSS for design customization, utilizing `Simple Custom CSS and JS` plugin and Chrome Developer Tools for efficient styling.
-   **📌 In-depth WordPress Hooks Learning**: Completed extensive learning and practical application exercises for both Action and Filter Hooks, understanding their concepts, usage, and advanced features.
-   **📌 AI Technology Presentation Preparation & Delivery**: Dedicated significant time to preparing and successfully delivering a presentation on "Analysis of AI Technology's Impact on Online Search and Marketing Environments and Proposed Future Utilization Strategies."
-   **📌 Web Scraping Development for LLM Learning Assistant**: Commenced web scraping code development to gather data from WordPress, Elementor, and WooCommerce official documentation for an LLM-powered learning assistant.

## 🧠 What I Learned

-   **Integrated Understanding of WooCommerce System Structure**: Gained a comprehensive, end-to-end understanding of the WooCommerce e-commerce system, recognizing the interaction of various functions from product registration to order processing, customer management, payment/shipping settings (especially Shipping Zones), and analytics.
-   **Elementor Addon Functionality & Necessity**: Understood that Elementor Pro and third-party addons are essential for extending Elementor's capabilities, particularly recognizing the high utility of **Conditional Display features** for dynamic UI/UX control.
-   **PHP-based WooCommerce Template Override Methodology**: Mastered the concept and practical procedure of safely modifying WooCommerce default files by copying them to a child theme, which is crucial for maintaining brand identity and ensuring update robustness.
-   **'CSS-First' Principle for WooCommerce Customization**: Realized that most design and layout changes can be handled safely and efficiently with CSS, with PHP template overrides reserved for structural changes. I also mastered the use of Chrome Developer Tools for precise CSS selector targeting.
-   **Clear Distinction and Practical Use of WordPress Hooks**: Clearly understood the concepts, internal structure, and practical usage of **Action Hooks** (for execution) and **Filter Hooks** (for data modification and return). Emphasized the critical importance of `add_filter()` returning a value and understanding hook `Priority`.
-   **Diverse Applications of AI in Marketing & Search Evolution**: Gained a clear understanding that AI is transforming all aspects of marketing, including automation, content creation, predictive analytics, and personalization. Also realized how AI is changing the search experience itself, providing contextually relevant information.
-   **Duality of LLMs (Limitations and User Experience)**: Through discussion, I clearly recognized the limitation that LLM output quality can degrade with increasingly complex prompts, and understood the potential user frustration from repetitive prompting despite AI's convenience.
-   **Criticality of Data Quality and AI Governance**: Understood that the success of AI implementation heavily depends on data quality and robust ethical/legal frameworks.

## 🔧 Technical Problem-Solving Experience

-   **Accurate CSS Selector Targeting for WooCommerce Elements**:
    -   **Problem**: When attempting to style specific elements on WooCommerce pages (e.g., product attributes table values, block-based buttons), general tag selectors (`td`, `th`, `tr`) often didn't apply styles, leading to frustration.
    -   **Cause**: WooCommerce's complex DOM structure and nested elements often have more specific class names or IDs that override general tag styles.
    -   **Solution**: Consistently utilized Chrome Developer Tools (F12) to inspect elements, identify precise class names (e.g., `.woocommerce-product-attributes-item__value`, `wc-block-components-button`), and target them directly. This ensured styles were applied accurately and efficiently.
-   **Managing PHP Template Overrides for WooCommerce Stability**:
    -   **Problem**: Direct modification of WooCommerce core plugin files for customization risks losing changes during updates and introduces instability.
    -   **Solution**: Strictly adhered to the PHP template override methodology: copy the target template file from `wp-content/plugins/woocommerce/templates/` to the identical path within the child theme (e.g., `wp-content/themes/your-child-theme/woocommerce/`). This ensures changes persist across plugin updates and maintains site integrity.
-   **Ensuring Proper Filter Hook Functionality**:
    -   **Problem**: Initially, I encountered errors or unexpected behavior when using `add_filter()` if the callback function did not return a value.
    -   **Cause**: `add_filter()` is designed to modify data and _must_ return the (modified) data for the filter chain to continue correctly.
    -   **Solution**: Through practice and referencing official documentation, I learned and strictly applied the rule that any function attached to a filter hook must explicitly `return` a value.

## 💡 Reflections

-   **Iterative Customization Approach (CSS-First then PHP)**: I solidified my understanding of starting with CSS for visual adjustments before resorting to PHP template overrides for structural changes. This approach minimizes risk and maximizes efficiency.
-   **The Power and Pitfalls of WordPress Hooks**: While hooks offer immense power for extending WordPress and WooCommerce without modifying core files, their effective use requires a deep understanding of their type (Action vs. Filter), execution order (Priority), and argument handling. Misuse, especially with filters, can lead to critical errors.
-   **AI as a Double-Edged Sword**: My AI presentation and subsequent discussion highlighted that while AI is an incredibly powerful tool for marketing and efficiency, it also has limitations (e.g., degraded output with complex LLM prompts) and ethical considerations (data quality, governance). A nuanced, strategic approach is essential.
-   **Importance of Continuous Learning and Problem-Solving**: This week reinforced that web development, particularly in a dynamic environment like WordPress with WooCommerce, requires constant learning, adapting to new tools (Elementor addons), and effective problem-solving skills (developer tools, systematic troubleshooting).
-   **Bridging Frontend and Backend for Holistic Development**: My journey from CSS customization to PHP hooks and understanding AI's backend implications has shown the importance of integrating frontend (design) and backend (logic) knowledge for truly holistic web development.

## 🌱 Points of Improvement & Next Week's Goals

-   **Deepening WordPress Hooks Application**: While I grasped the concepts, I need more practical application of hooks, especially within WooCommerce, to perform complex functional extensions beyond simple examples.
-   **Mastering Web Scraping & Data Preprocessing for LLM**: The initial web scraping efforts highlighted challenges due to varying website structures. I need to refine my scraping techniques and thoroughly preprocess data to ensure high quality for LLM training.
-   **Integrating AI Insights into Development Workflow**: I need to find concrete ways to apply the AI knowledge gained this week into my development workflow, especially in utilizing LLMs more effectively (e.g., for coding assistance, documentation summarization) while mitigating their known limitations.

In Week 4, I'll focus on addressing these areas and deepening my learning:

-   **In-depth PHP Hooks Learning & Practical WooCommerce Functionality Extension**: Continue applying learned hook concepts to real WooCommerce scenarios (e.g., modifying product prices under specific conditions, customizing payment logic) via `functions.php`.
-   **Complete Web Scraping Code and Data Refinement for LLM Learning Assistant**: Finalize the web scraping code development and proceed with refining the collected data into a format suitable for LLM training, ensuring data cleanliness and structure.
-   **Research on Social Media Post/Design Automation Platforms**: Conduct thorough research on tools for automated social media content publishing and design, preparing a detailed report for the manager by next Wednesday.
-   **Advance AI and LLM Utilization Strategies in Practice**: Based on insights gained regarding LLM limitations and user experience, continue to research and apply methods for utilizing AI tools more efficiently and with less frustration in practical scenarios.
-   **Mastering Developer Tools & Pattern Recognition**: Further master the habit of using developer tools on various WooCommerce pages to understand HTML structures and CSS selectors, building my own snippet library.

----------

# 📝 3주차 회고 (2025.05.26 ~ 05.30)

이번 인턴십 3주차는 **WooCommerce 커스터마이징 및 워드프레스 백엔드 개발에 집중적인 학습을 진행했으며, AI가 마케팅에 미치는 영향에 대한 심층적인 이해를 더하는 기간**이었습니다. 디자인 커스터마이징 실무 능력을 향상시켰고, 워드프레스 기능 확장을 위한 훅의 중요성을 파악했으며, AI 관련 종합 발표를 성공적으로 준비하고 수행했습니다.

## ✅ 이번 주 주요 작업

-   **📌 WooCommerce 핵심 기능 종합 이해**: 상품 관리부터 배송, 결제에 이르는 WooCommerce의 엔드투엔드 시스템을 리서치하고 실무 적용 방안을 이해했습니다.
-   **📌 Elementor 애드온 탐색**: Elementor 애드온 개념을 탐색하고 디자인 및 기능 향상을 위한 필요성을 확인했습니다.
-   **📌 WooCommerce 기본 페이지 커스터마이징**: WooCommerce 기본 페이지(My Account, Cart, Checkout 등)를 안전하게 커스터마이징하기 위한 PHP 템플릿 오버라이드 방법을 학습하고 실습했습니다.
-   **📌 CSS-First 디자인 접근 방식**: 디자인 커스터마이징에 CSS를 우선적으로 활용하는 방식을 채택하고, `Simple Custom CSS and JS` 플러그인과 Chrome 개발자 도구를 활용하여 효율적인 스타일링을 진행했습니다.
-   **📌 워드프레스 훅(Hooks) 심층 학습**: Action Hook과 Filter Hook 모두에 대한 광범위한 학습과 실전 적용 연습을 완료하며, 그 개념, 사용법 및 고급 기능을 이해했습니다.
-   **📌 AI 기술 발표 준비 및 수행**: "AI 기술이 온라인 검색과 마케팅 환경에 끼친 영향 분석 및 향후 활용 전략 제안"이라는 주제로 발표 자료를 준비하고 성공적으로 발표를 완료했습니다.
-   **📌 LLM 학습 도우미를 위한 웹 스크래핑 개발**: WordPress, Elementor, WooCommerce 공식 문서로부터 LLM 학습에 필요한 데이터를 수집하기 위한 웹 스크래핑 코드 개발에 착수했습니다.

## 🧠 배운 핵심 개념

-   **WooCommerce 시스템 구조 통합 이해**: 상품 등록부터 주문 처리, 고객 관리, 결제/배송 설정(특히 Shipping Zone), 그리고 분석에 이르는 WooCommerce 이커머스 시스템의 전반적인 흐름과 각 기능의 상호작용을 통합적으로 이해했습니다.
-   **Elementor 애드온 기능 확장 및 필요성**: Elementor Pro 및 서드파티 애드온이 Elementor의 기능을 확장하는 데 필수적임을 이해했으며, 특히 동적 UI/UX 제어를 위한 **조건부 표시(Conditional Display) 기능**의 높은 유용성을 파악했습니다.
-   **PHP 기반 WooCommerce 템플릿 오버라이드 방법론**: 브랜드 아이덴티티 유지 및 업데이트 강건성을 위해 WooCommerce 기본 파일을 차일드 테마로 복사하여 안전하게 수정하는 개념과 실무 절차를 숙달했습니다.
-   **'CSS 우선' 원칙의 WooCommerce 커스터마이징**: 대부분의 디자인 및 레이아웃 변경은 CSS로 안전하고 효율적으로 처리할 수 있으며, PHP 템플릿 오버라이드는 구조적 변경이 필요한 경우에만 사용해야 함을 체득했습니다. 또한, 정확한 CSS 선택자 타겟팅을 위한 Chrome 개발자 도구의 활용을 숙달했습니다.
-   **워드프레스 훅의 명확한 구분 및 실무 적용**: **액션 훅(Action Hooks)**(실행 목적)과 **필터 훅(Filter Hooks)**(데이터 수정 및 반환 목적)의 개념, 내부 구조, 실제 사용법을 명확히 이해했습니다. 특히 `add_filter()` 사용 시 값 반환의 중요성과 훅의 `Priority` 이해가 필수적임을 강조했습니다.
-   **마케팅에서의 AI의 다각적 활용 및 검색 환경 변화**: AI가 자동화, 콘텐츠 제작, 예측 분석, 개인화 등 마케팅 전반에 걸쳐 핵심적인 도구로 자리 잡고 있음을 명확히 이해했습니다. 또한, AI가 사용자 의도를 파악하고 맥락에 맞는 정보를 제공하는 방식으로 검색 경험 자체를 변화시키고 있음을 파악했습니다.
-   **LLM의 양면성 (한계와 사용자 경험)**: 토론을 통해 LLM의 강력한 도구에도 불구하고, 복잡한 프롬프트에서 출력 품질이 저하될 수 있다는 한계를 명확히 인식했습니다. 또한, 편리함을 위해 AI를 사용하지만 반복적인 요청으로 스트레스를 받을 수 있다는 현실적인 사용자 경험을 깊이 고려하게 되었습니다.
-   **데이터 품질 및 AI 거버넌스의 중요성**: AI 활용의 성패가 데이터 품질과 견고한 윤리적, 법적 프레임워크에 크게 좌우됨을 인지했습니다.

## 🔧 기술적 문제 해결 경험

-   **WooCommerce 요소의 정확한 CSS 선택자 타겟팅**:
    -   **문제**: WooCommerce 페이지(예: 상품 속성 테이블 값, 블록 기반 버튼)의 특정 요소를 스타일링하려고 할 때, 일반 태그 선택자(`td`, `th`, `tr`)로는 스타일이 적용되지 않아 어려움을 겪었습니다.
    -   **원인**: WooCommerce의 복잡한 DOM 구조와 중첩된 요소들은 종종 일반 태그 스타일보다 더 구체적인 클래스명이나 ID를 가지고 있으며, 이들이 우선적으로 적용됩니다.
    -   **해결**: Chrome 개발자 도구(F12)를 지속적으로 활용하여 요소를 검사하고, 정확한 클래스명(예: `.woocommerce-product-attributes-item__value`, `wc-block-components-button`)을 식별하여 직접 타겟팅했습니다. 이를 통해 스타일이 정확하고 효율적으로 적용될 수 있었습니다.
-   **WooCommerce 안정성을 위한 PHP 템플릿 오버라이드 관리**:
    -   **문제**: WooCommerce 코어 플러그인 파일을 직접 수정하여 커스터마이징하면 업데이트 시 변경 사항이 손실되고 불안정성을 초래할 위험이 있었습니다.
    -   **해결**: PHP 템플릿 오버라이드 방법론을 엄격히 준수했습니다. 대상 템플릿 파일을 `wp-content/plugins/woocommerce/templates/`에서 차일드 테마 내의 동일한 경로(예: `wp-content/themes/your-child-theme/woocommerce/`)로 복사했습니다. 이는 플러그인 업데이트 전반에 걸쳐 변경 사항을 유지하고 사이트 무결성을 보장합니다.
-   **필터 훅 기능의 올바른 작동 보장**:
    -   **문제**: `add_filter()`를 사용할 때 콜백 함수가 값을 반환하지 않으면 오류가 발생하거나 예상치 못한 동작이 나타났습니다.
    -   **원인**: `add_filter()`는 데이터를 수정하고 (수정된) 데이터를 반환하여 필터 체인이 올바르게 계속되도록 설계되었습니다.
    -   **해결**: 실습과 공식 문서를 참조하여, 필터 훅에 연결된 모든 함수는 명시적으로 값을 `return`해야 한다는 규칙을 학습하고 엄격히 적용했습니다.

## 💡 느낀 점

-   **반복적인 커스터마이징 접근 방식 (CSS 우선, 그 다음 PHP)**: 시각적 조정을 위해 CSS를 먼저 사용하고, 구조적 변경이 필요한 경우에만 PHP 템플릿 오버라이드로 전환하는 접근 방식의 효율성을 확고히 이해했습니다. 이는 위험을 최소화하고 효율성을 극대화하는 방법입니다.
-   **워드프레스 훅의 힘과 함정**: 훅은 워드프레스와 WooCommerce를 코어 파일을 수정하지 않고 확장하는 엄청난 힘을 제공하지만, 효과적인 사용을 위해서는 유형(Action vs. Filter), 실행 순서(Priority), 인자 처리 방식에 대한 깊은 이해가 필요합니다. 특히 필터의 오용은 치명적인 오류로 이어질 수 있습니다.
-   **AI의 양면성**: AI 발표와 이후 토론을 통해 AI가 마케팅 및 효율성을 위한 강력한 도구임에도 불구하고, 한계(예: 복잡한 LLM 프롬프트에 따른 출력 저하)와 윤리적 고려 사항(데이터 품질, 거버넌스)이 있음을 알게 되었습니다. 미묘하고 전략적인 접근이 필수적입니다.
-   **지속적인 학습과 문제 해결의 중요성**: 이번 주는 워드프레스와 WooCommerce 같은 동적인 환경에서 웹 개발이 끊임없는 학습, 새로운 도구(Elementor 애드온)에 대한 적응, 그리고 효과적인 문제 해결 능력(개발자 도구, 체계적인 문제 해결)을 요구한다는 점을 재확인시켜 주었습니다.
-   **프론트엔드와 백엔드를 잇는 전반적인 개발**: CSS 커스터마이징부터 PHP 훅, 그리고 AI의 백엔드 함의에 대한 이해까지의 여정은 진정으로 전체적인 웹 개발을 위해 프론트엔드(디자인)와 백엔드(로직) 지식을 통합하는 것의 중요성을 보여주었습니다.

## 🌱 아쉬운 점 및 다음 주 목표

-   **워드프레스 훅 적용 심화**: 개념은 파악했지만, 간단한 예시를 넘어 WooCommerce 내에서 복잡한 기능 확장을 수행하기 위해서는 훅에 대한 더 많은 실전 적용 연습이 필요합니다.
-   **웹 스크래핑 및 LLM을 위한 데이터 전처리 마스터링**: 초기 웹 스크래핑 시도에서 웹사이트 구조의 다양성으로 인한 어려움을 겪었습니다. LLM 학습을 위한 고품질 데이터 확보를 위해 스크래핑 기술을 정제하고 데이터 전처리를 철저히 해야 합니다.
-   **AI 인사이트 개발 워크플로우 통합**: 이번 주 학습한 AI 지식을 개발 워크플로우에 구체적으로 적용하는 방법, 특히 알려진 한계를 완화하면서 LLM을 더 효과적으로 활용하는 방법을 찾아야 합니다.

4주차에는 이러한 아쉬운 점들을 보완하고 심화 학습에 집중합니다:

-   **PHP 훅 심화 학습 및 실제 WooCommerce 기능 확장 연습**: 학습한 훅 개념을 실제 WooCommerce 시나리오(예: 특정 조건에 따른 상품 가격 변경, 결제 로직 커스터마이징)에 `functions.php`를 통해 적용하는 연습을 계속합니다.
-   **LLM 학습 도우미를 위한 웹 스크래핑 코드 완성 및 데이터 정제**: 웹 스크래핑 코드 개발을 마무리하고, 수집된 데이터를 LLM 학습에 적합한 형태로 정제하는 작업을 진행하며 데이터의 청결도와 구조를 확보합니다.
-   **소셜 미디어 포스트/디자인 자동화 플랫폼 리서치**: 다음 주 수요일까지 매니저님께 보고할 소셜 미디어 콘텐츠 자동 발행 및 디자인 툴에 대한 철저한 리서치를 수행합니다.
-   **AI 및 LLM 활용 전략 실무 고도화**: LLM의 한계와 사용자 경험에 대한 인사이트를 바탕으로, AI 도구를 보다 효율적이고 스트레스 없이 활용하는 방법을 지속적으로 연구하고 실무에 적용합니다.
-   **개발자 도구 숙달 및 패턴화**: 다양한 WooCommerce 페이지에서 개발자 도구를 활용하여 HTML 구조와 CSS 선택자를 파악하는 습관을 더욱 숙달하고, 나만의 스니펫 라이브러리를 구축하기 시작합니다.
