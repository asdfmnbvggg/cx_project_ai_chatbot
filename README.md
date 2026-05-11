# L-Pick: 초개인화 AI 이커머스 셀러

> 탐색의 피로는 줄이고, 구매의 확신은 높이는 가전 구매 상담형 AI 셀러 서비스

## 프로젝트 소개

**L-Pick**은 가전 구매 전 단계에서 고객이 겪는 정보 탐색 피로를 줄이기 위해 기획한 AI 기반 이커머스 상담 서비스입니다.

고객은 가전 구매 시 제품 스펙, 가격, 리뷰, 혜택, 오프라인 매장 정보 등을 직접 비교해야 합니다.  
L-Pick은 이러한 탐색 부담을 줄이기 위해 고객의 구매 성향과 상황을 분석하고, 맞춤형 제품 패키지와 구매 경로를 추천합니다.

## 기획 배경

LG전자는 AI 상담 기술과 D2C 채널을 강화할 수 있는 역량을 보유하고 있습니다.  
하지만 기존 자사몰의 AI 챗봇은 단순 문의 응대 중심에 머물러 있어, 구매 전 단계에서 고객의 구매 확신을 높이는 데에는 한계가 있다고 판단했습니다.

따라서 본 프로젝트는 **AI 챗봇 고도화를 통한 D2C 채널 강화**를 목표로 진행했습니다.

## 핵심 문제

- 고객은 가전 구매 전 과도한 정보 탐색 피로를 경험함
- 온라인과 오프라인 구매 경험이 분리되어 있음
- 기존 챗봇은 단순 응대 중심으로 구매 전환까지 연결되기 어려움
- 고객의 실제 구매 맥락을 반영한 개인화 추천이 필요함

## 주요 기능

### 1. 사용자 구매 성향 파악

고객에게 간단한 질문을 제시하여 구매 기준과 라이프스타일을 파악합니다.

예시 질문:

- 가전 구매 시 어떤 기준을 중요하게 생각하시나요?
- 어떤 가전 제품이 필요하신가요?
- 예산은 어느 정도인가요?
- 가격, 성능, 디자인 중 무엇을 우선하시나요?

### 2. 맞춤형 AI 셀러

AI 상담사인 **지셀 상담사**가 고객의 구매 맥락에 맞춰 상담을 제공합니다.  
단순 제품 나열이 아니라, 고객의 조건을 바탕으로 필요한 정보를 정리하고 다음 선택을 유도합니다.

### 3. AI 추천 패키지 제공

고객의 라이프스타일, 예산, 제품 선호도를 기반으로 맞춤형 가전 패키지를 추천합니다.

예시:

- 신혼부부 맞춤 가전 패키지
- 다품목 구매 추천 패키지
- 가격 효율 중심 패키지
- 라이프스타일 기반 제품 조합

### 4. 최적 구매 경로 안내

온라인 구매, 오프라인 매장 방문, 카드 혜택, 프로모션 등을 비교하여 고객에게 가장 합리적인 구매 방법을 안내합니다.

## 데이터 분석 과정

본 프로젝트에서는 고객의 가전 구매 전 탐색 행동을 파악하기 위해 온라인 데이터를 수집하고 분석했습니다.

### 데이터 수집

- 총 약 27만 건의 데이터 수집
- 오프라인 구매, 온라인 구매, 일반 구매 데이터를 각각 1만 건씩 균형화
- 최종 분석 데이터 약 3만 건 사용

### 데이터 전처리

- 결측치 제거
- 중복 데이터 제거
- 특수문자 제거
- 광고성 데이터 제거
- 불용어 제거
- 정규화
- Stemming 처리

### 임베딩 모델 비교

다음 임베딩 모델을 비교했습니다.

- Doc2Vec
- Ko-SBERT
- KURE
- E5
- BGE
- GTE

Dendrogram, UMAP, PCA, t-SNE, HDBSCAN 기반 시각화와 실루엣 지수를 비교한 결과, **E5 모델**을 최종 임베딩 모델로 선정했습니다.

### 클러스터링

- UMAP을 활용한 차원 축소
- HDBSCAN을 활용한 밀도 기반 클러스터링
- c-TF-IDF를 활용한 클러스터별 주요 키워드 추출
- Actor / Action 기반 고객 유형 정의

## Actor / Action 분석

클러스터링 결과를 바탕으로 고객 유형을 **Actor**, 고객의 행동 및 니즈를 **Action**으로 정의

## 서비스 흐름

1. 메인 페이지 진입
2. 구매 기준 관련 질문 응답
3. AI 셀러 로딩
4. 필요한 가전 카테고리 선택
5. 예산 입력
6. AI 추천 패키지 확인
7. 추천 제품 확인
8. 최적 구매 경로 안내

## 프로토타입 (데모 페이지)
<img width="1918" height="882" alt="image" src="https://github.com/user-attachments/assets/d8f0809d-b141-465a-82ec-2e097465fd45" />

https://cx-project-ai-chatbot.vercel.app/

## 기술 스택

### Frontend

- React
- Vite
- TypeScript
- Tailwind CSS
- Framer Motion
- Lucide React
- MUI
- Radix UI

### Data Analysis

- Python
- Pandas
- NumPy
- Scikit-learn
- UMAP
- HDBSCAN
- c-TF-IDF

### NLP / Embedding

- E5 Embedding
- Doc2Vec
- Ko-SBERT
- BGE
- GTE
- KURE
- Hugging Face Transformers

## 폴더 구조

```bash
cx_project_ai_chatbot-main/
├── README.md
├── Cx_project-압축됨.pdf
├── Action_cluster/
│   ├── cluster0.csv
│   ├── cluster1.csv
│   ├── cluster2.csv
│   ├── cluster3.csv
│   ├── cluster4.csv
│   ├── cluster5.csv
│   └── ldavis_cluster*.html
├── ai_chatbot_ui_ux/
│   ├── package.json
│   ├── vite.config.ts
│   ├── index.html
│   └── src/
│       ├── main.tsx
│       ├── app/
│       │   ├── App.tsx
│       │   ├── routes.tsx
│       │   ├── components/
│       │   └── pages/
│       ├── assets/
│       └── styles/
├── hugging_face_구현코드/
│   ├── Doc2Vec_Embedding.ipynb
│   ├── E5_Embedding.ipynb
│   ├── GTE_Embedding.ipynb
│   ├── Ko_SBERT_Embedding.ipynb
│   ├── Kure_Embedding.ipynb
│   └── 스팸탐지.ipynb
└── 크롤링 코드/
    ├── 네이버지식인 크롤링 코드.ipynb
    ├── 네이버카페크롤링.ipynb
    ├── 빅카인즈_크롤링.ipynb
    ├── 유튜브 링크 수집 코드.ipynb
    └── 유튜브댓글크롤링.ipynb
```

---

````md
## 실행 방법

본 프로젝트의 프론트엔드 코드는 `ai_chatbot_ui_ux` 폴더 안에 있습니다.

### 1. 저장소 클론

```bash
git clone https://github.com/사용자명/저장소명.git
````

```bash
cd 저장소명
```

### 2. 프론트엔드 폴더로 이동

```bash
cd ai_chatbot_ui_ux
```

### 3. 패키지 설치

```bash
npm install
```

### 4. 개발 서버 실행

```bash
npm run dev
```

실행 후 브라우저에서 아래 주소로 접속합니다.

```bash
http://localhost:5173
```

### 5. 배포용 빌드

```bash
npm run build
```

빌드가 완료되면 `dist` 폴더가 생성됩니다.

### 6. 빌드 결과 미리보기

```bash
npm run preview
```

---

## 배포 설정

본 프로젝트는 Vercel을 통해 배포할 수 있습니다.

Vercel 배포 시 설정값은 다음과 같습니다.

```bash
Root Directory: ai_chatbot_ui_ux
Framework Preset: Vite
Build Command: npm run build
Output Directory: dist
```

프론트엔드 코드가 `ai_chatbot_ui_ux` 폴더 안에 있으므로, Vercel에서 **Root Directory를 `ai_chatbot_ui_ux`로 설정**해야 합니다.

---

## GitHub 반영 명령어

README 수정 후 GitHub에 반영하려면 아래 명령어를 실행합니다.

```bash
git add README.md
```

```bash
git commit -m "docs: add run and deployment instructions"
```

```bash
git push origin main
```

전체 파일을 한 번에 반영하려면 아래 명령어를 사용할 수 있습니다.

```bash
git add .
```

```bash
git commit -m "docs: update README"
```

```bash
git push origin main
```

```
```

