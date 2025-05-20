# 📝 Week 1 Reflection (2025.05.12 ~ 05.16)

## ✅ Key Tasks This Week

- **Started real project using Elementor**  
  - Began rebuilding the DentalCore website based on a backup of the previous version  
  - Used the Hello Elementor theme as the base and reconstructed the full page layout  
  - Completed desktop version and conducted a review with the designer before moving on to mobile responsiveness

- **Solved header button alignment issue**  
  - The right-side header buttons (📞 Phone and 📅 Request a Callback) displayed correctly with `Content Width: Full Width`, but were misaligned in `Boxed` mode  
  - Resolved the issue by creating a full-width section for the buttons and dividing it into two containers with individual background colors

## 🧠 What I Learned

- **Understanding Elementor’s Layout Structure**  
  - Learned the differences between Section, Container, and Inner Section, and how each contributes to layout behavior  
  - Became more familiar with using Flex Containers for horizontal and vertical alignment

- **Responsive Design Considerations**  
  - Gained hands-on experience in adjusting layouts between desktop and mobile views  
  - Used the Navigator effectively to manage element hierarchy and alignment

## 🔧 Technical Problem-Solving Experience

- **Header Button Alignment Issue**  
  - **Problem**: When switching Section’s `Content Width` from Full Width to Boxed, the right-aligned buttons moved to the center  
  - **Cause**: Boxed mode limits the content area’s width (e.g., `max-width: 1140px`) and centers it  
  - **Solution**:
    - Separated the button section into its own full-width Section  
    - Divided it into two Flex Containers with distinct background colors  
    - Placed transparent buttons inside each container to simulate styled buttons

## 💡 Reflections

- This week showed me that practical design issues require more than just technical knowledge — layout debugging skills are just as critical  
- Learned how to creatively structure Elementor layouts to overcome limitations  
- I expect more UI challenges ahead, but I’ve gained confidence in solving them step by step

---

# 📝 1주차 회고 (2025.05.12 ~ 05.16)

## ✅ 이번 주 주요 작업

- **Elementor 실무 프로젝트 본격 시작**  
  - 기존 백업본을 바탕으로 DentalCore 사이트를 복원하는 작업을 진행  
  - Hello Elementor 테마를 기반으로 전체 페이지 레이아웃을 재구성함  
  - 데스크톱 레이아웃 완성 후 디자이너와 리뷰 진행 → 모바일 반응형 작업 착수

- **헤더 버튼 정렬 문제 해결**  
  - 헤더 우측에 위치한 버튼 2개(📞 전화 / 📅 Request a Callback)가 `Content Width: Full Width`일 땐 정상이었으나, `Boxed`로 변경 시 가운데로 밀리는 현상 발생  
  - 버튼 영역을 Full Width로 분리하고 내부를 Flex 컨테이너 2개로 나눈 후 각각 배경색 설정하여 문제 해결

## 🧠 배운 점

- **Elementor 레이아웃 구조 이해**  
  - Section, Container, Inner Section의 역할 차이를 명확히 파악함  
  - Flex Container를 활용한 정렬 및 배치 방식에 익숙해짐

- **반응형 웹 디자인 실무 적용**  
  - 데스크톱과 모바일 간 디자인을 전환하며 반응형 설계 감각을 체득  
  - Navigator를 활용해 구조적으로 요소를 조정하고 정리하는 습관을 들임

## 🔧 기술적 문제 해결 경험

- **헤더 버튼 정렬 이슈**  
  - **문제**: Section의 `Content Width`를 Full Width → Boxed로 바꾸면 오른쪽 버튼들이 가운데로 밀림  
  - **원인**: Boxed 모드에서는 콘텐츠 영역이 `max-width: 1140px` 등으로 제한되며 가운데 정렬됨  
  - **해결**:
    - 버튼 섹션을 별도의 Full Width Section으로 분리
    - 내부를 Flex Container 2개로 구성 후 각각 배경색 지정
    - 각 Container 안에 투명 버튼 삽입하여 디자인 표현

## 💡 느낀 점

- 실무에선 단순히 기능 구현보다도, 디자인 레이아웃 문제를 분석하고 해결하는 역량이 중요하다는 걸 느꼈다.
- Elementor의 도구적 한계를 창의적인 구조 설계로 극복할 수 있다는 가능성을 경험함
- 앞으로도 다양한 UI 이슈가 발생하겠지만, 차근차근 접근하면 충분히 해결할 수 있을 것이라는 자신감을 얻음


