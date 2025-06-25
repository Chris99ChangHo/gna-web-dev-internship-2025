# ✨ npm & Yarn: JavaScript Package Managers

## 1. What are npm & Yarn?

**npm** (Node Package Manager) and **Yarn** are **package managers** used in JavaScript projects to handle code dependencies (libraries, frameworks, tools, etc.). They help developers easily install, update, configure, and remove necessary packages, playing a crucial role in maintaining project dependency consistency. They are a core part of the Node.js ecosystem.

**Key Aspects of Package Managers:**

-   **Dependency Management:** They track and manage all external code (packages) that a project relies on.
-   **Package Registry Access:** They provide access to central repositories (e.g., npm Registry) where countless open-source JavaScript packages are hosted, allowing for package downloads.
-   **Script Execution:** They offer the functionality to run custom scripts defined in a project (e.g., `start`, `build`, `test`).
-   **Consistent Environments:** Through `lock` files, they ensure that the exact same versions of packages are installed across all development environments, preventing "it works on my machine..." issues.

## 2. Basic npm & Yarn Syntax

npm and Yarn operate via a command-line interface (CLI) and manage packages based on the `package.json` file in the project's root directory. Here are the most essential commands for beginners:

-   **Initialize a New Project:** Creates a new `package.json` file to manage project metadata and dependencies.
    
    ```Bash
    # npm
    npm init
    
    # Yarn
    yarn init
    ```
    
-   **Install All Dependencies:** Installs all packages listed in `package.json` into the project's `node_modules` directory.
    
    ```Bash
    # npm
    npm install
    # or npm i
    
    # Yarn
    yarn install
    # or yarn 
    ```
    
-   **Install a Specific Package:** Adds a new package to the project and records its dependency in the `package.json` file.
    
    ```Bash
    # npm (runtime dependency)
    npm install <package-name>
    # e.g., npm install react
    
    # npm (development dependency, --save-dev or -D)
    npm install <package-name> --save-dev
    # e.g., npm install webpack --save-dev
    
    # Yarn (runtime dependency)
    yarn add <package-name>
    # e.g., yarn add react
    
    # Yarn (development dependency, --dev or -D)
    yarn add <package-name> --dev
    # e.g., yarn add webpack --dev
    ```
    
-   **Uninstall a Package:** Removes a package from `node_modules` and deletes its entry from `package.json`'s dependency list.
    
    ```Bash
    # npm
    npm uninstall <package-name>
    # e.g., npm uninstall lodash
    
    # Yarn
    yarn remove <package-name>
    # e.g., yarn remove lodash
    ```
    
-   **Update Packages:** Updates installed packages to their latest compatible versions.
    
    ```Bash
    # npm
    npm update <package-name> # specific package
    npm update # all packages
    
    # Yarn
    yarn upgrade <package-name> # specific package
    yarn upgrade # all packages
    ```
    
-   **Run Scripts:** Executes custom commands defined in the `scripts` section of `package.json`.
    
    ```Bash
    # npm
    npm run <script-name>
    # e.g., npm run start (often shorthand for "npm start")
    
    # Yarn
    yarn <script-name>
    # e.g., yarn start
    ```
    
-   **Check Installed Versions:** Checks the installed packages and their dependency tree.
    
    ```Bash
    # npm
    npm list --depth=0 # show top-level dependencies
    # or npm ls
    
    # Yarn
    yarn list --depth=0 # show top-level dependencies
    ```
    

## 3. Where are npm & Yarn Used?

npm and Yarn are at the heart of JavaScript projects, playing a crucial role in almost all JavaScript-based development. They are indispensable tools for managing dependencies and automating development workflows.

-   **Web Frontend Development:**
    -   In modern frontend framework projects like React, Angular, and Vue.js, they install and manage all necessary libraries (e.g., `react`, `react-dom`, `axios`, UI component libraries).
-   **Backend (Node.js) Development:**
    -   They manage server-side dependencies such as database drivers, authentication middleware, and utility libraries in Node.js-based server applications like Express.js and NestJS.
-   **Build Tools and Module Bundlers:**
    -   They install and configure build tools and plugins like Webpack, Babel, Rollup, and Parcel to set up development environments and optimize code for production.
-   **Testing Frameworks:**
    -   They install testing libraries like Jest, React Testing Library, and Cypress, and automate test execution through `package.json` scripts.
-   **CLI (Command Line Interface) Tool Development:**
    -   When developers create and distribute CLI tools, they manage necessary libraries and enable global installation.
-   **Cross-Platform Mobile/Desktop App Development:**
    -   In mobile apps built with React Native or desktop apps built with Electron, they manage JavaScript dependencies, facilitating code sharing across platforms.
-   **Code Quality and Formatting Tools:**
    -   They install linters like ESLint and code formatters like Prettier, integrating them into scripts to maintain code quality and consistency.
-   **Automated Workflows:**
    -   They leverage the `scripts` section of `package.json` to automate and standardize various development tasks, including project initialization, starting development servers, building code, running tests, and deployment.

npm and Yarn are foundational to the JavaScript ecosystem, enabling developers to efficiently manage projects, maintain consistent development environments, and avoid "dependency hell."

**Official Documentation:** [npm](https://docs.npmjs.com/) | [Yarn](https://yarnpkg.com/)

----------

# ✨ npm & Yarn: JavaScript 패키지 관리자

## 1. npm & Yarn이란?

**npm** (Node Package Manager)과 **Yarn**은 JavaScript 프로젝트에서 코드 의존성(라이브러리, 프레임워크, 도구 등)을 처리하는 데 사용되는 **패키지 관리자**입니다. 개발자가 필요한 패키지를 쉽게 설치, 업데이트, 구성 및 제거할 수 있도록 지원하며, 프로젝트의 의존성 일관성을 유지하는 데 핵심적인 역할을 합니다. 이들은 Node.js 생태계의 주요 부분입니다.

**패키지 관리자의 주요 특징:**

-   **의존성 관리:** 프로젝트가 의존하는 모든 외부 코드(패키지)를 추적하고 관리합니다.
-   **패키지 레지스트리 접근:** 수많은 오픈 소스 JavaScript 패키지가 호스팅되는 중앙 저장소(예: npm Registry)에 접근하여 필요한 패키지를 다운로드합니다.
-   **스크립트 실행:** 프로젝트에 정의된 스크립트(예: `start`, `build`, `test`)를 실행하는 기능을 제공합니다.
-   **일관된 환경:** `lock` 파일을 통해 모든 개발 환경에서 정확히 동일한 버전의 패키지가 설치되도록 보장하여 "제 컴퓨터에서는 되는데요..."와 같은 문제를 방지합니다.

## 2. npm & Yarn 기본 문법

npm과 Yarn은 명령줄 인터페이스(CLI)를 통해 작동하며, 프로젝트의 루트 디렉터리에 있는 `package.json` 파일을 기반으로 패키지를 관리합니다. 다음은 초보자가 알아야 할 가장 기본적인 명령어들입니다.

-   **새 프로젝트 초기화:** 프로젝트 메타데이터 및 의존성 관리를 위한 새로운 `package.json` 파일을 생성합니다.
    
    ```Bash
    # npm
    npm init
    
    # Yarn
    yarn init
    ```
    
-   **모든 의존성 설치:** `package.json`에 나열된 모든 패키지를 프로젝트의 `node_modules` 디렉터리에 설치합니다.
    
    ```Bash
    # npm
    npm install
    # 또는 npm i
    
    # Yarn
    yarn install
    # 또는 yarn
    ```
    
-   **특정 패키지 설치:** 프로젝트에 새 패키지를 추가하고 `package.json` 파일에 해당 의존성을 기록합니다.
    
    ```Bash
    # npm (런타임 의존성)
    npm install <패키지_이름>
    # 예: npm install react
    
    # npm (개발 의존성, --save-dev 또는 -D)
    npm install <패키지_이름> --save-dev
    # 예: npm install webpack --save-dev
    
    # Yarn (런타임 의존성)
    yarn add <패키지_이름>
    # 예: yarn add react
    
    # Yarn (개발 의존성, --dev 또는 -D)
    yarn add <패키지_이름> --dev
    # 예: yarn add webpack --dev 
    ```
    
-   **패키지 제거:** `node_modules`에서 패키지를 제거하고 `package.json`의 의존성 목록에서 삭제합니다.
    
    ```Bash
    # npm
    npm uninstall <패키지_이름>
    # 예: npm uninstall lodash
    
    # Yarn
    yarn remove <패키지_이름>
    # 예: yarn remove lodash
    ```
    
-   **패키지 업데이트:** 설치된 패키지를 최신 호환 버전으로 업데이트합니다.
    
    ```Bash
    # npm
    npm update <패키지_이름> # 특정 패키지
    npm update # 모든 패키지
    
    # Yarn
    yarn upgrade <패키지_이름> # 특정 패키지
    yarn upgrade # 모든 패키지
    ```
    
-   **스크립트 실행:** `package.json`의 `scripts` 섹션에 정의된 사용자 지정 명령어를 실행합니다.
    
    ```Bash
    # npm
    npm run <스크립트_이름>
    # 예: npm run start ("npm start"로 축약 가능)
    
    # Yarn
    yarn <스크립트_이름>
    # 예: yarn start
    ```
    
-   **설치된 버전 확인:** 설치된 패키지와 그 의존성 트리를 확인합니다.
    
    ```Bash
    # npm
    npm list --depth=0 # 최상위 의존성만 확인
    # 또는 npm ls
    
    # Yarn
    yarn list --depth=0 # 최상위 의존성만 확인
    ```
    

## 3. npm & Yarn은 어디에 사용되나요?

npm과 Yarn은 JavaScript 프로젝트의 핵심이며, 거의 모든 JavaScript 기반 개발에서 필수적인 역할을 합니다. 의존성을 관리하고 개발 워크플로우를 자동화하는 데 없어서는 안 될 도구입니다.

-   **웹 프론트엔드 개발:**
    -   React, Angular, Vue.js와 같은 최신 프론트엔드 프레임워크 프로젝트에서 필요한 모든 라이브러리(예: `react`, `react-dom`, `axios`, UI 컴포넌트 라이브러리)를 설치하고 관리합니다.
-   **백엔드 (Node.js) 개발:**
    -   Express.js, NestJS 등 Node.js 기반 서버 애플리케이션에서 데이터베이스 드라이버, 인증 미들웨어, 유틸리티 라이브러리 등 서버 측 의존성을 관리합니다.
-   **빌드 도구 및 모듈 번들러:**
    -   Webpack, Babel, Rollup, Parcel과 같은 빌드 도구와 플러그인을 설치하고 구성하여 개발 환경을 설정하고 프로덕션 코드를 최적화합니다.
-   **테스팅 프레임워크:**
    -   Jest, React Testing Library, Cypress 등 테스트 라이브러리를 설치하고, `package.json` 스크립트를 통해 테스트 실행을 자동화합니다.
-   **CLI (Command Line Interface) 도구 개발:**
    -   개발자들이 CLI 도구를 만들고 배포할 때, 필요한 라이브러리를 관리하고 전역적으로 설치 가능하게 만듭니다.
-   **크로스 플랫폼 모바일/데스크톱 앱 개발:**
    -   React Native를 사용한 모바일 앱이나 Electron을 사용한 데스크톱 앱에서 JavaScript 의존성을 관리하여 플랫폼 간 코드 공유를 용이하게 합니다.
-   **코드 품질 및 포매팅 도구:**
    -   ESLint, Prettier와 같은 린터(linter) 및 코드 포맷터를 설치하고 스크립트에 통합하여 코드 품질과 일관성을 유지합니다.
-   **자동화된 워크플로우:**
    -   `package.json`의 `scripts` 섹션을 활용하여 프로젝트 초기화, 개발 서버 실행, 코드 빌드, 테스트 실행, 배포 등 다양한 개발 작업을 자동화하고 표준화합니다.

npm과 Yarn은 개발자가 의존성 문제에 갇히지 않고, 프로젝트를 효율적으로 관리하며, 일관된 개발 환경을 유지할 수 있도록 돕는 JavaScript 생태계의 기반입니다.

**공식 문서:** [npm](https://docs.npmjs.com/) | [Yarn](https://yarnpkg.com/)
