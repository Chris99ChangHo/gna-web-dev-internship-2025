# WordPress Core Hooks

The official WordPress Hooks reference ([https://developer.wordpress.org/reference/hooks/](https://developer.wordpress.org/reference/hooks/)) provides a vast amount of hook information, but in practice, certain hooks are predominantly used. The following are representative Action and Filter hooks frequently utilized in actual WordPress theme and plugin development, along with their practical use cases.

## Most Frequently Used WordPress Hooks in Practice

| Hook Name             | Type   | Main Purpose and Practical Use Cases                                                                                                                              |
| :-------------------- | :----- | :------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `wp_head`             | Action | Add scripts, stylesheets, and meta tags (e.g., Google Analytics, SEO tags) within the `<head>` tag of the website.                                           |
| `wp_footer`           | Action | Add JavaScript code, analytics scripts, custom messages, etc., right before the `</body>` tag of the website.                                              |
| `init`                | Action | Executed during WordPress initialization. Used for registering custom post types, custom taxonomies, enabling custom functionalities, and initializing global variables. |
| `admin_init`          | Action | Executed when the admin page is initialized. Used for admin-specific functionalities, registering option pages, and database update routines.                 |
| `admin_menu`          | Action | Add new menu items (e.g., plugin settings pages, custom reports) to the WordPress admin menu.                                                             |
| `wp_enqueue_scripts`  | Action | Safely and correctly register and enqueue stylesheets (`CSS`) and scripts (`JavaScript`) required for the front-end.                                         |
| `template_redirect`   | Action | Executed right before template files are loaded. Used for redirecting pages based on certain conditions, controlling user access, and loading custom page templates. |
| `widgets_init`        | Action | Register custom widget areas (sidebars) or define custom widgets.                                                                                         |
| `the_content`         | Filter | Modify the post content right before it is retrieved from the database and displayed on the screen (e.g., inserting ads, related post links, filtering specific words). |
| `the_title`           | Filter | Modify the post title right before it is displayed on the screen (e.g., adding emojis based on conditions, adding prefixes/suffixes, filtering titles).        |
| `excerpt_length`      | Filter | Change the default length of WordPress excerpts.                                                                                                            |
| `upload_mimes`        | Filter | Add new file extensions (e.g., SVG, PDF) to the list of allowed file types during WordPress media uploads.                                                |
| `comment_text`        | Filter | Modify comment content right before it is displayed on the screen (e.g., adding auto-links, filtering specific words in comments).                         |
| `wp_mail_from`        | Filter | Change the 'From' email address for emails sent from WordPress.                                                                                           |

## Practical Use Cases

* `wp_head`, `wp_footer`:
    In practice, these are essential for adding external scripts and styles like Google Analytics, Facebook Pixel, or custom CSS/JS code to the website's header or footer. This is crucial for website performance monitoring, marketing campaign tracking, and fine-tuning design.
* `the_content`, `the_title`:
    Useful for content marketing and automation. For example, automatically inserting ads into all blog post content, or adding emojis to titles containing specific keywords.
* `wp_enqueue_scripts`:
    The standard method for safely and efficiently enqueuing necessary stylesheets (.css) and JavaScript (.js) files when developing themes or plugins. This helps prevent conflicts and optimize performance.
* `admin_menu`, `admin_init`:
    Core hooks for extending the WordPress admin backend. Essential for adding plugin settings pages, custom report pages, or executing code at the time of activating specific admin features.
* `init`:
    One of the most fundamental WordPress initialization hooks, always used when modifying or extending WordPress's core structure, such as registering Custom Post Types or Custom Taxonomies.

## Conclusion

Hooks like `wp_head`, `wp_footer`, `the_content`, `the_title`, `wp_enqueue_scripts`, `admin_menu`, and `init` are the core elements most frequently used in practical WordPress development. These hooks are essential in almost all WordPress themes and plugins for extending and customizing website functionalities.

By focusing on these core hooks in the official Hooks reference and practicing their application in real projects, you can significantly enhance your WordPress development capabilities and contribute immediately in a practical setting.

---

### Essential Hooks for Plugin Development

The following are core Action and Filter hooks frequently utilized in plugin development.

### Essential Action Hooks for Plugin Development

| Hook Name         | Main Purpose and Description                                                                                              |
| :---------------- | :------------------------------------------------------------------------------------------------------------------------ |
| `init`            | Executed right after WordPress has finished loading. Used for registering custom post types, taxonomies, and initializing global variables. |
| `admin_init`      | Executed when the admin page is initialized. Used for adding admin functionalities such as registering option pages and saving settings. |
| `admin_menu`      | Used for adding custom pages/submenus to the WordPress admin menu.                                                        |
| `wp_enqueue_scripts` | Used for registering assets like stylesheets and JavaScript files.                                                       |
| `wp_head`         | Used for adding code (e.g., meta tags, scripts) to the site's `<head>` section.                                         |
| `wp_footer`       | Used for adding code (e.g., scripts, analytics code) to the site's footer section.                                        |
| `save_post`       | Executed when a post is saved. Used for additional tasks upon saving (e.g., email notifications, logging).                |
| `plugins_loaded`  | Executed after all plugins have been loaded. Used for integration with other plugins and initialization tasks.             |

### Essential Filter Hooks for Plugin Development

| Hook Name     | Main Purpose and Description                                                                                   |
| :------------ | :------------------------------------------------------------------------------------------------------------- |
| `the_content` | Modifies the post content before it is displayed. Used for inserting ads, adding related posts, or content transformation. |
| `the_title`   | Modifies the post title before it is displayed. Used for adding prefixes/suffixes, inserting emojis, etc.      |
| `the_excerpt` | Modifies the excerpt before it is displayed. Used for adjusting length, adding content, etc.                   |
| `wp_title`    | Modifies the `<title>` tag (document title) before it is displayed. Used for SEO, changing title format, etc.  |
| `upload_mimes` | Adds/modifies allowed file extensions for uploads. Used for allowing additional file types like SVG, PDF.      |
| `comment_text` | Modifies comment content before it is displayed. Used for auto-linking, filtering, adding content, etc.        |

### Summary (for Plugin Development)

* **Action Hooks** are used to execute code at specific points in time (e.g., initialization, saving, displaying header/footer).
* **Filter Hooks** are used to modify data (e.g., content, title, excerpt) before it is output.
* In plugin development, these hooks are utilized to extend functionalities, transform data, and add administrator features.

---

# 워드프레스 핵심 훅 (WordPress Core Hooks)

워드프레스 공식 Hooks 레퍼런스(https://developer.wordpress.org/reference/hooks/)는 방대한 양의 훅 정보를 제공하지만, 실무에서는 특정 훅들이 압도적으로 많이 사용됩니다. 다음은 실제 워드프레스 테마 및 플러그인 개발에서 빈번하게 활용되는 대표적인 액션(Action) 및 필터(Filter) 훅과 그 실무 활용 예시입니다.

## 실무에서 가장 많이 쓰이는 워드프레스 훅

| 훅 이름             | 타입   | 주요 용도 및 실무 활용 예시                                                                                                                              |
| :------------------ | :----- | :------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `wp_head`           | 액션   | 웹사이트의 `<head>` 태그 내에 스크립트, 스타일시트, 메타태그(예: Google Analytics, SEO 태그) 추가                                                              |
| `wp_footer`         | 액션   | 웹사이트의 `</body>` 태그 직전에 자바스크립트 코드, 분석 스크립트, 커스텀 메시지 등 추가                                                                   |
| `init`              | 액션   | 워드프레스 초기화 시점에 실행. 사용자 정의 포스트 타입, 택소노미 등록, 사용자 정의 기능 활성화, 전역 변수 초기화 등                               |
| `admin_init`        | 액션   | 관리자 페이지 초기화 시점에 실행. 관리자 전용 기능, 옵션 페이지 등록, 데이터베이스 업데이트 루틴 등                                                          |
| `admin_menu`        | 액션   | 워드프레스 관리자 메뉴에 새로운 메뉴 항목(예: 플러그인 설정 페이지, 커스텀 보고서) 추가                                                                     |
| `wp_enqueue_scripts` | 액션   | 프론트엔드에 필요한 스타일시트(`CSS`) 및 스크립트(`JavaScript`)를 안전하고 올바른 방식으로 등록하고 불러오기                                                   |
| `template_redirect` | 액션   | 템플릿 파일이 로드되기 직전에 실행. 특정 조건에 따라 페이지 리다이렉트, 사용자 접근 권한 제어, 커스텀 페이지 템플릿 로드 등                                   |
| `widgets_init`      | 액션   | 사용자 정의 위젯 영역(사이드바)을 등록하거나 커스텀 위젯을 정의할 때 사용                                                                                |
| `the_content`       | 필터   | 글 본문 내용이 데이터베이스에서 불러와져 화면에 출력되기 직전, 본문 내용을 수정(예: 본문 내 광고 삽입, 관련 글 링크 추가, 특정 단어 필터링)                    |
| `the_title`         | 필터   | 글 제목이 화면에 출력되기 직전, 제목을 수정(예: 특정 조건에 따라 제목에 이모지 추가, 접두사/접미사 추가, 제목 필터링)                                           |
| `excerpt_length`    | 필터   | 워드프레스 요약문(excerpt)의 기본 길이를 변경                                                                                                              |
| `upload_mimes`      | 필터   | 워드프레스 미디어 업로드 시 허용되는 파일 확장자 목록에 새로운 확장자(예: SVG, PDF) 추가                                                                   |
| `comment_text`      | 필터   | 댓글 내용이 화면에 출력되기 직전, 댓글 내용을 수정(예: 댓글 내 자동 링크 추가, 특정 단어 필터링)                                                               |
| `wp_mail_from`      | 필터   | 워드프레스에서 발송되는 이메일의 '보낸 사람' 주소를 변경                                                                                                |

## 실무에서의 주요 활용 예시

* `wp_head`, `wp_footer`:
    실무에서는 Google Analytics, Facebook Pixel, 맞춤형 CSS/JS 코드 삽입 등 외부 스크립트 및 스타일을 웹사이트의 헤더나 푸터에 추가할 때 필수로 사용됩니다. 이는 웹사이트 성능 모니터링, 마케팅 캠페인 추적, 그리고 디자인 미세 조정에 필수적입니다.
* `the_content`, `the_title`:
    콘텐츠 마케팅 및 자동화에 유용합니다. 예를 들어, 모든 블로그 게시물 본문에 자동으로 광고를 삽입하거나, 특정 키워드가 포함된 제목에 이모티콘을 추가하는 등의 작업에 활용됩니다.
* `wp_enqueue_scripts`:
    테마나 플러그인을 개발할 때 필요한 스타일시트(.css)와 자바스크립트(.js) 파일을 웹페이지에 안전하고 효율적으로 불러오는 표준적인 방법입니다. 이를 통해 충돌을 방지하고 성능을 최적화할 수 있습니다.
* `admin_menu`, `admin_init`:
    워드프레스 관리자 백엔드를 확장할 때 핵심적인 훅입니다. 플러그인 설정 페이지, 사용자 정의 보고서 페이지, 또는 특정 관리자 기능 활성화 시점에 코드를 실행하는 데 필수적으로 사용됩니다.
* `init`:
    워드프레스의 가장 기본적인 초기화 훅 중 하나로, 사용자 정의 포스트 타입(Custom Post Type), 사용자 정의 분류(Custom Taxonomy) 등록과 같이 워드프레스의 핵심 구조를 변경하거나 확장할 때 반드시 사용됩니다.

## 결론

`wp_head`, `wp_footer`, `the_content`, `the_title`, `wp_enqueue_scripts`, `admin_menu`, `init` 등의 훅은 워드프레스 개발 실무에서 가장 빈번하게 사용되는 핵심 요소입니다. 이 훅들은 거의 모든 워드프레스 테마 및 플러그인에서 웹사이트의 기능을 확장하고 맞춤화하는 데 필수적으로 활용됩니다.

공식 훅 레퍼런스에서 이 핵심 훅들을 중심으로 학습하고 실제 프로젝트에 적용하는 연습을 한다면, 워드프레스 개발 역량을 크게 향상시키고 실무에 즉시 기여할 수 있을 것입니다.

---

## 플러그인 개발에 자주 활용되는 핵심 액션(Action) 훅과 필터(Filter) 훅

플러그인 개발에서 자주 활용되는 핵심 액션(Action) 훅과 필터(Filter) 훅은 다음과 같습니다.

### 플러그인 개발에 자주 쓰이는 핵심 액션 훅

| 훅 이름             | 주요 용도 및 설명                                                                                                |
| :------------------ | :--------------------------------------------------------------------------------------------------------------- |
| `init`              | 워드프레스가 초기화된 직후 실행. 커스텀 포스트 타입, 택소노미 등록, 글로벌 변수 초기화 등에 사용.                 |
| `admin_init`        | 관리자 페이지가 초기화될 때 실행. 옵션 페이지 등록, 세팅 저장 등 관리자 기능 추가에 사용.                       |
| `admin_menu`        | 관리자 메뉴에 커스텀 페이지/서브메뉴 추가 시 사용.                                                             |
| `wp_enqueue_scripts` | 스타일시트, 자바스크립트 등 에셋(Asset)을 등록할 때 사용.                                                        |
| `wp_head`           | 사이트 `<head>` 영역에 코드(예: 메타태그, 스크립트) 추가 시 사용.                                              |
| `wp_footer`         | 사이트 푸터 영역에 코드(예: 스크립트, 분석 코드) 추가 시 사용.                                                 |
| `save_post`         | 글/포스트가 저장될 때 실행. 저장 시 추가 작업(이메일 알림, 로그 등)에 사용.                                    |
| `plugins_loaded`    | 플러그인이 모두 로드된 후 실행. 다른 플러그인과의 연동, 초기화 작업에 사용.                                    |

### 플러그인 개발에 자주 쓰이는 핵심 필터 훅

| 훅 이름         | 주요 용도 및 설명                                                                                               |
| :-------------- | :-------------------------------------------------------------------------------------------------------------- |
| `the_content`   | 글 본문 출력 전 수정. 광고 삽입, 관련글 추가, 본문 변환 등에 사용.                                               |
| `the_title`     | 글 제목 출력 전 수정. 접두사/접미사 추가, 이모지 삽입 등에 사용.                                                |
| `the_excerpt`   | 요약문(excerpt) 출력 전 수정. 길이 조정, 내용 추가 등에 사용.                                                    |
| `wp_title`      | `<title>` 태그(문서 제목) 출력 전 수정. SEO, 제목 포맷 변경 등에 사용.                                        |
| `upload_mimes`  | 업로드 허용 파일 확장자 추가/수정. SVG, PDF 등 추가 허용 시 사용.                                                |
| `comment_text`  | 댓글 내용 출력 전 수정. 자동 링크, 필터링, 내용 추가 등에 사용.                                                 |

### 요약

* **액션 훅**은 특정 시점(예: 초기화, 저장, 헤더/푸터 출력 등)에 코드를 실행할 때 사용합니다.
* **필터 훅**은 데이터(예: 본문, 제목, 요약문 등)를 출력 전에 수정할 때 사용합니다.
* 플러그인 개발에서는 위의 훅들을 활용해 기능 확장, 데이터 변환, 관리자 기능 추가 등을 구현합니다.
