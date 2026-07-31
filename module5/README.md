# 📔 Module 5: 보안/데이터 통합 및 AI 서빙·RAG 인프라 실무 기록
> **기간: 2026.07.04 ~ 2026.07.27**
> Spring Boot 기반의 실시간 메시징 암호화 인프라와 Flyway DBA 관리를 완성함과 동시에, FastAPI 기반 AI 서빙, ChromaDB VectorDB 연동, LangChain RAG 파이프라인 및 Spring Boot와의 Function Calling 통합 아키텍처를 구축한 실무 학습·개발 기록입니다.
* 팀 구성: 백엔드 5명 (JSON 응답 설계) / 프론트엔드 2명

---

### 📂 상세 기록 바로가기

#### 1. [🎓 프로젝트 회고](/module5/project_review)
* **주제**: 보안/데이터 통합 및 실시간 인프라 고도화 회고 (콘솔에서 실시간 인프라까지)
* **핵심 내용**: 
  * AttributeConverter 기반 **AES 메시지 자동 암호화** 및 `.env` 키 격리 관리를 통한 DB 유출 리스크 차단
  * **Flyway 마이그레이션 규칙 학습** 및 300여 건 이상의 배포용 더미 데이터 연관관계 전수 수선 (DBA 역할 완수)
  * AWS EC2/Nginx 환경에서 발생한 웹소켓 1006 에러 해결 및 Nginx `proxy_read_timeout` 설정을 통한 유휴 끊김 방지
  * 마감 직전(D-2) 배포 리스크를 유발하는 무리한 요구사항 거절 및 시스템 한계점 정의로 배포 안정성 사수

#### 2. [⚙️ 내가 맡은 기능](/module5/my_role)
* **주요 역할**: 메시지 암호화 인프라 구축, 입력 중(Typing) 웹소켓 인프라, API 스펙 정밀 리팩토링, Flyway & 더미 데이터 정합성 담당 (DBA)
* **핵심 로직**:
  * **AES 양방향 자동 암호화**: `@Convert` 기반 DB 저장 시 암호화/조회 시 복호화 및 기존 평문 더미 데이터 예외 안전망 구현
  * **실시간 Typing Indicator**: 인메모리 파이프라인을 통한 동적 문구 가공(`민수님 외 2명이 입력중입니다.`) 및 가나다 정렬 방출
  * **API 스펙 정밀 개편**: 방명록 쿼리 스트링 전환, 채팅 멤버 최상단 `"(나)"` 고정 및 친구 요청 수락/거절 시 알림 자동 읽음 연동
  * **DBA 형상 통제**: Flyway `USE` 구문 제거 및 ERD 최신화를 주도적으로 전담

#### 3. [📝 학습 내용 및 AI 서빙·RAG 주석 정리](/module5/lecture_notes)
* **Python & FastAPI 프레임워크**: Pydantic 스키마 기반 유효성 검증, APIRouter 계층화 및 Uvicorn/LifeSpan 생명주기 관리
* **Hugging Face & AI 서빙**: Transformers `pipeline()` 활용 감정분석/요약, Double-Checked Locking 기반 Thread-Safe 지연 로딩
* **VectorDB & LangChain RAG**: ChromaDB 코사인 유사도 검색, 문맥 Chunking(Overlap), LCEL 기반 환각(Hallucination) 방지 프롬프트 파이프라인
* **Function Calling & 이종 언어 통합**: Spring Boot ↔ FastAPI 연동, Bulkhead 타임아웃 장애 격리 및 `@JsonNaming` 기반 snake_case 통신 규약 확립

---
💡 **각 항목을 클릭하여 보안·실시간 인프라 고도화와 FastAPI 기반 AI 서빙·RAG 통합 아키텍처 구축 과정을 확인해보세요!**
