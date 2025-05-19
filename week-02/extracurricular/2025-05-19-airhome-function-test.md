# 🧪 Manual Functional Testing – Practical Overview

## 1. What is Manual Functional Testing?

Manual Functional Testing is the process where a tester **directly executes test scenarios** to verify that developed features work exactly as specified in requirements or design documents.  
It is essential for validating UI/UX and complex user flows, especially before release, where automated testing might fall short.

---

## 2. Why is it Important?

- **Direct verification of client requirements**  
- Detect UI/UX and usability issues  
- Covers areas difficult for automation  
- Prevents costly bugs before release  
- Provides an external perspective beyond developer views

---

## 3. How is it Performed in Practice?

| Step | Description |
|-------|-------------|
| 1. Analyze requirements | Review specs, design docs, client requests; prioritize functions |
| 2. Write test scenarios & cases | Include normal and edge cases with detailed steps and expected results |
| 3. Prepare test environment | Use correct versions, test accounts, record OS/browser info |
| 4. Execute manual tests | Follow scenarios, check UI, data, and functionality |
| 5. Log issues | Document symptoms, reproduction steps, screenshots in collaboration tools |
| 6. Provide feedback & retest | Share with developers, verify fixes with regression tests |

---

## 4. Key Checkpoints in Manual Testing

- **Functional completeness:** Does every feature work as required?  
- **UI/UX consistency:** Are buttons, forms, links functional and visually intact?  
- **User flow:** Are screen transitions and data inputs/outputs smooth?  
- **Exception handling:** Are invalid inputs and unexpected cases handled gracefully?  
- **Data integration:** Is data stored, retrieved, and updated correctly?  
- **Permissions & security:** Are access rights enforced correctly?  
- **Response & error messages:** Is performance adequate and are errors informative?

---

## 5. Recommended Learning Topics

- Basics of software testing: types, principles, and quality assurance  
- Requirements and specification analysis  
- Test case and scenario design  
- Effective bug reporting skills  
- Usage of QA collaboration tools (JIRA, Notion, etc.)  
- Understanding platform/browser specifics  
- Basics of automated testing for future readiness

---

## 6. Example: Airhome New Function Testing Context

- Focus on separate Land and Building reservation flows  
- Incentive settings per reservation type  
- Dashboard displays and permissions per role  
- Reservation status and ticket system logic  
- How these detailed requirements emphasize the need for thorough manual functional testing

---

# 🧪 수동 기능 테스트 – 실무 중심 정리

## 1. 수동 기능 테스트란?

수동 기능 테스트는 개발된 기능이 **기획서, 요구사항, 사용자 기대에 맞게 제대로 작동하는지** 사람이 직접 시나리오를 따라 실행하며 확인하는 과정입니다.  
자동화 테스트로 커버하기 어려운 UI/UX 검증, 복잡한 사용자 흐름, 초기 배포 전 필수 품질 점검 단계에서 주로 수행됩니다.

---

## 2. 왜 중요한가?

- **고객 요구사항 충족 여부 직접 검증**  
- UI/UX 문제 및 사용성 오류 발견 가능  
- 자동화가 어려운 부분 보완  
- 배포 전 심각한 오류 사전 발견 → 비용/시간 절감  
- 개발자 시야에 잘 들어오지 않는 문제도 발견 가능 (외부 시각 확보)

---

## 3. 실무에서의 수행 절차

| 단계 | 설명 |
|---|---|
| 1. 요구사항 분석 | - 기획서, 디자인 문서, 클라이언트 요청사항 파악<br>- 기능별 중요도 및 우선순위 선정 |
| 2. 테스트 시나리오 및 케이스 작성 | - 정상 케이스뿐 아니라 예외상황도 포함<br>- 상세 단계 및 기대 결과 명시 |
| 3. 테스트 환경 준비 | - 테스트 가능한 버전, 테스트 계정 준비<br>- OS, 브라우저 환경 통일 및 기록 |
| 4. 수동 테스트 실행 | - 시나리오대로 직접 기능 동작<br>- UI, 데이터, 기능 모두 점검 |
| 5. 문제 발견 시 기록 | - 오류 증상, 재현 절차, 스크린샷 등 증거 자료와 함께<br>- 협업툴에 기록 및 공유 |
| 6. 피드백 및 재검증 | - 개발자에게 이슈 전달<br>- 수정 후 재테스트(Regression Test) 수행 |

---

## 4. 수동 기능 테스트 시 중점 체크 포인트

- **기능 완전성**: 모든 기능이 요구사항대로 동작하는가?  
- **UI/UX**: 버튼, 폼, 링크 등이 올바르게 작동하고 디자인이 깨지지 않는가?  
- **사용자 흐름**: 화면 이동, 데이터 입력/출력이 자연스러운가?  
- **예외 처리**: 잘못된 입력이나 예기치 않은 상황에서 안정적인가?  
- **데이터 연동**: 데이터 저장, 조회, 수정이 올바르게 반영되는가?  
- **권한 및 보안**: 사용자 권한에 맞게 접근 제한이 제대로 설정되어 있는가?  
- **반응 속도 및 오류 메시지**: 충분히 빠르고, 오류 시 친절한 안내가 나오는가?

---

## 5. 공부하고 준비하면 좋은 것들

- **소프트웨어 테스트 기초**: 테스트 종류, 원칙, 품질 보증 기본 지식  
- **요구사항 및 기획서 분석법**: 명확한 요구사항 해석법  
- **테스트 케이스 및 시나리오 작성법**: 구체적이고 재현 가능한 케이스 설계  
- **버그 리포팅 스킬**: 명확한 증상 기록, 재현 절차, 증거 첨부  
- **QA 협업툴 사용법**: JIRA, Notion, TestRail 등 도구 활용  
- **웹/앱 환경별 특성 이해**: 브라우저 차이, 반응형 UI 점검법  
- **자동화 테스트 기본 지식**: 향후 테스트 자동화 전환 시 이해도 상승

---

## 6. Airhome 신규 기능 테스트와 수동 기능 테스트 연결점

- 토지(Land)와 건물(Building) 예약 분리 및 각 대시보드 반영  
- 인센티브 설정 및 예약 상태별 티켓 시스템 적용  
- 역할별 권한과 기능 표시 테스트 필요  
- 상세 요구사항에 따른 UI/UX 및 기능 정상 작동 여부 점검  
- 실무에서 요구하는 꼼꼼한 테스트 시나리오 설계와 문제 기록 필수

