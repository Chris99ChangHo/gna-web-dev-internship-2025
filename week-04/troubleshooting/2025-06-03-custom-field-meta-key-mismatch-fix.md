# ✅ Custom Field (Meta Key) Mismatch Fix

## 🔍 Problem Situation

I encountered an issue where the **"Release Year" value for a Movie custom post type was not displaying** on the screen or in the page source, even after entering "2011". Furthermore, attempting to retrieve the value using `get_post_meta` yielded no results.

## 📌 Cause Analysis

The root cause was a **mismatch in the custom field (meta key) name (slug)**. When creating the custom field in WCK, the slug was set as, for example, `release-year` (using a hyphen). However, in the code, I was attempting to retrieve it using `get_post_meta(get_the_ID(), 'release_year', true)` (using an underscore).

WordPress strictly requires an **exact match for the `meta_key`** to return a value. This subtle difference between a hyphen and an underscore in the slug caused the data retrieval to fail.

## 🛠 Solution

### ✅ Core Idea

The core idea was to **verify the actual meta key stored in the database** and ensure **exact consistency between the custom field's slug and the `meta_key` used in the code.**

### 💡 Step-by-Step Resolution

1.  **Verify Stored Meta Key:** I used `print_r(get_post_meta(get_the_ID()))` to inspect all meta keys actually saved for the post. This crucial step revealed the true slug being stored.
    
2.  **Compare and Correct:** I compared the slug defined in WCK (e.g., `release-year`) with the `meta_key` used in my code (e.g., `release_year`).
    
3.  **Modify Code to Match:** I modified the `meta_key` in my PHP code to exactly match the stored slug:
    
    
    ```php
    get_post_meta(get_the_ID(), 'release-year', true)
    
    ```
    
    After this change, a page refresh successfully displayed the "Release Year" (2011) value.
    

## 🎯 Result

By ensuring the meta key in the code precisely matched the custom field slug, the "Release Year" value was successfully retrieved and displayed on the front end.

## 💡 Lessons Learned

-   **Exact Match is Critical for Custom Fields:** Custom field (meta key) names must be **absolutely identical** between the custom field definition and the code accessing them. This includes hyphens (-), underscores (_), and case sensitivity.
-   **`print_r(get_post_meta(get_the_ID()))` is Your Best Friend:** When a custom field value isn't appearing, always start by using `print_r(get_post_meta(get_the_ID()))` to inspect the actual keys stored in the database. This debugging experience is invaluable in real-world development.
-   **Structured Troubleshooting:** Going forward, for any custom field issues, I will follow this sequence:
    1.  **Verify the custom field slug.**
    2.  **Check for exact consistency between the slug and the code's `meta_key`.**
    3.  **Use `print_r` to confirm actual data.** This systematic approach will allow for rapid problem resolution.
-   **PHP and HTML Commenting Rules:** When mixing PHP and HTML in files, remember that **HTML comments (``) must reside outside of PHP code blocks (`<?php ... ?>`)**. If you need to comment within a PHP block, use PHP-specific comment syntax (`//` for single line or `/* ... */` for multi-line). Placing HTML comments directly inside PHP code without wrapping them in PHP comment syntax will lead to errors.

## 🗂️ Related Keywords

`WordPress`, `Custom Fields`, `Meta Key`, `WCK`, `get_post_meta`, `Troubleshooting`, `PHP`, `Debugging`, `Slug Mismatch`, `HTML Comments`, `PHP Syntax`

----------

# ✅ 커스텀 필드 (메타 키) 불일치 문제 해결

## 🔍 문제 상황

영화(Movie) 커스텀 포스트 타입에서 출시년도(Release Year) 값을 "2011"로 입력했지만, 화면에도, 페이지 소스에도 출시년도 값이 출력되지 않는 문제가 발생했습니다. `get_post_meta` 함수로 값을 불러와도 아무 값도 나오지 않았습니다.

## 📌 원인 분석

근본적인 원인은 **커스텀 필드(메타 키) 이름(슬러그)의 불일치**였습니다. WCK에서 커스텀 필드를 생성할 때 슬러그를 예를 들어 `release-year` (하이픈 사용)로 설정했지만, 코드에서는 `get_post_meta(get_the_ID(), 'release_year', true)` (언더스코어 사용)처럼 잘못된 `meta_key`로 값을 가져오려 했습니다.

워드프레스는 `meta_key`가 정확히 일치할 때만 값을 반환합니다. 이처럼 슬러그에서 하이픈과 언더스코어의 미묘한 차이로 인해 데이터 가져오기가 실패했습니다.

## 🛠 해결 방법

### ✅ 핵심 아이디어

핵심 아이디어는 **실제로 데이터베이스에 저장된 메타 키를 확인**하고, **커스텀 필드의 슬러그와 코드에서 사용되는 `meta_key` 간의 정확한 일치**를 보장하는 것이었습니다.

### 💡 단계별 해결

1.  **실제 저장된 메타 키 확인:** `print_r(get_post_meta(get_the_ID()))` 함수를 사용하여 포스트에 실제로 저장된 모든 메타 키를 확인했습니다. 이 중요한 단계를 통해 실제 저장된 슬러그를 파악할 수 있었습니다.
    
2.  **비교 및 수정:** WCK에서 생성한 필드의 슬러그(예: `release-year`)와 코드에서 사용하고 있던 `meta_key`(예: `release_year`)를 비교했습니다.
    
3.  **코드 수정:** PHP 코드에서 `meta_key`를 실제 저장된 슬러그와 동일하게 수정했습니다.
    
    
    ```php
    get_post_meta(get_the_ID(), 'release-year', true)
    
    ```
    
    이 변경 후 페이지를 새로고침하자 출시년도(2011) 값이 정상적으로 출력되었습니다.
    

## 🎯 결과

코드의 메타 키가 커스텀 필드 슬러그와 정확히 일치하도록 함으로써, 출시년도 값이 성공적으로 검색되어 프론트엔드에 표시되었습니다.

## 💡 느낀 점

-   **커스텀 필드는 정확한 일치가 필수적**: 커스텀 필드(메타 키) 이름은 커스텀 필드 정의와 해당 필드에 접근하는 코드 간에 **완전히 동일해야 합니다**. 여기에는 하이픈(-), 언더스코어(_), 대소문자 구분이 모두 포함됩니다.
-   **`print_r(get_post_meta(get_the_ID()))`는 최고의 디버깅 도구**: 커스텀 필드 값이 나타나지 않을 때는 항상 `print_r(get_post_meta(get_the_ID()))`를 사용하여 데이터베이스에 저장된 실제 키를 먼저 확인해야 합니다. 이러한 디버깅 경험은 실무에서 매우 큰 도움이 됩니다.
-   **체계적인 문제 해결**: 앞으로 커스텀 필드 문제가 발생하면 다음 순서로 점검할 것입니다:
    1.  **커스텀 필드 슬러그 확인.**
    2.  **슬러그와 코드의 `meta_key`가 완전히 일치하는지 점검.**
    3.  **`print_r`로 실제 데이터를 확인.** 이러한 체계적인 접근 방식은 빠른 문제 해결을 가능하게 할 것입니다.
-   **PHP와 HTML 주석 규칙**: PHP와 HTML을 함께 사용하는 파일에서는 **HTML 주석(``)은 PHP 코드 블록(`<?php ... ?>`) 바깥에만 존재해야 합니다**. PHP 블록 내에서 주석을 달아야 할 경우, PHP 전용 주석 문법(`//` 또는 `/* ... */`)을 사용해야 합니다. PHP 주석 문법 없이 HTML 주석을 PHP 코드 안에 직접 배치하면 오류가 발생합니다.

## 🗂️ Related Keywords

`WordPress`, `Custom Fields`, `Meta Key`, `WCK`, `get_post_meta`, `Troubleshooting`, `PHP`, `Debugging`, `Slug Mismatch`, `HTML Comments`, `PHP Syntax`
