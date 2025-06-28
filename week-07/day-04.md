# 📅 Day 04 (2025-06-26, Thu)

## 🎓 What I Did Today

**📌 Participated in a development meeting to discuss yesterday's endpoint issues and new app development plans, receiving specific feedback.**  
**📌 Continued debugging efforts to resolve existing WordPress theme-related endpoint and front-end (CSS) issues.**  
**📌 Conducted installation and relevant research for the React Native (Expo) development environment and tools (React DevTools), confirming initial setup and data linkage possibilities.**  
**📌 Initiated the development of a simple mobile news app based on React Native (Expo), linked with the WordPress REST API.**  

### Detailed Activities

**1. Participation in Development Meeting and Discussion**

-   **Reporting and Discussing Yesterday's Issues:** Reported on and discussed the `popular-news` endpoint issue from yesterday (Day 03), which was not functioning correctly. The senior developer advised to clearly identify the cause, and if no immediate solution was apparent, rolling back to previous code and retrying might be the fastest and most reliable method.
-   **Reporting on React-based Simple App Development Plan:** Reported on the plan to develop a simple app using React, stating, "After resolving the endpoint issues and confirming data transfer, I will try to build it with basic functionalities." The senior developer praised this as a very important and good attempt for gaining experience in data communication and utilization, encouraging me to take time and conduct thorough research during development.
-   **Ongoing Feedback Requests and Learning Advice:** The senior developer requested continuous progress sharing during development meetings for feedback purposes and advised me to consistently pursue studies in areas like REST API and plugin development.

**2. Initial Development of WordPress News API Integration App**

-   **Objective:** Began development with the goal of fetching the latest news data from my WordPress server (using a custom `news` post type) and displaying it as a list in a mobile app (React Native/Expo).
-   **Basic Structure Design and Implementation:** Designed the app structure and wrote basic code in the React Native (Expo) environment.
    -   **Utilizing `useState`:** Used `useState`, a tool for storing "mutable values (state)" within a component, to manage states like the news list (`posts`).
        
```JavaScript
const [posts, setPosts] = useState([]);
```
        
-   **Utilizing `useEffect`:** Implemented logic primarily for fetching data from the API, using `useEffect`, a code block that automatically executes "when the component first appears on screen" or "when a specific value changes."
          
```JavaScript
useEffect(() => {
	// Code to fetch data here
}, []); // [] means "execute only once at first render"
```
        
-   **Fetching Data with `fetch`:** Used the `fetch` function to asynchronously retrieve article data from the WordPress REST API (`wp-json/wp/v2/news?_embed&per_page=10`).
          
```JavaScript
fetch('https://dev.gnasolutions.com.au/intern02/wp-json/wp/v2/news?_embed&per_page=10')
	.then(res => res.json())
	.then(data => setPosts(data))
	.catch(err => console.error(err))
```
        
-   **Rendering Article List with `FlatList`:** Used `FlatList`, a list component that efficiently renders multiple data items in a scrollable view, to display the article list with titles and excerpts.
        
```JavaScript
<FlatList
	data={posts}
	renderItem={({ item }) => (
		<Text>{item.title.rendered}</Text>
	)}
	keyExtractor={item => item.id.toString()}
/>
```
        
   -   **HTML Tag Removal and Text Cleanup:** Applied simple text cleanup by removing HTML tags from the excerpt data fetched from the API.
    -   **Flexible API Integration Confirmation:** Confirmed that merely changing the API URL instantly reflects data from a different WordPress server in the app, showcasing a flexible integration structure.
    -   **App Execution Confirmation:** Confirmed that the emulator or Expo Go automatically launched upon app execution, and data was displayed correctly.
    -   **Complete Code Example Developed Today:**
 
        ```JavaScript
        import React, { useEffect, useState } from 'react';
        import { FlatList, SafeAreaView, Text, TouchableOpacity } from 'react-native';
        
        const WP_API_URL = 'https://dev.gnasolutions.com.au/intern02/wp-json/wp/v2/news?_embed&per_page=10';
        
        export default function NewsScreen() {
          const [posts, setPosts] = useState([]);
        
          useEffect(() => {
            fetch(WP_API_URL)
              .then(res => res.json())
              .then(data => setPosts(data))
              .catch(err => console.error(err));
          }, []);
        
          return (
            <SafeAreaView style={{ flex: 1, padding: 16 }}>
              <FlatList
                data={posts}
                keyExtractor={item => item.id.toString()}
                renderItem={({ item }) => (
                  <TouchableOpacity>
                    <Text style={{ fontWeight: 'bold', fontSize: 18 }}>
                      {item.title.rendered}
                    </Text>
                    <Text numberOfLines={2}>
                      {item.excerpt.rendered.replace(/<[^>]+>/g, '')}
                    </Text>
                  </TouchableOpacity>
                )}
              />
            </SafeAreaView>
          );
        }
        ```
        

**3. Development Environment and Tool Setup & Issue Recognition**

-   **Attempted React DevTools Installation and Execution:** Attempted to globally install and execute React DevTools (standalone version).
-   **Resolving Command Typos and PATH Issues:** Learned that the correct command was `react-devtools` instead of `react devtools` and addressed PATH-related issues.
-   **Confirming DevTools Role:** Confirmed that DevTools is independent of app execution and is a tool specifically for debugging apps by inspecting the component tree, state, and props.
-   **Confirming Expo CLI Execution Method:** Confirmed that the emulator automatically launches (with Expo Go automatically installing and running the app) after the `expo start` command, either by clicking a button on the web UI, pressing the `a` key in the terminal, or using the `expo start -a` command.
-   **Recognizing Console Warnings:** Noted the following console warning messages during app execution:
    -   `shadow*` style props deprecated → Use `boxShadow`: Indicates that `shadow*` related style properties are deprecated, recommending the use of `boxBoxShadow` in the future.
    -   `props.pointerEvents` deprecated → Use `style.pointerEvents`: Indicates that passing the `pointerEvents` property directly as `props` is deprecated, and it should be passed within the `style` object, like `style.pointerEvents`, to conform to the latest standards.

**4. Continued Debugging Efforts for Existing WordPress Theme Issues**

-   Continued debugging efforts to resolve the JSON response error of the `devnewshub/v1/popular-news` REST API, which was discovered yesterday. Reviewed and attempted to modify the logic to ensure the API correctly returns data.
-   Persisted in identifying and exploring solutions for the issue where the `popular-news-styles.css` file was not correctly applied to the web page. Used browser developer tools to thoroughly examine CSS load paths, selector specificity, and caching issues.
-   Attempted to create a new REST API endpoint (`comments-popular`) for sorting news by comment count, but similar to other API issues, data was not being transferred correctly, leading to continued analysis of the cause and potential solutions.

## 🧠 Key Concepts Learned

-   **Importance of Rollback Strategy in Problem Solving:** Reconfirmed that sometimes, rather than spending excessive time on root cause analysis, rolling back the code to a stable previous state and re-approaching the problem from scratch can be more efficient in reducing inefficiency and solving issues quickly.
-   **Value of Practical Development Experience:** Realized that beyond merely implementing features, gaining practical experience in sending, receiving, and utilizing data through APIs to build new services is crucial for enhancing development capabilities.
-   **Necessity of Thorough Prior Research:** Was reinforced that when undertaking projects with new technology stacks (like React Native Expo), taking time for comprehensive prior research and conceptual learning is key to successful implementation.
-   **Core React Native Hooks:** Understood and practically applied the basic principles of managing component state with `useState` and handling lifecycle events and side effects like data loading with `useEffect`.
-   **React Native List Rendering:** Learned how to efficiently render large amounts of data as a scrollable list using the `FlatList` component.
-   **Meaning and Resolution of Console Warnings:** Learned that console warnings, such as `shadow*` style props transitioning to `boxShadow` and `props.pointerEvents` to `style.pointerEvents`, indicate the need for gradual code modification to align with the latest React Native standards.
-   **Method for Verifying API Data Structure:** Learned the importance of directly opening API URLs in a browser to check JSON data and comparing it with data fetched in the app using `console.log()` for verification.
-   **Flexibility of WordPress REST API:** Confirmed the advantage of a structure where simply changing the API URL can instantly link to data from a different WordPress server.

## 💡 Practical Learnings and Tips

-   **Courage to Rollback When Stuck:** When debugging takes considerable time, or the cause is hard to find, or issues are complexly intertwined, daring to rollback to a previous commit and approaching the problem from a fresh perspective can surprisingly be very efficient. This saves time and aids in finding solutions.
-   **Systematic Debugging Approach:** Reconfirmed the effectiveness of recognizing and resolving issues step-by-step by utilizing `error_log` within the code, checking server-side `debug.log` and `error.log` files, and inspecting content in browser developer tools (console, network tab, etc.).
-   **Proficiency in Development Tools:** Understood that specialized debugging tools like React DevTools are essential for understanding the state and prop flow of components, independent of app execution, and that proficiency in their use is crucial.

## 🔜 Future Learning Directions

-   **Most Pressing Issue Resolution:** Prioritize resolving the JSON response issues of the view-count-based news endpoint and CSS non-application problems, as well as the comment count endpoint issue related to the existing `DevNewsHub` WordPress theme. This includes gathering browser developer tool information and re-verifying file paths as requested by the senior developer.
-   **REST API and Thumbnail Logic Improvement:** Once JSON response issues are resolved, optimize the yearly filtering and view count sorting logic for the `popular-news` endpoint, and complete the work to ensure the `news-search-thumb` (thumbnail size) is correctly applied across all popular news sections.
-   **React Native Expo App Development Progress:** Focus on implementing basic functionalities for the promised Expo app and gaining experience in sending and receiving data via the WordPress REST API.
-   **In-depth REST API Research:** Plan to conduct in-depth research on general REST API concepts and various query parameter usage (categories, tags, search, pagination, images, etc.), beyond just the WordPress REST API.
-   **Code Modularization Principles Research:** Intend to study code modularization principles and effective patterns applicable across various programming languages, including PHP.
-   **Advanced React Native Expo Utilization Research:** Aim to research best practices, performance optimization techniques, and advanced feature implementation methods (e.g.,  `boxShadow` instead of `shadow*`, passing `pointerEvents` via `style`) for React Native app development using the Expo framework.
-   **Materializing New App Ideas:**
    -   **Basic News Reader/Feed App:** Implement core functionalities such as latest news lists, category-specific/search/detail views, and infinite scrolling.
    -   **Keyword/Topic-based News Curation:** Implement features for registering keywords of interest, personalized news feeds, and notification functions.
    -   **News Summarization/Highlighting:** (Consider future AI integration possibilities)
    -   **News Archive/Search:** Implement diverse search and filter conditions based on date, category, tag, and reporter name.
    -   **Notification/Push Functionality:** Implement push notifications upon new article registration via Expo/Firebase, and personalized notifications by category/keyword.
    -   **SNS Sharing/Scrap:** Implement social media sharing buttons (KakaoTalk, Twitter, Facebook, etc.) for each article, and article bookmarking/scraping features.
    -   **TTS (Text-to-Speech) Functionality:** Implement article body audio output using libraries like `expo-speech` (extendable with "read aloud" buttons, auto-playlists, speed/voice options), providing accessibility, multitasking, and a differentiated user experience.

----------

# 📅 4일차 (2025-06-26, 목)

## 🎓 오늘 한 일

**📌 개발 미팅에 참여하여 어제 발생한 엔드포인트 문제와 새로 시작한 앱 개발 계획에 대해 논의하고 구체적인 피드백을 받았습니다.**  
**📌 기존 워드프레스 테마 관련 엔드포인트 및 프런트엔드(CSS) 문제 해결을 위한 디버깅을 계속 진행했습니다.**  
**📌 React Native(Expo) 개발 환경 및 도구(React DevTools) 설치와 관련 리서치를 진행하며, 초기 설정 및 데이터 연동 가능성을 확인했습니다.**  
**📌 워드프레스 REST API를 연동한 React Native(Expo) 기반의 간단한 모바일 뉴스 앱 개발을 시작했습니다.**  

### 상세 활동

**1. 개발 미팅 참여 및 논의**

-   **어제 문제점 보고 및 논의:** 어제(Day 03) `popular-news` 엔드포인트가 제대로 작동하지 않았던 문제에 대해 보고하고 논의했습니다. 개발 선임은 원인을 명확히 파악하고, 만약 해결 방법이 마땅치 않다면 이전 코드로 롤백하여 다시 시도하는 것이 때로는 가장 빠르고 확실한 방법일 수 있다고 조언했습니다.
-   **React 기반 심플 앱 개발 계획 보고:** React를 활용한 심플 앱 개발 계획에 대해 "엔드포인트 문제를 해결하고 데이터가 제대로 전달되는 것을 확인한 후에 간단한 기능을 넣어 만들어보겠다"고 보고했습니다. 개발 선임은 데이터 주고받고 활용하는 경험이 매우 중요하고 좋은 시도라고 평가하며, 시간을 가지고 충분히 리서치하면서 만들어보라고 격려했습니다.
-   **지속적인 피드백 요청 및 학습 조언:** 개발 선임으로부터 피드백을 위해 지속해서 개발 미팅 때 진척 상황을 공유해달라는 요청을 받았으며, REST API나 플러그인 개발과 같은 학습도 꾸준히 이어갈 것을 조언받았습니다.

**2. 워드프레스 뉴스 API 연동 앱 개발 (초기 단계)**

-   **목표:** 내 워드프레스 서버(news 커스텀 포스트 타입)에서 최신 뉴스 데이터를 가져와 모바일 앱(React Native/Expo)에서 리스트로 보여주는 것을 목표로 개발을 시작했습니다.
-   **기본 구조 설계 및 구현:** React Native(Expo) 환경에서 앱 구조를 설계하고 기본 코드를 작성했습니다.
    -   **`useState` 활용:** 컴포넌트 안에서 "변할 수 있는 값(상태)"을 저장하는 도구인 `useState`를 사용하여 뉴스 목록(`posts`)과 같은 상태를 관리했습니다.
        
```JavaScript
const [posts, setPosts] = useState([]);
```
        
-   **`useEffect` 활용:** "컴포넌트가 화면에 처음 보일 때" 또는 "특정 값이 바뀔 때" 자동으로 실행되는 코드 블록인 `useEffect`를 사용하여 주로 API에서 데이터를 불러오는 로직을 구현했습니다.
        
```JavaScript
useEffect(() => {
	// 여기에 데이터 불러오는 코드
}, []); // []는 "처음 한 번만 실행"이라는 뜻
```
        
-   **`fetch`로 API 데이터 불러오기:**  `fetch` 함수를 사용하여 워드프레스 REST API(`wp-json/wp/v2/news?_embed&per_page=10`)에서 기사 데이터를 비동기적으로 가져왔습니다.
        
```JavaScript
fetch('https://dev.gnasolutions.com.au/intern02/wp-json/wp/v2/news?_embed&per_page=10')
	.then(res => res.json())
	.then(data => setPosts(data))
	.catch(err => console.error(err));
```
        
-   **`FlatList`로 기사 리스트 렌더링:** 여러 데이터를 효율적으로 스크롤하여 보여주는 리스트 컴포넌트인 `FlatList`를 사용하여 기사 리스트를 렌더링하고 제목과 요약을 표시했습니다.
        
```JavaScript
<FlatList
	data={posts}
	renderItem={({ item }) => (
		<Text>{item.title.rendered}</Text>
	)}
	keyExtractor={item => item.id.toString()}
/>
```
        
   -   **HTML 태그 제거 및 텍스트 클린업:** API에서 가져온 데이터 중 본문 요약의 HTML 태그를 제거하여 간단한 텍스트 클린업을 적용했습니다.
    -   **유연한 API 연동 확인:** API URL만 바꿔도 다른 워드프레스 서버의 데이터가 즉시 앱에 반영되는 구조임을 확인했습니다.
    -   **앱 실행 확인:** 앱 실행 시 에뮬레이터 또는 Expo Go가 자동으로 실행되고 데이터가 정상적으로 표시되는 것을 확인했습니다.
    -   **오늘 만든 전체 코드 예시:**
       
        ```JavaScript
        import React, { useEffect, useState } from 'react';
        import { FlatList, SafeAreaView, Text, TouchableOpacity } from 'react-native';
        
        const WP_API_URL = 'https://dev.gnasolutions.com.au/intern02/wp-json/wp/v2/news?_embed&per_page=10';
        
        export default function NewsScreen() {
          const [posts, setPosts] = useState([]);
        
          useEffect(() => {
            fetch(WP_API_URL)
              .then(res => res.json())
              .then(data => setPosts(data))
              .catch(err => console.error(err));
          }, []);
        
          return (
            <SafeAreaView style={{ flex: 1, padding: 16 }}>
              <FlatList
                data={posts}
                keyExtractor={item => item.id.toString()}
                renderItem={({ item }) => (
                  <TouchableOpacity>
                    <Text style={{ fontWeight: 'bold', fontSize: 18 }}>
                      {item.title.rendered}
                    </Text>
                    <Text numberOfLines={2}>
                      {item.excerpt.rendered.replace(/<[^>]+>/g, '')}
                    </Text>
                  </TouchableOpacity>
                )}
              />
            </SafeAreaView>
          );
        }
        ```
        

**3. 개발 환경 및 도구 세팅 및 문제점 인식**

-   **React DevTools 설치 및 실행 시도:** React DevTools (standalone 버전)를 글로벌 설치하고 실행을 시도했습니다.
-   **명령어 오타 및 PATH 문제 해결:**  `react devtools` 대신 `react-devtools`라는 올바른 명령어를 사용해야 함을 알게 되었고, PATH 문제 등을 해결했습니다.
-   **DevTools 역할 확인:** DevTools는 앱 실행 자체와는 무관하며, 컴포넌트 트리, 상태(state), 속성(props) 등을 확인하여 앱을 디버깅하는 용도의 도구임을 확인했습니다.
-   **Expo CLI 실행 방식 확인:**  `expo start` 명령 후 웹 UI에서 버튼을 클릭하거나 터미널에서 `a` 키를 입력, 또는 `expo start -a` 명령어를 통해 에뮬레이터가 자동으로 실행(Expo Go 자동 설치 및 앱 실행)됨을 확인했습니다.
-   **콘솔 경고 인식:** 앱 실행 중 다음과 같은 콘솔 경고 메시지를 확인했습니다.
    -   `shadow*` 스타일 props deprecated → `boxShadow` 사용 권장:  `shadow*` 관련 스타일 속성들이 deprecated(사용 중단 예정)되었으며, 앞으로는 `boxShadow`를 사용할 것을 권장한다는 내용입니다.
    -   `props.pointerEvents` deprecated → `style.pointerEvents` 사용 권장:  `pointerEvents` 속성을 `props`로 직접 전달하는 방식이 deprecated되었고,  `style.pointerEvents`와 같이 `style` 객체 내에서 전달해야 최신 표준에 맞는다는 내용입니다.

**4. 기존 워드프레스 테마 관련 문제점 디버깅 지속**

-   어제 발견된 `devnewshub/v1/popular-news` REST API의 JSON 응답 오류 문제를 해결하기 위한 디버깅을 이어갔습니다. API가 데이터를 올바르게 반환하도록 로직을 재검토하고 수정 시도했습니다.
-   `popular-news-styles.css` 파일이 웹 페이지에 올바르게 적용되지 않는 문제를 계속해서 파악하고 수정 방안을 모색했습니다. 브라우저 개발자 도구를 활용하여 CSS 로드 경로, 선택자 우선순위, 캐싱 문제 등을 면밀히 검토했습니다.
-   댓글 수를 기준으로 뉴스를 정렬하기 위한 새로운 REST API 엔드포인트(`comments-popular`)를 작성했으나, 이 역시 데이터가 제대로 넘어오지 않는 문제가 발생하여 원인 분석 및 해결 방안을 모색했습니다.

## 🧠 배운 핵심 개념

-   **문제 해결 시 롤백 전략의 중요성:** 때로는 원인 분석에 지나치게 많은 시간을 소요하기보다, 문제가 발생하기 직전의 안정적인 상태로 코드를 롤백하고 처음부터 다시 접근하는 것이 비효율을 줄이고 문제를 빠르게 해결하는 데 도움이 될 수 있음을 재확인했습니다.
-   **실용적인 개발 경험의 가치:** 단순히 기능을 구현하는 것을 넘어, API를 통해 데이터를 주고받고 이를 활용하여 새로운 서비스를 만들어보는 실질적인 경험이 개발 역량 강화에 매우 중요함을 인지했습니다.
-   **충분한 사전 리서치의 필요성:** 새로운 기술 스택(React Native Expo)을 활용하여 프로젝트를 진행할 때, 시간을 가지고 충분한 사전 리서치와 개념 학습이 성공적인 구현의 핵심임을 다시 한번 강조받았습니다.
-   **React Native 핵심 Hook:**  `useState`로 컴포넌트 상태를 관리하고,  `useEffect`로 생명 주기 및 데이터 로딩과 같은 부수 효과를 처리하는 기본 원리를 이해하고 실제 적용했습니다.
-   **React Native 리스트 렌더링:**  `FlatList` 컴포넌트를 사용하여 대량의 데이터를 효율적으로 스크롤 가능한 리스트로 렌더링하는 방법을 학습했습니다.
-   **콘솔 경고의 의미와 해결법:**  `shadow*` 스타일 props가 `boxShadow`로,  `props.pointerEvents`가 `style.pointerEvents`로 변경되는 등 최신 React Native 표준에 맞춰 코드를 점진적으로 수정해야 함을 알게 되었습니다.
-   **API 데이터 구조 확인법:** API URL을 브라우저에서 직접 열어 JSON 데이터를 확인하고, 앱에서 불러온 데이터와 일치하는지 `console.log()` 등으로 비교하는 것이 중요함을 배웠습니다.
-   **워드프레스 REST API의 유연성:** API URL만 바꿔도 다른 워드프레스 서버의 데이터를 즉시 연동할 수 있는 구조의 장점을 확인했습니다.

## 💡 실전 시행착오 및 팁

-   **막다른 길에 다다랐을 때 롤백의 용기:** 디버깅에 상당한 시간을 소요했음에도 원인을 찾기 어렵거나 문제가 복잡하게 얽혀 있을 경우, 과감히 이전 커밋으로 롤백하고 새로운 관점에서 다시 접근하는 전략이 의외로 효율적일 수 있습니다. 이는 시간을 절약하고 해결책을 찾는 데 도움이 됩니다.
-   **체계적인 디버깅 접근:** 코드 내 `error_log`를 활용하고, 서버의 `debug.log`,  `error.log` 파일 그리고 브라우저 개발자 도구(콘솔, 네트워크 탭 등)에서 나타나는 내용들을 통해 문제를 인식하고 단계별로 해결하는 것이 효과적임을 다시 한번 확인했습니다.
-   **개발 도구 활용법 숙지:** React DevTools와 같은 전문 디버깅 도구는 앱 실행과는 별개로, 컴포넌트의 상태와 속성 흐름을 파악하는 데 필수적임을 이해하고 그 활용법을 숙지하는 것이 중요합니다.

## 🔜 이후 학습 방향

-   **가장 시급한 문제 해결:** 기존 `DevNewsHub` 워드프레스 테마 관련, 조회수 기반 뉴스 엔드포인트의 JSON 응답 문제 및 CSS 미적용 문제, 댓글 수 엔드포인트 문제를 최우선으로 해결할 예정입니다. 개발 선임이 요청한 브라우저 개발자 도구 정보 수집과 파일 경로 재확인을 진행할 것입니다.
-   **REST API 및 썸네일 로직 개선:** JSON 응답 문제가 해결되면,  `popular-news` 엔드포인트의 연도 필터링 및 조회수 정렬 로직을 최적화하고, 썸네일 크기(`news-search-thumb`)가 모든 인기 뉴스 섹션에 올바르게 적용되도록 개선 작업을 완료할 예정입니다.
-   **React Native Expo 앱 개발 진척:** 약속한 Expo 앱의 간단한 기능 구현과 워드프레스 REST API를 통한 데이터 주고받는 경험을 쌓는 데 집중할 계획입니다.
-   **REST API 심화 연구:** 워드프레스 REST API뿐만 아니라 일반적인 REST API 개념과 다양한 쿼리 파라미터(카테고리, 태그, 검색, 페이징, 이미지 등) 사용법에 대해 심층적으로 연구할 예정입니다.
-   **코드 모듈화 원칙 연구:** PHP를 포함한 다양한 프로그래밍 언어에서 적용되는 코드 모듈화 원칙과 효과적인 패턴에 대해 학습할 것입니다.
-   **React Native Expo 활용 심화 연구:** Expo 프레임워크를 활용한 React Native 앱 개발의 베스트 프랙티스, 성능 최적화 기법, 그리고 고급 기능 구현 방식(예:  `shadow*` 대신 `boxShadow`,  `pointerEvents` 스타일 전달 등)에 대해 더 깊이 연구할 것입니다.
-   **신규 앱 아이디어 구체화 및 구현:**
    -   **기본 뉴스 리더/피드 앱:** 최신 기사 리스트, 카테고리별/검색/상세 뷰, 무한 스크롤 등 기본 기능 구현.
    -   **키워드/주제별 뉴스 큐레이션:** 관심 키워드 등록, 맞춤형 뉴스 피드, 알림 기능.
    -   **뉴스 요약/하이라이트:** (추후 AI 연동 가능성을 고려)
    -   **뉴스 아카이브/검색:** 날짜, 카테고리, 태그, 기자명 등 다양한 조건 검색/필터 기능.
    -   **알림/푸시 기능:** 새 기사 등록 시 Expo/Firebase 푸시 알림 발송, 카테고리/키워드별 맞춤 알림.
    -   **SNS 공유/스크랩:** 기사별 카카오톡, 트위터, 페이스북 등 공유 버튼, 기사 북마크/스크랩 기능.
    -   **TTS (Text-to-Speech) 기능:** 기사 본문을 `expo-speech` 등 라이브러리로 음성 출력 ("읽어주기" 버튼, 자동 플레이리스트, 속도/음성 옵션 등 확장 가능), 접근성 및 멀티태스킹, 차별화된 사용자 경험 제공.
