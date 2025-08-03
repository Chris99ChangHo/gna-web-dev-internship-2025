# 📅 Day 05 (2025-08-01, Fri)

## 🎓 What I Did Today

**📌 In a development meeting, I presented a plan to add Korean and Chinese language support to the PDF report and to use dynamic cover images from WordPress. I received feedback to optimize performance and to proceed with improvements after a successful test run.**   
**📌 My attempts to fix font and image loading issues in the PDF generation process using Base64 embedding failed to produce a working result due to limitations with the `xhtml2pdf` library.**   


### Detailed Activities

**1. Development Meeting & Work Plan Discussion:**

-   **Reported Progress:**
    
    -   I reported my plan to improve PDF reports to **support multiple languages (Korean, Chinese, etc.)** based on yesterday's feedback from the manager.
        
    -   I also mentioned my intention to implement the senior developer's feedback: **dynamically fetching cover images from WordPress media files** and, if possible, allowing users to select them.
        
    -   I stated that I would build a test version for both features today, and if successful, proceed with the improvements in that direction.
        
-   **Feedback & Directives:**
    
    -   I was asked to report the results if successful.
        
    -   I was told to ask for help if needed.
        
    -   It was also emphasized that if the system becomes too slow due to overload, it's better to optimize it by trying different modules or tech stacks, as the goal is convenience, not endless waiting.
        

**2. PDF Multi-Language Fonts and Image Loading Issue Resolution Attempts:**

-   **Multi-language Font Base64 Embedding System Implementation:**
    
    -   **Problem:** Korean and Chinese text appeared broken in the PDF output.
        
    -   **Attempt:** I implemented a system to convert font files to Base64 and embed them directly into the HTML template to bypass file system issues.
        
    -   **Result:** **Noto Sans**, **Noto Sans KR**, and **Noto Sans SC** were all perfectly embedded as Base64, but the text corruption issue in the PDF output was not solved.
        
-   **WordPress Image Base64 Encoding and Loading:**
    
    -   **Problem:** Images from WordPress did not display correctly in the PDF.
        
    -   **Attempt:** Instead of using URLs, I tried fetching the image data in Python, encoding it in Base64, and embedding it directly into the HTML template.
        
    -   **Result:** All WordPress images were confirmed to be loaded successfully as Base64 encoded data, but they still did not appear in the final PDF output.
        
### ❌ Unsuccessful Attempts

-   **Image Compression/Optimization:**
    
    -   **Suggestion:** Shrink image sizes, convert to WebP, etc.
        
    -   **Not Reflected:** Since the images were already loading successfully, this was deprioritized.
        
-   **Image Caching System:**
    
    -   **Suggestion:** Cache Base64 images for reuse.
        
    -   **Not Reflected:** This conflicted with the requirement for a new random cover image each time.
        

## 🧠 Key Concepts Learned

-   **Using Base64 Encoding:** Confirmed it's an effective way to remove file system path dependencies and safely transfer binary data. Learned it's especially useful for **embedding images and font files directly into HTML** to bypass file path issues during PDF generation.
    
-   **Runtime Environment Control with `os.environ`:** Learned to dynamically control thread settings in a Python script's execution environment using `os.environ` variables. This is a crucial optimization technique for **preventing process termination issues** caused by multi-threading in resource-limited environments like cPanel.
    
-   **`xhtml2pdf` Limitations:** The `xhtml2pdf` library had **compatibility issues**, failing to fully render Base64-encoded images and font data. This suggests that the library itself has limitations, and its method of parsing HTML and applying CSS for PDF conversion may not be fully compatible with modern web technologies.
    

## 💡 Practical Trial-and-Error and Tips

-   **WP Plugin and External Integration Limitations:** I tried to use a WordPress plugin to set up image categories and load random cover images, but it didn't work. This happened because the plugin's PHP functions and shortcodes were not compatible with the external API call environment. This taught me that a **direct API approach for managing image data is more stable**.
    
-   **Complexity of Environment-Specific Font Paths:** I implemented logic to handle different font paths for Windows and Linux (cPanel), but ultimately learned that embedding font data directly with Base64 is the most reliable way to solve file path dependency issues.
    
-   **Importance of Debugging Logs:** Using `app.logger.debug` to print the size of the image and font data was crucial for verifying if the data was successfully passed to `pdf_generator.py`. This was a huge help in **clearly distinguishing where the problem was occurring (data loading vs. PDF conversion)**.
    
-   **Limitations of Older Libraries:** Older libraries like `xhtml2pdf` may not fully support modern web standards. This can lead to unexpected bugs, especially in **multi-language font rendering and Base64 image display**. In such cases, it is a good idea to consider alternative, more robust libraries like `WeasyPrint` or using a Headless Chrome instance with `Playwright`.
    
    
## 🔜 Next Steps

-   **Evaluate Alternative PDF Conversion Libraries:** To solve the issue of images and fonts not rendering correctly, I will research and test **more powerful PDF conversion libraries** like `WeasyPrint` or using Headless Chrome.
    
-   **Reattempt Dynamic PDF Cover Image Implementation:** Since WordPress images are now loading successfully, I will try again to **dynamically apply them as the background for the PDF cover**.
    
-   **Re-analyze Base64 Issues in `xhtml2pdf`:** If switching libraries is difficult, I will conduct a deeper investigation into the **specific reasons why Base64-encoded images and fonts are not being applied** in `xhtml2pdf` by reviewing its documentation and community.


----------


# 📅 5일차 (2025-08-01, 금)

## 🎓 오늘 한 일

**📌 개발 미팅에서 PDF 리포트의 다국어 지원 및 동적 커버 이미지 기능 구현 계획을 공유하고, 성능 최적화에 대한 피드백을 받았습니다.**   
**📌 PDF 생성 과정에서 폰트 깨짐 및 이미지 로딩 문제를 해결하기 위해 Base64 임베딩을 시도했으나, `xhtml2pdf`의 한계로 인해 최종 결과물에는 반영되지 않았습니다.**   

### 상세 활동

**1. 개발 미팅 및 작업 계획 공유:**

-   **보고 사항:**
    
    -   어제 매니저님 피드백을 반영하여 PDF 리포트에 **한국어, 중국어 등 다국어를 지원**하도록 개선하는 계획을 보고했습니다.
        
    -   개발 선임의 피드백이었던 **WordPress 미디어 파일에서 커버 이미지를 가져와 동적으로 적용**하고, 가능하면 사용자가 선택할 수 있는 기능까지 구현해볼 예정임을 밝혔습니다.
        
    -   두 기능 모두 오늘 테스트 버전을 만들어 실행해보고, 성공하면 해당 방향으로 개선을 진행하겠다고 보고했습니다.
        
-   **피드백 및 지시 사항:**
    
    -   두 기능의 테스트 결과를 보고해달라는 요청을 받았습니다.
        
    -   도움이 필요하면 언제든지 요청하라고 했습니다.
        
    -   기능 구현 시 **성능 저하로 인해 시스템이 느려지면 다른 모듈이나 기술 스택을 시도**하여 최적화하는 것이 중요하다고 강조했습니다. (편의를 위해 만드는 시스템이 너무 느리면 안 된다는 점을 지적했습니다.)
        

**2. PDF 다국어 폰트 및 이미지 로딩 문제 해결 시도:**

-   **다국어 폰트 Base64 임베딩 시스템 구현:**
    
    -   **문제:** PDF 결과물에 한국어/중국어 텍스트가 깨져 보이는 문제가 있었습니다.
        
    -   **시도:** 폰트 파일을 Base64로 변환하여 HTML 템플릿에 직접 임베딩하는 시스템을 구현했습니다.
        
    -   **결과:** `Noto Sans`, `Noto Sans KR`, `Noto Sans SC` 세 가지 폰트가 Base64로 완벽하게 변환되었지만, PDF 변환 시 텍스트 깨짐 문제는 해결되지 않았습니다.
        
-   **WordPress 이미지 Base64 인코딩 및 로딩:**
    
    -   **문제:** WordPress에서 가져온 이미지가 PDF에 정상적으로 표시되지 않는 문제가 있었습니다.
        
    -   **시도:** 이미지를 Python에서 가져와 Base64로 인코딩한 후 HTML 템플릿에 직접 삽입했습니다.
        
    -   **결과:** 모든 WordPress 이미지가 Base64로 정상적으로 인코딩되는 것을 확인했으나, PDF 변환 후 최종 결과물에는 이미지가 나타나지 않았습니다.

### ❌ 시도했지만 반영되지 않은 것들

-   **이미지 압축/최적화**: 이미지 크기 축소나 WebP 변환 등을 제안했지만, 이미지가 이미 정상적으로 Base64 인코딩되어 넘어오는 것을 확인하여 우선순위에서 밀렸습니다.
    
-   **이미지 캐싱 시스템**: 매번 새로운 랜덤 커버 이미지를 가져와야 하는 요구사항과 충돌하여 캐싱 시스템은 반영하지 않았습니다.
- 

## 🧠 배운 핵심 개념

-   **`Base64` 인코딩의 활용**: 파일 시스템 경로 의존성을 제거하고 바이너리 데이터를 안전하게 전달하는 효과적인 방법입니다. 특히, PDF 생성 시 **이미지나 폰트 파일을 직접 HTML에 삽입하여 파일 경로 문제를 우회하는 데 유용**하다는 것을 배웠습니다.
    
-   **`os.environ`을 이용한 런타임 환경 제어**: `os.environ` 변수를 통해 Python 스크립트의 스레드 설정을 동적으로 제어하는 방법을 습득했습니다. 이는 cPanel과 같은 리소스 제한 환경에서 **멀티 스레딩으로 인한 프로세스 종료 문제를 방지**하는 중요한 최적화 기법입니다.
    
-   **`xhtml2pdf`의 한계**: `xhtml2pdf` 라이브러리가 Base64로 인코딩된 이미지나 폰트 데이터를 완벽하게 렌더링하지 못하는 **호환성 문제**를 겪었습니다. 이는 라이브러리 자체의 한계일 수 있으며, PDF 변환을 위해 HTML을 파싱하고 CSS를 적용하는 방식이 최신 웹 기술과 완전히 호환되지 않을 수 있음을 시사합니다.


## 💡 실전 시행착오 및 팁

-   **WP 플러그인과 외부 연동의 한계**: WordPress 플러그인을 활용해 이미지 카테고리를 설정하고 랜덤으로 이미지를 불러오는 기능을 구현하려 했으나, 외부 시스템(Flask 앱)과의 연동 과정에서 해당 기능이 제대로 작동하지 않았습니다. 이는 플러그인이 제공하는 PHP 함수나 Shortcode가 외부 API 호출 환경과 호환되지 않아 발생한 것으로 보이며, **직접 API를 통해 이미지 데이터를 관리하는 방식**이 더 안정적임을 깨달았습니다.
    
-   **환경별 폰트 경로 설정의 복잡성**: Windows와 Linux(cPanel) 환경의 폰트 경로를 분기 처리하는 로직을 구현했지만, 최종적으로 폰트 데이터 자체를 Base64로 임베딩하는 것이 파일 경로 의존성 문제를 가장 확실하게 해결하는 방법임을 깨달았습니다.
    
-   **디버깅 로그의 중요성**: `app.logger.debug`를 활용해 이미지와 폰트 데이터의 크기를 출력하는 것은, 데이터가 `pdf_generator.py`까지 정상적으로 전달되었는지 확인하는 데 결정적인 역할을 했습니다. 이는 문제가 **데이터 로딩 단계**와 **PDF 변환 단계** 중 어디서 발생하는지 명확히 구분하는 데 큰 도움이 되었습니다.
    
-   **오래된 라이브러리의 한계**: `xhtml2pdf`와 같은 일부 오래된 라이브러리는 다국어 폰트 처리나 Base64 이미지 렌더링에서 예상치 못한 버그를 일으킬 수 있습니다. 이 경우, `WeasyPrint`나 `Playwright`를 사용하는 등 **더 강력하고 현대적인 PDF 변환 라이브러리를 고려**하는 것이 좋습니다.


## 🔜 이후 학습 방향

-   **`xhtml2pdf` 대체 라이브러리 검토**: `xhtml2pdf`의 한계로 인해 PDF에 이미지와 폰트가 올바르게 표시되지 않는 문제를 해결하기 위해, `WeasyPrint` 또는 Headless Chrome을 사용하는 등 **더 강력한 PDF 변환 라이브러리를 리서치하고 테스트**할 예정입니다.
    
-   **PDF 커버 이미지 동적 적용 기능 재시도**: WordPress 이미지 로딩은 성공했으므로, **해당 이미지를 PDF 커버의 배경으로 동적으로 적용하는 기능**을 다시 시도할 것입니다.
    
-   **`xhtml2pdf`에서의 Base64 문제 재분석**: 대체 라이브러리 전환이 어렵다면, 현재 `xhtml2pdf`에서 Base64로 인코딩된 이미지와 폰트가 적용되지 않는 **구체적인 원인을 파악하기 위해 관련 문서와 커뮤니티를 더 깊이 조사**할 것입니다.
