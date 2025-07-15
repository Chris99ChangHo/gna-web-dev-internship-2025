# 📅 Day 01 (2025-07-14, Mon)

## 🎓 What I Did Today

**📌 Participated in the morning development meeting, reporting success in fetching SERanking and GA4 data simultaneously and discussing next steps for report automation, including PDF generation and new dashboard ideas.**   
**📌 Devised and developed a Flask-integrated marketing report solution, eliminating dummy data and transitioning to real data for all processing.**   
**📌 Initiated significant UI and code improvements for the integrated dashboard and PDF reports, focusing on layout optimization, English unification, branding, and advanced data visualization.**  

### Detailed Activities

**1. Morning Development Meeting — Report Automation Next Steps:**

-   I reported on last Friday's success: after my presentation, I managed to **fetch SERanking and GA4 data concurrently and display it successfully** in the dashboard.
    
-   For the next phase of the report automation project, I suggested focusing on **generating aesthetically pleasing PDFs** and exploring my ideas for a **dashboard and AutoViz** (automated data visualization).
    
-   The team acknowledged the successful data retrieval and advised me to **research and implement a more sophisticated PDF generation method**.
    
-   Regarding adopting new technologies or stacks, it was emphasized that introducing additional tools would increase management and security overhead. Therefore, I was directed to first explore ways to achieve the desired functionalities **within the existing PHP environment**, even if initial development uses familiar languages/tools like Python for prototyping.
    

**2. Flask-based Marketing Report Solution Development (Real Data Integration):**

-   **Dummy Data Removal & Real Data Implementation:** Following your feedback, I devised and began developing a marketing report solution that completely removes dummy data and utilizes **real, live data**. This solution leverages Flask as the backend.
    
-   **`app.py` Enhancements:**
    
    -   Implemented **keyword ranking processing logic** to reflect the **actual keyword data** you provided (e.g., `house painters Wahroonga`, `house painters St Ives`).
        
    -   Added logic to visually display **rank changes** (rise, fall, maintain, new entry, drop out).
        
    -   Ensured **rank segment summaries** (e.g., Top 10, Top 30) are dynamically calculated.
        
-   **`templates/report_full_document.html` Modifications:**
    
    -   Integrated this template to receive processed data from `app.py` and accurately display **keyword rankings and changes** in the table.
        
    -   Added sections for **"New in Top 100" and "Dropped out" keywords** to display relevant data. (Note: This section might be removed later as it deviates from the existing report format.)
        
-   **`js/main.js` Role Segregation & Improvements:**
    
    -   Its role was segregated to solely handle **chart generation logic**.
        
    -   Utilized **real data passed via Flask** to draw charts for page views, device users, traffic sources, keyword rank change distribution, and overall rank distribution. (Note: This might also be modified later due to inconsistencies with the existing format.)
        

**3. Dashboard/Report UI and Code Improvements (General):**

-   **GA4/SERanking/Google Ads Integrated Dashboard & PDF Report Layout:** Began refining the overall layout for a unified experience across GA4, SERanking, and Google Ads data.
    
-   **English Language Unification:** Standardized all UI elements, tables, buttons, and instructional texts to English.
    
-   **Brand Customization:** Implemented brand-specific modifications for titles and headers (e.g., "GNA Report").
    
-   **Clear Section Separation:** Clearly delineated major sections for SERanking, Google Ads, and other key data points.
    
-   **SERanking Table Enhancements:**
    
    -   Integrated **increment/decrement icons** (▲/▼) with numerical values for changes in ranking.
        
    -   Handled **"New in Top 100" and "Dropped out"** keywords by listing them separately below the main table, displaying only numerical changes within the table itself.
        
-   **SERanking Table Visualizations/Distribution Charts:** Proposed and started adding visualizations such as a **doughnut chart** to show the overall rank change distribution (rise/fall/maintain/new/dropped) for all keywords, accompanying the new/dropped keyword lists.
    
-   **PDF Report A3 Landscape Style Optimization:**
    
    -   Adjusted `width`, `padding`, and `height` of `.page-section` elements.
        
    -   Refined `width`, `height`, and `overflow` for table and chart containers.
        
    -   Applied styling like minimized `padding`/`margin`, `overflow-x: auto`, and `max-width: 100%` to **prevent content from being cut off** in the actual PDF output.
        
    -   Focused on **optimizing styles** to ensure all major content is fully visible and correctly rendered within the PDF.
        

## 🧠 Key Concepts Learned

-   **Real Data-Driven Development:** I learned the critical importance of developing with **actual data from the outset**. This helps in identifying edge cases and complexities that dummy data might miss, leading to a more robust and reliable solution.
    
-   **Efficient Backend-Frontend Data Flow (Flask & JS):** I gained practical experience in seamlessly connecting a Python Flask backend to HTML templates and JavaScript charting libraries. This involved effectively passing processed data for dynamic display and visualization, deepening my understanding of full-stack data flow.
    
-   **Importance of Data Visualization and Report Design:** I realized that beyond merely fetching data, effective UI/UX design, layout, and visualization are crucial for conveying information to users. Especially for fixed formats like PDFs, optimization similar to responsive design is essential.
    
-   **Consideration for Scalability within Existing Stacks:** I reconfirmed that adopting new technology stacks isn't always the best solution. Prioritizing ways to implement functionalities within existing environments (PHP) and minimizing management and security overhead contributes to long-term project stability.
    

## 💡 Practical Trial-and-Error and Tips

-   **Data Format Mismatch in Flask-JS Integration:** I encountered issues matching the data format from the Flask backend with the specific requirements of the JavaScript charting library. **Tip:** Proactively transform and post-process data on the backend to precisely match frontend expectations before transmission, ensuring smoother integration.
    
-   **Maintaining Report Format Consistency:** Adding new sections like "New/Dropped keywords" and modifying chart implementation in `main.js` led to inconsistencies with the existing report format. **Tip:** Establish and strictly adhere to a consistent UI/UX design and information delivery guideline from the initial planning stages to avoid costly rework later.
    
-   **Solving PDF Output Layout Issues:** I struggled with web page layouts getting unexpectedly cut off or broken when converted to PDF. **Tip:** Meticulously adjust CSS properties like `width`, `padding`, `margin`, and `overflow` for the PDF output environment. Actively use `overflow-x: auto` and `max-width: 100%` to prevent content truncation in fixed layouts.
    
-   **Clarity in Data Visualization:** Initially, I tried to include all SERanking change information within the main table, which led to information overload. **Tip:** Separate core numerical changes within the table and present supplementary details (like "New in Top 100" / "Dropped out") in distinct, clearly labeled sections or lists to improve overall readability and impact.
    

## 🔜 Next Steps

-   **Unify Report Format:** Rectify inconsistencies in `templates/report_full_document.html` and `js/main.js` with the existing report format, optimizing them according to unified UI/UX guidelines.
    
-   **Implement PDF Report Generation:** Research and apply methods to implement the actual PDF report generation function based on the improved UI/UX and real data. Prioritize exploring libraries or solutions feasible within the PHP environment as directed.
    
-   **Elaborate Dashboard and AutoViz Ideas:** Further concretize the proposed dashboard and automated visualization (AutoViz) ideas, and explore their technical feasibility and integration with the existing PHP environment.
    
-   **Continue SERanking and Google Ads Data Integration & Visualization:** Proceed with additional integration and visualization work for SERanking and Google Ads data to enhance the dashboard's completeness.
    
----------

# 📅 1일차 (2025-07-14, 월)

## 🎓 오늘 한 일

**📌 오전 개발 미팅에서 SERanking 및 GA4 데이터 동시 가져오기 성공을 보고하고, PDF 리포트 생성 및 대시보드 아이디어에 대한 다음 단계를 논의했습니다.**   
**📌 더미 데이터를 제거하고 실제 데이터를 기반으로 하는 Flask 연동 마케팅 보고서 솔루션 구축을 고안하고 개발했습니다.**   
**📌 통합 대시보드 및 PDF 리포트 UI/코드 개선 작업을 시작했으며, 레이아웃 최적화, 영어 통일, 브랜딩, 고급 데이터 시각화에 중점을 두었습니다.**  

### 상세 활동

**1. 오전 개발 미팅 — 리포트 자동화 다음 단계:**

-   지난 금요일 발표 이후 **SERanking 및 GA4 데이터를 동시에 가져와 대시보드에 성공적으로 표시**했음을 보고했습니다.
    
-   리포트 자동화 프로젝트의 다음 단계로 **미려한 PDF 생성**과 **대시보드 및 AutoViz(자동 데이터 시각화) 아이디어**를 탐색할 것을 제안했습니다.
    
-   팀에서는 데이터 검색 성공을 인정하며, **더욱 정교한 PDF 생성 방법을 연구하고 구현**해 볼 것을 조언했습니다.
    
-   새로운 기술이나 스택 도입과 관련하여, 추가 도구 도입은 관리 및 보안 오버헤드를 증가시키므로, 초기 개발은 익숙한 언어/도구(예: Python)를 사용하더라도 궁극적으로는 **기존 PHP 환경 내에서 원하는 기능을 달성할 수 있는 방법을 먼저 모색**하라는 지시를 받았습니다.
    

**2. Flask 기반 마케팅 보고서 솔루션 구축 (실제 데이터 연동):**

-   **더미 데이터 제거 및 실제 데이터 기반 개발:** 사용자님의 피드백에 따라 기존의 더미 데이터를 완전히 제거하고 실제 데이터를 활용한 마케팅 보고서 솔루션 구축 방안을 고안하고 개발에 착수했습니다. 이는 Flask를 백엔드로 활용하는 방식입니다.
    
-   **`app.py` 개선:**
    
    -   사용자께서 제공해주신 **실제 키워드 데이터**(`house painters Wahroonga`, `house painters St Ives` 등)를 반영하여 **키워드 랭킹 처리 로직**을 구현했습니다.
        
    -   순위 변화(상승, 하락, 유지, 새로 진입, 이탈)를 시각적으로 표시하는 로직을 추가했습니다.
        
    -   순위 세그먼트 요약(예: Top 10, Top 30)도 동적으로 계산되도록 했습니다.
        
-   **`templates/report_full_document.html` 수정:**
    
    -   `app.py`에서 처리된 데이터를 받아 **키워드 랭킹 테이블에 정확한 순위와 변화를 표시**하도록 연동했습니다.
        
    -   "Top 100에 새로 진입" 및 "Top 100에서 이탈" 키워드 섹션을 추가하여 해당 데이터를 보여주도록 했습니다. **(단, 기존 보고서 형식과 달라서 추후 이 부분은 제거할 예정입니다.)**
        
-   **`js/main.js` 역할 분리 및 개선:**
    
    -   **차트 생성 로직만 담당**하도록 역할을 분리했습니다.
        
    -   Flask를 통해 전달된 **실제 데이터를 사용**하여 페이지 뷰, 기기 사용자, 트래픽 소스, 그리고 키워드 순위 변화 분포 및 전체 순위 분포 차트를 그렸습니다. **(이 역시 기존 형식과의 불일치로 추후 수정될 가능성이 있습니다.)**
        

**3. 대시보드/리포트 UI 및 코드 개선 (공통):**

-   **GA4/SERanking/Google Ads 통합 대시보드 및 PDF 리포트 레이아웃:** GA4, SERanking, Google Ads 데이터를 아우르는 통합 대시보드 및 PDF 리포트의 전반적인 레이아웃 개선 작업을 시작했습니다.
    
-   **영어 통일:** 모든 UI 요소, 표, 버튼, 안내 문구를 영어로 통일했습니다.
    
-   **브랜드 맞춤형:** 타이틀 및 헤더(예: "GNA Report")에 브랜드 맞춤형 변경 사항을 적용했습니다.
    
-   **명확한 섹션 분리:** SERanking, Google Ads 및 기타 주요 데이터 포인트에 대한 주요 섹션을 명확하게 구분했습니다.
    
-   **SERanking 테이블 개선:**
    
    -   순위 변화에 대한 증감 아이콘(▲/▼)과 숫자 값을 통합했습니다.
        
    -   "New in Top 100" 및 "Dropped out" 키워드는 메인 테이블 아래에 별도로 나열하여, 테이블 자체에는 숫자 변화만 표시하도록 처리했습니다.
        
-   **SERanking 테이블 시각화/분포 차트:** 전체 키워드의 순위 변화 분포(상승/하락/유지/신규/탈락)를 보여주는 **도넛 차트**와 같은 시각화를 추가하여, 신규/탈락 키워드 목록과 함께 제공하도록 제안하고 작업을 시작했습니다.
    
-   **PDF 리포트 A3 가로 스타일 최적화:**
    
    -   `.page-section` 요소의 `width`, `padding`, `height`를 조정했습니다.
        
    -   테이블 및 차트 컨테이너의 `width`, `height`, `overflow`를 세밀하게 조정했습니다.
        
    -   실제 PDF 출력 시 콘텐츠가 잘리지 않도록 `padding`/`margin` 최소화, `overflow-x: auto`, `max-width: 100%` 등 스타일을 적용했습니다.
        
    -   모든 주요 콘텐츠가 PDF 내에서 완전히 보이고 올바르게 렌더링되도록 **스타일 최적화**에 집중했습니다.
        

## 🧠 배운 핵심 개념

-   **실제 데이터 기반 개발의 중요성:** 더미 데이터로만 작업할 때 놓칠 수 있는 실제 데이터의 복잡성과 예외 상황을 미리 파악하고 대응하는 것의 중요성을 배웠습니다. 초기 단계부터 실제 데이터를 연동하는 것이 더 견고한 솔루션으로 이어진다는 것을 확인했습니다.
    
-   **백엔드(Flask)와 프론트엔드(HTML/JS)의 효율적인 데이터 연동:** Flask를 통해 파이썬에서 처리된 데이터를 HTML 템플릿과 JavaScript 차트 라이브러리로 효율적으로 전달하고 시각화하는 방법을 구현하며, 백엔드-프론트엔드 간의 데이터 흐름에 대한 이해를 높였습니다.
    
-   **데이터 시각화 및 리포트 디자인의 중요성:** 단순히 데이터를 가져오는 것을 넘어, 사용자에게 정보를 효과적으로 전달하기 위한 UI/UX 디자인, 레이아웃, 시각화의 중요성을 깨달았습니다. 특히 PDF와 같은 고정된 형식에서는 반응형 디자인과 유사한 최적화가 필수적임을 배웠습니다.
    
-   **기존 스택 내에서의 확장성 고려:** 새로운 기술 스택 도입이 항상 최선이 아님을 다시 한번 확인했습니다. 기존 환경(PHP) 내에서 기능을 구현하는 방법을 먼저 모색하고, 관리 및 보안 측면에서의 오버헤드를 최소화하는 것이 장기적인 프로젝트 안정성에 기여함을 배웠습니다.
    

## 💡 실전 시행착오 및 팁

-   **데이터 형식 불일치 문제:** Flask 백엔드에서 처리한 데이터 형식을 프론트엔드 JavaScript 차트 라이브러리가 예상하는 형식으로 정확히 맞추는 과정에서 시행착오를 겪었습니다. **팁:** 데이터를 전달하기 전에 프론트엔드 요구사항에 맞춰 후처리하는 것이 중요함을 깨달았습니다.
    
-   **보고서 형식 일관성 유지:** 기존 보고서 형식과 제가 추가한 "새로 진입/이탈" 키워드 섹션 및 `main.js`의 차트 구현 방식 간에 불일치가 발생했습니다. **팁:** 초기 기획 단계에서 모든 요소의 일관된 디자인 및 정보 전달 방식을 확립하는 것이 중요하며, 그렇지 않을 경우 재작업 비용이 발생할 수 있음을 상기시켜주었습니다.
    
-   **PDF 출력 시 레이아웃 문제 해결:** 웹 페이지에서 보이는 레이아웃이 PDF로 변환될 때 예상치 못하게 잘리거나 깨지는 문제를 겪었습니다. **팁:** CSS의 `width`, `padding`, `margin`, `overflow` 속성을 PDF 출력 환경에 맞춰 세밀하게 조정하는 시행착오를 겪었으며, `overflow-x: auto`와 `max-width: 100%`를 적극 활용하여 내용 잘림을 방지하는 팁을 얻었습니다.
    
-   **데이터 시각화의 명확성:** SER 테이블의 증감 표시나 신규/탈락 키워드 처리 방식에 대해, 처음에는 모든 정보를 테이블 내에 넣으려 했으나, 정보 과부하로 인해 가독성이 떨어진다는 것을 확인했습니다. **팁:** 핵심 정보(숫자 증감)는 테이블 내에, 부가 정보(신규/탈락)는 별도 섹션으로 분리하는 것이 정보 전달력을 높이는 효과적인 방법임을 배웠습니다.
    

## 🔜 이후 학습 방향

-   **보고서 형식 일관성 재확립:** `templates/report_full_document.html` 및 `js/main.js`에서 기존 보고서 형식과의 불일치 부분을 수정하고, 통합된 UI/UX 가이드라인에 맞춰 최적화할 것입니다.
    
-   **PDF 리포트 생성 기능 구현:** 현재 개선된 UI/UX를 바탕으로 실제 PDF 리포트 생성 기능을 구현하는 방법을 연구하고 적용할 것입니다. PHP 환경 내에서 가능한 라이브러리나 솔루션을 우선적으로 검토할 것입니다.
    
-   **대시보드 및 AutoViz 아이디어 구체화:** 제안했던 대시보드 및 자동 시각화(AutoViz) 아이디어를 더욱 구체화하고, 이를 기존 PHP 환경에서 구현할 수 있는 기술적 가능성을 탐색할 것입니다.
    
-   **SERanking, Google Ads 데이터 통합 및 시각화 지속:** SERanking 및 Google Ads 데이터의 추가적인 통합 및 시각화 작업을 진행하여 대시보드의 완성도를 높일 것입니다.
