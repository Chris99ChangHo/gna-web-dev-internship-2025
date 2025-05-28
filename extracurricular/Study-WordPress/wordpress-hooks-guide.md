
# WordPress Hooks: A Complete Guide from Core Concepts to Practical Use

When you're running or developing a WordPress website, do you want to add functionalities without directly modifying core files? WordPress's **Hooks** system is the key element responsible for this "extensibility." This guide will summarize the core concepts, types, practical applications, and advanced tips for Hooks, integrating information from YouTube videos and official documentation.

## 1. What is a Hook?

A Hook is a **core system** designed to allow WordPress core, theme, and plugin code to interact with each other. Think of it like pre-installed power outlets at specific points in a building. You can plug your code into these 'outlets' to interfere with WordPress's default behavior or add new features.

The most crucial point is that using Hooks means you **don't need to directly modify WordPress core files**. This ensures your added functionalities remain safe during updates, without the worry of your code being overwritten.

## 2. Two Types of Hooks: Action & Filter

WordPress Hooks are broadly divided into two types. It's important to understand their distinct roles.

### 2.1. Action Hook

Directs WordPress to **"execute my code"** at specific moments.

-   **Example moments:** When a post is saved, when the footer is displayed, when a theme is loaded, etc.
-   **Usage:** `add_action('hook_name', 'callback_function');`
-   **Callback Function:** Simply **executes** and does not return any value.

**PHP Example Code:** To add a specific message to the WordPress page footer:

```
<?php
function custom_footer_message() {
    echo '<p>Copyright © ' . date('Y') . ' My Awesome Website.</p>';
}
add_action('wp_footer', 'custom_footer_message'); // Connect custom_footer_message function to the 'wp_footer' action hook
?>
```

### 2.2. Filter Hook

Directs WordPress to **"intercept and modify"** specific data (values).

-   **Example data:** Post content, title, menu items, URLs, etc. (Can also modify data from plugins like WooCommerce.)
-   **Usage:** `add_filter('hook_name', 'callback_function');`
-   **Callback Function:** Must receive the data, **modify it, and then explicitly return the modified value**. Failing to return a value can lead to critical errors.

**PHP Example Code:** To add "Thanks for reading!" at the end of post content:
```
<?php
function add_thanks_to_content($content) {
    return $content . '<p>Thanks for reading!</p>';
}
add_filter('the_content', 'add_thanks_to_content'); // Connect add_thanks_to_content function to the 'the_content' filter hook
?>
```

## 3. How Hooks Work

Throughout WordPress core files, there are pre-defined "hook points." These hook points are inserted into the code in the form of `do_action('hook_name');` or `apply_filters('hook_name', $value);`.

The functions (`callback_function`) you register using `add_action()` or `add_filter()` will automatically **execute** or **modify data** when WordPress encounters these hook points.

## 4. Practical Application: Where to Put Your Code?

The most common ways to use WordPress Hooks are:

1.  **Theme's `functions.php` file:** Suitable for simple customizations. However, content can be lost during theme updates, so it's **strongly recommended to add your code to a Child Theme's `functions.php` file.**
2.  **Custom Plugin file:** Best for adding complex or reusable functionalities. Creating a separate plugin ensures your functionality persists regardless of the theme used.

## 5. Advanced Hook Usage: Priority and Arguments

The `add_action()` and `add_filter()` functions can accept additional arguments beyond the callback function.

### 5.1. Priority

Determines the **execution order** of callback functions.

-   `add_action('hook_name', 'callback_function', [priority]);`
-   `add_filter('hook_name', 'callback_function', [priority]);`
-   **Default:** `10`
-   **Behavior:** Lower numbers execute **earlier**.
    -   `priority` 5: Likely to execute before other functions.
    -   `priority` 100: Likely to execute after other functions.
-   **Use Case:** Use when a particular function needs to run before or after others. Developers sometimes use very high values like `9999` to ensure their function runs last after almost all other functions have executed.

**PHP Example Code:**

```
<?php
add_action('wp_footer', 'my_custom_footer_early', 5);   // Executes earlier (lower number)
add_action('wp_footer', 'my_custom_footer_default');    // Default priority 10
add_action('wp_footer', 'my_custom_footer_late', 99);   // Executes last (higher number)
?>
```

### 5.2. Accepted Arguments

Specifies the **number of arguments** to be passed to the callback function.

-   `add_action('hook_name', 'callback_function', [priority], [accepted_args]);`
-   `add_filter('hook_name', 'callback_function', [priority], [accepted_args]);`
-   **Default:** `1` (Only the first argument is passed to the callback function.)
-   **Use Case:** Use when a particular hook passes multiple arguments, and you want your callback function to receive and utilize all of them.

**PHP Example Code:** The `get_the_excerpt` filter passes two arguments: the excerpt (`$excerpt`) and the post object (`$post`). If you want to use both, you must specify `2` for the number of accepted arguments.

```
<?php
function my_custom_excerpt($excerpt, $post) {
    // $excerpt: excerpt content, $post: WP_Post object
    return $excerpt . ' (excerpted from ' . $post->post_title . ')';
}
add_filter('get_the_excerpt', 'my_custom_excerpt', 10, 2); // Priority 10, accepts 2 arguments
?>
```

### 5.3. Hook Execution Order and Full Hook List

WordPress executes numerous action/filter hooks in a **defined order** during the request processing. When performing complex customizations, understanding the hook execution order is crucial to ensure your code runs precisely when intended.

-   **Reference:** You can check the name of all action/filter hooks, their passed arguments, and their approximate execution order in the WordPress Developer Handbook's [Hooks Reference](https://developer.wordpress.org/reference/hooks/).

## 6. Benefits of WordPress Hooks (Why Use Them?)

Hooks are central to the WordPress ecosystem and offer powerful advantages:

-   **Maintainability:** Your added code remains safe during WordPress core, theme, and plugin updates because you don't directly modify their files.
-   **Compatibility:** Provides a standardized way for multiple plugins and themes to add/modify functionalities without conflicts.
-   **Extensibility:** Easy to add and modify features as your site scales or requirements become more complex.
-   **Community Collaboration:** A standardized method allows anyone to extend or modify other developers' plugins/themes.

## 7. Practical Tips & Cautions

-   **Actions "only execute," Filters "must return":** Failing to return a value in a filter hook can cause critical errors in WordPress. Always remember this!
-   **Priority Adjustment:** Multiple functions can be connected to a single hook, allowing for precise control over their execution order using priority.
-   **Creating Custom Hooks:** When developing your own plugins or themes, you can use `do_action()` or `apply_filters()` to **create your own custom hooks**, allowing other developers to extend your code.

## 8. Learning Guide: Mastering WordPress Hooks

By understanding and practicing the content in this guide, you can fully grasp the **core concepts and usage essential for practical WordPress customization** using Hooks (Actions/Filters)!

Follow these steps for learning:

1.  **Core Hook Concepts:** Clearly understand the difference between Actions and Filters.
2.  **`add_action`/`add_filter` Practical Examples:** Write and apply simple code snippets yourself.
3.  **Priority/Arguments/Execution Order:** Understand advanced usage and work with hooks that accept multiple arguments.
4.  **Finding Hooks in Official Documentation:** Practice finding the right hook name and location for your desired functionality.

**Things to do for further practice:**

-   **Directly apply the example code** from this guide to your own WordPress site (in `functions.php` or a custom plugin).
-   Consistently explore the WordPress Developer Handbook's [Hooks Reference](https://developer.wordpress.org/reference/hooks/) to practice **finding the "right hook name and location"** for your desired actions.
-   **Experiment with changing the priority and accepted arguments** for `add_action`/`add_filter` functions. Directly observing the changes is key to understanding.

---

# 워드프레스 훅(Hooks): 핵심 개념부터 실전 활용까지 완벽 가이드

워드프레스 웹사이트를 운영하거나 개발할 때, 코어 파일을 직접 수정하지 않고도 원하는 기능을 추가하고 싶으신가요? 워드프레스의 **훅(Hooks)** 시스템은 바로 이런 '확장성'을 책임지는 핵심 요소입니다. 이 가이드에서는 훅의 개념부터 종류, 실전 활용법, 그리고 고급 팁까지 유튜브 영상과 공식 문서를 통합하여 핵심만 요약해 드립니다.

## 1. 훅(Hook)이란 무엇인가?

훅은 워드프레스 코어, 테마, 플러그인 코드가 서로 영향을 주고받을 수 있도록 설계된 **핵심 시스템**입니다. 마치 건물의 특정 지점에 미리 콘센트를 만들어두는 것과 같죠. 여러분은 이 '콘센트'에 코드를 꽂아 워드프레스의 기본 동작에 간섭하거나 새로운 기능을 추가할 수 있습니다.

가장 중요한 점은, 훅을 사용하면 워드프레스의 **코어 파일을 직접 수정할 필요가 없다**는 것입니다. 이는 업데이트 시 코드가 덮어씌워질 걱정 없이 안전하게 기능을 추가/수정/삭제할 수 있다는 것을 의미합니다.

## 2. 훅의 두 가지 종류: 액션(Action)과 필터(Filter)

워드프레스 훅은 크게 두 가지로 나뉩니다. 각자의 역할이 명확하니 잘 이해하는 것이 중요합니다.

### 2.1. 액션 훅 (Action Hook)

특정 시점에 **"내 코드를 실행"**하도록 지시합니다.

-   **예시 시점:** 글이 저장될 때, 푸터(footer)가 출력될 때, 테마가 로드될 때 등
-   **사용 형태:** `add_action('hook_name', 'callback_function');`
-   **콜백 함수:** 단순히 **실행만** 하고 어떤 값을 반환하지 않습니다.

**PHP 예시 코드:** 워드프레스 페이지 하단(푸터)에 특정 문구를 추가하고 싶을 때:

```
<?php
function custom_footer_message() {
    echo '<p>Copyright © ' . date('Y') . ' My Awesome Website.</p>';
}
add_action('wp_footer', 'custom_footer_message'); // 'wp_footer' 액션 훅에 custom_footer_message 함수 연결
?>
```

### 2.2. 필터 훅 (Filter Hook)

특정 **데이터(값)를 "가로채서 수정"**하도록 지시합니다.

-   **예시 데이터:** 게시글 내용, 제목, 메뉴 항목, URL 등 (WooCommerce와 같은 플러그인의 데이터도 수정 가능합니다.)
-   **사용 형태:** `add_filter('hook_name', 'callback_function');`
-   **콜백 함수:** 데이터를 받아서 **수정한 후 반드시 그 값을 반환**해야 합니다. 값을 반환하지 않으면 심각한 오류가 발생할 수 있습니다.

**PHP 예시 코드:** 게시글 내용의 끝에 "읽어주셔서 감사합니다!" 문구를 추가하고 싶을 때:

```
<?php
function add_thanks_to_content($content) {
    return $content . '<p>읽어주셔서 감사합니다!</p>';
}
add_filter('the_content', 'add_thanks_to_content'); // 'the_content' 필터 훅에 add_thanks_to_content 함수 연결
?>
```

## 3. 훅의 동작 구조

워드프레스 코어 파일의 곳곳에는 미리 정의된 "훅 포인트"가 존재합니다. 이 훅 포인트들은 `do_action('hook_name');` 또는 `apply_filters('hook_name', $value);` 형태로 코드 내에 삽입되어 있습니다.

`add_action()`이나 `add_filter()`를 통해 여러분이 등록한 함수(`callback_function`)들은 워드프레스가 이 훅 포인트를 만날 때 **자동으로 실행**되거나 **데이터를 수정**하게 됩니다.

## 4. 실전 활용법: 어디에 코드를 넣을까?

워드프레스 훅을 사용하는 가장 일반적인 방법은 다음과 같습니다.

1.  **테마의 `functions.php` 파일:** 간단한 커스터마이즈에 적합합니다. **하지만 테마 업데이트 시 내용이 사라질 수 있으므로, 반드시 자식 테마(Child Theme)의 `functions.php` 파일에 추가하는 것이 강력히 권장됩니다.**
2.  **커스텀 플러그인 파일:** 복잡하거나 재사용 가능한 기능을 추가할 때 가장 좋습니다. 별도의 플러그인으로 만들면 어떤 테마를 사용하더라도 기능이 유지됩니다.

## 5. 훅의 고급 사용법: 우선순위와 인자

`add_action()`과 `add_filter()` 함수는 콜백 함수 외에 추가적인 인자를 받을 수 있습니다.

### 5.1. 우선순위 (Priority)

콜백 함수가 실행되는 **순서를 지정**합니다.

-   `add_action('hook_name', 'callback_function', [priority]);`
-   `add_filter('hook_name', 'callback_function', [priority]);`
-   **기본값:** `10`
-   **동작:** 숫자가 **낮을수록 먼저 실행**됩니다.
    -   `priority` 5: 다른 함수들보다 먼저 실행될 가능성이 높음.
    -   `priority` 100: 다른 함수들보다 나중에 실행될 가능성이 높음.
-   **활용:** 특정 기능이 다른 기능보다 먼저/나중에 실행되어야 할 때 사용합니다. 개발자들은 가끔 `9999`처럼 아주 높은 값을 사용하여 거의 모든 다른 함수가 실행된 후 마지막에 실행되도록 하기도 합니다.

**PHP 예시 코드:**

```
<?php
add_action('wp_footer', 'my_custom_footer_early', 5);   // 다른 훅들보다 먼저 실행 (숫자가 낮음)
add_action('wp_footer', 'my_custom_footer_default');    // 기본값 10
add_action('wp_footer', 'my_custom_footer_late', 99);   // 가장 마지막에 실행 (숫자가 높음)
?>
```

### 5.2. 인자 개수 (Accepted Arguments)

콜백 함수로 전달될 **인자의 개수를 지정**합니다.

-   `add_action('hook_name', 'callback_function', [priority], [accepted_args]);`
-   `add_filter('hook_name', 'callback_function', [priority], [accepted_args]);`
-   **기본값:** `1` (첫 번째 인자만 콜백 함수로 전달됩니다.)
-   **활용:** 특정 훅이 여러 개의 인자를 전달할 때, 콜백 함수에서 그 인자들을 모두 받아서 사용하고 싶을 때 명시합니다.

**PHP 예시 코드:** `get_the_excerpt` 필터는 발췌문(`$excerpt`)과 게시물 객체(`$post`) 두 가지 인자를 전달합니다. 이 둘을 모두 사용하고 싶다면 인자 개수를 `2`로 지정해야 합니다.

```
<?php
function my_custom_excerpt($excerpt, $post) {
    // $excerpt: 발췌문 내용, $post: WP_Post 객체
    return $excerpt . ' (' . $post->post_title . '에서 발췌)';
}
add_filter('get_the_excerpt', 'my_custom_excerpt', 10, 2); // 우선순위 10, 인자 2개 사용
?>
```

### 5.3. 훅 실행 순서 및 전체 훅 목록

워드프레스는 요청 처리 과정에서 수많은 액션/필터 훅을 **정해진 순서대로 실행**합니다. 복잡한 커스터마이즈를 할 때는 내가 원하는 시점에 정확히 코드를 실행시키기 위해 훅의 실행 순서를 아는 것이 중요합니다.

-   **참고:** 워드프레스 개발자 핸드북의 [Hooks Reference](https://developer.wordpress.org/reference/hooks/)에서 모든 액션/필터 훅의 이름, 전달되는 인자, 그리고 대략적인 실행 순서를 확인할 수 있습니다.

## 6. 워드프레스 훅의 장점 (왜 사용해야 할까?)

훅은 워드프레스 생태계의 핵심이며, 다음과 같은 강력한 장점을 제공합니다.

-   **유지보수성:** 워드프레스 코어, 테마, 플러그인이 업데이트되어도 내가 추가한 코드가 안전하게 유지됩니다. 직접 수정할 필요가 없기 때문입니다.
-   **호환성:** 여러 플러그인이나 테마가 충돌 없이 기능을 추가/수정할 수 있도록 표준화된 방법을 제공합니다.
-   **확장성:** 사이트 규모가 커지거나 요구사항이 복잡해져도 기능을 쉽게 추가하고 수정할 수 있습니다.
-   **커뮤니티 협업:** 표준화된 방식으로 누구나 다른 개발자의 플러그인/테마를 확장하거나 수정할 수 있습니다.

## 7. 실무 팁 & 주의점

-   **액션은 "실행만", 필터는 "반드시 `return`":** 필터 훅에서 값을 반환하지 않으면 워드프레스에 치명적인 오류가 발생할 수 있습니다. 항상 기억하세요!
-   **우선순위 조절:** 여러 함수가 하나의 훅에 연결될 수 있으므로, 우선순위를 통해 실행 순서를 세밀하게 제어할 수 있습니다.
-   **커스텀 훅 생성:** 여러분이 직접 플러그인이나 테마를 개발할 때 `do_action()`이나 `apply_filters()`를 사용하여 다른 개발자들이 여러분의 코드에 기능을 추가할 수 있도록 **커스텀 훅을 만들 수도 있습니다.**

## 8. 학습 가이드: 워드프레스 훅 마스터하기

이 가이드의 내용만 제대로 이해하고 실습한다면, 워드프레스 훅(액션/필터)의 실무 커스터마이즈에 필요한 **핵심 개념과 사용법은 충분히 익힐 수 있습니다!**

다음 순서로 학습해 보세요:

1.  **코어 훅 개념:** 액션과 필터의 차이를 명확히 이해합니다.
2.  **`add_action`/`add_filter` 실전 예시:** 간단한 코드를 직접 작성하여 적용해 봅니다.
3.  **우선순위/인자/실행 순서:** 고급 사용법을 이해하고 인자가 여러 개인 훅을 다뤄봅니다.
4.  **공식 문서에서 훅 찾는 방법:** 원하는 기능에 맞는 훅을 직접 찾아보는 연습을 합니다.

**추가로 해보면 좋은 것:**

-   이 가이드에서 제시된 예시 코드를 **직접 여러분의 워드프레스 사이트(`functions.php` 또는 커스텀 플러그인)에 적용**해 보세요.
-   워드프레스 개발자 핸드북의 [Hooks Reference](https://developer.wordpress.org/reference/hooks/)를 탐색하며 **"내가 원하는 동작"에 맞는 훅 이름과 위치**를 찾아보는 연습을 꾸준히 합니다.
-   `add_action`/`add_filter` 함수의 **우선순위와 인자 값을 바꿔가며 실험**해 보세요. 직접 관찰하고 경험하는 것이 가장 중요합니다.
