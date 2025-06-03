# WordPress Custom Development Core Concepts: CPT and WP_Query

This document summarizes the core theoretical concepts of **Custom Post Types (CPT)** and **WP_Query**, which are fundamental to custom WordPress development.

## Custom Post Type (CPT) Concept

### What is a Custom Post Type?

A **Custom Post Type** is a feature in WordPress that allows users to add new content types beyond the default ones (e.g., 'posts', 'pages'). This enables the creation of independent data structures and management menus tailored to specific purposes.

-   **Examples:** 'Movies', 'Portfolios', 'Events', 'Products', 'Recipes', 'Team Members', 'Real Estate Listings', etc., to suit various website purposes.

### Why is it Necessary?

CPTs allow for **independent and systematic management** of data with different characteristics, preventing them from being mixed in one place. For example, by creating a 'Recipe' CPT, you can systematically input and manage recipe-specific information such as cooking time, ingredients, and difficulty. This prevents data confusion and improves management efficiency.

### Practical Usage Examples

-   **Products:** Primarily used when implementing e-commerce functionalities, similar to WooCommerce.
-   **Portfolio:** Useful for systematically showcasing a designer's or developer's work.
-   **Events:** Used for managing event-related information such as dates, locations, and participation fees.
-   **Team Members:** Used for organizing team members' roles, photos, and biographies.
-   **Real Estate Listings:** Utilized for structuring real estate-related information like location, area, and price.

## WP_Query Concept

### What is WP_Query?

**WP_Query** is the **most essential query tool in WordPress** used to retrieve all types of content (posts, pages, CPTs, etc.) stored in the database according to specified conditions. This class allows for highly flexible retrieval and display of data, such as posts from a specific category, data from a particular post type, or content sorted by date, randomly, or by specific criteria.

### Key Features of WP_Query

-   **Diverse Conditional Queries:** Allows for **flexible filtering of data** based on various conditions such as categories, tags, authors, dates, custom fields (Meta Query), and post types.
-   **Loop-Based Output:** The query results can be **iteratively displayed using WordPress loops** like `while ($query->have_posts()) { $query->the_post(); ... }`.
-   **CPT Data Access:** By simply adding a parameter like `'post_type' => 'movie'`, you can easily retrieve data from your created Custom Post Type.

### Basic Usage Example

```php
<?php
$args = array(
    'post_type' => 'movie',        // Retrieves data for the custom post type 'movie'.
    'posts_per_page' => 10,        // Outputs 10 posts per page.
    'orderby' => 'date',           // Sorts by date.
    'order' => 'DESC'              // Sorts in descending order (newest first).
);

$query = new WP_Query($args); // Creates a WP_Query object and executes the query.

if ($query->have_posts()) { // Checks if there are posts to retrieve.
    while ($query->have_posts()) { // Loops as long as there are posts.
        $query->the_post(); // Sets up the current post's data.
        // Add code here to display post title, content, custom fields, etc.
        // E.g., the_title(), the_content(), get_post_meta()
    }
    wp_reset_postdata(); // Important step! Restores the main query.
} else {
    echo 'No posts found.'; // Displays a message if no posts are found.
}
?>

```

Beyond this basic example, various parameters like `category_name`, `orderby`, and `meta_query` can be used to retrieve desired data with great flexibility.

## Summary

-   **Custom Post Type (CPT):** A WordPress feature for adding desired content types, creating **independent data structures and management menus** for specific purposes.
-   **WP_Query:** WordPress's **core tool for querying various types of data** (posts, pages, CPTs, etc.) from the database according to specific conditions and displaying them on screen.

A solid understanding and practical application of these two concepts will provide the foundation for handling most WordPress customization needs. They are the starting point and core of custom WordPress development.

## References

-   [WCK (WordPress Creation Kit) Plugin](https://wordpress.org/plugins/wck-custom-fields-and-custom-post-types-creator/)
-   [WP_Query Official Documentation](https://developer.wordpress.org/reference/classes/wp_query/)

----------

# 워드프레스 커스텀 개발 핵심 개념: CPT와 WP_Query

이 문서는 워드프레스 맞춤 개발의 기반이 되는 핵심 이론 개념인 **커스텀 포스트 타입(Custom Post Type, CPT)**과 **WP_Query**를 정리합니다.

## 커스텀 포스트 타입 (CPT) 개념

### 커스텀 포스트 타입이란?

**워드프레스의 기본 콘텐츠 유형(예: '글', '페이지') 외에 사용자가 직접 정의하여 추가하는 새로운 콘텐츠 유형**을 의미합니다. 웹사이트의 특정 목적에 맞춰 독립적인 데이터 구조와 관리 메뉴를 생성할 수 있게 해줍니다.

-   **예시:** '영화', '포트폴리오', '이벤트', '상품', '레시피', '팀 멤버', '부동산 매물' 등 웹사이트의 목적에 맞는 다양한 콘텐츠 유형을 만들 수 있습니다.

### 왜 필요한가?

서로 다른 성격의 데이터를 한곳에 섞이지 않도록 **각각 독립적으로 체계적인 관리**가 가능하게 합니다. 예를 들어, '레시피' CPT를 만들면 조리 시간, 재료, 난이도 등 레시피에 특화된 정보를 체계적으로 입력하고 관리할 수 있습니다. 이는 데이터의 혼란을 방지하고 관리 효율성을 높여줍니다.

### 실제 사용 예시

-   **제품 (Products):** WooCommerce와 같이 전자상거래 기능을 구현할 때 주로 사용됩니다.
-   **포트폴리오 (Portfolio):** 디자이너나 개발자의 작업물을 체계적으로 보여줄 때 유용합니다.
-   **이벤트 (Events):** 날짜, 장소, 참가 비용 등 이벤트 관련 정보를 관리할 때 사용됩니다.
-   **팀 멤버 (Team Members):** 회사 구성원의 역할, 사진, 소개 등을 정리할 때 사용됩니다.
-   **부동산 매물 (Real Estate Listings):** 위치, 면적, 가격 등 부동산 관련 정보를 구조화할 때 활용됩니다.

## WP_Query 개념

### WP_Query란?

**워드프레스 데이터베이스에 저장된 모든 종류의 콘텐츠(글, 페이지, 커스텀 포스트 타입 등)를 개발자가 원하는 조건에 맞춰 불러오는 가장 핵심적인 쿼리 도구**입니다. 이 클래스를 사용하면 특정 카테고리의 글, 특정 포스트 타입의 데이터, 최신순/랜덤/조건별 정렬 등 매우 유연하게 데이터를 조회하고 출력할 수 있습니다.

### WP_Query의 주요 특징

-   **다양한 조건 쿼리:** 카테고리, 태그, 작성자, 날짜, 커스텀 필드(Meta Query), 포스트 타입 등 매우 **다양한 조건으로 데이터를 자유롭게 필터링**할 수 있습니다.
-   **루프(Loop) 기반 출력:** 쿼리 결과를 `while ($query->have_posts()) { $query->the_post(); ... }`와 같은 **워드프레스 루프를 통해 반복적으로 출력**할 수 있습니다.
-   **CPT 데이터 접근:** `'post_type' => 'movie'`와 같이 간단하게 파라미터만 추가하면, 생성한 커스텀 포스트 타입의 데이터를 쉽게 불러올 수 있습니다.

### 기본 사용 예시

```php
<?php
$args = array(
    'post_type' => 'movie',        // 'movie'라는 커스텀 포스트 타입의 데이터를 불러옵니다.
    'posts_per_page' => 10,        // 한 페이지에 10개의 게시물을 출력합니다.
    'orderby' => 'date',           // 날짜를 기준으로 정렬합니다.
    'order' => 'DESC'              // 내림차순(최신순)으로 정렬합니다.
);

$query = new WP_Query($args); // WP_Query 객체를 생성하고 쿼리를 실행합니다.

if ($query->have_posts()) { // 불러올 게시물이 있는지 확인합니다.
    while ($query->have_posts()) { // 게시물이 있는 동안 루프를 실행합니다.
        $query->the_post(); // 현재 게시물의 데이터를 설정합니다.
        // 여기에 게시물 제목, 내용, 커스텀 필드 등을 출력하는 코드를 작성합니다.
        // 예: the_title(), the_content(), get_post_meta() 등
    }
    wp_reset_postdata(); // 중요한 단계! 메인 쿼리를 복원합니다.
} else {
    echo '게시물을 찾을 수 없습니다.'; // 게시물이 없을 때 메시지를 출력합니다.
}
?>

```

이 외에도 `category_name`, `orderby`, `meta_query` 등 다양한 파라미터를 활용하여 원하는 데이터를 매우 유연하게 불러올 수 있습니다.

## 요약

-   **커스텀 포스트 타입 (CPT):** 워드프레스에서 원하는 콘텐츠 유형을 추가하여 목적에 맞는 **독립적인 데이터 구조와 관리 메뉴를 만드는 기능**입니다.
-   **WP_Query:** 워드프레스 데이터베이스에서 글, 페이지, CPT 등 **다양한 데이터를 조건에 맞게 쿼리하여 화면에 출력하는 워드프레스의 핵심 도구**입니다.

이 두 가지 개념을 제대로 이해하고 활용할 수 있다면, 워드프레스 커스터마이징의 대부분을 스스로 해결할 수 있는 기반을 다지게 됩니다. 이것이 워드프레스 맞춤 개발의 시작이자 핵심입니다.

## 참고자료

-   [WCK (WordPress Creation Kit) 플러그인](https://wordpress.org/plugins/wck-custom-fields-and-custom-post-types-creator/)
-   [WP_Query 공식 문서](https://developer.wordpress.org/reference/classes/wp_query/)
