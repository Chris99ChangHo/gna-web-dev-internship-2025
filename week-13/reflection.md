# 📝 Week 13 Reflection (2025.08.04 ~ 08.08)

## ✅ Key Tasks This Week

**📌 Automated a large-scale Shopify product location assignment task, successfully processing over 2,900 items using a resilient script with checkpoint and retry logic.**   
**📌 Stabilized the PDF report generation pipeline by fixing persistent Korean font rendering issues and resolving complex layout challenges by switching to a pre-synthesis approach.**   
**📌 Completed a comprehensive documentation effort, including codebase internationalization, a detailed `README.md`, and a new System Architecture & Operations Report.**  

## 🧠 What I Learned

-   **API Job Stability with Checkpoints**: I learned the critical importance of designing large-scale automation scripts with **checkpoint systems**. By saving and resuming progress, I was able to reliably handle server interruptions and API rate limits, ensuring a complex job with over 2,900 items was completed without losing progress.
    
-   **Problem-Solving Paradigm Shifts**: I learned a crucial lesson in not getting stuck on one technology. When `xhtml2pdf`'s CSS limitations made a design impossible, I pivoted to an image **pre-synthesis approach using the PIL library**. This flexibility was key to solving the problem efficiently.
    

## 🔧 Technical Problem-Solving Experience

-   **Complex PDF Layouts**: The problem was to overlay text on an image for the PDF cover. After realizing that `xhtml2pdf`'s limited CSS support for `z-index` and `position: absolute` made this impossible, I switched my approach entirely. The solution was to use Python's **PIL (Pillow) library** to programmatically combine the text and background image into a single file, which was then seamlessly rendered by `xhtml2pdf`.
    
-   **API Concurrency Errors**: During the Shopify automation, I encountered HTTP `409 Conflict` errors when the script attempted to modify multiple variants of the same product simultaneously. The solution was to implement a **product-level locking mechanism** to serialize API calls, preventing concurrent modifications and ensuring data integrity.
    

## 💡 Reflections

-   **The Value of an Iterative Process**: My work on the PDF report highlighted that design-centric deliverables require an iterative approach. I received feedback to change the image layout after implementing an initial solution, which reinforced the need for continuous refinement based on user needs.
    
-   **Documentation as a Core Task**: I realized that documentation isn't a secondary task; it's a critical part of the development process. By internationalizing comments and writing a detailed project report, I've not only clarified my own work but also significantly improved the project's long-term maintainability and collaborative potential.
    

## 🌱 Points of Improvement & Next Week's Goals

-   **Area for Improvement**: The PDF image scaling issue still needs a final decision. My current approach to upscaling images did not resolve the physical size limitation within the PDF layout, indicating a need for a deeper discussion on the design strategy.
    
-   **Next Week's Goal 1**: Finalize the image scaling issue by consulting with the manager to either adjust the A3 layout size or procure larger source images.
    
-   **Next Week's Goal 2**: Complete all remaining project documentation, including the final `README.md` and the System Architecture Report, and hand it off to the senior developer to initiate the full workflow test.

----------

# 📝 13주차 회고 (2025.08.04 ~ 08.08)

## ✅ 이번 주 주요 작업

**📌 체크포인트와 재시도 로직을 적용한 견고한 스크립트를 통해 2,900개 이상의 상품에 대한 Shopify 제품 위치 자동 할당 작업을 성공적으로 완료했습니다.**   
**📌 지속적으로 발생하던 한국어 폰트 렌더링 문제를 해결하고, 복잡한 PDF 커버 레이아웃 문제를 이미지 사전 합성 방식으로 전환하여 안정화했습니다.**   
**📌 코드베이스 영문화, 상세한 `README.md` 작성, 시스템 아키텍처 보고서 작성 등 광범위한 문서화 작업을 마쳤습니다.**  

## 🧠 배운 핵심 개념

-   **체크포인트를 활용한 API 작업 안정성 확보**: 대규모 자동화 스크립트를 개발할 때 **체크포인트 시스템**이 얼마나 중요한지 배웠습니다. 작업 진행 상태를 저장하고 중단 지점부터 다시 시작함으로써, 서버 오류나 API 한도 초과와 같은 문제에도 안정적으로 작업을 완료할 수 있었습니다.
    
-   **문제 해결 패러다임 전환**: 특정 기술(`xhtml2pdf`)의 한계에 갇히지 않고, **PIL 라이브러리를 활용한 이미지 사전 합성 방식**으로 문제 해결의 접근법을 완전히 바꾸는 유연한 사고의 중요성을 깨달았습니다.
    

## 🔧 기술적 문제 해결 경험

-   **복잡한 PDF 레이아웃**: PDF 커버에 텍스트를 이미지 위에 겹쳐서 배치하는 문제가 있었습니다. `xhtml2pdf`의 제한적인 `z-index`와 `position` 지원으로는 불가능하다는 것을 파악한 후, 접근 방식을 완전히 바꿨습니다. **PIL(Pillow) 라이브러리**를 사용해 텍스트와 배경 이미지를 미리 합성한 하나의 완성된 이미지를 만든 다음, 이를 PDF에 간단히 삽입하여 문제를 해결했습니다.
    
-   **API 동시성 오류(409) 해결**: Shopify 자동화 작업 중, 스크립트가 같은 제품의 여러 변형을 동시에 수정하려 시도할 때 HTTP `409 Conflict` 오류가 발생했습니다. **제품 단위 락(Product-level lock) 메커니즘**을 도입하여 API 호출을 순차적으로 처리함으로써 동시성 오류를 방지하고 데이터 무결성을 확보했습니다.
    

## 💡 느낀 점

-   **반복적인 피드백의 가치**: PDF 보고서 작업에서 이미지를 페이지에 꽉 차게 만들어달라는 피드백을 받으며, 디자인 중심의 결과물은 초기 구현 이후에도 **지속적인 피드백을 반영한 반복적인 최적화 과정**이 필수적이라는 것을 깨달았습니다.
    
-   **문서화는 핵심 업무**: 문서화가 단순한 부수적인 작업이 아니라, 개발 프로세스의 핵심이라는 것을 체감했습니다. 주석을 영문화하고 상세한 문서를 작성함으로써 제 작업 내용을 명확히 했을 뿐만 아니라, 프로젝트의 장기적인 유지보수성과 협업 효율성을 크게 향상시켰습니다.
    

## 🌱 아쉬운 점 및 다음 주 목표

-   **개선할 점**: PDF 이미지 스케일링 문제는 최종 해결이 필요한 부분입니다. 이미지를 업스케일했음에도 불구하고 PDF 내에서 물리적 크기가 커지지 않는 한계에 부딪혔으므로, 디자인 전략에 대한 더 깊은 논의가 필요합니다.
    
-   **다음 주 목표 1**: 매니저와 상의하여 A3 레이아웃 크기를 조정할지, 아니면 고품질의 원본 이미지를 준비할지 결정하고, PDF 이미지 스케일링 문제를 최종적으로 해결하겠습니다.
    
-   **다음 주 목표 2**: 남은 프로젝트 문서화 작업을 모두 완료하고, 개발 선임에게 최종 결과물을 공유하여 전체 워크플로우 테스트가 시작될 수 있도록 준비하겠습니다.
