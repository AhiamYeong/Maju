# 마주교실 (Maju Class) - 발달장애 학생을 위한 AI 기반 사회적 상황 시뮬레이션 서비스

## 프로젝트 소개

- 삼성 청년 SW 아카데미 13기 자율 프로젝트
- 서울2반 우수상 수상
- 프로젝트 기간: 2025.10.14 - 2025.11.20

**마주교실**은 발달장애·통합학급 학생들이 일상 사회 상황을 안전하게 연습할 수 있는 시뮬레이션 기반 교육 플랫폼입니다. 교사는 카페 주문, 영화표 구매 등 실생활 시나리오를 생성하고, 학생들은 난이도별 시뮬레이션을 통해 사회적 상호작용을 학습합니다.

## 팀 구성

### FE

- 이아영, 류연서, 심양관

### BE

- 김호정, 신해봄, 조수인

---

## 기술 스택

### Frontend

- **Core**: React, TypeScript, Vite
- **상태관리**: Zustand, TanStack Query
- **스타일링**: Tailwind CSS, CSS Modules
- **UI/UX**: Lottie, Chart.js, React Icons
- **통신**: Axios

### Backend

- **Core**: Java 21, Spring Boot 3.5.6
- **보안**: Spring Security, JWT
- **데이터**: JPA/Hibernate, MySQL
- **캐시**: Redis
- **통신**: WebClient

### AI Service

- **Core**: Python 3.11, FastAPI
- **AI/ML**: OpenAI GPT, Whisper (STT), ChromaDB
- **임베딩**: 한국어 특화 모델
- **처리**: LangChain (RAG), SentenceTransformers, PyTorch

### Infrastructure

- **컨테이너**: Docker Compose
- **스토리지**: AWS S3
- **문서화**: Swagger, FastAPI Docs

---

## 주요 기능

### 교사 기능

- **학생 관리**: CRUD, CSV 일괄 등록
- **시나리오 생성**:
  - 수동 생성 (질문/답변/픽토그램)
  - AI 자동 생성 (RAG 기반, 백그라운드 처리)
- **학습 분석**: 통계 대시보드, 월별 캘린더

### 학생 기능

- **난이도별 시뮬레이션**:
  - EASY: 이미지 선택
  - NORMAL: 텍스트 선택
  - HARD: 음성 답변 (STS 분석)
- **실시간 피드백**: 정답/오답 즉시 확인
- **음성 지원**: TTS 질문 읽기, STS 답변 분석

---

## 프로젝트 구조

```
프로젝트 루트/
├── frontend/                 # React 애플리케이션
│   ├── src/
│   │   ├── apis/            # API 통신
│   │   ├── components/      # React 컴포넌트
│   │   ├── pages/          # 페이지 컴포넌트
│   │   ├── stores/         # Zustand 스토어
│   │   └── types/          # TypeScript 타입
│   └── public/
│
├── backend/                 # Spring Boot API
│   └── src/main/java/
│       ├── domain/         # 비즈니스 도메인
│       │   ├── auth/       # 인증/토큰
│       │   ├── user/       # 사용자
│       │   ├── student/    # 학생
│       │   ├── scenario/   # 시나리오
│       │   └── scenariosession/  # 세션
│       └── global/         # 공통 기능
│           ├── config/     # 설정
│           ├── security/   # JWT
│           └── s3/        # 파일 업로드
│
└── ai/                     # FastAPI AI 서비스
    └── app/
        ├── domains/
        │   ├── speech_to_text/  # STT + 평가
        │   ├── text_to_speech/  # TTS
        │   └── scenario/        # RAG 생성
        └── common/             # 공통 유틸
```

---

## 실행

### 1. 환경 요구사항

- Node.js 18+
- Java 21
- Python 3.11
- Docker & Docker Compose
- MySQL 8.4
- Redis 7

### 2. Docker Compose로 실행

```bash
docker compose up -d

docker compose up --build -d

docker compose logs -f

docker compose down
```

### 3. 개별 서비스 실행

**Frontend:**

```bash
cd frontend
npm install
npm run dev
```

**Backend:**

```bash
docker compose up spring
```

**AI Service:**

```bash
cd ai
docker compose up astapi
```

---

## 주요 페이지

- 온보딩 페이지
  <img width="1919" height="860" alt="image" src="https://github.com/user-attachments/assets/73efcc83-1d96-4481-b85c-dbe30fd66994" />

- 교사 대시보드
  <img width="1919" height="860" alt="image" src="https://github.com/user-attachments/assets/061450ae-2fa4-4f8c-b104-394bb38f538d" />

- 시나리오 목록
  <img width="1000" height="563" alt="image" src="https://github.com/user-attachments/assets/f40025a6-355d-49f5-a9b6-1b73478f49d7" />

- 수동 시나리오 생성
  <img width="1800" height="1013" alt="image" src="https://github.com/user-attachments/assets/2c31b47a-22de-48c3-b5c1-2a0c5f60b5c8" />
  <img width="1897" height="864" alt="image" src="https://github.com/user-attachments/assets/8d68fbd5-52fe-4b43-858d-33bc0fa57d66" />

- AI 시나리오 생성
  <img width="1800" height="1013" alt="image" src="https://github.com/user-attachments/assets/f5500383-0f4a-4882-b693-8b292bea3420" />

- 시뮬레이션 실행
  <img width="1919" height="865" alt="image" src="https://github.com/user-attachments/assets/a5f35b2a-8d81-47da-bdfe-e1b9f2326833" />

- 시뮬레이션 난이도 (상)
  <img width="1918" height="866" alt="image" src="https://github.com/user-attachments/assets/5bcec3f3-310f-4c85-9f12-66c3d0b2e5d8" />

<img width="1918" height="866" alt="image" src="https://github.com/user-attachments/assets/19b6da73-6d3b-464a-af7a-b4b6d2f8bb4a" />

- 시뮬레이션 답변 성공
  <img width="1909" height="851" alt="image" src="https://github.com/user-attachments/assets/bcec1a34-a7e5-421c-9b7a-973fdc0f4747" />

- 시뮬레이션 답변 실패
  <img width="1914" height="850" alt="image" src="https://github.com/user-attachments/assets/74893b5f-585d-4ba9-85b1-ac137f3a919f" />

- 학생 통계
  <img width="1500" height="843" alt="image" src="https://github.com/user-attachments/assets/e8d984ed-d709-4b00-bb6e-f9c1f9311cc6" />

---

## 핵심 기능 상세

### AI 시나리오 생성 파이프라인

1. GPT 기반 시나리오 자동 생성
2. RAG (Retrieval-Augmented Generation) 활용한 맥락 기반 생성
3. 백그라운드 처리 및 실시간 알림
4. 벡터 데이터베이스 활용

### STS 음성 유사도 평가 시스템

1. 음성 인식 모델 기반 변환
2. 다차원 평가:
   - 의미적 유사도
   - 음성 매칭 점수
   - 키워드 추출 및 교집합
3. AI 기반 피드백 생성

### 실시간 캐싱 전략

- Redis 캘린더 캐시
- JWT 토큰 관리
- 스케줄러 기반 자동 갱신
