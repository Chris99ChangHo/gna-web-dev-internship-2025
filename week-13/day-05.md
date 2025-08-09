# 📅 Day 05 (2025-08-08, Fri)

## 🎓 What I Did Today

**📌 I had a meeting with my senior developer (Owen) and reported that the implemented features were stable enough for a full workflow test. We agreed that testing would begin once my documentation is complete.**   
**📌 I successfully resolved the PDF font rendering and image resolution issues and provided detailed documentation of the process.**   
**📌 I conducted a comprehensive documentation effort across the entire codebase, including internationalization (English comments) and updating project files to enhance readability and maintainability.**  

### Detailed Activities

1. Development Meeting & Documentation Status Update

-   **Meeting Summary**: I met with my senior developer, Owen, to discuss the final stages of the internship. I reported that the **fixed functionalities were in a stable state for a full workflow test**, even while documentation tasks are still ongoing.
    
-   **Agreement**: Owen asked me to inform him upon completion of the documentation, at which point he would initiate the overall system testing.
    

2. PDF Font Rendering and Image Resolution Fixes

I addressed and resolved the persistent font and image resolution problems encountered with `xhtml2pdf` and other libraries.

-   **Font Issue Resolution**:
    
    -   **Root Cause**: Korean fonts were not applying correctly in various rendering libraries (PIL/Pillow, `xhtml2pdf`, Matplotlib) due to issues with font file path resolution or system font cache registration.
        
    -   **Actions Taken**:
        
        1.  Improved `xhtml2pdf`'s **`link_callback`** to accurately resolve `file://` scheme, absolute, and relative paths, and to process only font file extensions.
            
        2.  Explicitly registered Noto Sans family fonts with **`ReportLab`** (`pdfmetrics.registerFont`) for internal use by `xhtml2pdf`.
            
        3.  Configured `Matplotlib` by adding fonts to `fontManager` and forcing font application via `rcParams`, also preventing negative sign corruption.
            
        4.  Ensured `Pillow`'s `ImageFont.truetype` used consistent Noto Sans KR paths for visual uniformity.
            
    -   **Result**: All text within the PDF (including main body, chart labels, cover/back cover text) now consistently uses the specified fonts, significantly improving readability and multi-language display stability.
        
-   **Image Resolution and Scaling Attempts**:
    
    -   **Goal**: To render cover/back cover images at a high resolution (approx. 4,770x3,318px at 300dpi) to "exactly" fill the content area (404x281mm) of an A3 landscape layout.
        
    -   **Approach**:
        
        1.  Implemented code to upscale source images to the target resolution and re-render text onto a high-resolution canvas to ensure text sharpness.
            
        2.  Introduced a "cover + center-crop" logic to fit background images without distortion while maintaining aspect ratio.
            
        3.  Applied a method of explicitly defining **physical dimensions** (`width:404mm; height:281mm`) in HTML/CSS to match the PDF layout.
            
    -   **Result and Limitation**: While the upscaling code itself functioned, the **physical size of the image in the final PDF did not increase as intended**. This is due to the PDF generator prioritizing CSS-defined physical dimensions (`mm` units). Text sharpness improved, but overall background image quality was limited by original detail.
        

3. Project Codebase Documentation

I performed extensive documentation efforts to enhance the project's readability, maintainability, and collaboration efficiency.

-   **Codebase Internationalization**: Translated all Korean comments and strings in key backend and frontend files (e.g., Python scripts, HTML templates, JavaScript files) to English.
    
-   **File-wise Role Descriptions**: Added header comments to major files, detailing their purpose, dependencies, and key functions.
    
-   **`README.md` Update**: Comprehensively updated `README.md` to include: Architecture Overview, Module Descriptions, Key Workflows (User Auth, Data Loading, PDF Generation, AI Summary), Local Development Setup, cPanel Deployment Procedures, and Security/Operations Notes.
    
-   **Comprehensive Document Creation**: Generated a holistic Markdown document (for Google Docs integration) detailing Architecture, Module Descriptions, Workflows, Setup, Deployment, Security, Limitations, and Roadmap.
    
-   **Directory Structure Documentation**: Documented the actual directory tree based on the cPanel deployment, specifying runtime data/log locations and Passenger-related files.
    
-   **Other Document Updates**: Reorganized and internationalized Google Ads documentation (`etc/google-ads.md`) and future improvement plans (`etc/Future Improvement.md`).
    
-   **WordPress Admin Page UX Enhancements**: Rewrote Security Features list to a "How to Use" guide, added "Open Dashboard" and "View Docs / View README" buttons, and unified visual styling.
    
-   **Key Changes Summarized**: Clarified JWT authentication, GA4 multi-tenancy status/plans, improved deployment/operations sections, and detailed the PDF pipeline.
    
-   **Deliverables Listed**: Outlined the specific documents created/updated (e.g., `README.md`, Word doc, various `etc/` files, WP Admin code snippets).

## 🧠 Key Concepts Learned

-   **Holistic Font Management**: I learned that for consistent font rendering across multiple PDF-generating libraries, it's crucial to **standardize and integrate font registration and path resolution methods** across all components.
    
-   **Distinction Between Image Resolution and Physical Size**: I gained a clear understanding that an image's **pixel resolution** is separate from its **physical printed size** in a PDF. Achieving precise layout requires explicitly defining physical dimensions (e.g., in `mm`) in CSS, regardless of source image pixel count.
    
-   **Strategic Value of Documentation**: Internationalizing the codebase and creating thorough, accessible documentation dramatically enhances a project's **collaborative efficiency** and **long-term maintainability**, providing strategic value beyond just technical implementation.

## 💡 Practical Trial-and-Error and Tips

-   **Deep Dive into Font Path Resolution**: When fonts fail to render, don't just check basic `@font-face` or `registerFont` calls; **thoroughly debug the `link_callback` (for `xhtml2pdf`) and similar mechanisms** that resolve font file paths at runtime, considering various path schemes.
    
-   **Matching Pixel and Physical Dimensions**: For precise image sizing in PDF generation, if you're upsizing an image in Python, remember that the PDF renderer often prioritizes CSS dimensions. **Ensure your Python-generated image's pixel dimensions are proportional to the CSS `mm` dimensions** you intend to use in the HTML template.

## 🔜 Next Steps

-   **Resolve Image Scaling Discrepancy**: I will consult with the manager to decide whether to adjust the A3 landscape layout size to match the generated image or to procure larger source images that fit the current PDF structure.
    
-   **Finalize and Share Documentation**: I will complete the remaining documentation tasks and share the finalized documents with Owen to enable him to begin the full system testing.
    
-   **Review Remaining Improvement Tasks**: I will review the items documented in `Future Improvement.md`, such as GA4 client mapping, frontend XSS hardening, and date logic, to prioritize potential next steps.

-	**WordPress Admin Page UX Improvements**: I rewrote the "Security Features" list as a "How to Use" guide and unified the visual style by adding "Open Dashboard" and "View Docs / View README" buttons. This is currently a **draft** and requires further revision before final implementation.

----------

# 📅 5일차 (2025-08-08, 금)

## 🎓 오늘 한 일

**📌 개발 선임(Owen)과 미팅을 가지고 현재 진행 중인 문서화 작업과 수정된 기능들의 테스트 준비 상태를 공유했습니다. 문서화가 끝나는 대로 전체 테스트를 시작하기로 합의했습니다.**   
**📌 PDF 생성 시 발생하는 폰트 렌더링 문제와 이미지 해상도 문제를 해결하고, 이 과정에 대한 상세 기록을 남겼습니다.**   
**📌 프로젝트의 가독성과 유지보수성을 극대화하기 위해 전체 코드베이스에 대한 국제화(주석 영문화) 및 광범위한 문서화 작업을 진행했습니다.**  

### 상세 활동

1. 개발 미팅 및 문서화 현황 공유

-   **미팅 내용**: 개발 선임(Owen)과 인턴십 마무리와 관련하여 대화를 나누었습니다. 현재 진행 중인 문서화 작업에 대해 보고했으며, **수정된 기능들이 큰 틀에서 전체 워크플로우 테스트를 진행하기에 문제 없는 상태**임을 보고했습니다.
    
-   **합의 사항**: 문서화 작업이 끝나는 대로 알려달라는 요청을 받았고, 그 후 전체 시스템 테스트를 시작하기로 합의했습니다.
    

2. PDF 폰트 렌더링 및 이미지 해상도 문제 해결

`xhtml2pdf`를 비롯한 다양한 라이브러리에서 발생하는 폰트 문제와 이미지 해상도 문제를 해결했습니다.

-   **폰트 문제 해결**:
    
    -   **원인**: PIL/Pillow, `xhtml2pdf`, Matplotlib 등 각 렌더링 라이브러리에서 폰트 파일 경로가 정확히 해석되지 않거나, 시스템 폰트 캐시에 등록되지 않아 한글 글꼴이 적용되지 않는 문제가 발생했습니다.
        
    -   **조치**:
        
        1.  `FontManager.validate_fonts()`를 통해 폰트 파일의 실제 존재 여부를 사전 검증했습니다.
            
        2.  `xhtml2pdf`의 `link_callback`을 개선하여 `file://` 스킴, 절대/상대 경로를 정확히 해석하고 폰트 파일 확장자만 처리하도록 강화했습니다.
            
        3.  `ReportLab`의 `pdfmetrics.registerFont` 및 `pdfmetrics.registerFontFamily`로 Noto Sans 계열 폰트들을 사전에 명시적으로 등록했습니다.
            
        4.  `Matplotlib`의 `fontManager.addfont` 및 `rcParams` 설정을 통해 폰트를 강제 적용하고 음수 부호 깨짐을 방지했습니다.
            
        5.  `Pillow`에서 `ImageFont.truetype` 사용 시에도 동일한 폰트 경로를 사용하도록 일관성을 확보했습니다.
            
    -   **결과**: PDF 내 텍스트, 차트 라벨, 커버/백커버 텍스트 모두 지정 폰트가 안정적으로 적용되어 다국어 표시 안정성과 가독성이 크게 향상되었습니다.
        
-   **이미지 해상도 및 크기 확대 시도**:
    
    -   **목표**: A3 가로 레이아웃(420×297mm)에서 마진(8mm)을 제외한 콘텐츠 영역(404×281mm)을 고해상도 이미지(300dpi 기준 약 4,770×3,318px)로 "정확히" 채우고 싶었습니다.
        
    -   **시도**:
        
        1.  원본 이미지를 목표 해상도로 업스케일하고, 텍스트를 고해상도 캔버스에 다시 렌더링하여 텍스트 선명도를 확보하는 코드를 구현했습니다.
            
        2.  원본 배경의 종횡비가 다를 때 왜곡 없이 꽉 차게 맞추기 위해 "cover + center-crop" 로직을 도입했습니다.
            
        3.  HTML/CSS에서 `width:404mm; height:281mm`와 같이 물리적 크기를 명시하여 PDF 레이아웃에 정확히 일치시키는 방식을 적용했습니다.
            
    -   **결과 및 한계**: 업스케일 코드는 정상 작동했지만, **실제 PDF 결과물에서 이미지의 물리적 크기는 커지지 않았습니다.** 이는 PDF 생성기가 HTML/CSS 레이아웃(특히 `mm` 단위)을 우선하기 때문입니다. 텍스트 선명도는 향상되었으나, 배경 이미지 품질은 원본의 한계 내에서만 개선되었습니다.
        

3. 프로젝트 코드베이스 문서화

프로젝트의 가독성, 유지보수성, 협업 효율성을 극대화하기 위한 광범위한 문서화 작업을 진행했습니다.

-   **주석 영문화**: 백엔드/프런트엔드 주요 파일(`app.py`, `auth_service.py`, `ga4_service.py`, `pdf_generator.py`, `seranking_service.py`, `utils.py`, `wp_auth.py`, `passenger_wsgi.py`, `index.html`, `report_full_document.html`, `static/js/*`) 내의 모든 한국어 주석과 문자열을 영어로 번역했습니다.
    
-   **파일별 역할 설명**: 모든 주요 파일에 헤더 주석을 추가하여 파일의 목적, 주요 의존성, 핵심 함수를 상세히 설명했습니다.
    
-   **`README.md` 업데이트**: 아키텍처 개요, 모듈 설명, 핵심 워크플로우(사용자 인증, 데이터 로딩/표시, PDF 보고서 생성, AI 요약 생성)를 상세히 문서화했습니다. 또한 기술 스택, cPanel 배포 절차, 보안/운영 노트 등 프로젝트 설정 및 관리에 필요한 모든 정보를 최신화했습니다.
    
-   **종합 문서 생성**: Google Docs에 쉽게 붙여넣기 가능한 마크다운 형식으로 아키텍처 개요, 모듈 상세 설명, 워크플로우, 설정/배포 가이드 등을 포함하는 종합 문서를 생성했습니다.
    
-   **디렉토리 구조 정리 및 문서화**: cPanel 배포본 기준의 실제 디렉토리 트리를 문서화하고, 런타임 데이터/로그 관리 방안을 명시했습니다.
    
-   **기타 문서 업데이트**: Google Ads 관련 비활성/계획 문서(`etc/google-ads.md`)와 향후 개선 계획(`etc/Future Improvement.md`)을 영문화 및 정리했습니다.
    
-   **WordPress Admin 페이지 UX 개선**: 보안 기능 목록을 "How to Use" 중심으로 재작성하고, "Open Dashboard", "View Docs / View README" 버튼 추가 등 시각적 스타일을 통일했습니다.

## 🧠 배운 핵심 개념

-   **통합적인 폰트 관리의 중요성**: PDF 생성 과정에서 여러 폰트 렌더링 라이브러리(`xhtml2pdf`, `Matplotlib`, `Pillow`)가 사용될 때, 각 라이브러리의 폰트 등록 방식과 **경로 해석 방식**을 통일하고 통합적으로 관리하는 것이 안정적인 폰트 적용의 핵심임을 배웠습니다.
    
-   **레이아웃과 해상도의 분리**: 이미지의 **픽셀 해상도**와 PDF 내에서 **보이는 물리적 크기**는 분리된 개념입니다. 고해상도 이미지를 생성하는 것과 별개로, CSS에서 `mm` 단위로 물리적 크기를 명시해야 원하는 레이아웃을 정확히 구현할 수 있다는 것을 명확히 이해했습니다.
    
-   **문서화의 전략적 가치**: 코드 주석의 국제화부터 상세한 `README` 및 종합 문서 작성까지, 프로젝트 문서를 최신화하고 명확히 하는 작업이 프로젝트의 **협업 효율성**과 **유지보수성**을 극적으로 향상시키는 전략적 가치가 있음을 체감했습니다.

## 💡 실전 시행착오 및 팁

-   **폰트 경로 해석 문제 해결**: `xhtml2pdf`에서 폰트가 적용되지 않을 때, 단순히 `@font-face`나 `pdfmetrics.registerFont`를 확인하는 것을 넘어 **`link_callback`이 폰트 파일 경로를 정확히 해석하는지**를 심층적으로 디버깅해야 합니다.
    
-   **이미지 스케일링의 시각적 착각**: 파이썬에서 이미지를 고해상도로 업스케일했더라도, PDF 라이브러리가 HTML/CSS의 `mm` 단위 물리적 크기를 우선한다면 시각적으로 이미지가 커지지 않을 수 있습니다. **생성된 이미지 픽셀 크기와 PDF CSS의 물리적 크기를 일치시키는 것**이 중요합니다.

## 🔜 다음 계획

-   **이미지 크기 문제 최종 해결**: 매니저와 상의하여 A3 가로 레이아웃 크기를 생성되는 이미지에 맞게 조정할지, 아니면 커버 이미지를 현재 PDF 구조에 맞게 크게 제작할지 결정하고 해당 작업을 진행할 것입니다.
    
-   **문서화 최종 완료 및 공유**: 현재 진행 중인 문서화 작업을 마무리하고, 개발 선임에게 최종 결과물을 공유하여 테스트를 시작할 수 있도록 할 것입니다.
    
-   **남은 개선 과제 검토**: GA4 클라이언트 매핑 구현, 프런트엔드 XSS 하드닝, 날짜 로직 개선 등 `Future Improvement.md`에 문서화된 남은 과제들을 검토하고 우선순위를 정할 것입니다.

-	**WordPress Admin 페이지 UX 개선**: 보안 기능 목록을 "How to Use" 중심으로 재작성하고, "Open Dashboard", "View Docs / View README" 버튼을 추가하는 등 시각적 스타일을 통일했습니다. 이 작업은 현재 **초안**이며, 최종 반영 전에 추가적인 수정이 필요합니다.
    
