# 📅 Day 05 (2025-06-27, Fri)

## 🎓 What I Did Today

**📌 Participated in the development meeting, confirming data transfer to the React app, discussing app development plans, React Native's app focus (with clarification), potential app publishing, and Deep Linking functionality.**  
**📌 Completed the implementation of the search input field reset function and enhanced stability by applying event delegation for dynamic elements.**   
**📌 Performed AI rewriting work for the company's Korean website content and developed a Python script for visually comparing results from various AI models.**   
**📌 Clearly identified the root cause of the WordPress post date sorting issue using the `pre_get_posts` hook and reconfirmed the resolution method.**  

### Detailed Activities

**1. Participation in Development Meeting and Discussion**

-   Confirmed that data transfer from the WordPress backend to the React app was successful yesterday, and now it's time to start building practical functionalities.
-   Mentioned customizing existing WordPress-built websites.
-   Discussed the ease of installing Expo and connecting to the REST API, noting it seemed simpler than Flutter. However, it was acknowledged that while Flutter's coding might be more complex, its inherent design for cross-platform app building could make it superior as a full-fledged application. **(Fact-check: React Native, built upon React's principles, is indeed a robust framework specifically designed for native mobile app development.)**
-   The senior developer suggested that if I want to gain deeper app development experience, exploring app publishing would be beneficial. They noted that Android publishing is straightforward, but Apple (iOS) has numerous complex and strict procedures involving accounts, company certifications, and personal authentication. Despite the challenges, I was encouraged to research and consider iOS publishing if interested.
-   Furthermore, using Facebook as an example, the concept of actions on the web directly leading to actions within the app (this is indeed **Deep Linking**) was discussed, and I was encouraged to research and attempt to implement such functionality, as it seems achievable.**

**2. Search Input Field Initialization and UI Logic Improvement (JavaScript)**

-   Implemented an `input` event listener for the search input field (`$searchInput`) in the `search-news-ajax.js` file. Added logic to restore the UI to its `search-initial-state` when the search query is empty.
-   Improved the initial state restoration by using `$originalSearchInitialState.clone(true)` to clone the DOM, ensuring that event handlers of the copied category buttons were not lost and remained intact.
-   Changed the category button click event listener to an event delegation method on `$searchResultsContainer`. This ensured stability, allowing category buttons to function correctly even when dynamically added or restored to the initial state.    
-   Optimized performance by modifying the logic so that when sorting controls are clicked with an empty search query, the UI updates without unnecessary AJAX calls.
    

**3. Company Korean Website Content AI Rewriting and Comparison Tool Development**

-   Identified that the Korean content on `https://gnadesign.com.au/` had many awkward and unnatural phrases due to being a direct translation of the English site.
-   Scraped the Korean content page by page, organized it into a spreadsheet, and used various AI models (GPT, Claude, Gemini, ClovaX) to rewrite the content.
-   Generated a CSV file containing the original text and the rewritten results from each AI model.
-   Developed an HTML comparison tool using `pandas` and `difflib` libraries to visually highlight (emphasize) text differences between the original and AI-generated results.
-   This tool generates an `ai_rewriting_comparison.html` file with a two-column comparison layout, allowing for an at-a-glance comparison of changes and identification of characteristics specific to each AI model.
    

**4. `pre_get_posts` Date Sorting Issue Root Cause Identification and Solution Reconfirmation (PHP)**

-   Discussed the issue where the `pre_get_posts` hook, which sorts posts by `news-published-date` custom field, was not functioning correctly.
-   **Key Cause Identification:** Through debug logs (`error_log`), clearly confirmed that the actual stored format of the `news-published-date` meta field was `YYYY-MM-DD HH:MM:SS` (e.g., `2025-02-27 11:02:00`).
-   **Solution Reconfirmation:** Reconfirmed that setting `meta_type` to `DATETIME` in the `utility-function.php` file, to match this format, is the most appropriate approach. (This setting was already applied in the existing code, but the significance lies in gaining certainty about the actual data format.)
-   **Enhanced Debugging:** Strengthened debugging output using additional `error_log` statements to ensure query conditions were correctly applied and query parameters were set as expected.
    

## 🧠 Key Concepts Learned

-   **Event Delegation:** A method of efficiently handling events for dynamically added or changed DOM elements by setting a single listener on a parent element, instead of binding individual event listeners to each element. This is crucial for performance and memory management in React components and dynamic web pages.
-   **Text Similarity Comparison and Visualization:** Learned a useful technique for efficiently identifying differences between two text strings using the `difflib` module and visualizing these changes in HTML for quick comprehension. This can be highly valuable in evaluating the text generation capabilities of AI models or in content rewriting tasks.
-   **Importance of WordPress `pre_get_posts` Hook and `meta_type`:** Reconfirmed that when customizing `WP_Query` using the `pre_get_posts` hook and sorting by a custom field (`meta_key`), it's essential to accurately specify `meta_type` to match the actual stored format for the query to function correctly. Especially for date/time data, explicitly setting it to `DATETIME` ensures accurate chronological sorting.
    
## 💡 Practical Learnings and Tips

-   **Maintaining Event Handlers for Dynamic DOM Elements:** Re-emphasized the importance of the `true` argument in `$originalSearchInitialState.clone(true)`. This argument instructs the clone to deeply copy all child nodes and event handlers of the original element. This allowed for effective management of dynamically restored UI elements, preventing loss of functionality.
-   **Necessity of Comparing Text Styles Across AI Models:** Directly observed that various AI models (GPT, Claude, Gemini, ClovaX) rewrite the same original text with different nuances and writing styles. Visually comparing these differences using the HTML comparison tool provided valuable insights for selecting the most suitable AI model for specific purposes (e.g., marketing, technical documentation, friendly tone).
    

## 🔜 Next Steps

-   **Commence React App Feature Implementation:** With WordPress backend integration confirmed, the next step is to move into the phase of developing and implementing core functionalities in the actual React app.
-   **Deep Link Technology Research:** Intend to conduct in-depth research into deep link technology for seamless connections from web to app, and explore ways to apply it to the React app (referencing Facebook's case studies).
-   **Detailed Research on Apple (iOS) App Release Procedures:** To gain app publishing experience, plan to thoroughly research the complex procedures for distributing apps on the iOS App Store (accounts, authentication, review process, etc.) in advance, laying the groundwork for future actual releases.
    

### 🔍 React vs Flutter: Comparison (Further Discussion)

| Category        | React                                         | Flutter                                      |
| :-------------- | :-------------------------------------------- | :------------------------------------------- |
| **Characteristics** | App framework based on Web UI library (React Native) | UI toolkit developed by Google, native compilation |
| **Advantages** | - Familiar JS/CSS base for web developers     | - Excellent native performance and consistent UI |
|                 | - Rich library and community                  | - Simplicity of Dart language               |
|                 |                                               | - Fast development speed (hot reload)        |
| **Disadvantages** | - Requires native module access via bridge    | - Requires learning a new language (Dart)   |
|                 | - Limitations when implementing certain complex native features | - Relatively smaller ecosystem for web/desktop currently |
| **Use Cases** | Rapid app prototyping leveraging existing web development experience, hybrid apps | High-performance/high-quality near-native apps, complex animations/UI implementation |

### 📝 Summary

-   The comparison between React Native and Flutter highlights that while React Native offers familiarity for web developers and a strong ecosystem, Flutter provides superior native performance and a more consistent UI, leveraging its Dart language and dedicated app development focus.
-   The choice between them depends on specific project needs, existing team skills, and the desired level of native performance and UI consistency for the application.

### 🧾 References

**🔗 [React Native Official Documentation](https://reactnative.dev/): Reference for React Native features and development environment setup.**  
**🔗 [Flutter Official Documentation](https://flutter.dev/): Reference for Flutter features, Dart language, and cross-platform development.**  

----------

# 📅 5일차 (2025-06-27, 금)

## 🎓 오늘 한 일

**📌 개발 미팅에 참여하여 React 앱 데이터 연동 확인, 앱 개발 계획, React Native의 앱 지향성(팩트체크 포함), 앱 출시 가능성 및 딥링크 기능에 대해 논의했습니다.**  
**📌 검색 입력 필드 초기화 기능 구현을 완료하고, 동적 요소의 이벤트 위임 방식을 적용하여 안정성을 높였습니다.**   
**📌 회사 국문 웹사이트 콘텐츠의 AI 리라이팅 작업을 진행하며, 다양한 AI 모델의 결과물을 시각적으로 비교하는 파이썬 스크립트를 개발했습니다.**   
**📌 `pre_get_posts` 훅을 이용한 워드프레스 게시물 날짜 정렬 문제의 원인을 명확히 파악하고 해결 방안을 재확인했습니다.**  

### 상세 활동

**1. 개발 미팅 참여 및 논의**

-   어제 React 앱으로 워드프레스 백엔드에서 데이터를 성공적으로 가져오는 것을 확인했으며, 이제 실제로 앱을 만들어볼 때가 된 것 같다고 논의했습니다.
-   워드프레스 기반으로 만든 기존 웹사이트들을 커스터마이징하고 있다고 보고했습니다.
-   Expo를 설치하고 REST API를 연결하는 과정이 생각보다 간단하여 Flutter보다 쉽게 느껴졌다고 말씀드렸습니다. 하지만 Flutter는 코딩이 더 어려울 수 있지만 애초에 크로스 플랫폼 구축을 위해 나온 것이므로 애플리케이션으로서 더 뛰어날 수 있다는 점에 공감했습니다. **(팩트체크: React Native는 React의 원리를 기반으로 하여 실제로 네이티브 모바일 앱 개발을 위해 설계된 강력한 프레임워크입니다.)**
-   더 깊이 있는 앱 개발 경험을 원한다면 앱 출시를 시도해보는 것도 좋겠다는 조언을 받았습니다. 안드로이드는 비교적 쉽지만, 애플(iOS)은 계정, 회사, 개인 등 인증이나 여러 절차들이 많고 까다롭다고 언급되었습니다. 하지만 관심이 있다면 리서치를 해보면서 출시를 한번 고려해보라고 격려받았습니다.
-   그리고 페이스북을 예로 들면서 웹에서 특정 행동을 하면 바로 앱으로 연결되는 기능(이는 **딥링크(Deep Link)**가 맞습니다)에 대해서도 논의했으며, 충분히 리서치하고 시도해볼 수 있을 것 같다고 말씀하셨습니다.

**2. 검색 입력 필드 초기화 및 UI 로직 개선 (JavaScript)**

-   `search-news-ajax.js` 파일에서 검색 입력 필드(`$searchInput`)의 `input` 이벤트 리스너를 구현했습니다. 검색어가 비어있을 때 `search-initial-state`로 UI를 복원하도록 로직을 추가했습니다.
-   초기 상태 복원 시 `$originalSearchInitialState.clone(true)`를 사용하여 DOM을 복사함으로써, 복사된 카테고리 버튼들의 이벤트 핸들러가 유실되지 않고 유지되도록 개선했습니다.
-   카테고리 버튼 클릭 이벤트 리스너를 `$searchResultsContainer`에 대한 이벤트 위임 방식으로 변경하여, 동적으로 추가되거나 초기 상태로 복원될 때의 카테고리 버튼들도 정상적으로 작동하도록 안정성을 확보했습니다.
-   정렬 컨트롤 클릭 시 검색어가 비어있을 경우, 불필요한 AJAX 호출 없이 UI만 업데이트되도록 로직을 수정하여 성능을 최적화했습니다.
    

**3. 회사 국문 웹사이트 콘텐츠 AI 리라이팅 및 비교 도구 개발**

-   `https://gnadesign.com.au/` 국문 사이트 콘텐츠가 영문 사이트를 단순 번역한 결과, 어색하고 부자연스러운 문제가 많음을 파악했습니다.
-   페이지별 국문 콘텐츠를 스크랩하여 시트에 정리하고, GPT, Claude, Gemini, ClovaX 등 다양한 AI 모델을 활용하여 콘텐츠를 리라이팅했습니다.
-   원본 텍스트와 각 AI 모델의 리라이팅 결과들을 포함하는 CSV 파일을 생성했습니다.
-   `pandas`와 `difflib` 라이브러리를 활용하여 원본과 AI 결과물 간의 텍스트 차이를 시각적으로 강조(하이라이팅)하는 HTML 비교 도구를 개발했습니다.
-   이 도구는 2열 비교 레이아웃으로 `ai_rewriting_comparison.html` 파일을 생성하여, 한눈에 달라진 점을 비교하고 AI 모델별 특성을 파악할 수 있게 합니다.
    

**4. `pre_get_posts` 날짜 정렬 문제 원인 파악 및 솔루션 재확인 (PHP)**

-   `news-published-date` 커스텀 필드를 기준으로 게시물을 발행일 순으로 정렬하는 `pre_get_posts` 훅이 제대로 작동하지 않던 문제에 대한 논의를 진행했습니다.
-   **핵심 원인 파악:** 디버그 로그(`error_log`)를 통해 `news-published-date` 메타 필드의 실제 저장 형식이 `YYYY-MM-DD HH:MM:SS` (예: `2025-02-27 11:02:00`)임을 명확히 확인했습니다.
-   **솔루션 재확인:** 이 형식에 맞춰 `utility-function.php` 파일에서 `meta_type`을 `DATETIME`으로 설정하는 것이 가장 적합한 접근 방식임을 재확인했습니다. (이 설정은 기존 코드에 이미 적용되어 있었으나, 실제 데이터 형식에 대한 확신을 가졌다는 데 의미가 있습니다.)
-   **디버깅 강화:** 쿼리 조건이 올바르게 적용되고 쿼리 매개변수가 예상대로 설정되는지 추가 `error_log`를 통해 디버깅 출력을 강화했습니다.
    

## 🧠 배운 핵심 개념

-   **이벤트 위임 (Event Delegation):** 동적으로 추가되거나 변경되는 DOM 요소에 대해 개별적인 이벤트 리스너를 바인딩하는 대신, 부모 요소에 하나의 리스너를 설정하여 효율적으로 이벤트를 처리하는 방법입니다. React 컴포넌트나 동적 웹 페이지에서 성능과 메모리 관리에 매우 중요합니다.
-   **텍스트 유사도 비교 및 시각화:** `difflib` 모듈을 활용하여 두 텍스트 문자열 간의 차이점을 효율적으로 식별하고, 이를 HTML로 시각화하여 변화를 한눈에 파악할 수 있는 유용한 기법을 학습했습니다. 이는 AI 모델의 텍스트 생성 능력 평가나 콘텐츠 리라이팅 작업에서 매우 유용하게 활용될 수 있습니다.
-   **WordPress `pre_get_posts` 훅과 `meta_type`의 중요성:** `pre_get_posts` 훅을 사용하여 `WP_Query`를 커스터마이징할 때, 커스텀 필드(`meta_key`)로 정렬할 경우 `meta_type`을 실제 저장 형식에 맞춰 정확하게 지정해야 쿼리가 올바르게 동작한다는 것을 다시 한번 확인했습니다. 특히 날짜/시간 데이터는 `DATETIME`으로 명시해야 정확한 시간 순서 정렬이 가능합니다.
    

## 💡 실전 시행착오 및 팁

-   **동적 DOM 요소의 이벤트 핸들러 유지:** `$originalSearchInitialState.clone(true)`에서 `true` 인자의 중요성을 다시 한번 상기했습니다. 이 인자는 복사본에 원본 요소의 모든 자식 노드와 이벤트 핸들러까지 깊게 복사하도록 지시합니다. 이를 통해 동적으로 복원되는 UI 요소들의 기능이 유실되지 않도록 효과적으로 관리할 수 있었습니다.
-   **AI 모델별 텍스트 스타일 비교의 필요성:** GPT, Claude, Gemini, ClovaX 등 다양한 AI 모델이 동일한 원본 텍스트에 대해 각기 다른 뉘앙스와 문체로 리라이팅하는 것을 직접 확인했습니다. 이를 HTML 비교 도구를 통해 시각적으로 비교함으로써, 특정 목적(예: 마케팅, 기술 문서, 친근한 어조 등)에 가장 적합한 AI 모델을 선택하는 데 유용한 통찰을 얻었습니다.
    

## 🔜 이후 학습 방향

-   **React 앱 기능 구현 착수:** 워드프레스 백엔드 연동이 확인되었으므로, 실제 React 앱에서 핵심 기능들을 개발하고 구현하는 단계로 나아갈 것입니다.
-   **딥링크(Deep Link) 기술 리서치:** 웹에서 앱으로의 자연스러운 연결을 위한 딥링크 기술에 대해 심도 있게 조사하고, React 앱에 적용할 수 있는 방안을 탐색할 예정입니다. (Facebook 사례 참고)
-   **애플(iOS) 앱 출시 절차 상세 조사:** 앱 출시 경험을 위해 iOS 앱 스토어에 앱을 배포하는 복잡한 절차(계정, 인증, 심사 과정 등)를 미리 상세히 리서치하여 추후 실제 출시를 위한 기반을 마련할 것입니다.
    

### 🔍 React vs Flutter: 비교 (추가 논의)

| 구분        | React                                         | Flutter                                      |
| :---------- | :-------------------------------------------- | :------------------------------------------- |
| **특징** | 웹 UI 라이브러리 기반의 앱 프레임워크 (React Native) | Google이 개발한 UI 툴킷, 네이티브 컴파일     |
| **장점** | - 웹 개발자에게 익숙한 JS/CSS 기반              | - 뛰어난 네이티브 성능 및 일관된 UI            |
|             | - 풍부한 라이브러리 및 커뮤니티                 | - Dart 언어의 간결성                         |
|             |                                               | - 빠른 개발 속도 (핫 리로드)                  |
| **단점** | - 브릿지를 통한 네이티브 모듈 접근 필요         | - 새로운 언어(Dart) 학습 필요                |
|             | - 특정 복잡한 네이티브 기능 구현 시 제약        | - 웹/데스크톱은 아직 상대적으로 생태계 작음    |
| **사용 예시** | 기존 웹 개발 경험을 활용한 빠른 앱 프로토타이핑, 하이브리드 앱 | 고성능/고품질의 네이티브에 가까운 앱, 복잡한 애니메

### 📝 요약

-   React Native와 Flutter 비교에서는 React Native가 웹 개발자에게 친숙한 환경과 풍부한 생태계를 제공하는 반면, Flutter는 Dart 언어를 기반으로 한 우수한 네이티브 성능과 일관된 UI를 강점으로 내세우고 있습니다.
-   두 프레임워크의 선택은 프로젝트의 구체적인 요구사항, 팀의 기존 기술 스택, 그리고 앱의 성능 및 UI 일관성에 대한 목표에 따라 달라집니다.

### 🧾 참고자료

**🔗 [React Native Official Documentation](https://reactnative.dev/): React Native의 특징 및 개발 환경 설정 관련 내용 참조**   
**🔗 [Flutter Official Documentation](https://flutter.dev/): Flutter의 특징, Dart 언어 및 크로스 플랫폼 개발 관련 내용 참조**  
