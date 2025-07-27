# 📅 Day 05 (2025-07-25, Fri)

## 🎓 What I Did Today

**📌 Reported on the PDF design rework status in the morning dev meeting and shared the plan for implementing security features in the afternoon.**   
**📌 Focused on redesigning the PDF reports using `xhtml2pdf`, but couldn't complete the work today due to more CSS compatibility issues than expected.**   
**📌 Developed a detailed security plan for controlling Flask app access integrated with WordPress (WP) login.**  

### Detailed Activities

**1. Morning Development Meeting Summary:**

-   **PDF Design Rework Report**: In the morning meeting, I reported to the senior developer that while the `xhtml2pdf` module was functionally working, the PDF design needed to be redone from scratch. I mentioned it might take longer than anticipated but committed to finishing the design work in the morning and starting on security feature implementation in the afternoon.
    
-   **Security Feature Implementation Plan Share**: The senior developer acknowledged my report and asked for a specific explanation of how I planned to implement the security features. I immediately explained and began the work.
    

**2. PDF Design Rework Progress:**

-   I focused on redesigning the PDF reports using the `xhtml2pdf` library.
    
-   **Challenges Faced**: The work was much slower than expected because `xhtml2pdf` has many CSS elements it doesn't recognize. Even simple style expressions required me to search for and apply older syntax, which was incredibly frustrating.
    
-   **Outcome**: I couldn't complete the design rework by the end of today.
    

**3. WordPress (WP) Login Integrated Flask App Access Control Plan Established:**

Despite the unfinished PDF design work, I developed a detailed plan to ensure smooth progress on security feature implementation starting tomorrow.

-   **Goal**: Restrict Flask app access to only users logged into WordPress.
    
    -   **Step 1: HTTPS Application (Completed)**: Confirmed that cPanel's `AutoSSL` feature already automatically applies HTTPS, so this step is skipped.
        
    -   **Step 2: Generate Secret Key**: Create a **long, complex secret key** using an online password generator and store it securely for authentication between the two systems.
        
    -   **Step 3: WordPress Configuration (Token Issuance)**: Add provided **PHP code** to the WP theme's `functions.php` file, input the **secret key and Flask app URL**, and generate a link using the `[flask_app_link]` shortcode when a logged-in user clicks.
        
    -   **Step 4: Flask App Configuration (Token Verification)**: Apply provided **Python code** to `app.py` in cPanel, enter the **same secret key**, and **restart** the app to apply changes.
        
    -   **Step 5: Final Testing**: Verify that the Flask page opens when clicking the link after WP login, and that access is blocked when logged out or accessing the Flask URL directly.

## 🧠 Key Concepts Learned

-   **Unexpected Technical Hurdles**: I experienced that certain libraries (in this case, `xhtml2pdf`) might not fully support standard web technologies (CSS). This means going beyond simple technical application and requires a deep understanding of the library's characteristics, sometimes necessitating the use of older methods.
    
-   **Importance of Flexible Plan Adjustment**: I realized that when a task is more complex and takes longer than expected, it's crucial to flexibly adjust the plan and prepare for the next tasks in advance.

## 💡 Practical Trial-and-Error and Tips

-   **Caution When Selecting PDF Libraries**: Just because a library converts HTML/CSS to PDF doesn't mean it will perfectly reproduce all web designs. Especially for complex CSS properties or modern web technologies, it's essential to thoroughly test the library's **CSS parsing and rendering capabilities** beforehand.
    
-   **Need for Legacy CSS Knowledge**: Sometimes, older web standards or CSS syntax might work better in specific environments than the latest technologies. Understanding various web technology specifications can be helpful in problem-solving.

## 🔜 Next Steps

-   **Complete PDF Design Rework**: I will prioritize and complete the PDF report design rework using `xhtml2pdf` by next week.
    
-   **Begin Security Feature Implementation**: After the design work is completed, I will proceed with implementing the WordPress login integration and Flask app access control features according to the plan established today.
    
-   **Continuous Documentation**: I will continue to document each technical attempt and its results in detail for future reference in case similar issues arise.

----------

# 📅 Day 05 (2025-07-25, 금)

## 🎓 오늘 한 일

**📌 오전 개발 미팅에서 PDF 디자인 재작업 상황을 보고하고, 오후에 진행할 보안 기능 구현 계획을 공유했습니다.**   
**📌 `xhtml2pdf`를 이용한 PDF 보고서 디자인 재작업에 집중했으나, 예상보다 많은 CSS 호환성 문제로 인해 오늘까지 작업을 완료하지 못했습니다.**   
**📌 워드프레스(WP) 로그인 연동 Flask 앱 접근 제어에 대한 상세한 보안 계획을 수립했습니다.**  

### 상세 활동

**1. 오전 개발 미팅 요약:**

-   **PDF 디자인 재작업 보고**: 오전 미팅에서 개발 선임께 `xhtml2pdf` 모듈이 기능적으로는 작동하지만, PDF 디자인을 처음부터 다시 해야 하는 상황임을 보고했습니다. 예상보다 시간이 더 소요될 수 있지만, 오전에 디자인 작업을 마무리하고 오후부터 보안 기능 구현에 착수하겠다고 말씀드렸습니다.
    
-   **보안 기능 구현 계획 공유**: 개발 선임은 제 보고를 확인하고, 보안 기능을 어떤 방식으로 구현할 것인지 구체적으로 설명해달라고 요청했습니다. 저는 이에 대해 즉시 설명하고 작업을 시작했습니다.
    

**2. PDF 디자인 재작업 진행:**

-   `xhtml2pdf` 라이브러리를 사용하여 PDF 보고서의 디자인을 재작업하는 데 집중했습니다.
    
-   **직면한 문제**: `xhtml2pdf`가 인식하지 못하는 CSS 요소들이 많아 예상보다 작업이 훨씬 더뎠습니다. 간단한 스타일 표현조차도 옛날 문법을 검색하고 적용해야 하는 어려움이 있었습니다.
    
-   **결과**: 디자인 재작업은 오늘 퇴근 전까지 완료하지 못했습니다.
    

**3. 워드프레스(WP) 로그인 연동 Flask 앱 접근 제어 계획 수립:**

PDF 디자인 작업이 마무리되지 않았음에도 불구하고, 내일부터 보안 기능 구현을 차질 없이 진행하기 위해 상세 계획을 수립했습니다.

-   **목표**: 워드프레스에 로그인한 사용자만 Flask 앱에 접근할 수 있도록 제어합니다.
    
    -   **1단계: HTTPS 적용 (완료됨)**: cPanel의 `AutoSSL`로 자동 적용되어 건너뜁니다.
        
    -   **2단계: 비밀키 생성**: 두 시스템 간 인증을 위한 **길고 복잡한 비밀키**를 생성하여 보관합니다.
        
    -   **3단계: 워드프레스 설정 (토큰 발급)**: WP 테마 `functions.php`에 **PHP 코드**를 추가하고 **비밀키, Flask 앱 주소**를 입력하며, `[flask_app_link]` 숏코드로 링크를 생성합니다.
        
    -   **4단계: Flask 앱 설정 (토큰 검증)**: `app.py`에 **Python 코드**를 적용하고 동일한 **비밀키**를 입력 후 앱을 **재시작**합니다.
        
    -   **5단계: 최종 테스트**: WP 로그인 후 Flask 페이지가 열리는지, 로그아웃 또는 직접 URL 접근 시 차단되는지 확인합니다.

## 🧠 배운 핵심 개념

-   **예상치 못한 기술적 난관**: 특정 라이브러리(여기서는 `xhtml2pdf`)가 표준 웹 기술(CSS)을 완벽하게 지원하지 않을 수 있음을 경험했습니다. 이는 단순한 기술 적용을 넘어, 해당 라이브러리의 특성을 깊이 이해하고 때로는 오래된 방식을 찾아 적용해야 함을 의미합니다.
    
-   **유연한 계획 조정의 중요성**: 작업의 복잡성 때문에 예상보다 시간이 더 소요될 경우, 유연하게 계획을 조정하고 다음 작업에 대한 준비를 미리 해두는 것이 중요함을 깨달았습니다.

## 💡 실전 시행착오 및 팁

-   **PDF 라이브러리 선택 시 주의점**: 단순히 HTML/CSS를 PDF로 변환한다고 해서 모든 웹 디자인이 완벽하게 재현되는 것은 아닙니다. 특히 복잡한 CSS 속성이나 최신 웹 기술을 사용하는 경우, 라이브러리의 **CSS 파싱 및 렌더링 능력**을 미리 심층적으로 테스트해보는 것이 필수적입니다.
    
-   **레거시 CSS 지식의 필요성**: 때로는 최신 기술이 아닌 오래된 웹 표준이나 CSS 문법이 특정 환경에서 더 잘 작동할 수 있습니다. 다양한 웹 기술 스펙에 대한 이해가 문제 해결에 도움이 될 수 있습니다.

## 🔜 다음 학습 방향

-   **PDF 디자인 재작업 완료**: 다음주 중으로 `xhtml2pdf`를 이용한 PDF 보고서 디자인 재작업을 최우선으로 완료할 것입니다.
    
-   **보안 기능 구현 착수**: 디자인 작업 완료 후, 오늘 수립한 계획에 따라 워드프레스 로그인 연동 및 Flask 앱 접근 제어 기능을 구현할 것입니다.
    
-   **지속적인 문서화**: 각 기술적 시도와 그 결과를 상세히 문서화하여 향후 유사 문제 발생 시 참고할 수 있도록 할 것입니다.
