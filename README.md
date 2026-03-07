# BioPet

생성 AI를 활용해 반려동물의 건강 데이터를 정리하고, 이상 징후 위험도를 분석한 뒤, 사람이 이해하기 쉬운 건강 리포트를 제공하는 팀 프로젝트입니다.


## MVP(최소 기능) 범위

1. 반려동물 등록
2. 건강 데이터 입력
3. 위험도 분석 결과 확인
4. AI 건강 리포트 생성
5. 이전 분석 기록 조회

### 예시 입력값
- 이름
- 종(강아지/고양이)
- 나이
- 체중
- 활동량
- 식사량
- 수면시간
- 특이사항

### 예시 출력값
- 정상 / 주의 / 위험
- 위험 사유 요약
- 관리 팁
- 날짜별 분석 이력

---

### 정찬 — PM

### 양찬석 - Fullstack / API 연계
프론트와 백엔드를 연결하는 기준을 맞추는 역할입니다.

#### 해야 할 일
- API 명세서 구조 이해
- Swagger 문서 작성 또는 정리
- 프론트 요청 형식과 백엔드 응답 형식 통일
- 공통 응답 구조 설계
- 연동 과정에서 발생하는 오류 확인

#### 결과물
- API 명세서
- Swagger 문서
- 요청/응답 예시 JSON
- 프론트-백 연동 체크리스트

### 구승윤 — Frontend
사용자가 실제로 보게 되는 화면을 만드는 역할입니다.

#### 해야 할 일
- 화면 흐름 파악
- 페이지 구성
- 입력 폼 만들기
- 결과 화면 구성
- 버튼, 카드, 테이블 같은 UI 컴포넌트 구성
- API 연결 후 화면에 데이터 표시

#### 결과물
- 화면정의서 기반 UI
- 주요 페이지 구현
- 공통 컴포넌트
- 사용자 입력/결과 출력 화면

---

### 황두경 — Backend
서버 로직을 만드는 역할입니다.

#### 해야 할 일
- FastAPI 기본 구조 이해
- API 엔드포인트 작성
- 입력값 검증
- 서비스 로직 구현
- DB와 연결
- AI 결과를 받아서 응답으로 전달

#### 결과물
- FastAPI 서버
- CRUD API
- 분석 요청 API
- 리포트 생성 API

### 서병덕 — Data / AI
데이터와 모델을 담당하는 역할입니다.

#### 해야 할 일
- 사용할 데이터셋 조사
- 컬럼 의미 파악
- 결측치/이상치 처리
- 전처리 과정 정리
- 간단한 베이스라인 모델 생성
- 결과 해석 자료 정리

#### 결과물
- 데이터셋 정리표
- 전처리 규칙 문서
- 모델 학습 결과
- 성능 평가표

---

### 홍은수 — Database / Server
데이터를 저장하는 구조를 설계하는 역할입니다.

#### 해야 할 일
- ERD 작성
- 테이블 설계
- 정규화 검토
- PostgreSQL 연결
- 기본 CRUD 동작 확인
- 서버 실행 환경 보조

#### 결과물
- ERD
- 테이블 정의서
- DB 스키마
- 초기 SQL 또는 ORM 모델

## 프로젝트 문서 목록

### 필수 문서
- 요구사항 정의서
- 화면정의서
- ERD
- API 명세서
- 시스템 아키텍처
- WBS 또는 일정표
- 테이블 정의서
- 테스트 케이스

### 있으면 좋은 문서
- 유저 시나리오
- 리스크 관리표
- 발표 시나리오
- 환경변수 정리 문서
- Git 브랜치/커밋 규칙

---

## 9. 추천 폴더 구조

```text
Project-BioPet/
├─ README.md
├─ docker-compose.yml
├─ .env.example
├─ frontend/
│  ├─ app/
│  │  ├─ page.tsx
│  │  ├─ pets/
│  │  ├─ input/
│  │  ├─ result/
│  │  └─ history/
│  ├─ components/
│  ├─ lib/
│  │  ├─ api.ts
│  │  └─ utils.ts
│  ├─ types/
│  └─ public/
└─ backend/
   ├─ app/
   │  ├─ main.py
   │  ├─ api/
   │  │  └─ v1/
   │  ├─ core/
   │  ├─ models/
   │  ├─ schemas/
   │  ├─ services/
   │  └─ ml/
   ├─ requirements.txt
   └─ tests/
```

---

## 추천 초기 API 목록

```http
POST   /pets
GET    /pets/{petId}
POST   /measurements
GET    /measurements/{petId}
POST   /predictions
GET    /predictions/{petId}
POST   /reports
GET    /reports/{predictionId}
GET    /health
```

