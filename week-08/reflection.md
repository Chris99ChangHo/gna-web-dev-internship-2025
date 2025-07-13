# 📝 Week 08 Reflection (2025.06.30 ~ 2025.07.04)

## ✅ Key Tasks This Week

**📌 Significantly advanced the DevNewsHub mini-project app, implementing core screens, integrating WordPress API content (including taxonomies/custom fields), and developing features like TTS excerpt playback and persistent "Like" functionality.**   
**📌 Successfully completed the full, zero-base implementation of a new client one-page website, including initial responsive optimization for tablet and mobile environments.**   
**📌 Developed robust Python scripts for large-scale Shopify product data migration, focusing on `outerHTML` scraping, automated image uploads to Shopify's media backend (replacing URLs with CDN links), and conditional description updates.**  

## 🧠 What I Learned

-   **Comprehensive App & Web Development Workflows:** Gained hands-on experience in building out multi-screen React Native/Expo applications and full client websites from scratch, beyond just content migration or simple feature additions. This included structuring core app components, managing navigation (e.g., resolving Expo Router conflicts), and translating design drafts into code.
    
-   **Advanced WordPress API & Custom Field Management:** Deepened understanding of utilizing the WordPress REST API to fetch rich content, including taxonomies and custom fields, and the nuances of controlling `WP_Query` for precise data sorting.
    
-   **Strategic Data Migration & Asset Management:** Acquired critical insights into planning and executing large-scale data migrations, particularly recognizing the importance of not just transferring text/HTML but also ensuring all associated media assets (images) are properly hosted on the target platform's CDN for long-term stability and performance. This involved learning about Shopify's API for media uploads and effective pagination (`since_id`).
    
-   **Proactive Styling Preservation in Scraping:** Understood that direct `outerHTML` scraping may not preserve all original text styles (like color) in the target environment, highlighting the necessity for advanced HTML sanitization and style adaptation in migration scripts.
    

## 🔧 Technical Problem-Solving Experience

-   **WordPress Custom Date Sorting (`WP_Query`):** Encountered issues with Elementor's 'Posts' widget not supporting custom field sorting. Resolved by implementing custom PHP shortcodes and realizing the critical need for consistent `DATETIME` formatting in the `news-published-date` custom field for accurate `WP_Query` sorting.
    
-   **React Native Navigation Conflicts (Expo Router):** Faced persistent `NavigationContainer` nesting errors when attempting to integrate React Navigation with Expo Router. Diagnosed that Expo Router implicitly handles top-level navigation, and resolved by avoiding direct `NavigationContainer` use, instead focusing on Expo Router's file-tree based routing and `router.push()` with correct paths.
    
-   **Shopify Image Migration & CDN Replacement:** Identified that simply scraping `outerHTML` was insufficient for image stability as it relied on external hosting. Developed a solution to parse all image URLs, download images, upload them directly to Shopify's backend media files, and then programmatically replace original `src` URLs with new Shopify CDN links, ensuring image permanence.
    
-   **Preserving HTML Text Styling during Scraping:** Observed that scraped `outerHTML` was losing original text colors and other styles when imported into Shopify. While not fully resolved, this problem was identified as requiring further HTML sanitization and style attribute handling within the migration script, acknowledging the complexity of cross-platform style preservation.
    

## 💡 Reflections

-   **Agility in Task Prioritization:** The week demonstrated a high degree of adaptability, rapidly shifting from app development to a full client website build, and then to a complex data migration task. This agility was crucial for responding to dynamic project needs.
    
-   **The Power of Granular Control:** Repeatedly, the limitations of higher-level tools (e.g., Elementor widgets, generic navigation setups) became apparent, leading to the realization that direct code implementation (PHP shortcodes, custom React Native components, Python scripts) offers essential control and flexibility for specific requirements.
    
-   **Importance of Proactive Communication and Iteration:** Seeking early confirmation from designers and senior developers (e.g., for the one-page site) significantly streamlines the development process by catching potential misalignments early. Similarly, an iterative approach to responsive design and feature implementation (e.g., loading/error states in the app) improves quality and reduces rework.
    
-   **Thinking Beyond the Immediate Migration:** The Shopify data migration highlighted that a true migration involves more than just copying content; it requires fully integrating and hosting all associated assets on the target platform to ensure long-term functionality and prevent broken links, a critical lesson for data integrity.
    

## 🌱 Points of Improvement & Next Week's Goals

-   **Improve HTML Style Preservation in Shopify Migration:** Implement advanced HTML sanitization and style attribute handling within the Shopify migration script to ensure original text colors and other critical styling are preserved during `outerHTML` import.
    
-   **Complete Shopify Data Migration & Validation:** Finalize the Shopify migration script and execute the full migration for Melbourne Market product descriptions and images. Thoroughly verify that all scraped images are successfully hosted on Shopify's media backend and that their CDN links are correctly replaced, followed by comprehensive data validation on Shopify.
    
-   **Finalize Client One-Page Website:** Address any remaining feedback from the designer and senior developer for the "Kisa Sikdang" website and prepare it for final deployment.
    
-   **Advance DevNewsHub Mini-Project:** Continue refining core app features, completing component modularization, and exploring WordPress website enhancements (e.g., custom field sorting, category integration for "explore" functionality).
    
-   **Intensify AI Security Threat Research & PPT Preparation:** Dedicate significant time to in-depth research and preparation for the "AI Hacking, Scams, and Spamming" presentation, focusing on CPanel/WHM server security implications, ahead of the July 10, 2025 deadline.

----------

# 📝 26주차 회고 (2025.06.30 ~ 2025.07.04)

## ✅ 이번 주 주요 작업

**📌 DevNewsHub 미니 프로젝트 앱을 크게 발전시켜 핵심 화면을 구현하고, 워드프레스 API 콘텐츠(택소노미/커스텀 필드 포함)를 통합했으며, TTS 발췌문 재생 및 영구적인 "좋아요" 기능 등을 개발했습니다.**   
**📌 새로운 클라이언트 원페이지 웹사이트를 처음부터 끝까지 성공적으로 구현 완료했으며, 태블릿 및 모바일 환경에 대한 초기 반응형 최적화 작업을 포함했습니다.**   
**📌 대규모 Shopify 상품 데이터 마이그레이션을 위한 견고한 Python 스크립트를 개발했으며, `outerHTML` 스크래핑, Shopify 미디어 백엔드로의 이미지 자동 업로드(원본 URL을 CDN 링크로 교체), 조건부 설명 업데이트에 중점을 두었습니다.**  

## 🧠 배운 핵심 개념

-   **포괄적인 앱 및 웹 개발 워크플로우:** 콘텐츠 마이그레이션이나 단순 기능 추가를 넘어, 다중 화면 React Native/Expo 애플리케이션 및 전체 클라이언트 웹사이트를 처음부터 구축하는 실질적인 경험을 얻었습니다. 여기에는 핵심 앱 구성 요소 구조화, 내비게이션 관리(예: Expo Router 충돌 해결), 디자인 초안을 코드로 변환하는 과정이 포함되었습니다.
    
-   **고급 워드프레스 API 및 커스텀 필드 관리:** 워드프레스 REST API를 활용하여 택소노미 및 커스텀 필드를 포함한 풍부한 콘텐츠를 가져오는 방법과 `WP_Query`를 제어하여 정확한 데이터 정렬을 수행하는 미묘한 차이에 대한 이해를 심화했습니다.
    
-   **전략적 데이터 마이그레이션 및 자산 관리:** 대규모 데이터 마이그레이션을 계획하고 실행하는 데 대한 중요한 통찰력을 얻었으며, 특히 텍스트/HTML만 전송하는 것을 넘어 모든 관련 미디어 자산(이미지)이 대상 플랫폼의 CDN에 올바르게 호스팅되어 장기적인 안정성과 성능을 보장하는 것의 중요성을 인식했습니다. 이는 Shopify 미디어 업로드 API 및 효율적인 페이지네이션(`since_id`)에 대한 학습을 포함합니다.
    
-   **스크래핑 시 능동적인 스타일 보존:** `outerHTML` 스크래핑이 대상 환경에서 모든 원본 텍스트 스타일(예: 색상)을 보존하지 못할 수 있음을 이해했으며, 마이그레이션 스크립트 내에서 고급 HTML 정제 및 스타일 적용의 필요성을 강조했습니다.
    

## 🔧 기술적 문제 해결 경험

-   **워드프레스 커스텀 날짜 정렬 (`WP_Query`):** Elementor의 'Posts' 위젯이 커스텀 필드 정렬을 지원하지 않는 문제에 직면했습니다. 커스텀 PHP 숏코드를 구현하고 `news-published-date` 커스텀 필드에 일관된 `DATETIME` 형식을 사용하는 것이 정확한 `WP_Query` 정렬에 필수적임을 깨달아 해결했습니다.
    
-   **React Native 내비게이션 충돌 (Expo Router):** React Navigation을 Expo Router와 통합하려 할 때 지속적인 `NavigationContainer` 중첩 오류에 직면했습니다. Expo Router가 최상위 내비게이션을 암묵적으로 처리한다는 것을 진단하고, `NavigationContainer` 직접 사용을 피하고 Expo Router의 파일 트리 기반 라우팅 및 올바른 경로를 사용한 `router.push()`에 집중하여 해결했습니다.
    
-   **Shopify 이미지 마이그레이션 및 CDN 교체:** `outerHTML` 스크래핑만으로는 이미지 안정성이 부족하다는 것을 파악했습니다. 모든 이미지 URL을 파싱하고, 이미지를 다운로드하여 Shopify 백엔드 미디어 파일에 직접 업로드한 다음, 원본 `src` URL을 새로운 Shopify CDN 링크로 프로그래밍 방식으로 교체하여 이미지 영구성을 보장하는 솔루션을 개발했습니다.
    
-   **스크래핑 시 HTML 텍스트 스타일 보존:** 스크래핑된 `outerHTML`이 Shopify로 가져올 때 원본 텍스트 색상 및 기타 스타일이 손실되는 것을 확인했습니다. 완전히 해결되지는 않았지만, 이 문제는 마이그레이션 스크립트 내에서 추가적인 HTML 정제 및 스타일 속성 처리가 필요함을 확인했으며, 플랫폼 간 스타일 보존의 복잡성을 인정했습니다.
    

## 💡 느낀 점

-   **업무 우선순위의 민첩성:** 이번 주는 앱 개발에서 완전한 클라이언트 웹사이트 구축, 그리고 복잡한 데이터 마이그레이션 작업으로 빠르게 전환하는 높은 적응성을 보여주었습니다. 이러한 민첩성은 동적인 프로젝트 요구사항에 대응하는 데 매우 중요했습니다.
    
-   **세밀한 제어의 힘:** 상위 수준 도구(예: Elementor 위젯, 일반적인 React Navigation 설정)의 한계가 반복적으로 드러났으며, 특정 요구사항에 대한 필수적인 제어와 유연성을 제공하기 위해 직접 코드 구현(PHP 숏코드, 커스텀 React Native 컴포넌트, Python 스크립트)이 중요하다는 것을 깨달았습니다.
    
-   **능동적인 소통 및 반복의 중요성:** 디자이너 및 선임 개발자와의 조기 컨펌(예: 원페이지 사이트)을 통해 잠재적인 불일치를 일찍 발견하여 개발 프로세스를 크게 간소화했습니다. 유사하게, 반응형 디자인 및 기능 구현(예: 앱의 로딩/오류 상태)에 대한 반복적인 접근 방식은 품질을 향상시키고 재작업을 줄입니다.
    
-   **단순 마이그레이션을 넘어선 사고:** Shopify 데이터 마이그레이션은 진정한 마이그레이션이 단순히 콘텐츠를 복사하는 것 이상이라는 점을 강조했습니다. 장기적인 기능성과 깨진 링크 방지를 위해 모든 관련 자산을 대상 플랫폼에 완전히 통합하고 호스팅해야 한다는 중요한 교훈을 얻었습니다.
    

## 🌱 아쉬운 점 및 다음 주 목표

-   **Shopify 마이그레이션 시 HTML 스타일 보존 개선:** `outerHTML` 가져오기 시 원본 텍스트 색상 및 기타 중요한 스타일이 보존되도록 Shopify 마이그레이션 스크립트 내에서 고급 HTML 정제 및 스타일 속성 처리를 구현할 것입니다.
    
-   **Shopify 데이터 마이그레이션 완료 및 유효성 검사:** 멜번 마켓 상품 설명 및 이미지의 전체 마이그레이션을 위한 Shopify 마이그레이션 스크립트를 최종적으로 다듬고 실행할 것입니다. 스크랩된 모든 이미지가 Shopify 미디어 백엔드에 성공적으로 호스팅되고 CDN 링크로 올바르게 교체되었는지 철저히 확인한 다음, Shopify에서 포괄적인 데이터 유효성 검사를 수행할 것입니다.
    
-   **클라이언트 원페이지 웹사이트 최종 마무리:** "기사식당" 웹사이트에 대한 디자이너 및 선임 개발자의 남은 피드백을 반영하고 최종 배포를 준비할 것입니다.
    
-   **DevNewsHub 미니 프로젝트 진전:** 핵심 앱 기능 개선, 컴포넌트 모듈화 완료, 워드프레스 웹사이트 개선(예: 커스텀 필드 정렬, "탐색" 기능을 위한 카테고리 통합)을 계속 진행할 것입니다.
    
-   **AI 보안 위협 관련 PPT 리서치 및 준비 심화:** 2025년 7월 10일 마감일을 앞두고 CPanel/WHM 서버 보안 영향을 중심으로 "AI를 활용한 해킹, 스캠, 스팸의 진화" 발표 자료에 대한 심층 리서치 및 준비에 상당한 시간을 할애할 것입니다.
