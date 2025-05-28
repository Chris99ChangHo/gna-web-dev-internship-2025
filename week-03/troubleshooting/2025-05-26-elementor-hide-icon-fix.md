# ✅ Elementor Login/MyAccount Button Conditional Display Fix

## 🔍 Problem Situation

When both "Login" and "My Account" buttons (or icons) were placed in the Elementor header, the following UX issues occurred:

-   Both buttons were **always visible**, regardless of the user's login status.
-   The "Login" button **remained exposed even after a user logged in**.

## 📌 Cause Analysis

Elementor's default widgets (Icon List, Button, etc.) **lack a built-in feature to show/hide based on login/logout status**. While many conditional display plugins (like ElementsKit, Essential Addons) offer this, it's usually **only available in their paid (Pro) versions**. For a free or code-based solution, leveraging CSS with a dynamically added body class is the most reliable method.

## 🛠 Solution

### ✅ Core Idea

Dynamically add a CSS class to the `<body>` tag based on the user's login status using PHP. Then, use CSS to conditionally hide the respective buttons based on these body classes.

### 💡 Step-by-Step Resolution

1.  **Add Login Status Body Class to `functions.php` (Child Theme):**
    Place the following PHP code at the end of your child theme's `functions.php` file:

    ```php
    // Add class to body based on login/logout status
    add_filter('body_class', 'custom_login_status_body_class');
    function custom_login_status_body_class($classes) {
        if ( is_user_logged_in() ) {
            $classes[] = 'logged-in-condition';
        } else {
            $classes[] = 'logged-out-condition';
        }
        return $classes;
    }
    ```
    This code automatically assigns either `logged-in-condition` or `logged-out-condition` class to the `<body>` tag based on the user's status.

2.  **Assign CSS Classes to Each Button in Elementor:**
    * For the **Login button/icon**: In Elementor editor, go to "Advanced > CSS Classes" and add `hide-logged-in` (without the dot).
    * For the **My Account button/icon**: In Elementor editor, go to "Advanced > CSS Classes" and add `hide-logged-out` (without the dot).

3.  **Add Conditional Hide CSS to `style.css` or Additional CSS:**
    Add the following CSS code to your child theme's `style.css` file or via WordPress Admin > Appearance > Customize > Additional CSS:

    ```css
    body.logged-in-condition .hide-logged-in { display: none !important; }
    body.logged-out-condition .hide-logged-out { display: none !important; }
    ```
    This hides the "Login" button when logged in, and the "My Account" button when logged out.

4.  **Clear Caches & Refresh:**
    * Save all files.
    * Go to Elementor > Tools > Regenerate CSS & Data.
    * Perform a hard refresh (Shift+F5) in your browser.
    * Clear any site/server cache plugins.

5.  **Verify Functionality:**
    * **Logged-out status:** Only the "Login" button should be visible.
    * **Logged-in status:** Only the "My Account" button should be visible.

## 🎯 Result

Successfully implemented dynamic display for header buttons based on user login status, achieving the desired UX without requiring premium Elementor add-ons.

## 💡 Lessons Learned

-   This solution demonstrates a practical way to achieve conditional display using **PHP, CSS, and basic Elementor functionalities**, circumventing the need for paid plugins.
-   The core concept involves: **adding a conditional class to the `<body>`** → **assigning specific CSS classes to relevant Elementor widgets** → **applying conditional hiding CSS**.
-   This method is versatile and can be extended with PHP/JavaScript to handle other conditions (e.g., user roles, specific pages).
-   It provides a clean, maintainable way to control UI elements dynamically.

## 🗂 Related Keywords

`Elementor`, `Header`, `Login Button`, `My Account Button`, `Conditional Display`, `PHP`, `CSS`, `WordPress`, `Child Theme`, `UX`, `Troubleshooting`

---

# ✅ Elementor 헤더 로그인/마이페이지 버튼 조건부 표시 문제 해결

## 🔍 문제 상황

Elementor 헤더에 “Login” 버튼(또는 아이콘)과 “My Account” 버튼(또는 아이콘)을 모두 배치했을 때 다음과 같은 사용자 경험(UX) 문제가 발생했습니다:

-   사용자의 로그인 상태와 무관하게 **두 버튼이 항상 모두 보이는 현상**.
-   로그인한 상태임에도 불구하고 "Login" 버튼이 **계속 노출되는 현상**.

## 📌 원인 분석

Elementor의 기본 위젯(아이콘 리스트, 버튼 등)에는 **"로그인/로그아웃 상태에 따라 표시/숨김" 기능이 내장되어 있지 않습니다.** 실무에서 자주 사용되는 조건부 표시 플러그인(예: ElementsKit, Essential Addons 등)들은 대부분 **유료(Pro) 버전에서만 해당 기능을 제공**합니다. 무료 또는 코드 기반의 해결책으로는 CSS와 PHP를 활용하여 `<body>` 태그에 조건부 클래스를 추가하는 방식이 가장 확실합니다.

## 🛠 해결 방법

### ✅ 핵심 아이디어

PHP를 사용하여 사용자 로그인 상태에 따라 `<body>` 태그에 동적으로 CSS 클래스를 추가하고, 이 바디 클래스를 활용하여 CSS로 각 버튼을 조건부로 숨깁니다.

### 💡 단계별 해결

1.  **차일드 테마의 `functions.php`에 로그인 상태별 `body` 클래스 추가:**
    차일드 테마의 `functions.php` 파일 맨 아래에 다음 PHP 코드를 추가합니다.

    ```php
    // 로그인/로그아웃 상태에 따라 body에 클래스 추가
    add_filter('body_class', 'custom_login_status_body_class');
    function custom_login_status_body_class($classes) {
        if ( is_user_logged_in() ) {
            $classes[] = 'logged-in-condition';
        } else {
            $classes[] = 'logged-out-condition';
        }
        return $classes;
    }
    ```
    이 코드는 로그인/로그아웃 상태에 따라 `<body>` 태그에 각각 `logged-in-condition` 또는 `logged-out-condition` 클래스를 자동으로 부여합니다.

2.  **Elementor에서 각 버튼에 CSS 클래스 지정:**
    * **Login 버튼/아이콘:** Elementor 편집기에서 "고급 > CSS Classes"에 `hide-logged-in` (점 없이 입력)을 추가합니다.
    * **My Account 버튼/아이콘:** Elementor 편집기에서 "고급 > CSS Classes"에 `hide-logged-out` (점 없이 입력)을 추가합니다.

3.  **`style.css` 또는 추가 CSS에 조건부 숨김 코드 추가:**
    차일드 테마의 `style.css` 파일 또는 워드프레스 관리자 > 외모 > 사용자 정의 > 추가 CSS에 다음 CSS 코드를 추가합니다.

    ```css
    body.logged-in-condition .hide-logged-in { display: none !important; }
    body.logged-out-condition .hide-logged-out { display: none !important; }
    ```
    이 CSS는 로그인 상태일 때는 "Login" 버튼을 숨기고, 로그아웃 상태일 때는 "My Account" 버튼을 숨깁니다.

4.  **캐시 삭제 및 새로고침:**
    * 모든 파일을 저장합니다.
    * Elementor > 도구 > CSS 파일 재생성을 실행합니다.
    * 브라우저에서 강력 새로고침(Shift+F5)을 수행합니다.
    * 사이트/서버 캐시 플러그인이 있다면 모두 삭제합니다.

5.  **결과 확인:**
    * **로그아웃 상태:** "Login" 버튼만 보입니다.
    * **로그인 상태:** "My Account" 버튼만 보입니다.

## 🎯 결과

사용자 로그인 상태에 따라 헤더 버튼의 동적 표시를 성공적으로 구현하여, 프리미엄 Elementor 애드온 없이도 원하는 사용자 경험을 달성했습니다.

## 💡 느낀 점

-   이 해결책은 **PHP, CSS, 그리고 Elementor의 기본 기능만으로** 조건부 표시를 구현하는 실용적인 방법을 제시하며, 유료 플러그인의 필요성을 우회합니다.
-   핵심 개념은 **`<body>`에 조건부 클래스 추가** → **관련 Elementor 위젯에 특정 CSS 클래스 할당** → **조건부 숨김 CSS 적용**입니다.
-   이 방법은 확장성이 뛰어나며 PHP/JavaScript를 사용하여 다른 조건(예: 사용자 역할별, 특정 페이지)에도 적용할 수 있습니다.
-   동적으로 UI 요소를 제어하는 깔끔하고 유지보수가 용이한 방법을 제공합니다.

## 🗂 관련 키워드

`Elementor`, `헤더`, `로그인 버튼`, `마이페이지 버튼`, `조건부 표시`, `PHP`, `CSS`, `워드프레스`, `차일드 테마`, `UX`, `문제 해결`
