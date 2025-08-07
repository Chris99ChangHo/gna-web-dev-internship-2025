# 📅 Day 03 (2025-08-06, Wed)

## 🎓 What I Did Today

**📌 I shared updates in a development meeting about the Shopify follow-up task and the progress on the Report PDF layout. I received a new task to automate product location assignments on Shopify and reported that I would begin testing the PDF report once the layout issues were resolved.**   
**📌 I acknowledged the limitations of `xhtml2pdf` and solved the PDF cover design problem by switching to an image-synthesis approach using the PIL (Pillow) library.**   
**📌 I implemented a Python script to automate Shopify product location assignments, building a robust system to handle concurrency and server errors.**  

### Detailed Activities

1. Morning Development Meeting

-   **Shopify Follow-up**: As a follow-up to the previous Shopify shipping fee task, I identified a new problem: all products required manual assignment to locations. I received a new assignment to automate this process.
    
-   **Report PDF Progress**: I provided an update on the PDF layout work. I confirmed that the image selection feature was now working and that I would begin comprehensive testing as soon as the remaining layout issues were fixed.
    

2. Completed `xhtml2pdf` PDF Layout Optimization

After the meeting, I successfully resolved the layout issues by adopting a new approach that circumvents the limitations of `xhtml2pdf`.

-   **Problem-Solving Process**: I realized that `xhtml2pdf` was unstable with complex CSS overlays like `background-image`, `position: absolute`, and `z-index`. I adopted the core lesson: **"Don't force the impossible; find another way to achieve the same result."**
    
-   **New Approach**: I switched to using Python's **PIL (Pillow) library** to pre-synthesize the background image and text into a single, complete image. This final image was then simply inserted into the PDF using an `<img>` tag, completely solving the rendering issues.
    
-   **Final Optimization**: I precisely calculated the usable area of the A3 landscape page (404x281mm) based on the `@page` settings and margins. I then used a stable `table`-based structure with **`vertical-align: middle`** to ensure perfect alignment within the page.
    

3. Developed Shopify Product Location Automation Script

After finalizing the `xhtml2pdf` work, I began developing an automation script to solve the Shopify product location assignment problem.

-   **Problem-Solving Process**: My initial attempts failed due to API errors (inventory tracking disabled) and server issues (HTTP 500, 409). I devised a solution that temporarily enables inventory tracking, calls the `inventory_levels/set` API, and then disables tracking again.
    
-   **Building a Robust System**:
    
    -   I introduced a **Product-level Lock** to prevent multiple variants of the same product from being modified concurrently, which was causing the `409 Conflict` errors.
        
    -   I created a **DRY RUN** system to safely simulate the API calls and predict the outcome before making any actual changes.
        
    -   The script includes a retry logic for HTTP 409 and 500 errors and a checkpoint feature that saves progress to `shopify_progress.json`, allowing the job to be resumed after an interruption.
        
-   **Current Status & Achievements**: I have completed 41 out of 235 batches of the task. The **DRY RUN system** and robust error handling have allowed me to build a stable system for a complex, large-scale API job.

## 🧠 Key Concepts Learned

-   **Shifting Problem-Solving Paradigms**: I learned a valuable lesson in not getting stuck on a single technology (`xhtml2pdf`) and instead **pivoting to a completely different approach (PIL image synthesis)** to solve a problem. This mindset is crucial for saving time and effort in development.
    
-   **Ensuring Stability in Large-Scale API Jobs**: Working with the Shopify API taught me how to handle concurrency, server errors, and job interruptions during large-scale operations. I now understand the importance of implementing features like **checkpoints, retry logic, and concurrency control** to build a reliable system.

## 💡 Practical Trial-and-Error and Tips

-   **Overcoming `xhtml2pdf` Limitations**: I failed when trying to use complex CSS for overlays. The key takeaway is that for intricate visual effects, it's far more stable and predictable to **pre-synthesize images with a library like PIL** and insert them into the HTML, rather than relying on `xhtml2pdf` to render complex CSS.
    
-   **Solving API Concurrency Errors (409)**: When modifying large amounts of data via an API, a **`409 Conflict` error** can occur when the same resource is modified simultaneously. The solution is to implement a **Product-level Lock** to serialize modifications on a per-product basis.
    
-   **The Importance of DRY RUN**: For large-scale data modification tasks involving thousands of items, a **DRY RUN (simulation)** is essential. It allows you to test your logic, predict performance, and identify potential errors without making any destructive changes to the live data.

## 🔜 Next Steps

-   **Complete Shopify Automation Task**: I will resume and finish the remaining batches of the Shopify script to complete the entire job.
    
-   **Final PDF Report Testing**: I will conduct a final, comprehensive test of the PDF report generation feature now that the layout optimization is complete.
    
----------

# 📅 3일차 (2025-08-06, 수)

## 🎓 오늘 한 일

**📌 개발 미팅에서 Shopify 후속 작업과 Report PDF 레이아웃 진행 상황을 공유했습니다. Shopify 제품 위치 수동 할당 문제를 해결하기 위한 새로운 업무를 받고, PDF 레이아웃이 해결되면 테스트를 진행하겠다고 보고했습니다.**   
**📌 `xhtml2pdf`의 한계를 인정하고 PIL(Pillow) 라이브러리를 사용한 이미지 합성 방식으로 PDF 커버 디자인 문제를 완벽하게 해결했습니다.**   
**📌 Shopify 제품 위치 자동화 작업을 파이썬 스크립트로 구현했으며, 동시성 오류 및 서버 문제를 해결하는 견고한 시스템을 구축했습니다.**  

### 상세 활동

1. 개발 미팅

-   **Shopify 후속 작업**: 지난번 Shopify 배송비 설정 작업에 대한 후속 조치로, "모든 제품을 수동으로 위치에 할당해야 하는 문제"를 발견하고 이를 해결하기 위한 새로운 자동화 업무를 받았습니다.
    
-   **Report PDF 진행 상황**: 현재 진행 중인 PDF 레이아웃 작업에 대해 보고했습니다. 이미지 선택 기능은 구현되었지만, 레이아웃 이슈가 아직 남아있으며 이 문제가 해결되면 전체 테스트를 진행하겠다고 보고했습니다.
    

2. `xhtml2pdf` 기반 PDF 레이아웃 최적화 완료

개발 미팅 후, `xhtml2pdf`의 제약사항을 우회하는 새로운 접근법을 성공적으로 적용하여 레이아웃 문제를 최종적으로 해결했습니다.

-   **문제 해결 과정**: `xhtml2pdf`에서 `background-image`, `position: absolute`, `z-index`와 같은 복잡한 CSS 오버레이가 불안정하게 작동하는 것을 확인하고, **"불가능한 것을 억지로 하려 하지 않고 다른 방법으로 같은 결과를 만들어낸다"**는 교훈을 얻었습니다.
    
-   **새로운 접근**: Python의 **PIL(Pillow) 라이브러리**를 사용해 배경 이미지에 텍스트를 미리 합성한 후, 이 완성된 이미지를 HTML `<img>` 태그를 통해 PDF에 삽입하는 방식으로 방향을 전환했습니다.
    
-   **최종 최적화**: `@page` 설정을 기반으로 A3 용지 크기(420×297mm)와 마진(8mm)을 고려한 실제 사용 영역(404×281mm)을 정확히 계산하여, `table` 기반의 구조에 **`vertical-align: middle`**을 적용해 페이지 중앙에 완벽하게 정렬되도록 했습니다.
    

3. Shopify 제품 위치 자동화 스크립트 개발

`xhtml2pdf` 작업 완료 후, Shopify 제품 위치 수동 할당 문제를 해결하기 위한 파이썬 자동화 스크립트를 개발했습니다.

-   **문제 해결 과정**: 초기에는 재고 추적 비활성화 상태에서 API 호출 실패, HTTP 500, 409 같은 오류가 발생했습니다. 이를 해결하기 위해 재고 추적을 임시로 활성화하고 `inventory_levels/set` API를 호출하는 방식을 채택했습니다.
    
-   **안정적인 시스템 구축**:
    
    -   **제품 단위 락(Product-level Lock)**을 도입하여 같은 제품의 여러 변형이 동시에 수정되는 것을 방지했습니다.
        
    -   **DRY RUN(모의 실행)** 시스템을 구축하여 실제 API 호출 없이 안전하게 시뮬레이션할 수 있는 환경을 마련했습니다.
        
    -   HTTP 409, 500 에러 발생 시 재시도 로직을 적용하고, `shopify_progress.json` 파일에 진행 상황을 저장하여 작업 중단 후에도 이어서 실행할 수 있도록 했습니다.
        
-   **현재 상황 및 성과**: 총 2,350개 제품에 대한 작업 중 41개 배치를 완료했습니다. **DRY RUN 시스템 도입**으로 복잡한 API 문제와 동시성 문제를 해결하는 견고한 시스템을 구축했으며, 예상치 못한 오류에 대한 대응 능력을 강화했습니다.

## 🧠 배운 핵심 개념

-   **문제 해결의 패러다임 전환**: 특정 기술(`xhtml2pdf`)의 한계에 갇히지 않고, **전혀 다른 방식(PIL 이미지 합성)으로 접근하여 문제를 해결**하는 유연한 사고의 중요성을 깨달았습니다. 이는 개발 과정에서 시간과 노력을 크게 절약하는 중요한 교훈이었습니다.
    
-   **대규모 API 작업의 안정성 확보**: Shopify API를 다루며 대규모 작업을 처리할 때 발생하는 동시성, 서버 오류, 작업 중단 등의 문제에 대응하는 방법을 익혔습니다. **체크포인트, 재시도 로직, 동시성 제어**와 같은 기술이 안정적인 시스템 구축에 얼마나 중요한지 실감했습니다.

## 💡 실전 시행착오 및 팁

-   **`xhtml2pdf`의 한계 극복**: 복잡한 CSS 오버레이를 `xhtml2pdf`로 구현하려다 실패했습니다. 이 경험을 통해 **복잡한 시각적 효과는 파이썬의 PIL 라이브러리로 이미지를 미리 합성한 후 HTML에 간단히 삽입하는 방식**이 훨씬 안정적이고 예측 가능함을 알게 되었습니다.
    
-   **API 동시성 오류(409) 해결**: 대규모 API 작업 시 같은 리소스를 동시에 수정하여 발생하는 `409 Conflict` 에러를 해결하기 위해 **제품 단위 락(Product-level Lock)** 로직을 도입했습니다.
    
-   **DRY RUN의 중요성**: 수천 개의 데이터를 수정하는 대량 작업에서는 **DRY RUN(모의 실행)**을 통해 실제 API 호출 없이 로직의 오류를 확인하고 작업량과 시간을 예측하는 것이 필수적이라는 교훈을 얻었습니다.

## 🔜 다음 계획

-   **Shopify 제품 위치 자동화 작업 완료**: 현재 진행 중인 Shopify 스크립트의 나머지 배치를 마저 실행하여 전체 작업을 완료할 예정입니다.
    
-   **PDF 리포트 최종 테스트**: 레이아웃 최적화가 완료된 PDF 리포트 생성 기능을 종합적으로 테스트하여 실제 사용에 문제가 없는지 확인할 것입니다.
