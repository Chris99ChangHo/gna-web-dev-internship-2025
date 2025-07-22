# 📅 Day 02 (2025-07-22, Tue)

## 🎓 What I Did Today

**📌 Participated in the morning development meeting, reporting on the research progress for Flask application deployment to cPanel and receiving commitments for ongoing support with technical difficulties.**   
**📌 Attempted to deploy a Python Flask web app on cPanel, successfully resolving various obstacles related to file/folder structure, Python App configuration, `requirements.txt` issues, disk quota limits, and application lock states.**   
**📌 Encountered a critical unresolvable issue with the absence of the WSGI executable file, and through the senior developer, requested support from the hosting provider for the `/opt/alt/python312/bin/lswsgi` file.**   
**📌 Completed preparation for the Shopify & Shopify Plus presentation, which was postponed to tomorrow morning.**  

### Detailed Activities

**1. Morning Development Meeting Summary:**

-   Received cPanel access permissions and reported on research into registering applications (Python Flask, etc.) on the server.
    
-   Confirmed that Flask apps require `Setup Python App` (a cPanel feature), necessitating upload of essential application files to the root directory via `File Manager`. Mentioned excluding unnecessary files like test code or virtual environments.
    
-   Stated plans to attempt Flask app upload and registration after the afternoon PPT presentation.
    
-   The team advised not to rush, requesting a share only after the app is uploaded and fully tested on the server. Promised continued support for any difficulties.
    

**2. Flask Web App cPanel Deployment Attempts & Troubleshooting:**

-   **Initiated Server Setup**: Began setting up the Python Flask dashboard web app on cPanel hosting, focusing on subdomain assignment, `Document Root` connection, and `Python App (Application root)` synchronization.
    
-   **Resolved File/Folder Structure Issues**: Successfully **resolved** problems related to matching Flask project file locations, choosing a subdomain due to main domain permission issues, creating the subdomain and specifying its `Document Root`, moving code and `requirements.txt` to the top level, and re-adjusting nested folder structure errors.
    
-   **Resolved Python App Reconfiguration & Conflict Issues**: Faced "Specified directory already used by..." errors from multiple app registration attempts. **Successfully resolved** this by deleting/deactivating existing Python Apps and manually removing virtual environment (`virtualenv`) folders.
    
-   **Resolved `requirements.txt` Recognition Errors**: Failed to install packages via `pip install` due to incorrect `requirements.txt` location or spelling. This issue was **resolved** by uploading `requirements.txt` to the correct top-level folder.
    
-   **Resolved Disk Quota Exceeded & File Cleanup**: Repeated virtual environment creations led to exceeding disk space limits. This was **resolved** by actively freeing up space through deleting large/unnecessary folders (`venv`, `virtualenv`, old apps, backups, and crucially, emptying the `.trash` recycling bin).
    
-   **Resolved Python App Lock/Deadlock Issues**: Frequent "Can't acquire lock" errors occurred due to duplicate app registrations or abnormal terminations. These issues were **resolved** using practical tips like directly deleting lock files, completely deleting and recreating the app, and requesting an unlock from the administrator.
    
-   ----------
    
    **🚨 Critical Unresolved Issue: LiteSpeed Landing Page & Missing WSGI Executable 🚨**
    
    -   The website displayed only "Proudly Served by LiteSpeed Web Server...", indicating the Flask app's WSGI was not starting correctly.
        
    -   **The root cause was identified as the absence of or improper connection to the Flask (WSGI) executable files** (specifically `/opt/alt/python312/bin/lswsgi`) on the server.
        
    -   This infrastructure issue is beyond direct developer control. Therefore, **through the senior developer, a request for support was made to the hosting provider**, inquiring about Python 3.11/3.12 support and the availability of this critical WSGI file.
        
    -   Attempts with lower Python versions (e.g., 3.8) yielded similar symptoms or additional "Disk quota exceeded" problems.
        
-   ----------
    
-   **Efforts Towards Final Flask App Service Structure**: Aimed to achieve an optimized Flask app service structure using a subdomain (`dashboard.dev1.gnasolutions.com.au`) with `Document Root` & `Application root` both set to `public_html/subdomain_top_level`. All necessary files were reflected, but due to the underlying WSGI executable absence, the Flask `index` route's return message **could not yet be displayed**.
    
-   **Additional Practical Learnings**:
    
    -   If server issues prevent operation, always copy error messages (`stderr.log` etc.) before seeking help.
        
    -   Became proficient in the loop of subdomain creation, document root assignment, Flask app file location and permissions, and Python App registration-deletion-recreation.
        
    -   Honed the skill of drafting polite internal communications/requests (e.g., English specification/installation requests).
        

**3. Shopify/Shopify Plus Presentation Preparation:**

-   Completed the presentation materials for the Shopify & Shopify Plus overview and practiced the presentation.
    
-   The presentation has been **postponed to tomorrow morning**.

## 🧠 Key Concepts Learned

-   **Practical Deployment Hurdles on cPanel:** Gained extensive hands-on experience in the complexities of deploying a Python Flask application on cPanel, including managing file/folder structure, `requirements.txt`, and Python App configurations. Crucially, learned that **fundamental server infrastructure issues, such as a missing WSGI executable, can be outside the developer's immediate control.**
    
-   **Deep Diagnosis and Recognition of Server-Side Limitations:** Systematically diagnosed and resolved many server-side errors, strengthening problem-solving skills. However, the experience highlighted that **core infrastructure deficiencies, like an incomplete WSGI environment for Flask app execution, cannot be solved by developer efforts alone.**
    
-   **Necessity of External Support and Efficient Escalation:** Realized that when confronting fundamental server environment issues that cannot be self-resolved, **contacting the hosting provider with precise, detailed information, often through a senior developer, is the most efficient and necessary step** to progress.

## 💡 Practical Trial-and-Error and Tips

-   **Prioritize WSGI Verification**: If your Flask app displays a generic server page (e.g., LiteSpeed's default), **immediately verify the presence and accessibility of the correct WSGI executable file for your Python version.** This is the **critical bottleneck**. If it's missing or inaccessible, **do not waste further time on self-troubleshooting; contact hosting support immediately, potentially via a senior developer, with detailed error logs.**
    
-   **Disk Quota Management is Essential**: Regularly monitor disk usage. When encountering "Disk quota exceeded," promptly identify and delete large, unnecessary files/folders (especially old `venv` or `virtualenv` directories, backups, and crucially, empty the `.trash` bin).
    
-   **Handling `Can't Acquire Lock` Errors**: If a "Can't acquire lock" error occurs, try fully deleting and recreating the app. Additionally, **manually locating and deleting any residual lock files** can be effective. If persistent, escalate to the administrator.
    
-   **Effective Technical Communication**: When seeking external support (e.g., from hosting providers), always provide exact error messages, especially from `stderr.log`. This significantly speeds up diagnosis and resolution and is your **primary tool for effective communication.**

## 🔜 Next Steps

-   **Collaborate with Hosting Provider on WSGI Issue**: **Actively communicate with the hosting provider regarding the missing WSGI executable file for the desired Python version (3.11/3.12) to resolve this core roadblock for the Flask app's operation.**
    
-   **Complete Flask App Deployment & Test (Post-WSGI Resolution)**: Once the WSGI issue is resolved by the hosting provider, proceed with the final Flask app upload, registration, and thorough testing on the cPanel server.
    
-   **Deliver Shopify/Shopify Plus Presentation**: Prepare for and deliver the Shopify & Shopify Plus presentation tomorrow morning.
    
-   **Initiate Security Protocol Implementation**: Begin concrete steps for implementing security protocols, starting with research into login/administrator authentication for the Flask dashboard.
    
-   **Finalize WordPress Integration Plan**: Based on successful deployment, finalize the detailed plan for integrating the Flask dashboard with the WordPress site, focusing on subdomain linking.

----------

# 📅 Day 02 (2025-07-22, 화)

## 🎓 오늘 한 일

**📌 오전 개발 미팅에서 Flask 애플리케이션 cPanel 배포를 위한 리서치 진행 상황을 보고하고, 기술적 어려움 발생 시 지속적인 지원을 약속받았습니다.**   
**📌 cPanel에서 파이썬/Flask 웹 앱을 서비스하려 시도하는 과정에서 파일/폴더 구조, Python App 구성, `requirements.txt` 문제, 디스크 용량 제한, 애플리케이션 잠금 상태 등 다양한 장애물을 직접 해결했습니다.**   
**📌 핵심적인 WSGI 실행 파일 부재 문제에 직면하여, 개발 선임을 통해 `/opt/alt/python312/bin/lswsgi` 파일의 지원을 호스팅 제공업체에 요청했습니다.**   
**📌 Shopify & Shopify Plus 발표 자료를 완성했으며, 발표는 내일 오전으로 연기되었습니다.**  

### 상세 활동

**1. 오전 개발 미팅 요약:**

-   cPanel 접근 권한을 받았고, 서버에 애플리케이션(파이썬 Flask 등) 등록 방법에 대한 리서치 진행 상황을 보고했습니다.
    
-   Flask 앱 배포 시 cPanel의 `Setup Python App` 기능을 활용해야 하며, 필요한 파일들을 `File Manager`를 통해 root 디렉터리에 업로드해야 함을 확인했습니다. 불필요한 파일은 제외하고 정리 중임을 언급했습니다.
    
-   오후 PPT 발표 준비 후, 발표가 끝난 뒤에 Flask 앱 업로드 및 등록을 시도할 예정이라고 보고했습니다.
    
-   팀에서는 급하게 진행할 필요 없으니, 서버에 앱을 올리고 테스트까지 완료되면 공유해달라고 전달받았습니다. 어려운 점 발생 시 언제든 요청하면 도와주겠다고 재확인 받았습니다.
    

**2. Flask 웹 앱 cPanel 배포 시도 및 문제 해결 과정:**

-   **서버 세팅 착수**: Python Flask 대시보드 웹 앱을 cPanel 호스팅에 서비스할 목적으로 서브도메인 지정, `Document Root` 연결, `Python App (Application root)` 동기화 세팅을 시작했습니다.
    
-   **파일/폴더 구조 조정 및 문제 해결**: Flask 프로젝트 파일의 위치 맞추기, 메인 도메인 권한 문제로 인한 서브도메인 방식 선택, 서브도메인 생성 및 `Document Root` 지정, 코드 및 `requirements.txt` 최상위 이동, 중첩 폴더 구조 오류 재조정 등 파일/폴더 구조 관련 문제들을 **성공적으로 해결**했습니다.
    
-   **Python App 재설정 및 중복 충돌 문제 해결**: 여러 번 앱 등록 시도로 발생한 "Specified directory already used by..." 에러를 기존 앱 삭제/해제 및 가상 환경 폴더 직접 삭제를 통해 **해결**했습니다.
    
-   **`requirements.txt` 인식 오류 해결**: `pip install` 시 `requirements.txt` 위치/철자 오류로 인한 패키지 설치 실패 문제를 올바른 폴더 최상위에 업로드하여 **해결**했습니다.
    
-   **디스크 용량 초과(Disk quota exceeded) 및 파일 정리 해결**: 가상 환경 생성으로 인한 디스크 한도 초과 문제를 불필요한 폴더 삭제 및 휴지통 비우기를 통해 **해결**했습니다.
    
-   **Python App 락(lock)/Deadlock 상태 해결**: 앱 중복 등록, 비정상 종료 등으로 인한 "Can't acquire lock" 에러를 lock 파일 직접 삭제, 앱 완전 삭제 & 재생성, 관리자에게 unlock 요청 등의 방법으로 **해결**했습니다.
    
-   ----------
    
    **🚨 핵심 미해결 문제: LiteSpeed 안내 페이지 및 WSGI 실행 파일 부재 🚨**
    
    -   웹사이트 접속 시 "Proudly Served by LiteSpeed Web Server..."만 반복되는 문제에 직면했습니다. 이는 Flask 앱의 WSGI가 정상적으로 구동되지 않았음을 시사했습니다.
        
    -   **서버 내 Flask(WSGI) 실행 파일(특히 `/opt/alt/python312/bin/lswsgi`)이 부재하거나 올바르게 연결되지 않은 것이 원인임을 파악했습니다.**
        
    -   이 문제는 개발자 단독으로 해결할 수 없는 인프라 문제이므로, **개발 선임을 통해 호스팅 제공업체에 `/opt/alt/python312/bin/lswsgi` 파일의 지원을 포함한 문의 문서를 작성하여 지원을 요청했습니다.**
        
    -   하위 버전(3.8 등) 시도 중에도 동일 증상 또는 "Disk quota exceeded" 등 추가 문제가 발생했습니다.
          
-   ----------
    
-   **최종 Flask 앱 서비스 구조를 위한 노력**: 서브도메인(`dashboard.dev1.gnasolutions.com.au`)을 사용하고, `Document Root`와 `Application root`를 `public_html/서브도메인 최상위`로 일치시키는 최적화된 Flask 앱 서비스 구조를 구현하려 했습니다. 필요한 파일 반영은 완료했으나, WSGI 실행 파일 부재로 Flask `index` 라우트의 메시지는 **아직 노출되지 않았습니다.**
    
-   **추가로 진행·정리한 실전 포인트**:
    
    -   서버 문제 발생 시 에러 메시지(`stderr.log` 등)를 복사하여 질의해야 함을 배웠습니다.
        
    -   서브도메인 생성, 문서 루트 지정, Flask 앱 파일 위치 및 권한, Python App 등록-삭제-재생성 루프에 익숙해졌습니다.
        
    -   내부 커뮤니케이션/요청문(영문 사양/설치 요청)을 정중하게 작성하는 요령을 숙달했습니다.
        

**3. Shopify/Shopify Plus 발표 준비:**

-   오전에 Shopify & Shopify Plus 개요 발표 자료를 완성하고 연습을 진행했습니다.
    
-   발표는 **내일 오전으로 연기**되었습니다.

## 🧠 배운 핵심 개념

-   **cPanel 환경 배포의 실제**: Flask 앱 배포 시 파일/폴더 구조, `requirements.txt` 관리, Python App 설정 등 **다양한 초기 설정 문제들을 직접 해결하며 cPanel 환경에 대한 실질적인 이해를 높였습니다.**
    
-   **서버 인프라 문제 진단 및 한계 인식**: 개발자 역량으로 해결하기 어려운 **근본적인 WSGI 실행 환경 부재와 같은 서버 인프라 문제**에 직면할 수 있음을 명확히 인식했습니다. 이는 개발 범위를 넘어선 **외부 지원의 필요성**과, 때로는 **선임을 통한 에스컬레이션의 중요성**을 강조합니다.
    
-   **체계적인 문제 해결과 에스컬레이션**: 수많은 시행착오 속에서 에러 메시지를 기반으로 문제를 분석하고 해결 가능한 부분은 자체적으로 처리했으며, 해결 불가능한 부분은 **정확한 정보와 함께 선임을 통해 호스팅 제공업체에 신속히 요청하는 효율적인 접근 방식**을 체감했습니다.

## 💡 실전 시행착오 및 팁

-   **WSGI 구동 불가 시 최우선 조치**: Flask 앱이 일반적인 서버 안내 페이지만 표시된다면, **가장 먼저 해당 파이썬 버전에 맞는 WSGI 실행 파일 존재 여부와 접근성을 확인해야 합니다.** 이 **핵심 병목**이 확인되면, 자체 해결에 시간을 낭비하지 않고 **즉시 선임을 통해 호스팅 지원팀에 상세히 문의**해야 합니다.
    
-   **디스크 할당량 관리**: 가상 환경 생성 등으로 디스크 용량 초과 문제가 자주 발생할 수 있습니다. 불필요한 파일(`venv`, `.trash`)을 주기적으로 정리하고, 특히 `.trash` 휴지통을 비우는 것이 필수입니다.
    
-   **`Can't acquire lock` 에러 대처**: 락(lock) 에러 발생 시 앱 완전 삭제 후 재생성, 관리자에게 unlock 요청과 더불어 **직접 lock 파일을 찾아 삭제**하는 방법도 유용합니다.
    
-   **호스팅사에 기술 문의 시 요령**: 문제 발생 시 `stderr.log` 등에서 얻은 **정확한 에러 메시지를 복사하여 전달하는 것**이 진단과 해결 속도를 크게 높이는 **핵심적인 소통 방법**입니다.

## 🔜 다음 학습 방향

-   **호스팅 제공업체와의 WSGI 문제 해결 협력**: **Flask 앱 구동의 핵심 문제인 WSGI 실행 파일 부재에 대해 호스팅 제공업체와 적극적으로 소통하고, 문제 해결을 위해 협력할 것입니다.**
    
-   **Flask 앱 배포 및 테스트 완료 (WSGI 해결 후)**: WSGI 문제가 해결되는 즉시, Flask 앱의 최종 업로드, 등록 및 cPanel 서버에서의 철저한 테스트를 진행할 것입니다.
    
-   **Shopify/Shopify Plus 발표 수행**: 내일 오전 예정된 Shopify & Shopify Plus 발표를 준비하고 수행할 것입니다.
    
-   **보안 프로토콜 구현 착수**: Flask 대시보드의 로그인/관리자 인증 리서치를 시작으로 보안 프로토콜 구현을 위한 구체적인 단계를 밟을 것입니다.
    
-   **워드프레스 통합 계획 확정**: 성공적인 배포를 바탕으로 서브도메인 연결에 중점을 둔 Flask 대시보드와 워드프레스 사이트 통합에 대한 상세 계획을 확정할 것입니다.
