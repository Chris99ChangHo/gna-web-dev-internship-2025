# WordPress: Debugging with WP_DEBUG, WP_DEBUG_LOG, and WP_DEBUG_DISPLAY

## 1. Understanding WordPress Debugging

Debugging is a crucial process in web development for identifying and resolving issues in code. WordPress provides a powerful built-in debugging system that, when properly configured, can significantly accelerate problem-solving. This system is primarily controlled by several PHP constants that allow you to expose errors, warnings, and notices that might otherwise remain hidden. Effectively utilizing these debugging constants helps you pinpoint issues like code errors, plugin/theme conflicts, or function typos quickly.

It's vital to remember that these debugging features should **only be enabled in development or staging environments**. They must always be **disabled on live (production) websites** to prevent exposing sensitive internal information to potential attackers and to avoid confusing end-users with technical error messages.

### WP_DEBUG

The **`WP_DEBUG`** constant is the master switch for WordPress's built-in debugging system. When set to `true`, it activates the debugging mode, causing PHP errors, warnings, and notices to be displayed.

-   **Role:** Activates the core debugging features of WordPress. When enabled, it makes PHP errors, warnings, and notices visible on the screen.
-   **Purpose:** Helps developers quickly identify problems such as syntax errors, deprecated function calls, or unexpected behavior in custom code, themes, or plugins.

## 2. Enabling WP_DEBUG

To activate `WP_DEBUG`, you need to modify the `wp-config.php` file, which is located in the root directory of your WordPress installation.

-   **Steps:**
    1.  Access your WordPress files via FTP or a file manager provided by your hosting.
    2.  Locate and open the `wp-config.php` file.
    3.  Find the line `define('WP_DEBUG', false);`. If it exists, change `false` to `true`.
    4.  If the line doesn't exist, add `define('WP_DEBUG', true);` just before the line that says `/* That's all, stop editing! Happy publishing. */`.
    5.  Save the `wp-config.php` file and upload it back to your server (if using FTP).
    6.  Refresh your website in the browser. If there are any errors, warnings, or notices, they will now be displayed, often at the top of the page.

## 3. Controlling Error Output with WP_DEBUG_LOG and WP_DEBUG_DISPLAY

While `WP_DEBUG` turns on the debugging system, `WP_DEBUG_LOG` and `WP_DEBUG_DISPLAY` provide granular control over where and how these error messages are presented.

### WP_DEBUG_LOG

The **`WP_DEBUG_LOG`** constant, when set to `true`, directs all error messages, warnings, and notices to a specific log file instead of displaying them on the screen.

-   **Role:** Saves all debugging information (PHP errors, warnings, notices) to a file.
-   **Location:** By default, the log file is named `debug.log` and is created within the `/wp-content/` directory of your WordPress installation.
-   **Practical Use:** In a development environment, it's often safer and less intrusive to log errors to a file rather than display them directly on the screen, especially if you're not constantly looking at the browser output. This allows you to review errors later without interrupting the user experience (even if it's just you as the developer).

### WP_DEBUG_DISPLAY

The **`WP_DEBUG_DISPLAY`** constant controls whether debugging messages are shown on the browser screen.

-   **Role:** Determines if error messages are directly outputted to the HTML of the web page.
    
-   **Default Behavior:** When `WP_DEBUG` is `true`, `WP_DEBUG_DISPLAY` defaults to `true`, meaning errors are shown on screen.
    
-   **Practical Use:** Setting `WP_DEBUG_DISPLAY` to `false` is crucial when you want to log errors but prevent them from being visible to anyone Browse the site. This configuration (along with `WP_DEBUG_LOG` being `true`) is ideal for a more "stealthy" debugging process in non-production environments.
    
-   **Combined Example Configuration (in `wp-config.php`):**
    
    ```php
    <?php
    // Enable debug mode
    define('WP_DEBUG', true);
    // Log errors to /wp-content/debug.log
    define('WP_DEBUG_LOG', true);
    // Hide errors from being displayed on the screen
    define('WP_DEBUG_DISPLAY', false);
    // Remember to remove or set to false on live sites!
    ?>
    
    ```
    
    With this setup, any errors will now be recorded in `/wp-content/debug.log`, allowing you to inspect them without cluttering your browser view.

## 4. Additional Debugging Options

Beyond the primary `WP_DEBUG` constants, WordPress offers other useful debugging constants for more specific needs.

Constant Name

Purpose

Example Setting

`WP_DEBUG`

Overall ON/OFF switch for debug mode.

`define('WP_DEBUG', true);`

`WP_DEBUG_LOG`

Saves errors to the `debug.log` file.

`define('WP_DEBUG_LOG', true);`

`WP_DEBUG_DISPLAY`

Controls whether errors are displayed on the screen.

`define('WP_DEBUG_DISPLAY', false);`

`SCRIPT_DEBUG`

Uses development versions of JS/CSS files (unminified) for easier debugging.

`define('SCRIPT_DEBUG', true);`

`SAVEQUERIES`

Records database queries for performance analysis.

`define('SAVEQUERIES', true);`

Sheets로 내보내기

-   **`SCRIPT_DEBUG`**: When enabled, WordPress will load the development versions of its core JavaScript and CSS files (unminified). This is incredibly helpful for debugging front-end issues related to WordPress's built-in scripts.
-   **`SAVEQUERIES`**: This constant, when set to `true`, will save all database queries to an array. This array can then be accessed (e.g., global `$wpdb->queries`) to analyze query performance, identify slow queries, or understand how WordPress interacts with the database. It's particularly useful for optimizing database-heavy operations.

## 5. Practical Debugging Workflow with WP_DEBUG

Integrating `WP_DEBUG` into your development workflow is key for efficient problem-solving and improving code quality.

-   **During Development/Testing:** Always keep `WP_DEBUG` enabled (at least `WP_DEBUG_LOG`) in your development and staging environments. This proactive approach ensures that you catch errors, warnings, and notices as soon as they occur, allowing for immediate fixes and leading to higher code quality.
-   **On Live (Production) Sites:** It's absolutely critical to **disable all debugging options** on your live website. Exposing error messages can pose a security risk by revealing internal system details to potential attackers. It also provides a poor user experience, as technical error messages can confuse or alarm visitors.
-   **Troubleshooting Steps:**
    1.  When an issue arises (e.g., a blank screen, unexpected behavior, or a visible error message), **enable `WP_DEBUG` (and potentially `WP_DEBUG_LOG` with `WP_DEBUG_DISPLAY` set to `false`)**.
    2.  Reload the page where the issue occurs.
    3.  Carefully examine the error messages displayed on screen or within the `debug.log` file. Pay close attention to the **file name, line number, and the type of error**. This information is invaluable for pinpointing the exact location and nature of the problem (e.g., a typo in a variable, an incorrect function call, or a parameter mismatch).
    4.  Once you've identified and resolved the error, **immediately revert the `WP_DEBUG` settings** back to `false` for live environments or to `WP_DEBUG_LOG` only for development.

`WP_DEBUG` is an indispensable tool in WordPress development for **tracking error origins, solving problems, and enhancing code quality**. Mastering its use will significantly accelerate your ability to resolve issues in a real-world development setting.

----------

# 워드프레스: 디버깅 - WP_DEBUG, WP_DEBUG_LOG, WP_DEBUG_DISPLAY 활용

## 1. 워드프레스 디버깅 이해하기

디버깅은 코드의 문제를 식별하고 해결하는 데 필수적인 웹 개발 과정입니다. 워드프레스는 강력한 내장 디버깅 시스템을 제공하며, 올바르게 설정하면 문제 해결 시간을 크게 단축할 수 있습니다. 이 시스템은 주로 PHP 상수들을 통해 제어되며, 숨겨져 있을 수 있는 오류, 경고, 알림(notices)을 노출하도록 합니다. 이러한 디버깅 상수들을 효과적으로 활용하면 코드 오류, 플러그인/테마 충돌, 함수 오타와 같은 문제들을 빠르게 찾아낼 수 있습니다.

**주의할 점은 이러한 디버깅 기능은 개발 또는 스테이징 환경에서만 활성화해야 한다는 것입니다.** 운영(라이브) 웹사이트에서는 잠재적인 공격자에게 민감한 내부 정보를 노출하는 것을 방지하고, 최종 사용자에게 기술적인 오류 메시지로 혼란을 주지 않기 위해 **반드시 비활성화해야 합니다.**

### WP_DEBUG

**`WP_DEBUG`** 상수는 워드프레스 내장 디버깅 시스템의 마스터 스위치입니다. `true`로 설정하면 디버깅 모드를 활성화하여 PHP 오류, 경고, 알림을 화면에 출력합니다.

-   **역할:** 워드프레스의 핵심 디버깅 기능을 활성화합니다. 활성화되면 PHP 오류, 경고, 알림을 화면에 표시합니다.
-   **목적:** 개발자가 구문 오류, 더 이상 사용되지 않는 함수 호출, 사용자 정의 코드, 테마 또는 플러그인의 예상치 못한 동작과 같은 문제들을 빠르게 식별하는 데 도움을 줍니다.

## 2. WP_DEBUG 활성화 방법

`WP_DEBUG`를 활성화하려면 워드프레스 설치 루트 디렉토리에 있는 `wp-config.php` 파일을 수정해야 합니다.

-   **단계:**
    1.  FTP 또는 호스팅에서 제공하는 파일 관리자를 통해 워드프레스 파일에 접속합니다.
    2.  `wp-config.php` 파일을 찾아 엽니다.
    3.  `define('WP_DEBUG', false);` 줄을 찾습니다. 만약 존재한다면 `false`를 `true`로 변경합니다.
    4.  만약 해당 줄이 없다면 `/* That's all, stop editing! Happy publishing. */`이라고 적힌 줄 바로 위에 `define('WP_DEBUG', true);`를 추가합니다.
    5.  `wp-config.php` 파일을 저장하고 서버에 다시 업로드합니다 (FTP 사용 시).
    6.  브라우저에서 웹사이트를 새로고침합니다. 오류, 경고 또는 알림이 있다면 이제 화면 상단에 상세 메시지가 표시될 것입니다.

## 3. WP_DEBUG_LOG 및 WP_DEBUG_DISPLAY를 통한 오류 출력 제어

`WP_DEBUG`가 디버깅 시스템을 켜는 역할이라면, `WP_DEBUG_LOG`와 `WP_DEBUG_DISPLAY`는 이러한 오류 메시지들이 어디서, 어떻게 표시될지를 세부적으로 제어합니다.

### WP_DEBUG_LOG

**`WP_DEBUG_LOG`** 상수를 `true`로 설정하면, 모든 오류 메시지, 경고, 알림을 화면에 표시하는 대신 특정 로그 파일에 기록합니다.

-   **역할:** 모든 디버깅 정보(PHP 오류, 경고, 알림)를 파일에 저장합니다.
-   **위치:** 기본적으로 로그 파일은 `debug.log`라는 이름으로 워드프레스 설치의 `/wp-content/` 디렉토리 내에 생성됩니다.
-   **실무 활용:** 개발 환경에서는 오류를 화면에 직접 표시하는 것보다 파일에 기록하는 것이 더 안전하고 방해가 덜 됩니다. 특히 개발자가 항상 브라우저 출력을 보고 있지 않을 때 유용합니다. 이를 통해 사용자 경험을 방해하지 않고(개발자 본인일지라도) 나중에 오류를 검토할 수 있습니다.

### WP_DEBUG_DISPLAY

**`WP_DEBUG_DISPLAY`** 상수는 디버깅 메시지가 브라우저 화면에 표시될지 여부를 제어합니다.

-   **역할:** 오류 메시지가 웹 페이지의 HTML에 직접 출력될지 여부를 결정합니다.
    
-   **기본 동작:** `WP_DEBUG`가 `true`일 때, `WP_DEBUG_DISPLAY`는 기본적으로 `true`가 되며, 이는 오류가 화면에 표시된다는 것을 의미합니다.
    
-   **실무 활용:** 오류를 로그에 기록하고 싶지만, 사이트를 탐색하는 누구에게도 보이지 않게 하려면 `WP_DEBUG_DISPLAY`를 `false`로 설정하는 것이 중요합니다. 이 설정(그리고 `WP_DEBUG_LOG`가 `true`인 경우)은 비운영 환경에서 보다 "숨겨진" 디버깅 프로세스에 이상적입니다.
    
-   **결합된 설정 예시 (`wp-config.php`에 추가):**
    
    ```php
    <?php
    // 디버그 모드 활성화
    define('WP_DEBUG', true);
    // 오류를 /wp-content/debug.log에 기록
    define('WP_DEBUG_LOG', true);
    // 오류가 화면에 표시되지 않도록 숨김
    define('WP_DEBUG_DISPLAY', false);
    // 라이브 사이트에서는 반드시 제거하거나 false로 설정해야 합니다!
    ?>
    
    ```
    
    이 설정으로 모든 오류는 `/wp-content/debug.log`에 기록되어, 브라우저 화면을 어지럽히지 않고도 오류를 검사할 수 있습니다.

## 4. 추가 디버깅 옵션

주요 `WP_DEBUG` 상수들 외에도 워드프레스는 보다 구체적인 목적을 위한 유용한 디버깅 상수들을 제공합니다.

상수명

용도

설정 예시

`WP_DEBUG`

디버그 모드 전체 ON/OFF 스위치.

`define('WP_DEBUG', true);`

`WP_DEBUG_LOG`

오류를 `debug.log` 파일에 저장합니다.

`define('WP_DEBUG_LOG', true);`

`WP_DEBUG_DISPLAY`

오류가 화면에 표시될지 여부를 제어합니다.

`define('WP_DEBUG_DISPLAY', false);`

`SCRIPT_DEBUG`

JS/CSS의 개발용(축소되지 않은) 파일을 사용하여 디버깅을 용이하게 합니다.

`define('SCRIPT_DEBUG', true);`

`SAVEQUERIES`

데이터베이스 쿼리를 기록하여 성능 분석에 사용합니다.

`define('SAVEQUERIES', true);`

Sheets로 내보내기

-   **`SCRIPT_DEBUG`**: 이 상수를 활성화하면 워드프레스는 핵심 JavaScript 및 CSS 파일의 개발 버전(축소되지 않은 버전)을 로드합니다. 이는 워드프레스 내장 스크립트와 관련된 프론트엔드 문제를 디버깅하는 데 매우 유용합니다.
-   **`SAVEQUERIES`**: 이 상수를 `true`로 설정하면 모든 데이터베이스 쿼리가 배열에 저장됩니다. 이 배열은 (예: 전역 변수 `$wpdb->queries`를 통해) 쿼리 성능을 분석하고, 느린 쿼리를 식별하거나, 워드프레스가 데이터베이스와 어떻게 상호 작용하는지 이해하는 데 사용될 수 있습니다. 특히 데이터베이스 작업이 많은 경우 성능 최적화에 매우 유용합니다.

## 5. WP_DEBUG를 활용한 실용적인 디버깅 워크플로우

`WP_DEBUG`를 개발 워크플로우에 통합하는 것은 효율적인 문제 해결과 코드 품질 향상에 핵심입니다.

-   **개발/테스트 환경:** 개발 및 스테이징 환경에서는 항상 `WP_DEBUG`를 활성화(최소한 `WP_DEBUG_LOG`)해야 합니다. 이러한 사전 예방적 접근 방식은 오류, 경고, 알림이 발생하는 즉시 파악할 수 있도록 하여 즉각적인 수정과 더 높은 코드 품질로 이어집니다.
-   **운영(라이브) 사이트:** 라이브 웹사이트에서는 **모든 디버깅 옵션을 반드시 비활성화**해야 합니다. 오류 메시지를 노출하는 것은 잠재적인 공격자에게 내부 시스템 세부 정보를 드러내 보안 위험을 초래할 수 있습니다. 또한, 기술적인 오류 메시지는 방문자를 혼란시키거나 불안하게 만들 수 있으므로 좋지 않은 사용자 경험을 제공합니다.
-   **문제 해결 단계:**
    1.  문제가 발생하면(예: 흰 화면, 예상치 못한 동작, 보이는 오류 메시지), **`WP_DEBUG`를 활성화합니다(그리고 필요에 따라 `WP_DEBUG_LOG`를 `true`, `WP_DEBUG_DISPLAY`를 `false`로 설정).**
    2.  문제가 발생하는 페이지를 다시 로드합니다.
    3.  화면에 표시되거나 `debug.log` 파일에 기록된 오류 메시지를 신중하게 검토합니다. **파일 이름, 줄 번호, 오류 유형**에 특히 주의를 기울이세요. 이 정보는 문제의 정확한 위치와 성격(예: 변수 오타, 잘못된 함수 호출, 파라미터 불일치)을 파악하는 데 매우 중요합니다.
    4.  오류를 식별하고 해결한 후에는, 라이브 환경의 경우 `WP_DEBUG` 설정을 즉시 `false`로 되돌리거나 개발 환경의 경우 `WP_DEBUG_LOG`만 활성화된 상태로 되돌립니다.

`WP_DEBUG`는 워드프레스 개발에서 **오류 원인 추적, 문제 해결, 코드 품질 향상**을 위한 필수적인 도구입니다. 이를 숙달하는 것은 실제 개발 환경에서 문제를 해결하는 능력을 크게 향상시킬 것입니다.
