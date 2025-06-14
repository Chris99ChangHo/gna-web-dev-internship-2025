📅 Day 05 (2025-06-13, Fri)
🎓 What I Did Today
Participated in the morning development meeting, discussing progress and future learning path.
Implemented core structural, design, and functional customizations for the ISAAC Painting website using Elementor and custom code.
Explored and adopted efficient templating strategies for repetitive elements.
Gained deeper insights into responsive design specifics and the practical application of WordPress customization methods.
Detailed Activities
1. Morning Development Meeting & Future Task Discussion
Today's morning development meeting covered current progress and laid out the path for future learning and assignments.

ISAAC Painting Site Completion & Next Steps: I received feedback that once the ISAAC Painting site clone is completed, I should inform the team. Following this, I should continue with learning and practical exercises on topics like WordPress hooks and REST API, and a new assignment would then be provided. This solidifies the next steps for my learning journey.
2. Future Task: Post Archive & Articles Page Construction
My next significant task is to build out the Post Archive (e.g., blog/news list) and dedicated Articles pages.

Goal: To complete the Post Archive and Articles-specific pages.
Specific Task List:
Create and customize Elementor's Loop Grid and Loop Item templates.
Position and style content elements within post cards (category, title, excerpt, thumbnail).
Ensure design consistency (margins, padding, fonts, colors).
Apply responsive design (mobile, tablet, desktop).
Implement excerpt character limits and "..." display.
Style and position category underlines.
Add excerpt_more filter to functions.php if necessary.
Verify integration and compatibility with other widgets/elements on the page.
Check and resolve cache and style conflict issues.
Additional Tip: Elementor Pro's Loop Item template is most effective; Free version has limitations.
3. Implemented / Solved Today
I directly implemented and resolved various aspects of the ISAAC Painting website, focusing on styling and functionality.

A. Content Structure Customization (Category, Title, Excerpt)

Loop Item Template: Added dynamic category tags above the title in the Loop Item template and applied underline styling via CSS.
Consistent Styling: Unified styling for elements using classes like .elementor-post__title and .elementor-post__excerpt.
Excerpt Control: Managed excerpt character limits using widget options and added an excerpt_more filter to functions.php for "..." display (noting some widget-specific limitations).
Mobile-Friendly Links: Applied tel:, mailto:, and other mobile-friendly links to phone, email, and social media icons.
B. Design Consistency Achievement

Global CSS Styling: Consistently applied CSS styles across the board for margins, padding, fonts, colors, text shadows, and uppercase text.
Custom CSS: Maintained a consistent design for the entire layout and detailed elements using custom CSS.
Responsive Elements: Utilized object-fit, background-position, and media queries to ensure all elements (banners, headers, post cards, buttons) displayed correctly and responsively across various devices.
C. Detailed Feature Implementation

Breadcrumb Navigation (Breadcrumb NavXT): Customized the breadcrumb separator (») by wrapping it in a <span> tag, applying CSS for color and shadow, converting all text to uppercase, and bolding the last item.
Header/Navigation: Implemented a sticky + shrink effect where the header reduces in size and the logo becomes smaller upon scrolling.
Widget/Content Efficiency: Optimized repetitive structures by converting them into Template Parts / Loop Items for efficient management.
D. Problem Solving Process

Elementor Posts Widget Limitations: Directly identified limitations of the Elementor Posts widget (lack of options, non-application of PHP customizations) and resolved this by leveraging the Loop Item template.
WordPress Standard Customization: Applied standard WordPress customization methods in functions.php (e.g., excerpt_more filter, category display PHP code) and understood their practical limitations within the widget structure.
Clear Role Separation: Clearly distinguished the roles of CSS versus PHP/template customization in achieving desired design and functionality.
🧠 Key Concepts Learned
Practical Application of Responsive Design Principles: Applied specific unit and padding guidelines (1400px max, 100% width, 20-25px padding) for implementing truly responsive layouts, directly addressing a previous uncertainty.
Real-world Project Prioritization: Understood how project priorities shift based on new client tasks, leading to the temporary pausing of ongoing internal development like the Dev News Hub and Docscraper.
Clarifying Abstract Concepts (Hooks): Gained a clearer understanding of the practical scenarios where WordPress hooks (Actions/Filters) are valuable, moving beyond theoretical knowledge to concrete use cases for extending existing functionality.
Client Interaction & Task Management: Experienced the full cycle of receiving a new client task, understanding requirements, and beginning implementation, including managing communication and clarifying technical details.
WordPress Ecosystem Tooling: Confirmed the availability and methods for integrating common website features like Breadcrumb Navigation and Google Reviews using WordPress plugins and APIs, and the importance of dynamic content elements like Elementor's Loop Grid/Item templates for flexible post displays.
💡 Practical Trial-and-Error and Tips
Consistent Responsive Units: Adhering to the advised 1400px max container for desktop and 100% width with fixed padding for mobile/tablet provides a straightforward and effective strategy for responsive design.
Strategic Plugin Use: Recognizing when to use a plugin for common functionalities (like breadcrumbs or reviews) versus custom code is key for efficiency, especially when time is a factor.
Proactive Questioning in Meetings: Asking specific questions about confusing topics (like px vs. % for responsiveness or the practical use of hooks) during dedicated Q&A sessions in meetings is highly effective for gaining clarity from experienced developers.
Debugging Layout Issues: The tip on responsive unit application directly addresses my previous concern about layout inconsistencies, providing a clear starting point for debugging.
Leveraging Elementor Pro Features: Discovered that Elementor Pro's Loop Item template is crucial for advanced post display customization, highlighting the limitations of the free version and the need for appropriate tools for specific tasks.
Differentiating CSS vs. PHP Customization: Realized the importance of clearly distinguishing between what can be achieved with CSS for styling and what requires PHP in functions.php or template modifications for functionality.
🔜 Next Steps
ISAAC Painting Site Homepage Completion: Continue developing the isaacpainting.com.au homepage in Elementor, focusing on accurately cloning the layout and ensuring responsiveness.
Post Archive/Articles Page Construction: Proceed with building out the Post Archive and dedicated Articles pages using Elementor's Loop Grid and Loop Item templates.
Breadcrumb Navigation Integration: Install and configure a breadcrumb plugin (e.g., Breadcrumb NavXT) for the ISAAC Painting site tomorrow.
Google Review Integration: Attempt to integrate Google Reviews further, potentially exploring alternative display methods or understanding business account linking for actual review display.
Preparation for CMS/Web Builder Presentation: Although the presentation is postponed, keep the materials ready for next week.
Continue WordPress Hooks & REST API Learning: As guided by the morning meeting, continue deepening understanding and practical skills in WordPress hooks and REST API for future assignments.
🏁 Conclusion
Core Site Implementation: Today, I successfully implemented and resolved nearly all core structural, widget, design, and functional customizations for the site.
Value of Practical Experience: I truly felt the importance of hands-on experience, iterative learning, and the effectiveness of rapid feedback in the development process.
📅 5일차 (2025-06-13, 금)
🎓 오늘 한 일
오전 개발 미팅 참여, 진행 상황 및 향후 학습 경로 논의.
Elementor와 커스텀 코드를 활용하여 ISAAC Painting 웹사이트의 핵심 구조, 디자인 및 기능 커스터마이즈를 구현.
반복되는 요소를 위한 효율적인 템플릿 전략을 탐색하고 적용.
반응형 디자인의 세부 사항과 워드프레스 커스터마이즈 방법의 실질적인 적용에 대한 깊은 통찰력 확보.
상세 활동
1. 오전 개발 미팅 및 향후 작업 논의
오늘 오전 개발 미팅에서는 현재까지의 진행 상황을 논의하고 향후 학습 및 과제에 대한 방향을 설정했습니다.

ISAAC Painting 사이트 완료 및 다음 단계: ISAAC Painting 사이트 클론 작업이 완료되면 팀에 알려달라는 피드백을 받았습니다. 이후에는 워드프레스 훅(Hooks)과 REST API와 같은 학습 및 실습을 그대로 이어나가면 되며, 완료 시 새로운 과제가 주어질 것이라고 했습니다. 이는 저의 학습 여정에 대한 다음 단계가 명확해진 부분입니다.
2. 앞으로 해야 할 작업: 포스트 아카이브 & Articles 페이지 구축
다음 주요 작업은 포스트 아카이브(예: 블로그/뉴스 게시글 목록)와 Articles 전용 페이지를 구축하는 것입니다.

목표: 포스트 아카이브 및 Articles 전용 페이지를 완성하는 것.
구체적 작업 목록:
Elementor의 Loop Grid 및 Loop Item 템플릿 생성 및 커스터마이즈.
포스트 카드 내 카테고리, 타이틀, 요약문, 썸네일 등 콘텐츠 요소 배치 및 스타일링.
마진, 패딩, 폰트, 컬러 등 디자인 통일성 확보.
반응형 디자인 적용(모바일, 태블릿, 데스크탑 대응).
요약문 글자수 제한 및 "..." 표시 적용.
카테고리 밑줄 스타일링 및 위치 조정.
필요시 functions.php에 excerpt_more 필터 추가.
페이지 내 위젯 및 기타 요소와의 통합 및 호환성 확인.
캐시 및 스타일 충돌 문제 점검 및 해결.
추가 팁: Elementor Pro의 Loop Item 템플릿 활용이 가장 효과적이며, Free 버전 사용 시 제한사항이 있습니다.
3. 오늘 실제로 구현/해결한 내용
오늘 ISAAC Painting 웹사이트의 스타일링 및 기능과 관련된 다양한 측면을 직접 구현하고 해결했습니다.

A. 카테고리, 타이틀, 요약문 등 콘텐츠 구조 커스터마이즈

Loop Item 템플릿: Loop Item 템플릿에서 타이틀 위에 카테고리 동적 태그를 추가하고, CSS로 밑줄 스타일을 적용했습니다.
스타일 통일: .elementor-post__title, .elementor-post__excerpt 등 클래스를 활용하여 각 요소의 스타일을 통일했습니다.
요약문 제어: 위젯 옵션으로 요약문 글자수를 제한하고, functions.php에 excerpt_more 필터를 추가하여 "..." 표시를 적용했습니다 (일부 위젯 구조상 제한 확인).
모바일 친화적 링크: 전화, 이메일, SNS 아이콘 등에 tel:, mailto: 등 모바일 친화적인 링크를 적용했습니다.
B. 디자인 통일성 확보

전반적인 CSS 스타일링: 마진, 패딩, 폰트, 컬러, 텍스트 그림자, 대문자(uppercase) 등 CSS 스타일을 전반적으로 통일했습니다.
사용자 정의 CSS: 사용자 정의 CSS를 사용하여 전체 레이아웃과 세부 요소까지 일관된 디자인을 유지했습니다.
반응형 요소: object-fit, background-position, 미디어 쿼리 등을 활용하여 배너, 헤더, 포스트 카드, 버튼 등 모든 요소가 다양한 기기에서 반응형으로 잘 보이도록 구현했습니다.
C. 기능별 세부 구현

브레드크럼 (Breadcrumb NavXT): 브레드크럼 구분자(»)를 <span> 태그로 감싸고, CSS로 색상 및 그림자 적용, 전체 텍스트 대문자 변환, 마지막 항목 볼드 처리 등 세부적으로 커스터마이즈했습니다.
헤더/내비게이션: 스크롤 시 헤더가 줄어들고 로고가 작아지는 sticky + shrink 효과를 구현했습니다.
위젯/콘텐츠 효율화: 반복되는 구조는 템플릿 파트/루프 아이템으로 변환하여 효율적으로 관리했습니다.
D. 문제 해결 과정

Elementor Posts 위젯의 한계: Elementor Posts 위젯의 한계(옵션 부재, PHP 커스텀 미적용)를 직접 확인하고, Loop Item 템플릿을 활용하여 해결했습니다.
워드프레스 표준 커스터마이즈: functions.php에서 excerpt_more 필터, 카테고리 표시 PHP 코드 등 워드프레스 표준 커스텀 방법을 적용하고 그 한계를 파악했습니다.
역할 명확화: CSS와 PHP/템플릿 커스텀의 역할을 명확히 구분하여 디자인 및 기능 구현에 적용했습니다.
🧠 배운 핵심 개념
반응형 디자인 원칙의 실무 적용: 이전의 불확실했던 부분인 반응형 레이아웃 구현을 위해 특정 단위 및 패딩 가이드라인(최대 1400px, 100% 너비, 20-25px 패딩)을 적용하는 실질적인 경험을 했습니다.
실제 프로젝트 우선순위 조정: 새로운 고객 업무에 따라 프로젝트 우선순위가 어떻게 변경되는지 이해했으며, 이로 인해 데브 뉴스 허브나 Docscraper와 같은 내부 개발이 일시적으로 중단될 수 있음을 알게 되었습니다.
추상적 개념(훅)의 명확화: 워드프레스 훅(액션/필터)이 실제 프로젝트에서 언제 유용하게 사용되는지, 기존 기능을 확장하기 위한 구체적인 사용 사례를 통해 이론적 지식에서 벗어나 더 명확하게 이해했습니다.
클라이언트 상호작용 및 작업 관리: 새로운 클라이언트 작업을 받고, 요구사항을 이해하며, 구현을 시작하는 전체 사이클을 경험했습니다. 이는 커뮤니케이션 관리 및 기술적 세부사항 명확화의 중요성을 포함합니다.
워드프레스 생태계 도구 활용: 브레드크럼 내비게이션 및 구글 리뷰와 같은 일반적인 웹사이트 기능을 워드프레스 플러그인 및 API를 사용하여 통합하는 방법과 사용 가능성을 확인했으며, 유연한 게시물 표시를 위한 Elementor의 Loop Grid/Item 템플릿과 같은 동적 콘텐츠 요소의 중요성을 배웠습니다.
💡 실전 시행착오 및 팁
일관된 반응형 단위 사용: 데스크탑 컨테이너에 1400px 최대 너비를, 모바일/태블릿에 100% 너비와 고정 패딩을 적용하는 것은 반응형 디자인을 위한 명확하고 효과적인 전략이 됩니다.
전략적 플러그인 사용: 브레드크럼이나 리뷰와 같은 일반적인 기능에 플러그인을 사용할 시기와 커스텀 코드를 사용할 시기를 파악하는 것은 효율성을 위해 중요합니다.
미팅 중 적극적인 질문: 미팅 중 혼란스러웠던 주제(반응형 단위, 훅의 실제 사용처 등)에 대해 구체적인 질문을 하는 것은 숙련된 개발자로부터 명확한 설명을 얻는 데 매우 효과적입니다.
레이아웃 문제 디버깅: 반응형 단위 적용에 대한 팁은 레이아웃 불일치에 대한 이전의 우려를 직접적으로 해소해주어 명확한 디버깅 시작점을 제공했습니다.
Elementor Pro 기능 활용: Elementor Pro의 Loop Item 템플릿이 고급 게시물 표시 커스터마이징에 필수적임을 발견했으며, 이는 무료 버전의 한계와 특정 작업에 적합한 도구의 필요성을 강조합니다.
CSS와 PHP 커스터마이징의 역할 구분: 스타일링을 위한 CSS와 functions.php의 PHP 코드 또는 템플릿 수정이 기능 구현을 위해 각기 다른 역할을 한다는 점을 명확히 구분하는 것의 중요성을 깨달았습니다.
🔜 Next Steps
ISAAC Painting 사이트 홈페이지 완성: Elementor를 사용하여 isaacpainting.com.au 홈페이지 개발을 계속하고, 레이아웃을 정확하게 복제하고 반응형을 확보하는 데 집중할 것입니다.
포스트 아카이브/Articles 페이지 구축: Elementor의 Loop Grid 및 Loop Item 템플릿을 사용하여 포스트 아카이브와 전용 Articles 페이지 구축을 진행할 것입니다.
브레드크럼 내비게이션 통합: 내일 ISAAC Painting 사이트에 브레드크럼 플러그인(예: Breadcrumb NavXT)을 설치하고 구성할 계획입니다.
구글 리뷰 통합: 구글 리뷰 통합을 더 진행하여, 실제 리뷰 표시를 위한 대체 표시 방법이나 비즈니스 계정 연결 방법을 이해하려고 시도할 것입니다.
CMS/웹 빌더 발표 준비: 발표가 다음 주로 연기되었지만, 자료를 미리 준비된 상태로 유지할 것입니다.
워드프레스 훅 & REST API 학습 지속: 오전 미팅에서 안내받은 대로, 향후 과제를 위해 워드프레스 훅과 REST API에 대한 이해와 실무 역량을 계속해서 심화할 것입니다.
🏁 Conclusion
핵심 사이트 구현 완료: 오늘 사이트의 거의 모든 핵심 구조, 위젯, 디자인, 기능 커스터마이즈를 실제로 구현하고 해결했습니다.
실전 경험의 가치: 실전 경험과 반복 학습의 중요성, 그리고 빠른 피드백의 효과를 깊이 체감했습니다.
