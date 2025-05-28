# 📅 Day 03 (2025-05-28, Wed)

## 🎓 What I Did Today

**📌 Attended the 9 AM Daily Development Meeting and confirmed key directives.**  
**📌 Completed in-depth learning and practical application exercises for WordPress Hooks.**  
**📌 Proceeded with organizing HTML, CSS, JavaScript technical documentation and revising PHP documentation.**  
**📌 Began preparing materials for the Friday AI technology presentation.**  

### Detailed Activities

* **Attended the 9 AM Daily Development Meeting:**
    * During the meeting, the **importance of understanding Hooks and Actions in WordPress backend development and customization** was re-emphasized.
    * I received advice that sufficient time and practice are needed for learning hooks, and was encouraged to start with theme customization via `functions.php` before expanding to plugin development.
    * It was noted that I had forgotten the **Airhomes speed tests** since last week. I was instructed to perform the tests **every day, first thing in the morning**, starting today, and confirmed I would do so immediately.

* **Completed In-depth WordPress Hooks Learning and Practical Application Exercises:**
    * Following the directives from the development meeting, I focused on learning hooks using the four YouTube lectures below and the official WordPress documentation:
        * [WordPress Hooks 개요](https://www.youtube.com/watch?v=MW-evyl4nQU)
        * [Action Hook(액션 훅) 집중 설명](https://www.youtube.com/watch?v=D3e4ZxaQN5g)
        * [Filter Hook(필터 훅) 집중 설명](https://www.youtube.com/watch?v=EZNJWgq26_E)
        * [Working with Hooks (우선순위, 파라미터, 실행 순서 등)](https://www.youtube.com/watch?v=oUGP91_9RjE)
    * I clearly understood the concepts, internal structure, and actual workings of **Action Hooks** and **Filter Hooks**.
    * I practiced the **practical usage** of `add_action()` and `add_filter()` functions and explored various **real-world examples** for their application.
    * I learned advanced usage of hook **Priority** and **Parameter passing**, and understood the **execution order** of code.
    * I organized methods for effectively utilizing **official hook documentation and reference materials (Hooks Reference)**, confirming its essential role in finding the right hooks for specific functionalities.

* **Proceeded with Organizing Technical Documentation and Revising PHP Documentation:**
    * I **organized** my learning content related to `html` and `css`, which will be uploaded later.
    * `javascript` related materials were also **organized** and are slated for future upload.
    * I performed **revisions** on existing `php` documentation.

* **Began Preparing Materials for the Friday AI Technology Presentation:**
    * I started preparing for the presentation scheduled for this Friday, titled **"Analysis of AI Technology's Impact on Online Search and Marketing Environments and Proposed Future Utilization Strategies."** I collected relevant materials and outlined the main structure of the presentation before leaving work.

### 🧠 Key Concepts Learned

* **Reconfirmed the Importance of WordPress Hooks**: Understood that hooks are a core tool for backend development and customization, offering a safe and maintainable way to extend functionality without directly modifying core files.
* **Clear Distinction Between Action and Filter Hooks**: Realized that accurately understanding the purpose of Action hooks (for 'execution') and Filter hooks (for 'data modification and return') is the first step in effective hook utilization.
* **Essential Use of Developer Tools and Official Documentation**: Reconfirmed the critical role of Chrome Developer Tools and the official WordPress Hooks Reference in finding, applying, and debugging hooks in practice.

### 💡 Practical Trial & Error and Tips

* Through practice, I strongly remembered that `add_filter()` **must return a value**; failure to do so can lead to critical errors.
* I realized the high importance of **adjusting Priority** to control the execution order when multiple functions are attached to the same hook.
* I confirmed that when a hook passes multiple arguments, the `accepted_args` parameter in `add_action()` or `add_filter()` must **accurately specify the number of arguments** for the callback function to utilize all of them.

### 🔜 Future Study Direction

* **In-depth PHP Hooks Learning and Practical WooCommerce Functionality Extension**: Continue practicing applying learned hook concepts to real WooCommerce scenarios (e.g., modifying product prices under specific conditions, customizing payment logic).
* **Learning the Role of JavaScript and AJAX in WordPress/WooCommerce Environments**: Delve into actual use cases of JavaScript for implementing client-side dynamic interactions and asynchronous communication.
* **Refining AI Presentation Materials**: Based on the collected data for the Friday presentation, I will deepen the analysis, and proceed with structuring slides and writing content for specific utilization strategies.

---

# 📅 Day 03 (2025-05-28, 수)

## 🎓 오늘 한 일

**📌 오전 9시 일일 개발 미팅 참석 및 주요 지시사항 확인.**  
**📌 워드프레스 훅(Hooks)에 대한 심층 학습 및 실전 적용 연습 완료.**  
**📌 HTML, CSS, JavaScript 기술 문서 정리 및 PHP 문서 수정 진행.**  
**📌 금요일 AI 기술 발표 자료 준비 시작.**  

### 상세 활동

* **오전 9시 일일 개발 미팅 참석:**
    * 미팅에서는 **워드프레스 백엔드 개발 및 커스터마이징에 있어 훅(Hooks)과 액션(Actions) 이해의 중요성**을 다시 한번 강조받았습니다.
    * 훅 학습에 충분한 시간과 연습이 필요하다는 조언을 들었으며, `functions.php` 파일을 통한 테마 커스터마이징부터 시작하여 향후 플러그인 개발까지 확장할 것을 제안받았습니다.
    * **Airhomes 속도 테스트**를 지난주부터 잊고 있었다는 점을 확인받았고, 오늘부터 **매일 아침 가장 먼저 테스트를 진행**하라는 지시를 받았습니다. 이에 즉시 실행하겠다고 보고했습니다.

* **워드프레스 훅 심층 학습 및 실전 적용 연습 완료:**
    * 개발 미팅에서 강조된 내용에 따라, 아래 유튜브 강의 4편과 워드프레스 공식 문서를 활용하여 훅 학습을 집중적으로 진행했습니다.
        * [WordPress Hooks 개요](https://www.youtube.com/watch?v=MW-evyl4nQU)
        * [Action Hook(액션 훅) 집중 설명](https://www.youtube.com/watch?v=D3e4ZxaQN5g)
        * [Filter Hook(필터 훅) 집중 설명](https://www.youtube.com/watch?v=EZNJWgq26_E)
        * [Working with Hooks (우선순위, 파라미터, 실행 순서 등)](https://www.youtube.com/watch?v=oUGP91_9RjE)
    * **액션 훅(Action Hooks)**과 **필터 훅(Filter Hooks)**의 개념, 내부 구조, 실제 작동 방식에 대해 명확히 이해했습니다.
    * `add_action()`과 `add_filter()` 함수의 **실제 사용법**을 익히고 다양한 **실전 예시**를 통해 적용 방안을 모색했습니다.
    * 훅의 **우선순위(Priority)** 및 **인자(Parameter) 전달** 방식에 대한 고급 사용법을 학습하고, 코드가 실행되는 **순서**를 파악했습니다.
    * **훅의 공식 문서 및 참고 자료(Hooks Reference)를 효과적으로 활용하는 방법**을 정리했습니다. 이는 특정 기능에 필요한 훅을 찾아내는 데 필수적인 과정임을 확인했습니다.

* **기술 문서 정리 및 수정 진행:**
    * `html`, `css` 관련 학습 내용을 **정리**했으며, 이는 추후 업로드할 예정입니다.
    * `javascript` 관련 자료도 **정리** 작업을 진행했고, 역시 업로드 예정입니다.
    * `php` 관련 문서에 대해서는 기존 내용을 **수정**하는 작업을 수행했습니다.

* **금요일 AI 기술 발표 자료 준비 시작:**
    * 이번 주 금요일에 진행될 **"AI 기술이 온라인 검색과 마케팅 환경에 끼친 영향 분석 및 향후 활용 전략 제안"** 발표를 위해 자료 준비에 착수했습니다. 퇴근 시간까지 관련 자료를 수집하고 발표의 큰 틀을 구상했습니다.

### 🧠 배운 핵심 개념

* **워드프레스 훅의 중요성 재확인**: 백엔드 개발 및 커스터마이징의 핵심 도구이며, 코어 파일 직접 수정을 피하면서 기능을 확장하는 안전하고 유지보수성 높은 방법임을 다시금 체감했습니다.
* **액션과 필터 훅의 명확한 구분**: '실행' 목적의 액션과 '데이터 수정 및 반환' 목적의 필터의 역할을 정확히 이해하는 것이 훅 활용의 첫걸음임을 확인했습니다.
* **개발자 도구 및 공식 문서 활용의 필수성**: 실제 훅을 찾고 적용하며 디버깅하는 과정에서 크롬 개발자 도구와 워드프레스 공식 Hooks Reference의 중요성을 재확인했습니다.

### 💡 실전 시행착오 및 팁

* `add_filter()` 사용 시 **반드시 값을 반환(return)해야 한다**는 점을 실습을 통해 다시 한번 명심했습니다. 값을 반환하지 않으면 치명적인 오류가 발생할 수 있습니다.
* 여러 함수가 동일한 훅에 연결될 때 **우선순위(Priority)를 조절**하여 실행 순서를 제어하는 것이 매우 중요하다는 것을 깨달았습니다.
* 훅이 여러 인자를 전달할 경우, `add_action()` 또는 `add_filter()`의 `accepted_args` 파라미터를 통해 **인자 개수를 정확히 지정**해야 콜백 함수에서 모든 인자를 활용할 수 있음을 확인했습니다.

### 🔜 이후 학습 방향

* **PHP 훅 심화 학습 및 실제 우커머스 기능 확장 연습**: 배운 훅 개념을 바탕으로 실제 우커머스 시나리오(예: 특정 조건에 따른 상품 가격 변경, 결제 로직 커스터마이징)에 적용하는 연습을 계속합니다.
* **JavaScript와 AJAX의 워드프레스/우커머스 환경 내 역할 학습**: 클라이언트 측 동적 상호작용 및 비동기 통신 구현을 위해 JavaScript의 실제 활용 사례를 파고들어 학습합니다.
* **AI 발표 자료 구체화**: 금요일 발표를 위해 수집된 자료를 바탕으로, 분석 내용을 심화하고 구체적인 활용 전략 제안을 위한 슬라이드 구성 및 내용 작성을 본격적으로 진행합니다.

