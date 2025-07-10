# 📅 Day 03 (2025-07-09, Wed)

## 🎓 What I Did Today

**📌 Participated in the morning development meeting, reporting progress on report automation (GA4 and SERanking API integration) and receiving important feedback on Melbourne Market product migration.**   
**📌 Focused all day on researching and preparing the presentation (PPT) on "The Evolution of Hacking, Scams, and Spamming Using AI — and Its Impact on Server Security."**   
**📌 Identified a potential issue with Wix elements in Melbourne Market product HTML and decided on a solution to remove all Wix-related tags.**  

### Detailed Activities

**1. Development Meeting Discussions and Progress:** The morning development meeting covered updates on current projects and critical feedback.

-   **Report Automation Pipeline & API Integration:**
    
    -   I reported that I'd attempted integration with both GA4 and SERanking API, establishing a preliminary pipeline.
        
    -   Mentioned the need to verify if customer **GA4 Property IDs** were correctly passing to the backend.
        
    -   Identified a potential error in the **SERanking API** integration code that would require future review.
        
    -   The manager advised me to prioritize preparing for tomorrow's research presentation and to report any persistent SERanking issues after the presentation.
        
-   **Melbourne Market Product Information Migration Feedback:**
    
    -   **Problem Identified:** I received feedback that migrating the product information's `outerHTML` directly included **Wix-specific elements** (e.g., `wix-*` tags). This could cause issues like broken images or styles if the Wix service contract ends. My assumption that original backend images would automatically replace Wix elements if tags disappeared was too optimistic.
        
    -   **Solution & Considerations:**
        
        -   **Code Fix Required:** The code for uploading Melbourne Market products needs modification.
            
        -   **Filtering Recommended:** It was advised to extract only necessary styles like image ratios and text colors, **filtering out all Wix-related elements** and retaining only basic HTML elements.
            
        -   **Image Paths:** Image sources must be replaced with paths to the original images stored on our own server.
            
        -   **Styling:** If styling is absolutely necessary, apply it minimally using inline styles.
            
-   **Previous Presentation Feedback:** Before leaving, the manager provided feedback on my previous presentation, "Open-Source CMS vs. Web Builders," which also needs revision.
    

**2. Research and Presentation (PPT) Preparation:**

-   **Today's Progress:** I spent the entire day conducting in-depth research and preparing the presentation (PPT) on "The Evolution of Hacking, Scams, and Spamming Using AI — and Its Impact on Server Security."
    
-   **Future Plan:** I'll also incorporate the manager's feedback into the previous presentation to revise and improve it.

## 🧠 Key Concepts Learned

-   **Thorough HTML Sanitization in Migrations:** I learned that directly migrating `outerHTML` containing elements from external platforms (like Wix) is risky and can lead to service disruptions if the external platform's contract ends. It's crucial to **completely remove platform-dependent elements** and reconstruct the content using standard HTML during migrations.
    
-   **API Integration Validation:** Even with a preliminary pipeline established, **thorough validation** is essential at each step of API integration (e.g., verifying GA4 ID passing, checking for SERanking API code errors) to quickly identify and resolve issues.
    
-   **Prioritizing Development Tasks:** I reinforced the importance of **setting realistic priorities** and flexibly managing urgent deadlines (like presentation preparation) against ongoing development issues (like SERanking API problems).
    
-   **Continuous Improvement through Feedback:** Receiving feedback on previous presentations provides valuable **opportunities for ongoing learning and enhancement**.

## 💡 Practical Trial-and-Error and Tips

-   **Beware of Migration Assumptions:** Don't assume that external elements will gracefully fall back or disappear without issue if a third-party service is discontinued. When migrating data with external components, it's vital to **anticipate all potential risks and handle them explicitly** in the code.
    
-   **Validate Core Data Flow Early in API Integration:** After setting up an API pipeline, **immediately verify the most critical data flows** (e.g., ensuring GA4 IDs are passed correctly) to quickly catch and fix early-stage errors, ensuring efficiency.
    
-   **Balance Urgent and Ongoing Tasks:** When urgent tasks like presentations arise, it's important to **clearly prioritize and temporarily set aside** ongoing development issues to meet immediate deadlines effectively.

## 🔜 Next Steps

-   **Report Automation:** I'll review the **SERanking API** integration code for errors and share any persistent issues for resolution (after the presentation).
    
-   **Melbourne Market Product Migration:** I'll modify the code to **remove all Wix elements** and reconstruct product information using standard HTML, ensuring image sources link to original backend paths.
    
-   **Presentation Preparation:** I'll finalize the presentation for "The Evolution of Hacking, Scams, and Spamming Using AI — and Its Impact on Server Security," scheduled for tomorrow (July 11).
    
-   **Previous Presentation Revision:** I'll revise and improve the "Open-Source CMS vs. Web Builders" presentation based on the manager's feedback.

----------

# 📅 3일차 (2025-07-09, 수)

## 🎓 오늘 한 일

**📌 오전 개발 미팅에서 리포트 자동화(GA4 및 SERanking API 연동)의 진전 상황을 보고하고, 멜번마켓 상품 마이그레이션 관련 중요한 피드백을 받았습니다.**   
**📌 "AI 기반 해킹, 스팸, 서버 보안 영향" 주제로 하루 종일 리서치하고 발표 자료(PPT) 준비에 집중했습니다.**   
**📌 멜번마켓 상품 HTML에 포함된 Wix 요소의 잠재적 문제점을 파악하고, 모든 Wix 관련 태그를 제거하는 해결 방안을 결정했습니다.**  

### 상세 활동

**1. 개발 미팅 주요 논의 및 진행 상황:** 오전 개발 미팅에서는 현재 진행 중인 프로젝트 업데이트와 중요한 피드백이 오갔습니다.

-   **리포트 자동화 파이프라인 및 API 연동:**
    
    -   GA4와 SERanking API 모두 연동 시도를 완료했으며, 1차적인 파이프라인을 구축했다고 보고했습니다.
        
    -   고객사의 **GA4 Property ID**들이 백엔드에 실제로 잘 넘어오는지 추가 확인이 필요하다고 언급했습니다.
        
    -   **SERanking API**의 경우, 코드를 불러오는 부분에서 오류 가능성이 발견되어 추후 코드 점검이 필요하다고 보고했습니다.
        
    -   매니저님은 당장 내일 리서치 발표가 우선이므로 발표 준비에 집중하고, SERanking 연동 문제는 발표 이후에도 지속되면 공유해 달라고 당부했습니다.
        
-   **멜번마켓 상품정보 마이그레이션 피드백:**
    
    -   **문제점:** 상품 정보의 `outerHTML`을 마이그레이션하는 과정에서 **Wix 고유 요소**(예: `wix-*` 태그)가 그대로 포함되어 문제가 발생할 수 있다는 피드백을 받았습니다. Wix 서비스 계약이 종료되면 해당 요소들이 남아 있어 이미지나 스타일이 깨질 위험이 있다는 지적이었습니다. 저는 원본 이미지가 백엔드에 있으니 Wix 계약이 끝나도 태그의 Wix 요소가 빠지고 원본으로 대체될 것이라고 너무 안일하게 생각했습니다.
        
    -   **해결 방안 및 고려사항:**
        
        -   **코드 수정 필요:** 멜번마켓 업로드 코드를 수정해야 합니다.
            
        -   **필터링 권고:** 이미지 비율과 텍스트 색상 같은 필요한 스타일만 추출하고, **Wix 요소가 아닌 기본 HTML 요소만 남기고** 나머지는 모두 필터링하는 방식이 권장되었습니다.
            
        -   **이미지 경로:** 이미지 소스는 반드시 자체 서버에 저장된 원본 경로로 교체해야 합니다.
            
        -   **스타일 적용:** 스타일이 꼭 필요한 경우에만 최소한의 inline style로 적용하는 것이 안전합니다.
            
-   **이전 발표 자료 피드백:** 퇴근 전에 매니저님으로부터 이전 발표 자료인 "Open-Source CMS vs. Web Builders" 관련 피드백을 받아, 이 또한 수정해야 할 것 같습니다.
    

**2. 리서치 및 발표 자료(PPT) 준비:**

-   **오늘 진행 내용:** 하루 종일 "AI를 활용한 해킹, 스캠, 스팸의 진화 — 그리고 서버 보안에 미치는 영향" 주제로 심층 리서치를 진행하고 관련 내용을 바탕으로 발표 자료(PPT)를 제작했습니다.
    
-   **향후 계획:** 매니저님 피드백을 바탕으로 이전 발표 자료 수정 및 보완 작업도 병행할 예정입니다.

## 🧠 배운 핵심 개념

-   **HTML 마이그레이션 시 완전한 클리닝의 중요성:** 외부 플랫폼(예: Wix)의 요소를 `outerHTML`로 그대로 가져올 경우, 계약 종료 시 서비스 장애를 유발할 수 있음을 배웠습니다. 마이그레이션 시에는 **플랫폼 종속적인 요소를 완전히 제거하고 표준 HTML로 재구성하는 것이 필수적**이라는 것을 깨달았습니다.
    
-   **API 연동의 복잡성과 검증의 중요성:** 리포트 자동화 파이프라인을 1차적으로 구축했더라도, GA4 ID 전달 여부 확인이나 SERanking API 코드 오류와 같이 **각 단계별로 철저한 검증이 필요함**을 확인했습니다.
    
-   **개발 우선순위 관리:** 당면한 발표 준비와 같은 급한 일정과 개발 이슈(SERanking API 문제) 사이에서 **현실적인 우선순위를 설정하고 유연하게 대처**하는 것이 중요함을 다시 한번 인지했습니다.
    
-   **피드백을 통한 지속적인 개선:** 이전 발표 자료에 대한 피드백을 통해 **지속적인 학습과 개선의 기회**를 얻을 수 있음을 확인했습니다.

## 💡 실전 시행착오 및 팁

-   **마이그레이션 시 '가정'에 대한 경계:** "원본 이미지가 백엔드에 있으니 문제없을 것"과 같은 안일한 가정은 실제 시스템에서는 예상치 못한 문제를 야기할 수 있습니다. 외부 요소가 포함된 데이터 마이그레이션 시에는 **모든 잠재적 위험을 상정하고 명시적으로 처리**해야 합니다.
    
-   **API 초기 연동 후 즉각적인 핵심 지표 검증:** 파이프라인을 구축한 후에는 GA4 ID가 정확히 넘어오는지와 같이 **가장 중요한 데이터 흐름부터 먼저 검증**하여 초기 단계의 오류를 빠르게 발견하고 수정하는 것이 효율적입니다.
    
-   **긴급 업무와 개발 업무의 균형:** 발표 준비와 같이 긴급한 업무가 발생했을 때, 현재 진행 중인 개발 문제에 대한 미련을 두기보다 **우선순위를 명확히 하고 잠시 내려놓을 줄 아는 유연성**이 필요합니다.

## 🔜 이후 학습 방향

-   **리포트 자동화:** **SERanking API** 연동 코드의 오류를 점검하고, 문제가 지속될 경우 즉시 공유하여 해결 방안을 모색할 것입니다. (발표 이후 진행)
    
-   **멜번마켓 상품 마이그레이션:** Wix 요소들을 모두 제거하고 표준 HTML로만 상품 정보를 재구성하며, 이미지 소스를 자체 서버의 원본 경로로 교체하는 코드를 수정할 것입니다.
    
-   **발표 준비:** 내일(7월 11일) 있을 "AI를 활용한 해킹, 스캠, 스팸의 진화 — 그리고 서버 보안에 미치는 영향" 주제의 발표를 위해 자료를 최종적으로 다듬을 것입니다.
    
-   **이전 발표 자료 수정:** 매니저님 피드백을 바탕으로 "Open-Source CMS vs. Web Builders" 발표 자료를 수정하고 보완할 것입니다.
