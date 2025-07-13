# 📅 Day 05 (2025-07-11, Fri)

## 🎓 What I Did Today

**📌 Reported on current progress in the morning development meeting, covering presentation readiness, remaining Melbourne Market migration, and the Report project's SER API issue.**   
**📌 Received instructions to prepare for the presentation and notify on migration completion; for the SER API, was advised to check official docs for API key usage, not OAuth.**   
**📌 Immediately after the meeting, executed migration code and completed PPT preparation. Migration finished before lunch, and I reported its completion, then presented my research at 1 PM.**   
**📌 Received feedback on speaking too fast and PPT visuals lagging behind my speech, but my Q&A style was highly praised, emphasizing the need to practice conversational delivery.**   
**📌 Post-presentation, fixed the SER API data fetching, identifying and correcting endpoint issues. Successfully fetched SER client info and GA4 data after temporary ID mapping.**  

### Detailed Activities

**1. Morning Development Meeting Highlights:**

-   **Progress Report:** Briefly updated the team on current project statuses, including ongoing presentation preparation, the remaining portion of the Melbourne Market product information migration to be executed, and the necessity of resolving an SER API issue for the Report (Dashboard) project.
    
-   **Instructions and SER API Issue:** Received instructions to prepare well for the presentation and to inform the lead once the migration was complete. Regarding the SER API problem, I initially inquired if it was an OAuth authentication issue based on my research. However, I was informed that it's not OAuth-related and simply requires an API key, so I was directed to research the official documentation for API key usage.
    

**2. Today's Work and Progress:**

-   **Post-Meeting & Pre-Lunch:** Immediately after the meeting, I executed the remaining migration code. Concurrently, I finalized my PPT modifications and presentation preparations. The Melbourne Market migration completed before lunchtime, and I promptly reported its successful completion to the development lead.
    
-   **Afternoon Presentation:** My presentation commenced at 1 PM. As this was the first research assignment presentation for two other interns, and I had previous experience, I took the first slot. I received feedback that my speech was too fast, likely due to tight preparation schedules, and that the PPT material seemed to follow my words rather than being presented in sync. Simultaneously, the Q&A session was highly praised; they noted that my process of maintaining eye contact with the questioner, understanding their intent, and responding based on my knowledge was very effective. This feedback led me to realize that for future presentations, I need to practice delivering information in my own words while actively engaging with the audience, as if in a dialogue.
    
-   **Post-Presentation SER API Fix:** Immediately after my presentation, I began working on fixing the SER API data fetching issue. The problem was identified as incorrect endpoints within the code; not all endpoints were properly written. I reflected that rushing had led me to ask an LLM to find potential error-causing parts, but a slow, careful review of the code from the beginning would likely have resolved the issue much faster. After completing the necessary endpoint corrections, I proceeded to temporarily match GA4 customer IDs with our company's Korean site IDs for testing. This allowed me to successfully fetch SER client information (which was then applied to the frontend dropdown UI) and retrieve GA4 data.

## 🧠 Key Concepts Learned

-   **Effective Presentation Dynamics:** A successful presentation goes beyond merely conveying information; it involves actively engaging the audience through appropriate pacing, eye contact, and a conversational delivery style. Visual aids should complement the speech, not simply reflect it.
    
-   **API Endpoint Integrity in Data Integration:** Even minor inaccuracies in API endpoints can completely block data fetching. Thorough verification of all endpoints within the code is crucial for reliable data integration, and a methodical, manual review can often diagnose these issues faster than relying on automated error detection tools when the problem is fundamental.

## 💡 Practical Trial-and-Error and Tips

-   **Presentation Delivery:** Effective presentation isn't just about content; it's about delivery. Pacing, maintaining eye contact, and ensuring visual aids complement rather than just follow speech are crucial for audience engagement and comprehension. Practicing a conversational style can significantly enhance the audience's experience.
    
-   **API Troubleshooting & Debugging Strategy:** When facing API issues, a systematic and methodical review of basic elements like endpoints is often more efficient than relying on advanced tools or external help, especially under time pressure. Rushing can lead to overlooking simple yet critical errors.

## 🔜 Next Steps

-   **Continue Report Project Development:** With the SER API and GA4 data fetching issues resolved, proceed with developing the dashboard and other functionalities within the Report project.
    
-   **Prepare for Future Research Presentations:** Apply the presentation feedback to improve delivery and audience engagement for upcoming research presentations.
    

----------

# 📅 5일차 (2025-07-11, 금)

## 🎓 오늘 한 일

**📌 오전 개발 미팅에서 발표 준비, 멜번마켓 마이그레이션 잔여 실행, 리포트 프로젝트 SER API 문제 등 현재 진행 상황을 간략히 보고했습니다.**   
**📌 발표 준비 및 마이그레이션 완료 시 보고를 지시받았고, SER API 문제는 OAuth가 아닌 API 키 관련 공식 문서를 확인하라는 답변을 들었습니다.**   
**📌 미팅 후 즉시 마이그레이션 코드를 실행하고 PPT 준비를 마쳤습니다. 마이그레이션이 점심 전 완료되어 보고했고, 오후 1시에 발표를 진행했습니다.**   
**📌 발표는 말이 빠르고 PPT가 내용을 따라오는 듯하다는 피드백을 받았으나, Q&A는 훌륭했다는 평가를 받아 대화형 전달 연습의 중요성을 깨달았습니다.**   
**📌 발표 후 SER API 엔드포인트 문제를 해결하여, 임시 ID 매칭을 통해 SER 고객사 정보 및 GA4 데이터를 성공적으로 불러왔습니다.**  

### 상세 활동

**1. 오늘 개발 미팅 주요 내용:**

-   **진행 상황 보고:** 현재까지의 프로젝트 진행 상황을 간략히 보고했습니다. 여기에는 발표 준비 현황, 멜번마켓 상품정보 마이그레이션 잔여 부분 실행 계획, 그리고 리포트(대시보드) 프로젝트의 SER API 문제 해결 필요성 등이 포함되었습니다.
    
-   **지시 및 SER API 문제:** 발표 준비를 잘하고 마이그레이션이 완료되면 즉시 알려달라는 지시를 받았습니다. SER API 문제에 대해서는 제가 검색해본 내용에 기반하여 OAuth 인증 문제인지를 문의했으나, 매니저님께서는 OAuth와는 관련이 없으며 API 키만 발급받아 사용하니 관련 공식 문서를 찾아보라는 지시를 내리셨습니다.
    

**2. 오늘 작업 및 진행률:**

-   **미팅 후 ~ 점심시간 전:** 미팅이 끝나자마자 멜번마켓 마이그레이션 코드를 실행했습니다. 동시에 발표할 PPT 자료의 최종 수정 및 발표 준비를 마쳤습니다. 마이그레이션 작업은 점심시간이 시작되기 전에 완료되었고, 완료 즉시 개발선임에게 보고했습니다.
    
-   **오후 발표:** 오후 1시에 발표가 시작되었습니다. 다른 인턴 2명에게는 첫 번째 리서치 과제 발표였고, 저는 이전에 발표 경험이 있었기에 제가 첫 순서를 맡아 진행했습니다. 발표 후 피드백으로 말이 빠르다는 점과, PPT 자료가 제 말과 동일 선상에서 제공되지 못하고 마치 제가 말한 내용을 뒤늦게 따라오는 느낌이었다는 지적을 받았습니다. 하지만 Q&A 시간에는 질문자의 얼굴을 보며 질문의 의도를 파악한 뒤 제가 가진 지식에 기반하여 답변하는 프로세스는 아주 훌륭했다는 긍정적인 평가를 받았습니다. 이 피드백을 통해 앞으로는 발표를 준비할 때 청중과 눈을 맞추고 마치 대화를 주고받듯 저의 언어로 정보를 전달하는 연습을 더 해야겠다고 느꼈습니다.
    
-   **발표 후 SER API 문제 해결:** 발표가 끝난 후 바로 SER API로 데이터를 가져오는 부분의 수정에 착수했습니다. 문제는 코드 내 사용된 모든 엔드포인트가 올바르게 작성되지 않았던 것이었습니다. 급하게 진행하다 보니 LLM(거대 언어 모델)에게 오류를 찾으라고 요청했었는데, 처음부터 천천히 코드를 훑어 나갔더라면 훨씬 빨리 찾아서 해결했을 것이라고 반성했습니다. 해당 부분 수정을 완료한 뒤, GA4의 고객 아이디는 우리 회사의 국문 사이트 ID와 임시로 매칭 시켜 테스트를 진행했습니다. 그 결과, SER 고객사 정보를 성공적으로 불러오는 것(프론트엔드 드롭다운 UI에도 적용)과 GA4 데이터를 성공적으로 불러오는 데 성공했습니다.

## 🧠 배운 핵심 개념

-   **효과적인 발표 역학 (Effective Presentation Dynamics):** 성공적인 발표는 단순한 정보 전달을 넘어, 적절한 속도 조절, 청중과의 눈맞춤, 그리고 대화하는 듯한 전달 방식을 통해 청중을 적극적으로 참여시키는 것을 포함합니다. 시각 자료는 발표 내용을 단순히 반영하는 것이 아니라 보완하는 역할을 해야 합니다.
    
-   **API 엔드포인트 무결성 (API Endpoint Integrity):** API 엔드포인트의 사소한 부정확성도 데이터 가져오기를 완전히 막을 수 있습니다. 코드 내 모든 엔드포인트의 철저한 검증은 안정적인 데이터 통합에 필수적이며, 문제가 근본적일 경우 자동화된 오류 감지 도구에 의존하기보다 체계적인 수동 검토가 더 빠르게 문제를 진단할 수 있습니다.

## 💡 실전 시행착오 및 팁

-   **발표 전달력 향상:** 효과적인 발표는 단순히 내용을 전달하는 것을 넘어섭니다. 발표 속도 조절, 청중과의 눈맞춤, 그리고 시각 자료가 말과 자연스럽게 동기화되어 보조하는 방식은 청중의 몰입과 이해도를 높이는 데 매우 중요합니다. 대화하듯 정보를 전달하는 연습은 발표 능력을 크게 향상시킬 수 있습니다.
    
-   **API 문제 해결 및 디버깅 전략:** API 관련 문제에 직면했을 때, 엔드포인트와 같은 기본적인 요소들을 체계적이고 면밀하게 검토하는 것이 복잡한 도구나 외부 도움에 의존하는 것보다 효과적일 때가 많습니다. 특히 시간이 촉박할 때 서두르면 간단하지만 치명적인 오류를 간과할 수 있습니다.

## 🔜 이후 학습 방향

-   **리포트 프로젝트 개발 지속:** SER API 및 GA4 데이터 가져오기 문제가 해결되었으므로, 리포트 프로젝트 내 대시보드 및 기타 기능 개발을 계속 진행할 것입니다.
    
-   **향후 리서치 발표 준비:** 이번 발표에서 받은 피드백을 바탕으로, 앞으로의 리서치 발표에서는 전달력과 청중 참여도를 높이는 데 더욱 집중할 것입니다.
