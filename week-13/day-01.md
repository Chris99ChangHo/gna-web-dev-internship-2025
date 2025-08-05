# 📅 Day 01 (2025-08-04, Mon)

## 🎓 What I Did Today

**📌 In a morning development meeting, I reported on the persistent font-rendering issue with Korean/Chinese text and the malfunctioning dynamic cover image system. I received encouragement from the senior developer for my proposed solutions.**   
**📌 I successfully fixed the font-rendering issue in the PDF report by explicitly applying `font-family` to all relevant CSS selectors.**   
**📌 I completed an urgent new task: setting up shipping fees for a Shopify project, which involved creating local and general shipping zones based on postcodes and states.**   
**📌 My attempt to use the WordPress REST API to fetch cover images failed, as the API consistently returned a fallback or no image.**  

### Detailed Activities

**1. Morning Development Meeting & Feedback:**

-   **Issues Discussed**: I reported that despite specifying fonts, Korean and Chinese text was still appearing corrupted in the PDF reports. I also noted that the dynamic cover image system, intended to fetch random, non-duplicate images from WordPress, was not functioning.
    
-   **Proposed Solution**: I suggested improving the cover image system to not only fix the current issue but also to allow users to select images themselves.
    
-   **Senior Developer Feedback**: The senior developer acknowledged the font issue, sharing their own past experience of having to "force-apply" fonts. They encouraged me to proceed with the proposed cover image improvement.
    

**2. Core Project Bug Fix & Troubleshooting:**

-   **Font Issue Resolution**: I solved the font-rendering issue by explicitly applying the `font-family` property to a wide range of CSS selectors including `body`, `table`, `td`, `th`, `p`, and headings (`h1`~`h3`). This **force-applied** the correct font to all text elements, resolving the corruption.
    
-   **Cover Image API Failure**: I attempted to load images from a specific WordPress `media_category` via the REST API. However, the API consistently returned only a fallback URL or no image at all, confirming the core functionality was broken.
    

**3. Shopify Project Shipping Fee Setup:**

-   **New Task**: I was assigned an urgent task to configure shipping fees for a Shopify project.
    
-   **Implementation**:
    
    -   I created **local delivery** shipping zones for specific postcodes, using data from the current site.
        
    -   I set up **general shipping profile** zones for entire states, including WA, NT, TAS, and ACT.
        
    -   I accurately applied the shipping fees provided in an external Excel file.
        
-   **Result**: The shipping fee setup was completed successfully.

## 💡 Practical Trial-and-Error and Tips

-   **Resolving Font-Rendering with CSS Specificity**: When a PDF rendering library like `xhtml2pdf` fails to display multi-language fonts despite `@font-face` declarations, the issue often lies with CSS specificity. The solution was to **override default font settings by explicitly applying `font-family` to every relevant selector** (e.g., `body, p, h1, td`). This brute-force approach ensures the correct font is used, preventing unexpected rendering issues.
    
-   **Troubleshooting External API Integration Failures**: When integrating with an external API (like the WordPress REST API), a common pitfall is assuming the API will behave as expected. I learned to **validate the API response immediately** and not to rely on a working implementation from a previous environment. The failure to return the expected image data, even with a seemingly correct endpoint, signaled a deeper issue with either the API call parameters or the WordPress media library configuration itself. This highlighted the need for careful debugging of both the client and server sides.

## 🧠 Key Concepts Learned

-   **CSS Specificity in PDF Generation**: I learned that for reliable font rendering in a library like `xhtml2pdf`, it's often necessary to use a high-specificity approach. Instead of relying on a single `body` rule, explicitly applying **`font-family` to all relevant CSS selectors** ensures the font is correctly inherited and rendered, overriding any default behaviors.
    
-   **API Integration Troubleshooting**: My experience with the WordPress REST API taught me that successful API integration isn't just about sending a request; it's also about validating the response. The failure to receive the expected data highlighted a need to either refine the API call or investigate the WordPress setup itself.
    
-   **Efficient Task Switching**: I gained practical experience in seamlessly switching from a long-term development task to an urgent, short-term project and back again, which is a crucial skill in a fast-paced work environment.

## 🔜 Next Steps

-   **PDF Cover Image System Fix**: My immediate focus will be to troubleshoot the WordPress API issue, investigate why images are not being returned, and then implement the user-selection feature.
    
-   **Shopify Task Documentation**: I will create a brief summary of the completed Shopify shipping fee setup for documentation purposes.


----------


# 📅 Day 01 (2025-08-04, Mon)

## 🎓 오늘 한 일

**📌 오전 개발 미팅에서 한국어/중국어 폰트 깨짐 문제와 오작동하는 PDF 커버 이미지 시스템에 대한 개선 계획을 공유하고, 개발 선임으로부터 격려와 공감을 얻었습니다.**   
**📌 폰트 패밀리를 다양한 CSS 선택자에 강제 적용하여 PDF 리포트의 폰트 깨짐 문제를 성공적으로 해결했습니다.**    
**📌 긴급 업무로 Shopify 프로젝트의 배송비 설정을 성공적으로 완료했습니다.**   
**📌 WordPress REST API를 사용해 커버 이미지를 가져오려는 시도가 실패했습니다. API가 지속적으로 대체 이미지나 빈 값을 반환했습니다.**  

### 상세 활동

**1. 오전 개발 미팅 및 피드백:**

-   **논의된 이슈**: PDF 리포트 생성 시 폰트를 지정했음에도 불구하고 한국어/중국어 텍스트가 계속 깨지는 문제, 그리고 WordPress에서 이미지를 가져오는 동적 커버 이미지 시스템이 제대로 작동하지 않는 현상을 보고했습니다.
    
-   **개선 계획**: 폰트 깨짐 문제를 해결하고, 커버 이미지를 가져오는 기능을 개선하는 동시에 사용자가 직접 이미지를 선택할 수 있도록 기능을 확장하는 방안을 제안했습니다.
    
-   **개발 선임 피드백**: 개발 선임은 폰트 문제에 대해 과거에 "강제 적용" 방식으로 해결한 경험이 있다며 공감했습니다. 커버 이미지 개선 제안에 대해서도 시도해보라고 격려했습니다.
    

**2. 핵심 프로젝트 버그 수정 및 문제 해결:**

-   **폰트 문제 해결**: `@font-face`나 `font-family` 지정만으로는 해결되지 않던 폰트 깨짐 문제를 해결했습니다.
    
    -   `body`, `table`, `td`, `th`, `p`, `h1`~`h3` 등 PDF에 사용되는 모든 HTML 요소에 **`font-family`를 강제로 적용**하여 폰트가 올바르게 렌더링되도록 했습니다.
        
-   **커버 이미지 API 실패**: WordPress REST API를 통해 특정 `media_category`의 이미지를 불러오려고 시도했습니다. 하지만 API는 예상 이미지 대신 항상 대체 URL이나 아무 이미지도 반환하지 않아, 기능이 제대로 작동하지 않는 것을 확인했습니다.
    

**3. Shopify 프로젝트 배송비 설정:**

-   **새로운 업무**: 개발 선임의 지시로 Shopify 프로젝트의 배송비 설정 업무를 긴급하게 진행했습니다.
    
-   **작업 내용**:
    
    -   기존 사이트에서 우편번호(Postcode)를 추출하여 우편번호 기반 배송 지역에는 **`Local delivery`**를 설정했습니다.
        
    -   WA, NT, TAS, ACT 등 주(State) 전체를 대상으로 하는 배송 지역에는 **`General shipping profile`**을 적용했습니다.
        
    -   제공받은 엑셀 파일의 요율을 기준으로 배송비를 정확하게 설정했습니다.
        
-   **결과**: 배송비 설정 작업을 성공적으로 완료했습니다.

## 💡 실전 시행착오 및 팁

-   **CSS 우선순위를 활용한 폰트 렌더링 문제 해결**: `xhtml2pdf`와 같은 PDF 렌더링 라이브러리에서 `@font-face`를 선언했음에도 불구하고 다국어 폰트가 깨지는 문제는 종종 CSS 우선순위 문제 때문입니다. **`body`, `p`, `h1`, `td` 등 모든 관련 선택자에 `font-family`를 명시적으로 적용**하여 기본 폰트 설정을 재정의하는 강제적인 접근법이 예상치 못한 렌더링 문제를 해결하는 확실한 방법임을 알게 되었습니다.
    
-   **외부 API 연동 실패 원인 파악**: WordPress REST API와 같은 외부 API를 연동할 때, API가 예상대로 작동할 것이라고 가정하는 것은 일반적인 함정입니다. **API 응답을 즉시 검증**하고, 예상 데이터가 반환되지 않으면 API 호출 파라미터나 WordPress 미디어 라이브러리 설정 자체에 문제가 없는지 디버깅해야 함을 배웠습니다. 이는 클라이언트와 서버 양쪽에서 신중한 디버깅이 필요하다는 것을 강조합니다.

## 🧠 배운 핵심 개념

-   **PDF 생성 시 CSS 우선순위**: `xhtml2pdf`와 같은 라이브러리 환경에서는 폰트 렌더링의 신뢰성을 높이기 위해 높은 우선순위의 CSS 적용이 필요함을 배웠습니다. `body`에만 폰트를 적용하기보다, **`font-family`를 모든 관련 CSS 선택자에 명시적으로 적용**하는 것이 예상치 못한 폰트 깨짐을 확실하게 방지하는 방법임을 깨달았습니다.
    
-   **API 연동 문제 해결**: WordPress REST API 연동 실패를 경험하며, API 통합은 요청을 보내는 것뿐만 아니라 응답을 검증하는 것의 중요성을 배웠습니다. 예상과 다른 응답을 받았을 때는 API 호출 자체를 개선하거나 WordPress 설정을 점검할 필요가 있음을 알게 되었습니다.
    
-   **효율적인 작업 전환**: 핵심 프로젝트와 긴급 프로젝트 사이를 유연하게 오가며 두 가지 업무를 모두 효율적으로 처리하는 실무 경험을 했습니다.

## 🔜 다음 계획

-   **PDF 커버 이미지 시스템 수정**: WordPress API가 이미지를 제대로 반환하지 않는 문제를 해결하고, 사용자가 직접 이미지를 선택할 수 있는 기능을 구현하는 작업을 계속 진행할 예정입니다.
    
-   **Shopify 작업 문서화**: 오늘 완료한 Shopify 배송비 설정 작업에 대한 간략한 기술 문서를 정리할 계획입니다.
