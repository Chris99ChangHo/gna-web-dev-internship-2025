# WooCommerce Payment & Order Flow Testing Guide

This document outlines various free plugin options for testing bank transfer (Direct Bank Transfer / Wire Transfer) and general payment/order flows within a WooCommerce development environment, based on feedback from recent dev meetings.

## 1. WooCommerce Built-in 'Direct Bank Transfer'

The most fundamental option, requiring no additional plugin installation.

* **Description:**
    * This is a payment method inherently included in WooCommerce.
    * It can be activated directly within WooCommerce settings without needing any extra plugin installation.
    * Upon order completion, customers are guided to manually transfer funds using the bank account details provided by the store (bank name, account number, beneficiary, etc.).
    * After payment, the order status typically changes to `On hold`. The administrator must manually confirm the actual deposit and then change the status to `Processing` or `Completed`.

* **How to Test:**
    1.  Navigate to `WooCommerce > Settings > Payments`.
    2.  Locate `Direct Bank Transfer` and activate it (toggle switch).
    3.  Click the `Manage` button to enter detailed bank account information (e.g., Bank Name, Account Number, Account Holder Name).
    4.  As a simulated customer, add products to the cart on the storefront and proceed to the checkout page.
    5.  Select 'Direct Bank Transfer' as the payment method and complete the order.
    6.  The order will be created with `On hold` status without requiring an actual fund transfer, allowing you to observe the order management flow in the backend.

* **Key Highlights:**
    * **No Installation Needed:** Provided by default with WooCommerce, making it the quickest way to get started.
    * **Lightweight:** No concerns about performance degradation due to additional plugins.
    * **Manual Confirmation:** In a live environment, administrators must manually verify deposits (this step can be skipped during testing).
    * **Fundamental Understanding:** Helps in understanding the basic operational principle of bank transfer as a payment method.

## 2. WooCommerce Order Test Plugin

A dedicated plugin for comprehensively testing the entire WooCommerce order and payment flow without actual monetary transactions.

* **Description:**
    * A free plugin available for download and installation from the WordPress plugin repository.
    * Provides a specially designed 'test payment gateway' that allows simulating the entire WooCommerce checkout process without actual payments.
    * Can typically be configured for administrator-only use, preventing accidental exposure to real customers during development.

* **How to Test:**
    1.  From the WordPress Dashboard, go to `Plugins > Add New`, search for 'WooCommerce Order Test', then install and activate it.
    2.  Navigate to `WooCommerce > Settings > Payments`. You will find 'WooCommerce Order Test' added as a new payment method. Activate it.
    3.  (Optional) In the 'WooCommerce Order Test' settings, you can configure the test payment gateway to be visible only to specific user roles (e.g., Administrator) to prevent exposure to general visitors.
    4.  On the storefront, add products to the cart and proceed to the checkout page.
    5.  Select 'WooCommerce Order Test' as the payment method and complete the order.
    6.  The order will be instantly completed (or set to a designated test status) without needing to enter actual payment information (credit card numbers, bank details, etc.).
    7.  This allows you to verify the entire order management workflow after payment, including order creation, email notifications, inventory reduction, and order status changes, all without using real money.

* **Key Highlights:**
    * **Test-Specific:** Used purely for testing purposes, not for actual payment processing.
    * **Full Workflow Simulation:** Enables testing of the entire post-payment process (order processing, email notifications, inventory management) as if it were a live transaction.
    * **Safe Testing Environment:** Can be configured for administrator-only use, ensuring safe testing on a development site.
    * **Synergy with Bank Transfer:** Can be used in conjunction with the WooCommerce built-in Direct Bank Transfer to test the overall order flow, including the specific manual payment method.

## 3. Direct Payments for WooCommerce – Bank Transfer, Mobile Money, Crypto and Peer-to-Peer (P2P) Payments

A third-party plugin offering more flexible configuration options for direct payment methods than the built-in WooCommerce Direct Bank Transfer.

* **Description:**
    * A free plugin available for download and installation from the WordPress plugin repository.
    * The free version supports one direct payment method, including 'Bank Transfers'.
    * May offer more detailed account information display options or the ability to add specific payment instructions compared to the built-in Direct Bank Transfer.

* **How to Test:**
    1.  From the WordPress Dashboard, go to `Plugins > Add New`, search for 'Direct Payments for WooCommerce', then install and activate it.
    2.  Navigate to `WooCommerce > Settings > Payments` and activate 'Direct Payments'.
    3.  Configure the 'Bank Transfer' option within its settings and input the necessary account details.
    4.  As a simulated customer, add products to the cart and proceed to checkout, selecting 'Bank Transfer' as the payment method to complete the order.
    5.  Verify that the order is created without actual fund transfer and that the payment method instructions are displayed correctly.

* **Key Highlights:**
    * **Enhanced Settings:** Potentially offers more customization options than the default Direct Bank Transfer.
    * **Alternative Consideration:** Can be considered as an alternative if the built-in WooCommerce functionality doesn't meet specific requirements.
    * **Third-Party Dependency:** Introduces a dependency on a third-party plugin for updates and support.

---

# WooCommerce 결제 및 주문 흐름 테스트 가이드

이 문서는 최근 개발 미팅 피드백을 바탕으로, WooCommerce 개발 환경에서 무통장입금/계좌이체 및 전반적인 결제/주문 흐름을 테스트하는 데 활용할 수 있는 다양한 무료 플러그인 옵션들을 정리합니다.

## 1. WooCommerce 내장 '무통장입금' (Direct Bank Transfer) 기능

가장 기본적이며 추가 플러그인 설치가 필요 없는 WooCommerce의 핵심 기능입니다.

* **설명:**
    * WooCommerce에 기본적으로 포함된 결제 수단입니다.
    * 별도의 플러그인 설치 없이 WooCommerce 설정 내에서 바로 활성화하여 사용할 수 있습니다.
    * 고객이 주문을 완료하면, 쇼핑몰에서 제공하는 은행 계좌 정보(은행명, 계좌번호, 예금주 등)를 확인하여 수동으로 송금하도록 안내하는 방식입니다.
    * 결제 완료 후 주문 상태는 `보류 중(On hold)`으로 변경되며, 관리자가 실제 입금 확인 후 수동으로 `처리 중(Processing)` 또는 `완료(Completed)`로 변경해야 합니다.

* **테스트 방법:**
    1.  `WooCommerce > 설정 > 결제` 탭으로 이동합니다.
    2.  `무통장입금(Direct Bank Transfer)`을 찾아 활성화(토글)합니다.
    3.  `설정(Manage)` 버튼을 클릭하여 계좌 정보(예: 은행명, 계좌번호, 예금주)를 상세하게 입력합니다.
    4.  사이트의 프런트엔드에서 고객으로 가장하여 상품을 장바구니에 담고 결제 페이지로 이동합니다.
    5.  결제 방법 중 '무통장입금'을 선택하고 주문을 완료합니다.
    6.  실제 송금을 하지 않고도 주문이 `보류 중` 상태로 생성되며, 백엔드에서 주문 관리 흐름을 확인할 수 있습니다.

* **주목할 만한 부분:**
    * **설치 불필요:** WooCommerce 설치 시 기본 제공되므로 가장 간편하게 시작할 수 있습니다.
    * **사이트 경량 유지:** 추가 플러그인으로 인한 성능 저하 우려가 없습니다.
    * **수동 확인 필수:** 실제 운영 시에는 관리자가 입금 여부를 수동으로 확인해야 하는 번거로움이 있습니다 (테스트 시에는 이 과정 생략 가능).
    * **기본적인 송금 흐름 이해:** 무통장입금이라는 결제 방식의 가장 기본적인 작동 원리를 이해하는 데 도움이 됩니다.

## 2. WooCommerce Order Test (우커머스 오더 테스트) 플러그인

실제 금전 거래 없이 WooCommerce의 전체 주문 및 결제 흐름을 포괄적으로 테스트하기 위한 전용 플러그인입니다.

* **설명:**
    * WordPress 플러그인 저장소에서 무료로 다운로드 및 설치할 수 있는 플러그인입니다.
    * 실제 결제(돈의 이동) 없이 WooCommerce 체크아웃의 모든 과정을 시뮬레이션할 수 있도록 특별히 설계된 '테스트용 결제 게이트웨이'를 제공합니다.
    * 이 결제 게이트웨이는 일반적으로 관리자만 사용하도록 설정할 수 있어, 개발/테스트 환경에서 실수로 실제 고객에게 노출될 위험이 없습니다.

* **테스트 방법:**
    1.  WordPress 대시보드에서 `플러그인 > 새로 추가`로 이동하여 'WooCommerce Order Test'를 검색, 설치 및 활성화합니다.
    2.  `WooCommerce > 설정 > 결제` 탭으로 이동하면 'WooCommerce Order Test'라는 새로운 결제 수단이 추가된 것을 확인할 수 있습니다. 이를 활성화합니다.
    3.  (선택 사항) 'WooCommerce Order Test' 설정에서 테스트 결제 게이트웨이를 특정 사용자 역할(예: 관리자)에게만 보이도록 설정하여 일반 방문자에게는 노출되지 않게 할 수 있습니다.
    4.  사이트의 프런트엔드에서 상품을 장바구니에 담고 결제 페이지로 이동합니다.
    5.  결제 방법 중 'WooCommerce Order Test'를 선택하고 주문을 완료합니다.
    6.  실제 결제 정보(카드 번호, 계좌 정보 등)를 입력할 필요 없이 주문이 즉시 완료(또는 지정된 테스트 상태로)됩니다.
    7.  이를 통해 주문 생성, 이메일 알림 발송, 재고 감소, 주문 상태 변경 등 결제 이후의 모든 주문 관리 워크플로우를 실제 돈을 사용하지 않고 완벽하게 점검할 수 있습니다.

* **주목할 만한 부분:**
    * **테스트 전용:** 실제 결제 기능을 제공하는 것이 아니라, 오직 테스트 목적으로만 사용됩니다.
    * **전체 워크플로우 시뮬레이션:** 결제 성공 시의 주문 처리, 이메일 알림, 재고 관리 등 결제 이후의 모든 과정을 실제처럼 테스트할 수 있습니다.
    * **안전한 테스트 환경:** 관리자만 사용하도록 설정할 수 있어, 개발 중인 사이트에서 안전하게 테스트할 수 있습니다.
    * **무통장입금 기능과 시너지:** 이 플러그인을 사용하여 전체 주문 흐름을 테스트하고, 동시에 WooCommerce 내장 무통장입금 기능을 활성화하여 무통장입금 방식의 특정 테스트도 병행할 수 있습니다.

## 3. Direct Payments for WooCommerce – Bank Transfer, Mobile Money, Crypto and Peer-to-Peer (P2P) Payments

WooCommerce 내장 무통장입금보다 더 유연한 직접 결제 방식 설정 옵션을 제공하는 서드파티 플러그인입니다.

* **설명:**
    * WordPress 플러그인 저장소에서 무료로 다운로드 및 설치할 수 있습니다.
    * 무료 버전에서는 'Bank Transfers'를 포함한 한 가지 직접 결제 방법을 지원합니다.
    * 내장 무통장입금 기능보다 더 상세한 계좌 정보 표시 옵션이나, 특정 결제 지침 등을 추가할 수 있는 유연성을 제공할 수 있습니다.

* **테스트 방법:**
    1.  WordPress 대시보드에서 `플러그인 > 새로 추가`로 이동하여 'Direct Payments for WooCommerce'를 검색, 설치 및 활성화합니다.
    2.  `WooCommerce > 설정 > 결제` 탭에서 'Direct Payments'를 활성화하고 설정합니다.
    3.  설정 내에서 'Bank Transfer' 옵션을 구성하고 필요한 계좌 정보를 입력합니다.
    4.  고객으로 가장하여 상품을 주문하고 결제 페이지에서 'Bank Transfer'를 선택하여 주문을 완료합니다.
    5.  실제 송금 없이 주문이 생성되고 해당 결제 방법의 안내가 제대로 나오는지 확인합니다.

* **주목할 만한 부분:**
    * **향상된 설정:** 기본 무통장입금보다 약간 더 많은 커스터마이징 옵션을 제공할 수 있습니다.
    * **대안 고려:** 만약 WooCommerce 내장 기능이 특정 요구사항을 충족하지 못할 경우 대안으로 고려할 수 있습니다.
    * **서드파티 의존성:** 플러그인 업데이트 및 지원에 대한 의존성이 발생합니다.
