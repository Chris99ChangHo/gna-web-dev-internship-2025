# ✨ PHP: GET and POST - Concepts and Practical Use in WordPress User Management

## 1. Understanding GET and POST💡

GET and POST are fundamental HTTP request methods used for communication between a client (web browser) and a server. Based on your recent WordPress user management practice, here's a clear breakdown of each concept.

### GET

-   **Role:** Primarily used for **"retrieval" operations** such such as search, filter, and sort, by passing values via **URL parameters**. It's suitable for fetching data without altering the server's state.
-   **Today's Practice Examples:**
    -   **User Search:** `/user-list/?user_search=JohnDoe`
    -   **Role-based Filter:** `/user-list/?role=author`
-   **PHP Usage Example:**
    
    ```php
    <?php
    $search = isset($_GET['user_search']) ? sanitize_text_field($_GET['user_search']) : '';
    $role   = isset($_GET['role']) ? sanitize_text_field($_GET['role']) : '';
    ?>
    
    ```
    
-   **Characteristics:**
    -   Values are **exposed directly in the URL**.
    -   URLs can be **bookmarked or shared**.
    -   **Not suitable for data modification** (insert, update, delete) as it's primarily for fetching data.

### POST

-   **Role:** Used for securely transmitting form data to the server, primarily for **"modification" operations** like inserting, updating, or deleting data.
-   **Today's Practice Examples:**
    -   **User Addition Form:** Submitting form data to register a new user is handled via POST.
    -   **(Extensible)** User information modification or deletion would also typically be handled via POST.
-   **PHP Usage Example:**
    
    ```php
    <?php
    if (isset($_POST['add_user'])) {
        // $_POST['new_user_login'], $_POST['new_user_email'] etc.
        // User creation processing logic
    }
    ?>
    
    ```
    
-   **Characteristics:**
    -   Values are **not exposed in the URL**.
    -   **Suitable for data modification**.
    -   **Sensitive information** (e.g., passwords) should always be sent via POST for security reasons.

## 2. Where to Place This Content? (Practical/Learning Perspective) 📁

Based on practical and learning considerations, content regarding GET/POST concepts, example code, and the flow of practical application should ideally be placed in a **`php` folder**.

-   **Reasoning:** GET/POST are core concepts of PHP and are used recurrently across all web development, not just WordPress. Placing them in a dedicated `php` section ensures a structured approach to organizing fundamental language concepts.

**Example Folder Structure for Organizing Practice/Concept/Tips:**

```plaintext
/
├── php/
│   ├── GET_POST_Concepts.md             <-- This file would go here
│   ├── User_Management_IO.md
│   └── ...
├── wordpress/
│   ├── user-list-template.php
│   ├── movies-list-template.php
│   └── ...
├── docs/
│   ├── Daily_Log_20250604.md
│   └── ...
└── README.md

```

## 3. Conclusion and Additional Tips ✨

Organizing GET/POST concepts, practical code examples, and their application within WordPress in the **`php` folder** is the most systematic and practical approach.

Additionally, you can include **summaries or links to this concept document within your daily practice logs (`docs` folder) or other relevant documentation.** This will be highly beneficial for future review and for sharing knowledge with teammates.

---

# ✨ PHP: GET과 POST - 워드프레스 유저 관리 실습을 통한 개념과 활용

## 1. GET과 POST 이해하기💡

GET과 POST는 클라이언트(웹 브라우저)와 서버 간의 통신에 사용되는 기본적인 HTTP 요청 방식입니다. 최근 진행하신 워드프레스 유저 관리 실습을 바탕으로 각 개념을 명확하게 정리해 드릴게요.

### GET

-   **역할:** 주로 **URL 파라미터를 통해 값을 전달**하여 **검색, 필터, 정렬 등 데이터를 "조회"**하는 데 사용됩니다. 서버의 데이터를 변경하지 않고 가져올 때 적합합니다.
-   **오늘 실습 예시:**
    -   **유저 검색:** `/user-list/?user_search=홍길동`
    -   **역할별 필터:** `/user-list/?role=author`
-   **PHP 사용 예시:**
    
    ```php
    <?php
    $search = isset($_GET['user_search']) ? sanitize_text_field($_GET['user_search']) : '';
    $role   = isset($_GET['role']) ? sanitize_text_field($_GET['role']) : '';
    ?>
    
    ```
    
-   **특징:**
    -   값이 **URL에 직접 노출**됩니다.
    -   해당 URL을 **북마크하거나 공유**할 수 있습니다.
    -   서버의 **데이터를 변경(삽입/수정/삭제)하는 작업에는 부적합**합니다.

### POST

-   **역할:** 폼(form) 데이터를 서버로 **안전하게 전송**하며, 주로 **"삽입/수정/삭제"와 같이 서버의 데이터를 변경**하는 데 사용됩니다.
-   **오늘 실습 예시:**
    -   **유저 추가 폼:** 새 유저 등록 시 폼 데이터를 POST 방식으로 서버로 전송합니다.
    -   **(확장 시)** 유저 정보 수정이나 삭제도 POST 방식으로 처리하는 것이 일반적입니다.
-   **PHP 사용 예시:**
    
    ```php
    <?php
    if (isset($_POST['add_user'])) {
        // $_POST['new_user_login'], $_POST['new_user_email'] 등
        // 유저 생성 처리 로직
    }
    ?>
    
    ```
    
-   **특징:**
    -   값이 **URL에 노출되지 않습니다.**
    -   데이터 변경에 적합하며, 특히 **비밀번호와 같이 보안상 중요한 정보는 반드시 POST** 방식으로 전송해야 합니다.

## 2. 정리 내용을 어디에 올리는 것이 좋은가? (실무/학습 기준) 📁

GET/POST 개념 정리, 예시 코드, 실습 흐름 설명과 같은 내용은 실무/학습 기준에서 **`php` 폴더**에 올리는 것이 가장 적합하고 체계적입니다.

-   **이유:** GET/POST는 PHP의 핵심 개념이자, 워드프레스뿐만 아니라 **모든 웹 개발 전반에 걸쳐 반복적으로 쓰이는 중요한 내용**이기 때문입니다. 언어(`php`) 자체의 기본 개념을 정리하는 섹션에 배치하는 것이 좋습니다.

**프로젝트별 실습/개념/팁을 정리하는 폴더 구조 예시:**

```plaintext
/
├── php/
│   ├── GET_POST_Concepts.md             <-- 이 파일이 여기에 위치
│   ├── User_Management_IO.md
│   └── ...
├── wordpress/
│   ├── user-list-template.php
│   ├── movies-list-template.php
│   └── ...
├── docs/
│   ├── 실습일지_20250604.md
│   └── ...
└── README.md

```

## 3. 결론 및 추가 팁 ✨

GET/POST 개념 정리와 실습 코드, 워드프레스에서의 활용법은 **`php` 폴더에 올리는 것이 가장 체계적이고 실무적으로도 좋습니다.**

추가적으로, **실습 일지(`docs` 폴더)나 다른 관련 문서에도 이 개념 문서로의 요약이나 링크를 남겨두면, 나중에 복습하거나 팀원들과 공유할 때 매우 유용할 거예요.**
