# 📅 Day 04 (2025-08-07, Thu)

## 🎓 What I Did Today

**📌 With my senior developer in a meeting, I started my workday immediately.**  
**📌 I completed the manual registration for **8 Shopify products** that failed during the initial CSV migration.**   
**📌 The Shopify automation script, which was running since Wednesday, successfully finished. After loading **2,348 completed variants** from a checkpoint, the final part of the job processed in **52.5 minutes**.  
**📌 I began documenting the Report project and encountered a renewed Korean font rendering issue. I also received feedback to scale the cover and back cover images to fill the entire page, a task that is currently in progress.**  

### Detailed Activities

1. Morning Tasks & Shopify Automation/Manual Completion

-   **No Formal Meeting**: My day began without a formal development meeting, as my senior developer, Owen, had a client meeting.
    
-   **Shopify Automation Completed**: The `setting all locations to all products` script, which had been running since Wednesday, successfully finished. The script loaded **2,348 completed variants** from a checkpoint file, resuming the job and processing the remaining tasks in **52.5 minutes**.
    
-   **Manual Product Registration**: Following the automated process, I manually registered the **8 specific products** that failed to migrate during the initial CSV upload, resolving the last remaining migration issues.
    

2. Troubleshooting Font Rendering & Layout Issues

-   **Recurring Korean Font Issue**: The Korean font rendering problem resurfaced, and the previous solution, which involved **forcing the font, is no longer effective**. I'm now seeking a more fundamental fix, as the problem appears more complex than initially thought.
    
-   **Cover/Back Cover Image Scaling Feedback**: I received feedback that the cover and back cover images need to fill the entire page. I've begun working on this, using `@page` settings and the `table`-based structure to expand the images to the full page size.
    
-   **Fixed Previous Layout Errors**: While troubleshooting, I successfully resolved two prior layout errors. The `TypeError` caused by `@page :first` was fixed by switching to a more stable **"named page style" (`@page cover`)**, and a `LayoutError` in the table of contents was corrected by adjusting its top margin.
    

3. Project Documentation

-   **Documentation Start**: With the Shopify tasks completed, I shifted my focus to documenting the Report project. I cleaned up unnecessary files, began converting comments to English, and started planning the `README` file, which will include the directory structure.

## 🧠 Key Concepts Learned

-   **Reliability of Automation & Checkpoints**: I confirmed the importance of implementing **checkpoint files** for large-scale automation scripts. This allows a job to be paused and resumed, ensuring reliability even if the script is interrupted.
    
-   **Transience of Solutions**: My experience with the font issue has taught me that a solution that works once may not be permanent. For a library like `xhtml2pdf`, it's more crucial to **understand the underlying rendering principles** than to rely on simple, surface-level fixes.
    
-   **Iterative Design in Development**: Receiving new feedback like "make the image full-page" shows that a **design-centric deliverable like a PDF report requires an iterative process** of continuous refinement and optimization based on feedback.

## 💡 Practical Trial-and-Error and Tips

-   **Avoid One-Off Fixes**: Instead of relying on one-off code or tricks that work momentarily, it's more effective in the long run to **thoroughly follow the official documentation and best practices** for a library to ensure stability.
    
-   **Flexible Design Strategy**: Design-related feedback can introduce unexpected variables. My tip is to **keep a flexible structure in mind from the initial design phase** to make it easier to accommodate changes later on.

## 🔜 Next Steps

-   **Resume Font Fix**: I will restart the font fixing process. This will involve registering fonts and a "fake bold" feature in Python, and then re-adding the `@font-face` declaration and the `link_callback` in the code to ensure a solid font link.
    
-   **Implement Full-Page Image Scaling**: I will complete the work of scaling the cover and back cover images to fill the entire page, based on the feedback I received.
    
-   **Project Documentation**: I will finish cleaning up unnecessary files and converting comments to English, then create the final `README` file, including the directory structure.

----------

# 📅 4일차 (2025-08-07, 목)

## 🎓 오늘 한 일

**📌 개발 선임의 미팅으로 별도 미팅 없이 바로 업무를 시작했습니다.**  
**📌 초기 상품 마이그레이션 중 CSV 이슈로 실패했던 **8건의 Shopify 상품**을 수동으로 등록하여 처리를 완료했습니다.**  
**📌 수요일부터 실행한 Shopify 자동화 스크립트가 성공적으로 완료되었음을 확인했습니다. **체크포인트에서 2,348개의 완료 항목을 로드**한 후, 남은 작업을 **52.5분 만에** 처리했습니다.**  
**📌 PDF 생성 중 한글 폰트 렌더링 문제가 재발생해 해결을 시도했으며, 동시에 커버와 백커버 이미지를 페이지에 꽉 차게 확대해달라는 피드백을 받아 관련 작업을 진행했습니다.**  

### 상세 활동

1. 오전 업무 및 Shopify 자동화/수동 등록 완료

-   **정식 미팅 없음**: 개발 선임(Owen)의 미팅 일정으로 인해, 정식 개발 미팅 없이 바로 업무에 착수했습니다.
    
-   **Shopify 자동화 작업 완료**: 수요일부터 실행했던 `setting all locations to all products` 자동화 코드가 성공적으로 작업을 마쳤습니다. 스크립트가 **체크포인트 파일**에서 2,348개의 완료 항목을 로드하여 중단했던 지점부터 다시 시작했으며, 남은 작업을 **52.5분** 만에 모두 처리했습니다.
    
-   **Shopify 수동 등록 완료**: 자동화 작업 이후, 초기 마이그레이션 과정에서 CSV 이슈로 실패했던 **8건의 상품**을 수동으로 등록하여 마이그레이션 관련 모든 문제를 해결했습니다.
    

2. 폰트 및 레이아웃 문제 해결 시도

-   **한글 폰트 렌더링 문제 재발**: 이전에 성공적으로 작동했던 **폰트 강제 적용 방식이 더 이상 효과가 없어** 근본적인 원인을 찾고 있습니다. 여러 방법을 동원했지만, 한글이 빈칸으로 나오는 현상은 해결되지 않았습니다.
    
-   **커버/백커버 이미지 확대 피드백**: "커버와 백커버 이미지가 페이지에 꽉 차게 확대되어야 한다"는 피드백을 받아,  `@page` 설정과 `table` 기반 구조를 활용하여 이미지가 페이지에 꽉 차도록 확장하는 작업을 진행했습니다.
    
-   **기존 레이아웃 오류 수정**:  `@page :first` 구문 오류와 목차 레이아웃 오류를 **"이름 있는 페이지 스타일" (`@page cover`)**로 변경하고 여백을 조정하여 성공적으로 수정했습니다.
    

3. 프로젝트 문서화

-   **문서화 시작**: Shopify 작업이 끝난 후, Report 프로젝트 문서화 작업에 착수했습니다. 불필요한 파일을 정리하고 주석을 영문으로 바꾸는 작업을 시작했으며, 이 내용을 바탕으로 디렉토리 구조를 포함한 `README` 파일을 만들 준비를 마쳤습니다.

## 🧠 배운 핵심 개념

-   **자동화의 안정성 확보**: 대규모 자동화 작업은 **체크포인트 파일**을 활용한 작업 중단 및 재개 기능이 필수적입니다.
    
-   **솔루션의 일시적 안정성**:  `xhtml2pdf`와 같은 라이브러리의 경우,  **겉으로 보이는 해결책보다 라이브러리의 근본적인 렌더링 원리**를 이해하는 것이 중요합니다.
    
-   **반복적인 피드백과 디자인 변경**: 디자인 중심의 결과물은 초기 단계 이후에도 **반복적인 수정과 최적화 과정**이 필수적입니다.

## 💡 실전 시행착오 및 팁

-   **체크포인트를 통한 안정적인 대규모 작업**: 대규모 자동화 작업을 진행할 때는 중간 진행 상황을 저장하는 체크포인트를 반드시 구현해야 합니다.
    
-   **일회성 해결책 지양**: 일시적으로 작동하는 코드나 트릭에 의존하기보다,  **라이브러리의 공식 문서와 권장 사항**을 따르는 것이 장기적으로 안정성을 확보하는 데 더 효과적입니다.

## 🔜 다음 계획

-   **폰트 문제 해결 재착수**:  `pdfmetrics.registerFont`,  `pdfmetrics.registerFontFamily`를 사용해 한글 폰트를 등록하고 `link_callback` 옵션을 다시 추가하여 폰트 연결을 확실히 할 것입니다.
    
-   **커버/백커버 이미지 확대 구현**: 받은 피드백에 따라, 커버 이미지가 페이지에 꽉 차도록 만드는 작업을 완료할 것입니다.
    
-   **프로젝트 문서화**: 불필요한 파일을 정리하고 주석을 영문으로 변환하는 작업을 마무리한 후, 디렉토리 구조를 포함한 `README` 파일을 최종적으로 작성할 것입니다.
    

