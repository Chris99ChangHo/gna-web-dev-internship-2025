# 📅 Day 01 (2025-06-30, Mon)

## 🎓 What I Did Today

**📌 Participated in the morning development meeting: Shared DevNewsHub mini-project progress, discussed the CEO's directed task status, and planned future development.**  
**📌 Initiated DevNewsHub mini-project search UI improvements and custom publish date sorting attempts.**  
**📌 Implemented a custom news carousel using PHP shortcodes in WordPress to overcome Elementor widget limitations, adjusting its layout.**  
**📌 Set up the React Native/Expo development environment, resolved various errors, and implemented core app features like news listing, HTML entity decoding, and Text-to-Speech (TTS).**  
**📌 Attempted to integrate React Navigation but identified nesting errors, leading to a re-evaluation of its necessity for the current project scope.**  
**📌 Continued improving awkward Korean translations for the company's English website, reporting results and awaiting further instructions.** 

### Detailed Activities

**1. Morning Development Meeting Summary**

-   This morning's development meeting involved a brief update on the DevNewsHub mini-project.
    
-   **DevNewsHub Mini-Project Status:**
    
    -   Progress was made on search UI improvements.
        
    -   Attempted to customize the news publish date (using `news-published-date` custom field) but have not yet succeeded.
        
-   **CEO's Directed Tasks Status & Future Plans Discussion:**
    
    -   **Korean Translation Improvement for English Site:** Ongoing work to refine awkward Korean translations of the English website. Methods to correct unnatural phrasing were applied, and results were reported.
        
    -   **Awaiting Next Instructions:** No further instructions have been received from the CEO regarding this task yet.
        
    -   **Future Plans:**
        
        -   If there are no follow-up instructions from the CEO on the translation improvement task, I will check on the progress again and request further guidance.
            
        -   In the absence of specific directives, I will return to the DevNewsHub mini-project development and continue building the app.
            
        -   Alongside app development, I plan to concurrently explore additional avenues such as WordPress plugin development to expand the project's capabilities.
            

**2. WordPress Work Status & Problem Solving**

-   **Background:** Faced a limitation where Elementor's 'Posts' widget could not sort by 'actual publish date' (the custom field `news-published-date`). Consequently, I abandoned the Elementor widget for this functionality and switched to writing custom PHP shortcodes inserted into an HTML widget, aiming for more precise control.
    
-   **Initial PHP Shortcode Issues Identified:**
    
    -   The shortcode inserted into the HTML widget (calling `inc/carousel-shortcode.php`) showed that `WP_Query`'s sorting was set to `'orderby' => 'date'` and `'order' => 'ASC'`, which incorrectly displayed 2023 news first instead of the latest.
        
    -   There was a need to improve the logic for accurately parsing various date formats stored in the 'actual publish date' custom field (`news-published-date`) and unifying them to the `YYYY-MM-DD HH:MM:SS` format for consistent output.
        
-   **Layout & Feature Additions:**
    
    -   Directly implemented a custom carousel with code into the latest news container, replacing the old 'posts' widget, and adjusted the layout.
        
    -   Added a button utilizing a REST API to navigate to another page in the empty space below the right-side search bar, and readjusted the overall layout.
        
    -   Additionally, configured SNS icons for future connection to actual SNS accounts.
        

**3. React Native/Expo Work Status & Progress (DevNewsHub Mini Project)**

**3.1. Tech Environment Setup & Troubleshooting**

-   **Expo/React Native Environment Setup:** Configured the development environment within an Expo project for integrating with the WordPress News API.
    
-   **Library and Tool Error Resolution:** Resolved various errors encountered during the installation of essential libraries like `expo-speech` and `he`, as well as issues related to `npm`, `adb`, and the emulator.
    
-   **Emulator and ADB Connection Verification:** Successfully launched the Android emulator (API 34) and directly verified the `adb` connection, completing the development setup.
    

**3.2. Core Feature Implementation & Structure Improvement (Challenges & Solutions)**

-   **Basic News List App Structure Implementation:**
    
    -   Successfully fetched news data from the WordPress API within `HomeScreen` (or `index.tsx`).
        
    -   HTML Entity Decoding and Tag Removal: Utilized the `he` library to decode HTML entities and remove unnecessary tags from the news content, significantly improving readability.
        
    -   Dark Mode/Theme Issue Resolution: Explicitly styled basic components like `SafeAreaView`, `Text`, `View`, and `TouchableOpacity` to prevent issues where dark text appeared on a dark background in dark mode/theme.
        
-   **TTS (News Read-aloud) Feature Implementation:**
    
    -   Used the `expo-speech` library to add a "Play" button to each news card.
        
    -   Successfully implemented the functionality for the button to read the news article's body aloud.
        
-   **Component Modularization and Structure Improvement Attempt (Ongoing):**
    
    -   Successfully separated the news card (`NewsCard`) component into a distinct file like `components/NewsCard.tsx`, achieving UI/logic separation. The current structure aims to assign data fetching and list management to `HomeScreen`, and UI/logic to `NewsCard`, facilitating future expansion for features like sharing, bookmarking, and detail viewing.
        
    -   However, further improvements are deemed necessary to achieve complete modularization.
        
-   **Navigation (React Navigation) Introduction Attempt (Under Review):**
    
    -   Installed `@react-navigation/native` and `@react-navigation/stack`, attempting to configure `HomeScreen` (news list) and TTS (read-aloud) screens using `NavigationContainer` and `Stack.Navigator` in `App.tsx` or `index.tsx`.
        
    -   **Major Errors and Analysis of Failure Causes:**
        
        -   `NavigationContainer` Nesting Error: Encountered `Error: Looks like you have nested a 'NavigationContainer' inside another.` This error occurs when `NavigationContainer` is nested more than once in the app tree, particularly when Expo Router is used, which can implicitly cause duplication. This issue prevented the app from functioning correctly, resulting in blank screens or error messages.
            
        -   Screen Naming/Path Mismatch: Experienced issues where screen transitions failed or errors occurred because the `name` in `Stack.Navigator` did not precisely match the target for `navigation.navigate`.
            
        -   Package Installation/Path Issues: Also encountered errors where modules could not be found due to missing necessary navigation packages or mismatches between import paths/filenames and actual file locations.
            
    -   **Learnings for Improvement and Resolution:**
        
        -   Learned that `NavigationContainer` should be used only once across the entire app, and specifically, it should not be directly used when Expo Router is in place.
            
        -   Understood the importance of consistently matching screen `name`s, filenames, and `import` paths, and the necessity of restarting the app after package installation and cache clearing.
            
    -   **Current Assessment:** A definitive conclusion on the necessity of introducing navigation has not yet been reached, and further review is deemed necessary considering the current project scope and complexity.
        

## 🧠 Key Concepts Learned

-   **WordPress `WP_Query` Customization:** Learned the importance of directly controlling `WP_Query` for sorting by custom fields, going beyond the limitations of Elementor widgets.
    
-   **Importance of Date Format Parsing and Unification:** Understood that accurately parsing various date formats in custom fields (`news-published-date`) and unifying them to `YYYY-MM-DD HH:MM:SS` is essential for correct sorting and data utilization.
    
-   **React Native/Expo Environment Setup and Troubleshooting:** Gained experience in resolving common errors encountered during the setup of `expo-speech`, `he`, `npm`, and `adb` for React Native/Expo.
    
-   **React Native App Basic Component Styling:** Learned to explicitly style `SafeAreaView`, `Text`, `View`, `TouchableOpacity` to handle dark mode/theme issues where text might become unreadable against a dark background.
    
-   **HTML Entity Decoding and Tag Removal:** Applied the `he` library to effectively decode HTML entities and remove unnecessary tags from API-fetched news content for better readability.
    
-   **React Navigation Nesting Errors and Usage Precautions:** Identified that `NavigationContainer` should be used only once at the app's root and learned about potential conflicts when integrating with framework-specific routers like Expo Router, emphasizing careful setup and consistent naming.
    

## 💡 Practical Learnings and Tips

-   **Overcoming Elementor Widget Limitations:** When Elementor widgets lack specific sorting or custom functionalities, directly writing PHP shortcodes into HTML widgets provides more flexible and powerful control.
    
-   **PHP Date/Time Data Handling:** For `WP_Query` to sort by custom date fields, it's crucial to ensure the custom field's date format in the database is consistent and accurately matches the `DATETIME` format. Inconsistent data can be a primary cause of query malfunction.
    
-   **React Native/Expo Environment Troubleshooting:** For library installation errors via `npm` or `yarn`, checking error messages carefully, installing missing packages, clearing cache (`npm cache clean --force`, `expo start --clear`), and reinstalling dependencies (`npm install` after deleting `node_modules`) are effective solutions.
    
-   **React Native UI Debugging:** To prevent text from disappearing in dark mode/themes, explicitly setting `backgroundColor` and `color` in `style` props for components is a good practice to prevent unexpected theme applications.
    
-   **Navigation Library Integration Caution:** When using `React Navigation` with `Expo Router`, be aware of potential `NavigationContainer` nesting errors. It's important to avoid direct usage of `NavigationContainer` when Expo Router is present. Always ensure screen names, file names, and import paths are exactly consistent.
    

## 🔜 Next Steps

-   **Advanced WordPress `WP_Query` Utilization:** Further study of custom field-based sorting and complex query conditions to enhance dynamic content management.
    
-   **Deep Dive into React Native/Expo App Development:** Complete modularization of the news card component and implement advanced app features like detail views, bookmarking, and sharing.
    
-   **Research React Navigation and Expo Router Integration Strategies:** Based on the re-evaluation of navigation, conduct in-depth research into optimal strategies for integrating React Navigation with Expo Router, considering project complexity and scalability.
    
-   **Explore WordPress Plugin Development:** To expand the DevNewsHub mini-project, I plan to explore the basics of WordPress plugin development beyond just theme development.
    
-   **Learning Text Translation/NLP Improvement Techniques:** In relation to the company's Korean website translation task, I will study techniques to overcome the limitations of AI-based translation and generate more natural translations (e.g., fine-tuning language models).
    
----------

# 📅 1일차 (2025-06-30, 월)

## 🎓오늘 한 일

**📌 오전 개발 미팅에 참여하여 DevNewsHub 미니 프로젝트 진행 상황과 사장님 지시 업무 현황 및 향후 계획을 공유하고 논의했습니다.**  
**📌 DevNewsHub 미니 프로젝트의 검색 UI 개선 작업을 진행했으며, 뉴스 발행일 커스텀 필드 정렬을 시도했습니다.**  
**📌 워드프레스에서 Elementor 위젯의 한계로 PHP 숏코드를 활용하여 최신 뉴스 캐러셀을 직접 구현하고 레이아웃을 조정했습니다.**  
**📌 React Native/Expo 개발 환경을 세팅하고 다양한 오류를 해결했으며, 뉴스 리스트, HTML 엔티티 디코딩, TTS(뉴스 읽어주기) 기능 등 핵심 앱 기능을 구현했습니다.**  
**📌 React Navigation 도입을 시도했으나 중첩 오류 등 문제점을 파악하고 현재 프로젝트 범위에 대한 내비게이션 필요성을 재검토 중입니다.**  
**📌 회사 영문 웹사이트의 어색한 국문 번역 개선 작업을 진행하고 다음 지시를 기다리고 있습니다.**  

### Detailed Activities

**1. 오전 개발 미팅 요약**

-   오늘 오전 개발 미팅에서는 DevNewsHub 미니 프로젝트 진행 상황과 사장님 지시 업무 현황 및 향후 계획을 간단히 공유했습니다.
    
-   **DevNewsHub 미니 프로젝트 진행 상황:**
    
    -   검색 UI 개선 작업을 진행했습니다.
        
    -   발행일 커스텀 시도: 뉴스 발행일을 실제 발행일(`news-published-date` 커스텀 필드) 기준으로 정렬하려 시도했으나, 현재까지는 성공하지 못했습니다.
        
-   **사장님 지시 업무 현황 및 향후 계획 논의:**
    
    -   **영문 사이트 국문 번역 개선:** 현재 사장님께서 지시하신 영문 사이트의 어색한 국문 번역을 개선하는 작업을 진행하고 있으며, 어색한 번역투를 고치기 위한 방법을 찾아 적용하고 그 결과를 보고했습니다.
        
    -   **다음 지시 대기:** 이와 관련하여 아직 사장님으로부터 다음 지시는 받지 못했습니다.
        
    -   **향후 계획:**
        
        -   사장님의 번역 개선 업무에 대한 후속 지시가 없는 경우, 한 번 더 진행 상황을 확인하고 다음 지시를 요청할 예정입니다.
            
        -   별도의 지시가 없을 경우, DevNewsHub 미니 프로젝트 개발로 다시 복귀하여 앱 개발을 계속 진행할 것입니다.
            
        -   이때, 앱 개발 외에 플러그인 개발과 같은 추가적인 시도도 병행하여 프로젝트의 확장성을 모색할 계획입니다.
            

**2. 워드프레스 (WordPress) 작업 현황 및 문제 해결**

-   **배경:** 기존 Elementor의 'Posts' 위젯으로는 '실제 발행일'(`news-published-date` 커스텀 필드) 기준 최신순 정렬이 불가능하다는 한계에 부딪혔습니다. 이에 따라 Elementor 위젯 사용을 포기하고, PHP 숏코드를 직접 작성하여 HTML 위젯에 삽입하는 방식으로 전환하여 더욱 세밀한 제어를 시도했습니다.
    
-   **초기 PHP 숏코드 문제점 확인:**
    
    -   HTML 위젯에 삽입된 숏코드(`inc/carousel-shortcode.php` 호출)에서 `WP_Query`의 정렬 방식이 `'orderby' => 'date'` 및 `'order' => 'ASC'`로 설정되어 있어 최신순 정렬이 제대로 되지 않고 2023년 뉴스가 먼저 보이는 문제가 다시 확인되었습니다.
        
    -   '실제 발행일' 커스텀 필드(`news-published-date`)에 저장된 다양한 날짜 형식을 정확히 파싱하여 `YYYY-MM-DD HH:MM:SS` 형식으로 통일해 출력하는 로직 개선이 필요했습니다.
        
-   **레이아웃 및 기능 추가:**
    
    -   최신 뉴스 컨테이너에 기존 'posts' 위젯 대신 직접 코드로 캐러셀을 구현하여 삽입하고 레이아웃을 조정했습니다.
        
    -   이로 인해 발생한 우측 검색창 하단 여백에는 REST API를 활용한 다른 페이지로 이동하는 버튼을 추가하고 레이아웃을 재조정했습니다.
        
    -   추가로 SNS 아이콘을 구성하여 추후 실제 SNS 계정에 연결할 수 있도록 준비했습니다.
        

**3. React Native/Expo 작업 현황 및 진행 상황 (DevNewsHub 미니 프로젝트)**

**3.1. 기술 환경 세팅 및 문제 해결**

-   **Expo/React Native 환경 설정:** Expo 프로젝트에서 워드프레스 뉴스 API 연동을 위한 개발 환경을 세팅했습니다.
    
-   **라이브러리 및 도구 오류 해결:** `expo-speech`, `he` 등 필수 라이브러리 설치 과정과 `npm`, `adb`, 에뮬레이터 관련하여 발생한 다양한 오류들을 여러 차례 해결했습니다.
    
-   **에뮬레이터 및 ADB 연결 확인:** Android 에뮬레이터(API 34)를 성공적으로 구동하고, `adb` 연결까지 직접 확인하여 개발 준비를 마쳤습니다.
    

**3.2. 주요 기능 구현 및 구조 개선 과정 (도전 및 해결 방안)**

-   **기본 뉴스 리스트 앱 구조 구현:**
    
    -   `HomeScreen` (또는 `index.tsx`)에서 워드프레스 API로부터 뉴스 데이터를 성공적으로 가져왔습니다.
        
    -   HTML 엔티티 디코딩 및 태그 제거: `he` 라이브러리를 활용하여 텍스트의 HTML 엔티티를 디코딩하고 불필요한 태그를 제거해 뉴스 본문의 가독성을 크게 개선했습니다.
        
    -   다크모드/테마 문제 해결: `SafeAreaView`, `Text`, `View`, `TouchableOpacity` 등 기본 컴포넌트에 스타일을 명시적으로 지정하여 검은 배경에 검은 글씨가 보이는 다크모드/테마 문제를 해결했습니다.
        
-   **TTS (뉴스 읽어주기) 기능 구현:**
    
    -   `expo-speech` 라이브러리를 사용해 각 뉴스 카드에 "읽어주기(Play)" 버튼을 추가했습니다.
        
    -   버튼 클릭 시 뉴스 본문을 음성으로 읽어주는 기능을 성공적으로 구현했습니다.
        
-   **컴포넌트 모듈화 및 구조 개선 시도 (진행 중):**
    
    -   뉴스 카드(`NewsCard`) 컴포넌트를 `components/NewsCard.tsx`와 같은 별도 파일로 분리하여 UI/로직 분리에는 성공했습니다. 현재 구조는 `HomeScreen`이 데이터 fetch와 리스트 관리, `NewsCard`가 UI/로직을 담당하도록 역할을 분리하여 향후 공유, 북마크, 상세 보기 등 추가 기능 확장에 용이하도록 설계 방향을 잡았습니다.
        
    -   하지만 이 과정에서 모듈화의 완전한 해결까지는 추가적인 개선이 필요하다고 판단하고 있습니다.
        
-   **내비게이션 (React Navigation) 도입 시도 (검토 중):**
    
    -   `@react-navigation/native` 및 `@react-navigation/stack`을 설치하고, `App.tsx` 또는 `index.tsx`에서 `NavigationContainer`와 `Stack.Navigator`를 이용해 홈(뉴스 리스트)과 TTS(읽어주기) 스크린을 구성하려 했습니다.
        
    -   **주요 에러 및 실패 원인 분석:**
        
        -   `NavigationContainer` 중첩 오류: `Error: Looks like you have nested a 'NavigationContainer' inside another.` 오류가 발생했습니다. 이는 앱 트리에 `NavigationContainer`가 두 번 이상 중첩되어 발생한 것으로 보이며, 특히 Expo Router와 React Navigation을 함께 사용할 때 내부적으로 중복될 수 있음을 확인했습니다. 이 오류로 인해 앱이 정상적으로 동작하지 않고 화면이 비거나 에러가 출력되는 문제가 있었습니다.
            
        -   스크린 네이밍/경로 불일치: `Stack.Navigator`의 `name`과 `navigation.navigate`의 대상이 정확히 일치하지 않아 화면 전환이 되지 않거나 에러가 발생하는 문제를 겪었습니다.
            
        -   패키지 설치/경로 문제: 필요한 내비게이션 패키지가 누락되었거나 `import` 경로/파일명이 실제 파일과 불일치하여 모듈을 찾지 못하는 에러도 경험했습니다.
            
    -   **개선 및 해결 방향 습득:**
        
        -   `NavigationContainer`는 앱 전체에서 단 한 번만 사용해야 하며, 특히 Expo Router를 사용할 때는 직접 사용하지 않아야 함을 파악했습니다.
            
        -   스크린 `name`, 파일명, `import` 경로를 모두 일치시켜야 한다는 점과 패키지 설치 및 캐시 초기화 후 앱 재시작이 필요하다는 점을 배웠습니다.
            
    -   **현재 판단:** 내비게이션 도입의 필요성에 대해 아직 확실한 결론을 내리지 못했으며, 현재 프로젝트 범위와 복잡도를 고려하여 추가적인 검토가 필요하다고 판단하고 있습니다.
        

## 🧠 배운 핵심 개념

-   **워드프레스 `WP_Query` 커스터마이징:** Elementor 위젯의 한계를 넘어 커스텀 필드를 기준으로 정렬하는 등 `WP_Query`를 직접 제어하는 방법의 중요성을 배웠습니다.
    
-   **날짜 형식 파싱 및 통일의 중요성:** `news-published-date`와 같은 커스텀 필드의 다양한 날짜 형식을 정확히 파싱하고 `YYYY-MM-DD HH:MM:SS`와 같이 통일된 형식으로 관리하는 것이 정확한 정렬 및 데이터 활용에 필수적임을 이해했습니다.
    
-   **React Native/Expo 환경 설정 및 트러블슈팅:** `expo-speech`, `he`, `npm`, `adb` 등 다양한 라이브러리 및 도구 설치 과정에서 발생하는 일반적인 오류 해결 방법을 익혔습니다.
    
-   **React Native 앱의 기본 컴포넌트 스타일링:** `SafeAreaView`, `Text`, `View`, `TouchableOpacity` 등 기본 컴포넌트의 스타일을 명시적으로 제어하여 다크모드/테마 충돌과 같은 UI 문제를 해결하는 방법을 배웠습니다.
    
-   **HTML 엔티티 디코딩 및 태그 제거:** `he` 라이브러리를 활용하여 API에서 가져온 HTML 텍스트 내 불필요한 엔티티나 태그를 효과적으로 제거하여 가독성을 높이는 방법을 적용했습니다.
    
-   **React Navigation 중첩 오류 및 사용 주의점:** `NavigationContainer`가 앱 전체에서 한 번만 사용되어야 하며, 특히 Expo Router와 같은 프레임워크 자체 라우터와 함께 사용할 때 중복될 수 있음을 파악하고 관련 오류 해결 방안을 습득했습니다.
    

## 💡 실전 시행착오 및 팁

-   **Elementor 위젯의 한계 극복:** Elementor 위젯이 제공하지 않는 섬세한 데이터 정렬이나 커스텀 기능이 필요할 경우, 직접 PHP 숏코드를 작성하여 HTML 위젯에 삽입하는 방식이 훨씬 유연하고 강력한 제어를 제공함을 실감했습니다.
    
-   **PHP 날짜/시간 데이터 처리의 중요성:** `WP_Query`에서 커스텀 필드를 기준으로 날짜 정렬을 수행할 때, 데이터베이스에 저장된 커스텀 필드의 날짜 형식이 `DATETIME` 형식과 정확히 일치하도록 통일하는 것이 필수적입니다. 데이터 불일치는 쿼리 오작동의 주된 원인이 될 수 있습니다.
    
-   **React Native/Expo 환경 설정 시 문제 해결 팁:** `npm` 또는 `yarn`으로 라이브러리 설치 시 발생하는 오류는 대부분 의존성 문제이므로, 에러 메시지를 자세히 읽고 누락된 패키지 설치, 캐시 초기화(`npm cache clean --force`, `expo start --clear`), `node_modules` 삭제 후 재설치(`npm install`) 등을 시도하는 것이 효과적입니다.
    
-   **React Native UI 디버깅:** 다크모드/테마로 인해 텍스트가 보이지 않는 문제는 `style` 속성에 `backgroundColor`와 `color`를 명시적으로 지정하여 예상치 못한 테마 적용을 방지하는 것이 좋습니다.
    
-   **내비게이션 라이브러리 통합 주의:** `React Navigation`과 `Expo Router`를 함께 사용할 경우 `NavigationContainer` 중첩 오류가 발생할 수 있으므로, Expo Router 사용 시에는 React Navigation의 `NavigationContainer`를 직접 사용하지 않도록 주의해야 합니다. 또한 스크린 `name`, 파일명, `import` 경로가 정확히 일치하는지 항상 확인해야 합니다.
    

## 🔜 이후 학습 방향

-   **워드프레스 `WP_Query` 고급 활용:** 커스텀 필드 기반 정렬 및 복합 쿼리 조건에 대해 더 심도 있게 학습하여 동적인 콘텐츠 관리를 강화할 것입니다.
    
-   **React Native/Expo 앱 개발 심화:** 뉴스 카드 컴포넌트 모듈화를 완성하고, 앱의 상세 보기, 북마크, 공유 기능 등 핵심 기능을 추가 구현할 것입니다.
    
-   **React Navigation 및 Expo Router 통합 전략 연구:** 현재 내비게이션 도입에 대한 재검토를 바탕으로, 프로젝트의 복잡도와 확장성을 고려하여 React Navigation과 Expo Router를 효율적으로 통합할 수 있는 최적의 전략을 심층 연구할 것입니다.
    
-   **워드프레스 플러그인 개발 탐색:** DevNewsHub 미니 프로젝트의 확장성 모색을 위해, 단순 테마 개발을 넘어 워드프레스 플러그인 개발의 기본 개념과 실제 구현 방안을 탐색할 계획입니다.
    
-   **텍스트 번역/자연어 처리 개선 기술 학습:** 회사 영문 웹사이트 국문 번역 개선 작업과 관련하여, AI 기반 번역 기술의 한계점을 극복하고 더 자연스러운 번역을 생성하는 기술(예: 미세 조정된 언어 모델 활용)에 대해 학습할 것입니다.
