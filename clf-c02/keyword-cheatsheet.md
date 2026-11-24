# CLF-C02 키워드 암기 시트

> 사용법: 문제에서 **키워드**를 찾으면 → 바로 **정답** 선택.
> 🔁 = 반복 오답, ⚠️ = 오답 이력 있음, ❌ = 내가 골랐던 함정 보기

---

## 🔁 반복 오답 TOP (시험 직전 이것만 다시 보기)

| 문제 키워드 | ✅ 정답 | ❌ 내가 고른 함정 | 한 줄 규칙 |
|---|---|---|---|
| **루트 사용자만** 가능한 작업 | **계정 해지**, Support 플랜 변경, 루트 이메일 변경 | IAM 사용자 생성, EC2 종료 | **계정 자체 = 루트 / 리소스 = IAM** |
| **부서별·프로젝트별** 비용 | **비용 할당 태그** | Pricing Calculator ×2 | **이미 쓴 돈 나누기 = 태그** |
| **여러 계정** + 결제 통합·중앙 거버넌스 | **Organizations** (모든 기능 모드) | OS 자동 패치, Cost and Usage Report | **계정 여러 개 + 결제/중앙 = Organizations** |

---

## 1. 클라우드 개념

| 키워드 | 정답 |
|---|---|
| OS 설치·패치, 미들웨어 **직접** 관리 ⚠️ | **IaaS** (EC2) |
| 코드만 관리, 플랫폼은 AWS | **PaaS** (Elastic Beanstalk) |
| 완성된 소프트웨어 사용만 | **SaaS** |
| CAF **기술** 관점 ⚠️ | **Platform · Security · Operations** |
| CAF **비즈니스** 관점 | Business · People · Governance |
| 초기 투자(CapEx) → 사용량 과금(OpEx) | 클라우드 이점: **가변 비용** |
| 수요 예측 불필요, 필요할 때 늘리고 줄임 | **탄력성(Elasticity)** |
| 몇 분 만에 전 세계 배포 | **글로벌 확장** |

> 🧠 CAF: **"BPG / PSO"**

---

## 2. 보안 및 규정 준수

| 키워드 | 정답 |
|---|---|
| **게스트 OS 패치**, SG 설정, 데이터 암호화 ⚠️ | **고객 책임** |
| 물리 보안, 하이퍼바이저, 데이터센터 | **AWS 책임** |
| 여러 계정 **통합 결제** + 권한 상한 🔁 | **Organizations** (+ **SCP**) |
| 보안 그룹 **무제한 접근(0.0.0.0/0) 점검** ⚠️ | **Trusted Advisor** (❌ IAM) |
| 규정 준수 **보고서**(SOC, PCI, ISO) 다운로드 ⚠️ | **AWS Artifact** |
| **누가** API 호출했나 (감사) ⚠️ | **CloudTrail** |
| 리소스 **설정 변경** 이력·규칙 준수 | **AWS Config** |
| DDoS 방어 | **Shield** (Standard 무료 / Advanced 유료) |
| SQL 인젝션, XSS 차단 | **WAF** |
| 위협 탐지 (악성 IP, 이상 행동) | **GuardDuty** |
| EC2 취약점 스캔 | **Inspector** |
| S3 개인정보(PII) 탐지 | **Macie** |
| 암호화 키 관리 | **KMS** (전용 HSM = CloudHSM) |
| DB 비밀번호 자동 교체 | **Secrets Manager** |
| **전송 중 암호화**, SSL/TLS 인증서 ⚠️ | **ACM** (❌ Shield) |
| **저장 시 암호화** | **KMS** |
| 보안 결과 한곳에 모아 보기 | **Security Hub** |

> 🧠 감사 3종: **Trail = 누가 / Config = 어떻게 바뀌었나 / CloudWatch = 얼마나**

---

## 3. 기술 및 서비스

### 3-1. 컴퓨팅·배포

| 키워드 | 정답 |
|---|---|
| **코드만 업로드** → 자동 프로비저닝·확장 ⚠️ | **Elastic Beanstalk** |
| 서버 없이 이벤트로 코드 실행 | **Lambda** |
| 컨테이너 **이미지 저장소** | **ECR** (배포 기능 ❌) |
| 컨테이너 실행 (서버 관리 X) | **Fargate** |
| Kubernetes 관리형 | **EKS** |
| 간단한 VPS (고정 요금) | **Lightsail** |
| 코드에서 AWS API 호출 ⚠️ | **SDK** (Python = boto3) |
| 템플릿으로 인프라 생성 (IaC) | **CloudFormation** |

### 3-2. 데이터베이스

| 키워드 | 정답 |
|---|---|
| **키-값, NoSQL, 서버리스, 한 자릿수 ms** ⚠️ | **DynamoDB** |
| 마이크로초 (DynamoDB 캐시) | **DAX** |
| 관계형, Oracle / MSSQL / MySQL | **RDS** |
| MySQL·PostgreSQL 호환 + 고성능 | **Aurora** |
| 인메모리 캐시 (Redis) | **ElastiCache** |
| 데이터 웨어하우스, 분석 | **Redshift** |
| 온프레미스 DB → AWS 이전 | **DMS** |

### 3-3. 네트워크

| 키워드 | 정답 |
|---|---|
| 인터넷에서 **들어오는** 요청 ⚠️ | **인터넷 게이트웨이(IGW)** |
| 프라이빗 서브넷 → 인터넷 **나가기만** | **NAT 게이트웨이** |
| 인스턴스 방화벽, **상태 저장** | **보안 그룹** |
| 서브넷 방화벽, **상태 비저장**, Deny 가능 | **NACL** |
| 온프레미스 ↔ AWS **전용선** | **Direct Connect** |
| 온프레미스 ↔ AWS 인터넷 암호화 | **Site-to-Site VPN** |
| DNS | **Route 53** |
| CDN, 엣지 캐시 | **CloudFront** |

### 3-4. 글로벌 인프라

| 키워드 | 정답 |
|---|---|
| **가용 영역(AZ)** 정의 ⚠️ | **1개 이상 데이터센터**, 같은 리전 내 다른 AZ와 **물리적 분리** |
| 포함 관계 | **리전 ⊃ AZ ⊃ 데이터센터** |
| 고가용성 | **Multi-AZ** |
| 재해 복구, 지역 장애 | **Multi-Region** |
| CloudFront 캐시 위치 | **엣지 로케이션** |

### 3-5. 모니터링·운영

| 키워드 | 정답 |
|---|---|
| **CPU 80% 초과 → 알림** ⚠️ | **CloudWatch** (알람 + SNS) |
| 비용·성능·보안 **권장 사항** | **Trusted Advisor** |
| EC2 패치·명령 실행 일괄 | **Systems Manager** |
| AWS 서비스 장애 공지 (내 계정 영향) | **Health Dashboard** |

### 3-5-1. 메시징·통합

| 키워드 | 정답 |
|---|---|
| 팀 전체에 **경고/알림 발송** (이메일·SMS) ⚠️ | **SNS** (❌ EventBridge) |
| 메시지 **대기열**, 시스템 분리 | **SQS** |
| 이벤트를 **규칙으로 라우팅** | **EventBridge** |
| 클라우드 **콜센터** | **Amazon Connect** |

### 3-6. 스토리지

| 키워드 | 정답 |
|---|---|
| 객체 스토리지, 정적 웹 호스팅 | **S3** |
| 장기 보관, 저렴 | **S3 Glacier** |
| 접근 패턴 모를 때 자동 계층 이동 | **S3 Intelligent-Tiering** |
| EC2용 블록 디스크 | **EBS** |
| 여러 EC2 공유 파일 시스템 (Linux) | **EFS** |
| 대용량 오프라인 데이터 이전 | **Snowball** |

### 3-7. AI 서비스

| 키워드 | 정답 |
|---|---|
| 음성 → 텍스트 ⚠️ | **Transcribe** |
| 텍스트 → **음성** ⚠️ | **Polly** (❌ Translate) |
| 언어 번역 | **Translate** |
| 감정 분석, NLP | **Comprehend** |
| 챗봇 | **Lex** |
| 이미지·얼굴 인식 | **Rekognition** |
| 문서 OCR | **Textract** |
| ML 모델 구축·학습 | **SageMaker** |
| 생성형 AI 파운데이션 모델 | **Bedrock** |

> 🧠 **Polly = 앵무새 = 말한다**, **Transcribe = 받아쓴다**

---

## 4. 결제·요금·지원

| 키워드 | 정답 |
|---|---|
| 배포 **전** 견적 | **Pricing Calculator** |
| **부서별·프로젝트별** 비용 🔁 | **비용 할당 태그** |
| 과거 비용 시각화·예측 | **Cost Explorer** |
| 예산 초과 **알림** | **AWS Budgets** |
| 가장 상세한 비용 원시 데이터 | **Cost and Usage Report (CUR)** |
| 1년/3년 약정, 최대 72% 할인 | **Reserved Instance / Savings Plans** |
| 중단 가능, 최대 90% 할인 | **Spot 인스턴스** |
| 라이선스 규정(BYOL), 물리 서버 전용 | **Dedicated Host** |
| **가장 빠른 응답(15분) + 전담 TAM** ⚠️ | **Enterprise Support** |
| 프로덕션 장애 1시간 응답, TAM 없음 | **Business Support** |

> 🧠 비용 도구 시제: **전 = Calculator / 중 = Explorer·Budgets / 나누기 = 태그**
> ⚠️ 지원 플랜 구성·응답 시간은 개편될 수 있으니 시험 전 공식 문서로 확인

---

## 함정 보기 모음 (이름에 속지 말 것)

| 헷갈리는 쌍 | 구분 |
|---|---|
| CloudWatch vs **CloudTrail** | 얼마나(성능) vs 누가(감사) |
| IGW vs **NAT** | 양방향 vs 나가기만 |
| Beanstalk vs **ECR** | 배포·확장 vs 이미지 저장 |
| Polly vs **Translate** | 음성 합성 vs 번역 |
| DynamoDB vs **RDS** | NoSQL 키-값 vs 관계형 |
| 비용 태그 vs **Pricing Calculator** | 실제 비용 분류 vs 사전 견적 |
| Artifact vs **CodeArtifact** | 규정 준수 보고서 vs 패키지 저장소 |
| SDK vs **CLI** | 코드 안 vs 터미널 |
| 보안 그룹 vs **NACL** | 인스턴스·상태 저장 vs 서브넷·상태 비저장 |
| Trusted Advisor vs **IAM** | 설정 점검·권장 vs 권한 관리 |
| ACM vs **Shield** | 전송 중 암호화(TLS) vs DDoS 방어 |
| SNS vs **EventBridge** | 알림 발송 vs 이벤트 라우팅 |
| Organizations vs **CUR** | 결제 통합·거버넌스 vs 비용 보고서 |
