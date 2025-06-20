# ✅ Nextend Social Login Google Login Integration Fix

## 🔍 Problem Situation

Google login was failing on a WordPress site using the Nextend Social Login plugin:

-   Clicking the Google login button resulted in a "400 Error: `redirect_uri_mismatch`" message.
-   Users were unable to log in or register via their Google accounts.

## 📌 Cause Analysis

The "400 Error: `redirect_uri_mismatch`" is a standard OAuth 2.0 security error. It occurs when the `redirect_uri` (callback URL) sent by the client (the Nextend Social Login plugin) during the authentication request does not _exactly_ match one of the `Authorized Redirect URIs` pre-registered in the Google Cloud Console for that OAuth 2.0 Client ID. Even minor discrepancies like:

-   Protocol mismatch (`http` vs. `https`)
-   Missing or extra `www`
-   Trailing slash (`/`) differences
-   Typos

can trigger this error. The Google OAuth server expects a perfect match for security reasons.

## 🛠 Solution

### ✅ Core Idea

The core idea was to ensure the `redirect_uri` value used by the Nextend Social Login plugin was **identically registered** in the Google Cloud Console's OAuth client ID configuration.

### 💡 Step-by-Step Resolution

1.  **Verify the Exact `redirect_uri` from Nextend Social Login:** Access the WordPress admin panel, navigate to **Settings > Nextend Social Login > Google** (under the `Providers` tab). The required `redirect URI` for Google will be clearly displayed on this settings page. Copy this exact URL.
   
    ```plaintext
    Example of a redirect URI:
    https://yourdomain.com/wp-login.php?loginSocial=google
    ```
  
2.  **Access Google Cloud Console's OAuth Credentials:** Log in to [Google Cloud Console](https://console.cloud.google.com/) > Select your project > Navigate to **APIs & Services > Credentials**.
    
3.  **Update "Authorized Redirect URIs" for the OAuth Client ID:** Click on the specific OAuth 2.0 Client ID you are using (or create a new "Web application" type if you haven't yet). Locate the "Authorized redirect URIs" section.
    
    -   **Add the copied `redirect URI`**: Click "ADD URI" and paste the exact URL obtained from the Nextend Social Login plugin.
    -   **Ensure Exact Match**: Double-check that every character, including `http/https`, `www` presence, and trailing slashes, matches perfectly.
    -   (Optional but Recommended) If there were any old or incorrect URIs, consider removing them to avoid confusion, unless they are needed for other applications.
4.  **Save Changes in Google Cloud Console:** Click the `SAVE` button to apply the changes to your OAuth client ID.
    
5.  **Re-enable Google Provider in Nextend Social Login:** Go back to **WordPress Admin > Settings > Nextend Social Login > Google**, ensure the Client ID and Client Secret are correctly entered, and then click the `Enable` button for the Google provider.
    

## 🎯 Result

Upon re-attempting the Google login from the WordPress login/registration page, the `redirect_uri_mismatch` error was resolved. Users could successfully log in and register using their Google accounts, and the social login button appeared correctly on the forms.

## 💡 Lessons Learned

-   **Precision is Key in OAuth Configurations**: The `redirect_uri_mismatch` error highlights the strict security requirements of OAuth 2.0. Even a single character difference in the `redirect URI` will cause authentication to fail. Always copy and paste the URI directly from the plugin/application providing it.
-   **Security of `Client Secret`**: The `Client Secret` should be treated with extreme confidentiality. Ensure your WordPress admin panel is secured with strong passwords and two-factor authentication, as this information is stored there. Never expose it in public repositories.
-   **Understanding OAuth Flow**: Grasping the basic OAuth 2.0 authorization code flow (client requests, authorization server redirects to pre-registered URI) is crucial for effective troubleshooting of such issues across different services.

## 🗂 Related Keywords

`WordPress` `NextendSocialLogin` `GoogleOAuth` `OAuth2.0` `redirect_uri_mismatch` `Troubleshooting` `WebLogin`

----------

# ✅ Nextend Social Login 구글 로그인 연동 문제 해결

## 🔍 문제 상황

Nextend Social Login 플러그인을 사용하는 워드프레스 사이트에서 구글 로그인 시도가 실패했습니다:

-   구글 로그인 버튼 클릭 시 "400 오류: `redirect_uri_mismatch`" 메시지가 발생했습니다.
-   사용자들이 구글 계정을 통해 로그인하거나 회원가입을 할 수 없었습니다.

## 📌 원인 분석

"400 오류: `redirect_uri_mismatch`"는 표준 OAuth 2.0 보안 오류입니다. 이 오류는 클라이언트(Nextend Social Login 플러그인)가 인증 요청 시 보낸 `redirect_uri` (콜백 URL)가 구글 Cloud Console에 해당 OAuth 2.0 클라이언트 ID에 대해 사전에 등록된 `승인된 리디렉션 URI(Authorized Redirect URIs)` 중 하나와 **정확히 일치하지 않을 때** 발생합니다.

-   `http`와 `https` 프로토콜 불일치
-   `www` 유무 차이
-   끝의 슬래시(`/`) 유무 차이
-   오타

와 같은 사소한 불일치도 이 오류를 유발할 수 있습니다. 구글 OAuth 서버는 보안상의 이유로 정확한 일치를 요구합니다.

## 🛠 해결 방법

### ✅ 핵심 아이디어

핵심 아이디어는 Nextend Social Login 플러그인이 사용하는 `redirect_uri` 값이 구글 Cloud Console의 OAuth 클라이언트 ID 설정에 **동일하게 등록되었는지** 확인하는 것이었습니다.

### 💡 단계별 해결

1.  **Nextend Social Login에서 정확한 `redirect_uri` 확인:** 워드프레스 관리자 패널에 접속하여 **설정 > Nextend Social Login > Google** (Provider 탭 아래)로 이동합니다. Google 설정 페이지에 필요한 `redirect URI`가 명확하게 표시됩니다. 이 URL을 정확히 복사합니다.
    
    ```plaintext
    리디렉션 URI 예시:
    https://yourdomain.com/wp-login.php?loginSocial=google
    ```
    
2.  **구글 Cloud Console의 OAuth 사용자 인증 정보 접속:** [Google Cloud Console](https://console.cloud.google.com/)에 로그인 > 프로젝트 선택 > **API 및 서비스 > 사용자 인증 정보**로 이동합니다.
    
3.  **OAuth 클라이언트 ID의 "승인된 리디렉션 URI" 업데이트:** 사용 중인 특정 OAuth 2.0 클라이언트 ID를 클릭하여 편집 화면으로 들어갑니다 (아직 생성하지 않았다면 "웹 애플리케이션" 유형으로 새로 생성합니다). "승인된 리디렉션 URI" 섹션을 찾습니다.
    
    -   **복사한 `redirect URI` 추가**: Nextend Social Login 플러그인에서 얻은 정확한 URL을 "URI 추가" 버튼을 클릭하여 붙여넣습니다.
    -   **정확한 일치 확인**: `http/https`, `www` 유무, 끝 슬래시 등 모든 문자가 완벽하게 일치하는지 다시 확인합니다.
    -   (선택 사항이지만 권장) 기존에 잘못 등록된 URI가 있다면 혼동을 피하기 위해 삭제하는 것을 고려합니다 (단, 다른 애플리케이션에 필요하지 않은 경우).
4.  **구글 Cloud Console에서 변경 사항 저장:** `저장(SAVE)` 버튼을 클릭하여 OAuth 클라이언트 ID에 변경 사항을 적용합니다.
    
5.  **Nextend Social Login에서 구글 Provider 재활성화:** **워드프레스 관리자 > 설정 > Nextend Social Login > Google**로 돌아가 클라이언트 ID와 클라이언트 보안 비밀번호가 올바르게 입력되었는지 확인한 후, Google Provider의 `활성화(Enable)` 버튼을 클릭합니다.
    

## 🎯 결과

워드프레스 로그인/회원가입 페이지에서 구글 로그인을 다시 시도한 결과, `redirect_uri_mismatch` 오류가 해결되었습니다. 사용자들은 구글 계정을 사용하여 성공적으로 로그인 및 회원가입을 할 수 있었고, 소셜 로그인 버튼도 폼에 올바르게 표시되었습니다.

## 💡 느낀 점

-   **OAuth 설정의 정확성 중요성**: `redirect_uri_mismatch` 오류는 OAuth 2.0의 엄격한 보안 요구사항을 명확히 보여줍니다. `redirect URI`의 단 하나의 문자 차이도 인증 실패를 초래합니다. 항상 플러그인/애플리케이션에서 제공하는 URI를 직접 복사하여 붙여넣는 습관을 들여야 합니다.
-   **`Client Secret` 보안**: `클라이언트 보안 비밀번호`는 매우 민감한 정보입니다. 절대 외부에 노출되어서는 안 됩니다. 워드프레스 관리자 패널에 입력되므로, 워드프레스 관리자 계정 보안에 각별히 신경 써야 합니다. 강력한 비밀번호 사용, 2단계 인증(MFA) 활성화는 필수입니다.
-   **OAuth 흐름 이해의 중요성**: OAuth 2.0 인증 흐름(클라이언트 요청, 권한 서버의 사전 등록 URI로의 리디렉션)의 기본 원리를 이해하는 것은 이러한 종류의 문제를 진단하고 해결하는 데 결정적입니다.

## 🗂 관련 키워드

`워드프레스` `NextendSocialLogin` `구글OAuth` `OAuth2.0` `redirect_uri_mismatch` `문제해결` `웹로그인`
