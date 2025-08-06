# 📅 Day 02 (2025-08-05, Tue)

## 🎓 What I Did Today

**📌 I started my day's work without a development meeting, focusing on the design and rendering of the Report PDF cover and back cover.**   
**📌 I successfully implemented the PDF cover image selection feature using `xhtml2pdf` but am struggling with rendering issues related to image resolution and text overlay.**   
**📌 Despite attempts to overcome the CSS limitations of `xhtml2pdf`, my efforts to place text over an image have failed.**   
**📌 I organized security best practices for safely managing sensitive data and separating logs for development and production environments. Documentation will be needed in the future.**  

## Detailed Activities

1. Troubleshooting PDF Cover/Back Cover Rendering

I've been trying to solve the design challenges encountered with PDF covers and back covers by understanding the specific characteristics of the `xhtml2pdf` library.

-   **Failure to Fill a Full Page with Small Images**: I confirmed that `xhtml2pdf` **does not force-scale images beyond their original pixel size**. I am considering using high-resolution images for the A3 landscape format or a "frame cover" design that compromises by centering a smaller image. I've also run into problems with responsive CSS units not working correctly.
    
-   **Failure to Overlay Text on Images**: I attempted to solve the issue of `z-index` and `position` not working as flexibly as they do in a browser, but **my efforts to print text over an image ultimately failed.** The structural limitations of a `table`-based layout are making it extremely difficult to achieve the desired overlay effect.
    
-   **Readability and Text Alignment Issues**: Separate from the font corruption problem, the issue of text being unreadable on top of bright background images remains unsolved. I attempted to improve readability with **`text-shadow`** and force center alignment using **`width:100%` with inline styles**, but these solutions have not been successful.
    

2. Organizing `xhtml2pdf` CSS Limitations & Know-how

I've been organizing notes and code snippets on why `xhtml2pdf` behaves differently from a browser.

-   I confirmed that `z-index` only works for **very basic layer stacking** in combination with `position: absolute/relative`.
    
-   I documented that modern CSS features like `flex` and `grid` are not supported, so using a simple HTML structure with `mm`, `pt` units, and inline styles is recommended. This information has not yet been formally documented.
    

3. Strengthening Production Log Security

I've organized security best practices for managing sensitive information in production environments into code.

-   **Blocking Sensitive Information**: I've applied a principle in the code to ensure that original values for passwords, tokens, and personal data are not left in `console.log` or the logger.
    
-   **Masking and Tokenization**: If logging is unavoidable, I have decided to apply masking (e.g., `"us**@ho**.com"`) or log only a reference ID.
    
-   **Separating Log Levels**: I've organized the code to strictly separate log levels, allowing only essential logs like `INFO`, `WARN`, and `ERROR` in production, while permitting detailed `DEBUG` and `TRACE` logs in development.
    
-   **Deployment Management**: I have discussed plans to manage environment variables using separate files like `.env.production` and `.env.development`.

## 🧠 Key Concepts Learned

-   **Understanding Library-Specific Rendering Engine Characteristics**: I have come to a deeper understanding that `xhtml2pdf` has **different rendering rules than a web browser**. The limitations on image resizing and the restricted support for `position` and `z-index` have taught me that it's crucial to understand a library's unique characteristics before attempting to code, rather than just treating it as a coding problem.
    
-   **Practical Log Security Best Practices**: I've re-confirmed the importance of preventing sensitive information from appearing in logs from the very start. I feel the need to establish a systematic security process including **masking, tokenization, and environment-specific log levels**, and I have begun organizing the code for this purpose. I plan to document this work in the future.

## 💡 Practical Trial-and-Error and Tips

-   **PDF Image Size and Responsive Unit Issues**: I've faced the problem of relative units like `width:100%` and other responsive units not working correctly in `xhtml2pdf`, which prevents images from scaling beyond their original size. This experience taught me that for `xhtml2pdf`, it's much more stable to prepare **fixed, high-resolution images** rather than relying on responsive design.
    
-   **Difficulty Implementing Layered Overlays**: I spent a significant amount of time trying to get `z-index` and `position: absolute` to produce the desired overlay effect, but the text would not appear over the image. I realized this is a fundamental problem resulting from a combination of the `table`-based HTML structure and the limited CSS support of `xhtml2pdf`, making it a problem that cannot be solved with simple CSS properties.

## 🔜 Next Steps

-   **Re-evaluating Overlay Design for `xhtml2pdf`**: Since my previous approach to placing text over an image failed, I will explore other design patterns that work within the limitations of `xhtml2pdf` (e.g., a frame design where the image is a background and text is placed next to it).
    
-   **Documenting Log Security Best Practices**: I will finalize the security code I've organized and formally document the sensitive information logging best practices to share with the team.

----------

# 📅 2일차 (2025-08-05, 화)

## 🎓 오늘 한 일

** 📌오늘은 개발 미팅 없이 바로 업무를 시작하여, Report PDF 커버/백커버 디자인 및 렌더링 작업을 하였습니다. **   
**📌 `xhtml2pdf`를 활용한 PDF 커버 이미지 선택 기능 구현은 성공했으나, 이미지 해상도 및 텍스트 오버레이 문제로 인해 디자인 렌더링에 어려움을 겪고 있습니다.**    
**📌 `xhtml2pdf`의 CSS 지원 한계를 파악하고 이를 극복하려 했지만, 이미지 위에 텍스트를 올리는 기능 구현은 실패했습니다.**   
**📌 개발/운영 환경에서 민감 정보를 안전하게 관리하고 로그를 분리하기 위한 보안 베스트 프랙티스들을 코드로 정리했습니다. 추후 문서화가 필요합니다.**  

### 상세 활동

1. PDF 커버/백커버 렌더링 문제 해결 시도

`xhtml2pdf`의 특성을 파악하며 PDF 커버/백커버 디자인 시 발생하는 문제들을 해결하려 시도했습니다.

-   **작은 이미지로 풀페이지 채우기 실패 문제**: `xhtml2pdf`는 **원본 이미지 픽셀 크기 이상으로 강제로 늘리지 않는** 한계를 확인했습니다. A3 사이즈에 맞는 고해상도 이미지를 사용하거나, 작은 이미지를 중앙에 배치하는 "프레임 커버" 디자인으로 타협하는 방법을 고려 중입니다. 특히 CSS 반응형 단위가 제대로 적용되지 않는 문제가 있었습니다.
    
-   **이미지 위 텍스트 오버레이 실패 문제**: `z-index`와 `position` 속성이 브라우저처럼 자유롭게 작동하지 않는 문제를 해결하려 했지만, **결과적으로 이미지 위에 텍스트를 겹쳐서 출력하는 데 실패했습니다.** `table` 기반의 구조적 한계 때문에 원하는 오버레이 효과를 구현하는 데 큰 어려움을 겪고 있습니다.
    
-   **텍스트 가독성 및 중앙 정렬 문제**: 폰트 깨짐 문제와는 별개로, 밝은 배경 이미지 위에 텍스트가 잘 보이지 않는 문제는 **`text-shadow`** 등을 사용해 가독성을 높이고, **`width:100%`와 인라인 스타일**로 중앙 정렬을 시도했으나, 이는 최종적으로 해결되지 않은 문제입니다.
    

2. `xhtml2pdf` CSS 지원 한계 및 노하우 정리

`xhtml2pdf`가 브라우저와 다르게 작동하는 이유에 대한 노하우들을 코드 정리 및 메모 형식으로 남겼습니다.

-   `z-index`는 `position: absolute/relative`와 함께 **매우 기본적인 레이어 쌓기**까지만 작동함을 확인했습니다.
    
-   `flex`, `grid` 등 최신 CSS 기능은 지원하지 않으므로, 최대한 단순한 HTML 구조와 `mm`, `pt` 단위, 그리고 인라인 스타일 사용을 권장한다는 내용을 정리했습니다. 이는 아직 문서화되지 않은 상태입니다.
    

3. 운영 환경 로그 보안 강화

운영 환경에서 민감 정보를 안전하게 관리하기 위한 보안 베스트 프랙티스를 코드로 정리했습니다.

-   **민감 정보 로그 차단**: 패스워드, 토큰, 개인정보 등은 `console.log`나 `logger`에 원본 값을 남기지 않도록 하는 원칙을 코드로 적용했습니다.
    
-   **마스킹 및 토큰화**: 불가피하게 로그가 필요할 경우, `us**@ho**.com`처럼 일부를 마스킹하거나 참조 ID만 남기는 방식을 적용하기로 했습니다.
    
-   **로그 레벨 분리**: 운영 환경에서는 `INFO`, `WARN`, `ERROR` 등 필수 로그만 남기고, 개발 환경에서만 `DEBUG`, `TRACE` 로그를 허용하도록 엄격하게 분리하는 코드를 정리했습니다.
    
-   **배포 환경 관리**: `.env.production`와 `.env.development`처럼 환경 변수 파일을 분리하여 관리하는 방안을 논의했습니다.

## 🧠 배운 핵심 개념

-   **라이브러리별 렌더링 엔진 특성 이해**: `xhtml2pdf`는 **브라우저와 다른 렌더링 규칙을 가진다**는 점을 깊이 깨달았습니다. 특히 이미지 크기 조절의 한계와 `position`, `z-index`의 제한적인 지원은 단순한 코딩 문제를 넘어, 라이브러리 고유의 특성을 파악하고 접근해야 한다는 중요한 교훈을 주었습니다.
    
-   **실전 로그 보안 베스트 프랙티스**: 민감 정보가 로그에 남지 않도록 관리하는 것이 얼마나 중요한지 다시 한번 확인했습니다. **마스킹, 토큰화, 환경별 로그 레벨 분리**와 같은 체계적인 보안 프로세스 구축의 필요성을 느꼈고, 이를 위한 코드 정리를 시작했습니다. 추후 문서화 작업을 진행할 계획입니다.

## 💡 실전 시행착오 및 팁

-   **PDF 이미지 크기 및 반응형 단위 문제**: `<img>`의 `width:100%` 같은 상대적 단위나 반응형 단위가 `xhtml2pdf`에서 제대로 작동하지 않아, 원본 이미지 크기 이상의 확대가 불가능하다는 문제에 부딪혔습니다. 이 경험을 통해 `xhtml2pdf`를 사용할 때는 반응형 디자인보다는 **고정된 고해상도 이미지**를 준비하는 것이 훨씬 안정적이라는 교훈을 얻었습니다.
    
-   **레이어 겹침 구현의 어려움**: `z-index`와 `position: absolute`를 적용해도 원하는 대로 이미지 위에 텍스트가 올라오지 않는 문제로 많은 시간을 보냈습니다. 이는 `table` 기반의 HTML 구조와 `xhtml2pdf`의 제한적인 CSS 지원이 복합적으로 작용한 결과로, 단순한 CSS 속성으로는 해결하기 어려운 근본적인 문제임을 깨달았습니다.

## 🔜 다음 계획

-   **`xhtml2pdf` 기반의 오버레이 디자인 재검토**: 이미지 위에 텍스트를 올리는 기존 방식이 실패했으므로, `xhtml2pdf`의 한계를 고려한 다른 디자인 패턴(예: 이미지를 배경으로 넣고 텍스트를 그 옆에 배치하는 프레임형 디자인)을 찾아보고 구현을 시도할 것입니다. 
    
-   **로그 보안 베스트 프랙티스 문서화**: 코드 정리를 마친 민감 정보 로그 보안 관련 내용을 공식 문서로 정리하여 팀에 공유할 계획입니다.
