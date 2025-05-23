# 🧪 Manual Functional Testing – Practical Overview

## 1. What is Manual Functional Testing?

Manual Functional Testing is the process where a tester **directly executes test scenarios** to verify that developed features work exactly as specified in requirements or design documents.  
It is essential for validating UI/UX and complex user flows, especially before release, where automated testing might fall short.

## 2. Why is it Important?

- **Direct verification of client requirements**  
- Detect UI/UX and usability issues  
- Covers areas difficult for automation  
- Prevents costly bugs before release  
- Provides an external perspective beyond developer views

## 3. How is it Performed in Practice?

| Step | Description |
|-------|-------------|
| 1. Analyze requirements | Review specs, design docs, client requests; prioritize functions |
| 2. Write test scenarios & cases | Include normal and edge cases with detailed steps and expected results |
| 3. Prepare test environment | Use correct versions, test accounts, record OS/browser info |
| 4. Execute manual tests | Follow scenarios, check UI, data, and functionality |
| 5. Log issues | Document symptoms, reproduction steps, screenshots in collaboration tools |
| 6. Provide feedback & retest | Share with developers, verify fixes with regression tests |

## 4. Key Checkpoints in Manual Testing

- **Functional completeness:** Does every feature work as required?  
- **UI/UX consistency:** Are buttons, forms, links functional and visually intact?  
- **User flow:** Are screen transitions and data inputs/outputs smooth?  
- **Exception handling:** Are invalid inputs and unexpected cases handled gracefully?  
- **Data integration:** Is data stored, retrieved, and updated correctly?  
- **Permissions & security:** Are access rights enforced correctly?  
- **Response & error messages:** Is performance adequate and are errors informative?

## 5. Recommended Learning Topics

- Basics of software testing: types, principles, and quality assurance  
- Requirements and specification analysis  
- Test case and scenario design  
- Effective bug reporting skills  
- Usage of QA collaboration tools (JIRA, Notion, etc.)  
- Understanding platform/browser specifics  
- Basics of automated testing for future readiness

## 6. Connection between Airhome New Function Testing and Manual Functional Testing

### Features to Test:

- Separation of Land and Building reservations and their reflection on respective dashboards  
- Separate incentive settings and invoice sending for Land and Building  
- Separate management of construction reports  
- Verification of feature functionality according to each role (Developer, Builder, Manager, Partner, Buyer)  
- Integration of ticket system and notification handling when reservation status changes  

### Key Checkpoints:

- Accurate reflection of reservation separation in dashboards  
- Correct display of information (Land or Building only) when clicking “View”  
- Proper separation and display of incentives, invoices, commissions by role  
- Normal operation of ticket purchase, usage, remaining ticket count, and messaging  
- No errors or UI breaks during user flows  
- Correct enforcement of role-based access restrictions  

### How to Perform:

- Log in using each role’s account  
- Create and modify Land and Building reservations separately  
- Verify reservation lists and “View” functionality on dashboards  
- Check separation of incentive settings and invoice sending  
- Test ticket system and notification messages when changing reservation status  
- Check handling of edge cases (e.g., insufficient tickets, invalid reservations)  

### Handling Issues:

- Document detailed reproduction steps, symptoms, and screenshots in collaboration tools  
- Provide close feedback to the development team, repeating fix verification and retesting  

## 7. Conclusion

Manual functional testing is not just about clicking features randomly, but a crucial process to verify software completeness from the customer’s requirements and user perspective.  
In complex systems like Airhome, with multiple roles and intertwined reservation/incentive flows, careful scenario design and role-based feature verification are especially vital.  
Continuously gaining experience in test planning, execution, and reporting significantly enhances your QA professionalism and contributes to high-quality software delivery.

---

# 🧪 수동 기능 테스트 – 실무 중심 정리

## 1. 수동 기능 테스트란?

수동 기능 테스트는 개발된 기능이 **기획서, 요구사항, 사용자 기대에 맞게 제대로 작동하는지** 사람이 직접 시나리오를 따라 실행하며 확인하는 과정입니다.  
자동화 테스트로 커버하기 어려운 UI/UX 검증, 복잡한 사용자 흐름, 초기 배포 전 필수 품질 점검 단계에서 주로 수행됩니다.

## 2. 왜 중요한가?

- **고객 요구사항 충족 여부 직접 검증**  
- UI/UX 문제 및 사용성 오류 발견 가능  
- 자동화가 어려운 부분 보완  
- 배포 전 심각한 오류 사전 발견 → 비용/시간 절감  
- 개발자 시야에 잘 들어오지 않는 문제도 발견 가능 (외부 시각 확보)

## 3. 실무에서의 수행 절차

| 단계 | 설명 |
|---|---|
| 1. 요구사항 분석 | - 기획서, 디자인 문서, 클라이언트 요청사항 파악<br>- 기능별 중요도 및 우선순위 선정 |
| 2. 테스트 시나리오 및 케이스 작성 | - 정상 케이스뿐 아니라 예외상황도 포함<br>- 상세 단계 및 기대 결과 명시 |
| 3. 테스트 환경 준비 | - 테스트 가능한 버전, 테스트 계정 준비<br>- OS, 브라우저 환경 통일 및 기록 |
| 4. 수동 테스트 실행 | - 시나리오대로 직접 기능 동작<br>- UI, 데이터, 기능 모두 점검 |
| 5. 문제 발견 시 기록 | - 오류 증상, 재현 절차, 스크린샷 등 증거 자료와 함께<br>- 협업툴에 기록 및 공유 |
| 6. 피드백 및 재검증 | - 개발자에게 이슈 전달<br>- 수정 후 재테스트(Regression Test) 수행 |

## 4. 수동 기능 테스트 시 중점 체크 포인트

- **기능 완전성**: 모든 기능이 요구사항대로 동작하는가?  
- **UI/UX**: 버튼, 폼, 링크 등이 올바르게 작동하고 디자인이 깨지지 않는가?  
- **사용자 흐름**: 화면 이동, 데이터 입력/출력이 자연스러운가?  
- **예외 처리**: 잘못된 입력이나 예기치 않은 상황에서 안정적인가?  
- **데이터 연동**: 데이터 저장, 조회, 수정이 올바르게 반영되는가?  
- **권한 및 보안**: 사용자 권한에 맞게 접근 제한이 제대로 설정되어 있는가?  
- **반응 속도 및 오류 메시지**: 충분히 빠르고, 오류 시 친절한 안내가 나오는가?

## 5. 공부하고 준비하면 좋은 것들

- **소프트웨어 테스트 기초**: 테스트 종류, 원칙, 품질 보증 기본 지식  
- **요구사항 및 기획서 분석법**: 명확한 요구사항 해석법  
- **테스트 케이스 및 시나리오 작성법**: 구체적이고 재현 가능한 케이스 설계  
- **버그 리포팅 스킬**: 명확한 증상 기록, 재현 절차, 증거 첨부  
- **QA 협업툴 사용법**: JIRA, Notion, TestRail 등 도구 활용  
- **웹/앱 환경별 특성 이해**: 브라우저 차이, 반응형 UI 점검법  
- **자동화 테스트 기본 지식**: 향후 테스트 자동화 전환 시 이해도 상승

## 6. Airhome 신규 기능 테스트와 수동 기능 테스트 연결점

### 테스트 대상 기능:

- 토지(Land)와 건물(Building) 예약 분리 및 각 대시보드 반영  
- 인센티브 설정 및 송장 발송 분리  
- 건설 리포트 별도 관리  
- 각 역할별(Developer, Builder, Manager, Partner, Buyer) 권한에 맞는 기능 동작 확인  
- 예약 상태 변경 시 티켓 시스템 연동 및 알림 처리  

### 중점 체크 항목:

- 예약 분리가 정확하게 대시보드에 반영되는지  
- ‘View’ 클릭 시 올바른 정보(토지 혹은 건물)만 표시되는지  
- 인센티브, 송장, 수수료 등이 역할별로 제대로 분리, 표시되는지  
- 티켓 구매 및 사용, 남은 티켓 수 확인 및 메시지 출력 정상 동작 여부  
- 사용자 흐름 상 오류 혹은 UI 깨짐은 없는지  
- 역할별 접근권한 제한이 잘 적용되는지  

### 수행 방법 예시:

- 각 역할 계정으로 로그인  
- 토지 예약 및 건물 예약 각각 생성 및 수정  
- 대시보드 예약 리스트 확인 및 ‘View’ 기능 점검  
- 인센티브 설정 및 송장 발송 분리 확인  
- 예약 상태 변경 시 티켓 시스템과 알림 메시지 테스트  
- 예외 상황(티켓 부족, 잘못된 예약 등) 처리 점검  

### 문제 발견 시:

- 상세 재현 방법, 증상, 스크린샷 첨부 후 협업툴에 기록  
- 개발팀과 긴밀한 피드백과 수정/재검증 반복  

## 7. 마무리

수동 기능 테스트는 단순히 기능을 눌러보는 행위가 아니라, 고객 요구사항과 사용자 관점에서 소프트웨어가 완성도를 갖추었는지를 다각도로 검증하는 필수 과정입니다.  
Airhome과 같이 여러 역할, 복잡한 예약/인센티브 시스템에서는 꼼꼼한 시나리오 작성과 역할별 기능 점검이 특히 중요합니다.  
테스트 설계부터 보고서 작성까지 꾸준히 경험하며 실력을 쌓아가면, QA 프로세스의 전문성을 크게 높일 수 있습니다.

