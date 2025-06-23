## 📝 Commit Message Template (Conventional Commits)

## English

```text
<type>[optional scope]: <short description>   
[Optional body: detailed explanation, reasoning, or context]   
[Optional footer: references to issues, breaking changes, etc.]
```

**Types**

-   **type**: The purpose of the change (see below for common types)
    
-   **optional scope**: (Optional) The part of the codebase affected (e.g., user, api, docs)
    
-   **short description**: Brief summary of the change (imperative, under 50 characters)
    
-   **body**: (Optional) Detailed explanation, reasoning, or context for the change
    
-   **footer**: (Optional) Issue references (e.g., Closes #12), breaking changes, etc.
    

**Common Types**

-   feat: Add a new feature
    
-   fix: Fix a bug
    
-   docs: Documentation only changes
    
-   style: Code style changes (formatting, etc.)
    
-   refactor: Refactor code without changing functionality
    
-   test: Add or update tests
    
-   chore: Maintenance tasks (build, dependencies, etc.)
    
### **Usage Example**

```text
feat(auth): add OAuth2 login support

- Implemented Google and Facebook login
- Updated user model

Closes #42
```
----------

## 🔀 Pull Request Message Template

## English

```text
# [Type] Brief Summary

## What & Why
- What does this PR do?
- Why is this change necessary?

## How
- Key implementation details

## Testing
- How was this tested?
- Any test coverage added?

## References
- Closes #issue-number
- Related docs/links

---

### Checklist
- [ ] Code review completed
- [ ] Tests passed
- [ ] Documentation updated
```
-   **[Type] Brief Summary**: Short title for the PR (e.g., [feat] Add user login)
    
-   **What & Why**: What is changed and why it’s needed
    
-   **How**: Key implementation details or approaches
    
-   **Testing**: How you verified the change (manual, automated, etc.)
    
-   **References**: Related issues, documents, or links
    
-   **Checklist**: Review/merge readiness

----------

## 국문

```text
<타입>[선택적 범위]: <짧은 설명>   
[선택적 본문: 상세 설명, 배경, 추가 맥락]   
[선택적 푸터: 이슈 참조, 주요 변경점 등]
```

**타입**

-   **타입**: 변경의 목적(아래 타입 참고)
    
-   **선택적 범위**: (선택) 영향받는 모듈/컴포넌트 (예: user, api, docs)
    
-   **짧은 설명**: 한 줄 요약, 명령형, 50자 이내
    
-   **본문**: (선택) 상세 설명, 변경 이유, 구현 맥락 등
    
-   **푸터**: (선택) 이슈 번호(예: Closes #12), 주요 변경점(BREAKING CHANGE) 등
    

**자주 쓰는 타입**

-   feat: 새로운 기능 추가
    
-   fix: 버그 수정
    
-   docs: 문서 변경
    
-   style: 코드 스타일/포맷팅
    
-   refactor: 리팩토링(기능 변화 없음)
    
-   test: 테스트 코드 추가/수정
    
-   chore: 기타 유지보수 작업
    
### **사용 예시**

```text
feat(auth): OAuth2 로그인 지원 추가

- 구글, 페이스북 로그인 구현
- 사용자 모델 업데이트

Closes #42
```

## 국문

```text
# [타입] 간단 요약

## 주요 내용 및 목적
- 이 PR이 하는 일
- 변경이 필요한 이유

## 구현 방법
- 핵심 구현 내용

## 테스트
- 테스트 방법/범위
- 추가된 테스트 코드

## 참고 자료
- Closes #이슈번호
- 관련 문서/링크

---

### 체크리스트
- [ ] 코드 리뷰 완료
- [ ] 테스트 통과
- [ ] 문서화 완료
```

-   **[타입] 간단 요약**: PR 제목(예: [feat] 로그인 기능 추가)
    
-   **주요 내용 및 목적**: 무엇을, 왜 변경했는지
    
-   **구현 방법**: 핵심 구현 내용, 접근 방식
    
-   **테스트**: 테스트 방법, 범위, 추가된 테스트 코드
    
-   **참고 자료**: 관련 이슈, 문서, 참고 링크
    
-   **체크리스트**: 리뷰 및 병합 준비 상태
