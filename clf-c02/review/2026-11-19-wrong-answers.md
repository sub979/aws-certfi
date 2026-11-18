# CLF-C02 오답 노트 — 2026-11-19 (오늘의 문제)

## 결과 요약

| 도메인 | 점수 | 정답률 | 우선순위 |
|---|---|---|---|
| 1. 클라우드 개념 | 0/2 | 0% | 🔴 최우선 |
| 2. 보안 및 규정 준수 | 5/7 | 71% | 🟢 |
| 3. 기술 및 서비스 | 3/7 | 43% | 🔴 |
| 4. 결제·요금·지원 | 2/4 | 50% | 🟡 |
| **합계** | **10/20** | **50%** | 합격선 약 70% |

---

## 도메인 1. 클라우드 개념

### d1-009 | 서비스 모델 (IaaS vs PaaS)
- **정답:** IaaS / **내 답:** PaaS
- **핵심:** "OS 설치·패치, 미들웨어 구성을 **직접**" → IaaS
- **구분법 (내가 관리하는 범위):**

| 모델 | 고객 관리 | AWS 예시 |
|---|---|---|
| IaaS | OS, 미들웨어(Tomcat/WebLogic), 런타임, 앱, 데이터 | EC2, VPC, EBS |
| PaaS | 앱, 데이터 | Elastic Beanstalk, RDS |
| SaaS | 사용만 | Amazon WorkMail, Chime |

> 💡 EC2에 WebLogic 직접 설치·패치 = IaaS. 문제에 "OS 패치"가 고객 책임으로 나오면 무조건 IaaS.

### d1-021 | AWS CAF 관점
- **정답:** 플랫폼 / 운영 / **내 답:** 거버넌스 / 인력
- **6개 관점 = 비즈니스 3 + 기술 3**

| 구분 | 관점 | 키워드 |
|---|---|---|
| 비즈니스 역량 | Business | 비즈니스 결과, ROI |
| | People | 조직 문화, 교육, 인재 |
| | Governance | 리스크, 비용 관리, 프로그램 관리 |
| **기술 역량** | **Platform** | 아키텍처, 클라우드 플랫폼 구축 |
| | **Security** | IAM, 위협 탐지, 데이터 보호 |
| | **Operations** | 모니터링, 장애 대응, 운영 수준 |

> 💡 암기: **"BPG / PSO"** — 기술 쪽은 **P**latform·**S**ecurity·**O**perations.

---

## 도메인 2. 보안 및 규정 준수

### d2-013 | 루트 사용자 전용 작업
- **정답:** AWS 계정 해지 / **내 답:** IAM 사용자 생성
- **IAM 사용자 생성은 IAM 권한(`iam:CreateUser`)만 있으면 가능** → 루트 전용 아님
- **루트 전용 작업 (빈출):**
  1. 계정 해지(Close account)
  2. 계정 설정 변경(이메일, 루트 비밀번호, 계정 이름)
  3. AWS Support 플랜 변경
  4. 결제 정보(IAM 접근 활성화 전) 관련 일부
  5. 루트 MFA 설정/복구, Reserved Instance 마켓플레이스 판매자 등록 등

### d2-014 | AWS Organizations 이점 (복수 정답)
- **정답:** 통합 결제 + SCP / **내 답:** SCP + EC2 OS 자동 패치
- **오답 원인:** Organizations는 **계정 관리·거버넌스** 서비스. 게스트 OS 패치는 공동 책임 모델상 **고객 책임** → Systems Manager Patch Manager 영역
- **Organizations 핵심:** 통합 결제(볼륨 할인 공유), SCP(최대 권한 상한), OU 계층 구조, 계정 생성 자동화

---

## 도메인 3. 기술 및 서비스

### d3-013 | 코드만 올리면 자동 배포·확장
- **정답:** Elastic Beanstalk / **내 답:** Amazon ECR
- **Elastic Beanstalk:** 코드(war/jar/zip) 업로드 → 프로비저닝·ELB·Auto Scaling·헬스 모니터링 자동 (PaaS, Tomcat 플랫폼 기본 제공)
- **ECR:** 컨테이너 **이미지 저장소**(Docker Registry)일 뿐, 배포·확장 기능 없음

### d3-025 | 서버리스 키-값 NoSQL, 한 자릿수 ms
- **정답:** DynamoDB / **내 답:** RDS
- **키워드 매핑:**

| 키워드 | 서비스 |
|---|---|
| 키-값 / NoSQL / 서버리스 / 한 자릿수 ms | **DynamoDB** |
| 마이크로초 응답 (DynamoDB 캐시) | DAX |
| 관계형 / SQL / Oracle·MSSQL·MySQL | RDS, Aurora |
| 인메모리 캐시 | ElastiCache |

### d3-030 | 퍼블릭 서브넷 인바운드 인터넷
- **정답:** 인터넷 게이트웨이 / **내 답:** NAT 게이트웨이
- **구분:**

| 구성요소 | 방향 | 위치/용도 |
|---|---|---|
| **Internet Gateway (IGW)** | **양방향** (인바운드 O) | VPC에 연결, 퍼블릭 서브넷 |
| NAT Gateway | **아웃바운드 전용** | 프라이빗 서브넷 → 인터넷 (패치 다운로드 등) |

> 💡 "인터넷에서 **들어오는** 요청" = IGW. NAT는 외부에서 먼저 연결 불가.

### d3-037 | 음성 ↔ 텍스트
- **정답:** Transcribe / Polly / **내 답:** Transcribe / Translate
- **AI 서비스 정리:**

| 서비스 | 기능 | 암기 |
|---|---|---|
| Transcribe | 음성 → 텍스트 (STT) | 받아**쓰기** |
| **Polly** | 텍스트 → 음성 (TTS) | 앵무새(Polly)가 말함 |
| Translate | 언어 번역 | 번역 |
| Comprehend | 텍스트 감정·개체 분석 (NLP) | 이해 |
| Lex | 챗봇 (대화형) | Alexa 엔진 |
| Rekognition | 이미지·영상 분석 | 인식 |
| Textract | 문서에서 텍스트/표 추출 (OCR) | 추출 |

---

## 도메인 4. 결제·요금·지원

### d4-012 | 부서·프로젝트별 비용 추적
- **정답:** 비용 할당 태그 / **내 답:** Pricing Calculator
- **Pricing Calculator:** 배포 **전** 비용 **예상** (실제 사용량 추적 X)
- **비용 할당 태그:** 리소스에 `Department`, `Project` 태그 → Billing에서 활성화 → Cost Explorer/CUR에서 부서별 분리
- **비용 도구 정리:**

| 도구 | 용도 |
|---|---|
| Pricing Calculator | 사전 견적 |
| Cost Explorer | 과거/현재 비용 시각화·예측 |
| AWS Budgets | 예산 임계값 알림 |
| Cost Allocation Tags | 부서·프로젝트별 비용 분류 |
| Cost and Usage Report (CUR) | 가장 상세한 원시 데이터 |

### d4-015 | 가장 빠른 응답 + TAM
- **정답:** Enterprise Support / **내 답:** Business
- **결정 키워드:** "미션 크리티컬", "가장 빠른 응답(15분)", "TAM(기술 계정 관리자)", "Concierge" → **Enterprise**

| 플랜 | 비즈니스 크리티컬 장애 응답 | TAM |
|---|---|---|
| Business | 프로덕션 다운 1시간 | ❌ |
| Enterprise On-Ramp | 비즈니스 크리티컬 30분 | 풀(pool) TAM |
| **Enterprise** | **비즈니스 크리티컬 15분** | **전담 TAM** |

> ⚠️ 지원 플랜 명칭/구성은 개편될 수 있으므로 시험 직전 공식 문서로 최신 여부 확인.

---

## 다음 학습 계획 (Step-by-Step)

1. **도메인 1 (0%)** — 서비스 모델(IaaS/PaaS/SaaS), CAF 6관점, 클라우드 6가지 이점 집중 복습
2. **도메인 3** — "키워드 → 서비스" 매핑 표(DB, 네트워크, AI) 매일 1회 백지 복습
3. **도메인 4** — 비용 도구 5종 + 지원 플랜 3단계 표 암기
4. **도메인 2** — 공동 책임 모델(OS 패치 = 고객)과 루트 전용 작업 목록 재확인
5. 3일 뒤 이번 오답 10문항 재풀이 → 전부 맞히면 체크

- [ ] d1-009 · [ ] d1-021 · [ ] d2-013 · [ ] d2-014 · [ ] d3-013
- [ ] d3-025 · [ ] d3-030 · [ ] d3-037 · [ ] d4-012 · [ ] d4-015
