# CLF-C02 실전 모의 문제 세트 01 (Skill Builder 형식)

> - 형식: AWS Skill Builder 공식 연습 문제 세트와 같은 구성 (20문항, 단일 선택 + 복수 선택)
> - 도메인 비중: 클라우드 개념 5 · 보안 6 · 기술 7 · 요금 2 (실제 시험 비율 반영)
> - 🔁 표시: 지금까지 반복해서 틀린 개념을 **다른 상황으로 바꿔** 다시 묻는 문항
> - 목표 시간: **28분** (실제 시험 90분/65문항 기준)
> - 정답은 맨 아래 접힌 영역에 있습니다. 다 풀고 열어 보세요.

---

## 도메인 1. 클라우드 개념

### Q1.
한 회사는 신규 서비스의 트래픽을 예측하기 어려워, 매번 서버를 넉넉하게 구매했다가 상당 부분을 사용하지 못하고 있다. 클라우드로 이전했을 때 이 문제를 해결해 주는 AWS 클라우드의 이점은 무엇인가?

- A. 규모의 경제로 인한 이점
- B. 용량 추정 불필요
- C. 데이터 센터 운영 및 유지 관리 비용 투자
- D. 몇 분 만에 전 세계에 배포

### Q2.
AWS Well-Architected 프레임워크에서 "장애로부터 자동으로 복구하고, 수요를 충족하도록 컴퓨팅 리소스를 동적으로 확보하는 능력"에 초점을 둔 원칙(pillar)은 무엇인가?

- A. 운영 우수성
- B. 보안
- C. 안정성
- D. 비용 최적화

### Q3.
한 개발 팀은 애플리케이션 코드와 데이터만 관리하고, 운영 체제·런타임·미들웨어의 설치와 패치는 클라우드 공급자가 관리하기를 원한다. 이 요구 사항에 가장 적합한 클라우드 컴퓨팅 모델은 무엇인가?

- A. IaaS (Infrastructure as a Service)
- B. PaaS (Platform as a Service)
- C. SaaS (Software as a Service)
- D. 온프레미스

### Q4.
한 회사가 AWS 클라우드 도입 프레임워크(AWS CAF)를 활용하고 있다. 클라우드 워크로드의 상태를 모니터링하고, 장애 대응 절차와 서비스 수준을 정의하는 역할은 어느 관점에 해당하는가?

- A. 거버넌스 (Governance)
- B. 운영 (Operations)
- C. 인력 (People)
- D. 비즈니스 (Business)

### Q5.
한 회사가 온프레미스의 Tomcat 기반 애플리케이션을 **코드나 아키텍처 변경 없이** 그대로 Amazon EC2로 옮기려고 한다. 이 마이그레이션 전략은 무엇인가?

- A. 리팩터링 (Refactor)
- B. 리플랫폼 (Replatform)
- C. 리호스팅 (Rehost)
- D. 폐기 (Retire)

---

## 도메인 2. 보안 및 규정 준수

### Q6. 🔁 (2개 선택)
다음 중 **AWS 계정 루트 사용자**로만 수행할 수 있는 작업은 무엇인가? **(2개를 선택하십시오.)**

- A. AWS 계정 해지
- B. AWS Support 플랜 변경
- C. IAM 사용자 생성
- D. Amazon S3 버킷 삭제
- E. AWS CloudTrail 추적 생성

### Q7.
한 회사가 Amazon RDS for Oracle을 사용한다. AWS 공동 책임 모델에 따르면 **고객**의 책임은 무엇인가?

- A. 데이터베이스 엔진 소프트웨어 패치
- B. 기본 물리 서버 하드웨어 교체
- C. 데이터베이스 사용자 권한 및 보안 그룹 구성
- D. 데이터 센터 출입 통제

### Q8.
보안 팀이 지난주 특정 Amazon S3 버킷의 정책을 **어떤 IAM 사용자가 언제 변경했는지** 확인해야 한다. 어떤 AWS 서비스를 사용해야 하는가?

- A. Amazon CloudWatch
- B. AWS CloudTrail
- C. AWS Trusted Advisor
- D. Amazon Inspector

### Q9.
Amazon EC2 인스턴스에서 실행되는 애플리케이션이 Amazon S3 버킷에 접근해야 한다. 장기 자격 증명을 인스턴스에 저장하지 않는 **가장 안전한** 방법은 무엇인가?

- A. IAM 사용자의 액세스 키를 애플리케이션 설정 파일에 저장한다
- B. 인스턴스에 IAM 역할을 연결한다
- C. 루트 사용자의 자격 증명을 환경 변수에 저장한다
- D. IAM 그룹을 생성하고 인스턴스를 그룹에 추가한다

### Q10.
한 금융 회사의 감사인이 AWS 인프라가 PCI DSS 요구 사항을 준수한다는 **AWS의 규정 준수 보고서**를 요청했다. 이 보고서를 어디에서 받을 수 있는가?

- A. AWS Artifact
- B. AWS Config
- C. AWS Security Hub
- D. Amazon Macie

### Q11.
한 회사가 대규모 DDoS 공격에 대비하려고 한다. 공격 시 **24시간 AWS 대응 팀(SRT)의 지원**과 공격으로 인한 확장 **비용 보호**가 필요하다. 어떤 서비스를 사용해야 하는가?

- A. AWS WAF
- B. AWS Shield Standard
- C. AWS Shield Advanced
- D. Amazon GuardDuty

---

## 도메인 3. 기술 및 서비스

### Q12. 🔁
한 회사의 웹 애플리케이션은 **하나의 가용 영역 전체에 장애가 발생하더라도** 계속 서비스되어야 한다. 가장 적절한 설계는 무엇인가?

- A. 여러 엣지 로케이션에 EC2 인스턴스를 배포한다
- B. 같은 리전의 여러 가용 영역에 EC2 인스턴스를 배포한다
- C. 하나의 가용 영역에 더 큰 인스턴스 유형을 사용한다
- D. 하나의 가용 영역에 EC2 인스턴스 수를 두 배로 늘린다

### Q13. 🔁
운영 팀은 Amazon RDS DB 인스턴스의 **연결 수가 임계값을 넘으면 이메일 알림**을 받고 싶다. 어떤 서비스 조합이 적합한가?

- A. AWS CloudTrail + Amazon SES
- B. Amazon CloudWatch 경보 + Amazon SNS
- C. AWS Config + Amazon SQS
- D. AWS Trusted Advisor + AWS Budgets

### Q14. 🔁
**프라이빗 서브넷**의 EC2 인스턴스가 OS 패치를 인터넷에서 다운로드해야 한다. 단, 인터넷에서 인스턴스로 **들어오는 연결은 허용하지 않아야** 한다. 무엇을 사용해야 하는가?

- A. 프라이빗 서브넷에 인터넷 게이트웨이를 직접 연결
- B. NAT 게이트웨이
- C. AWS Direct Connect
- D. Amazon CloudFront

### Q15.
Amazon S3 버킷에 이미지가 업로드될 때마다 썸네일을 자동으로 생성하려고 한다. **서버를 프로비저닝하거나 관리하지 않고** 코드를 실행하려면 어떤 서비스를 사용해야 하는가?

- A. Amazon EC2
- B. AWS Lambda
- C. AWS Elastic Beanstalk
- D. Amazon Lightsail

### Q16. 🔁 (2개 선택)
한 쇼핑몰이 해외 고객 리뷰를 **한국어로 번역**하고, 리뷰가 긍정인지 부정인지 **감정을 분석**하려고 한다. 어떤 서비스를 사용해야 하는가? **(2개를 선택하십시오.)**

- A. Amazon Comprehend
- B. Amazon Polly
- C. Amazon Translate
- D. Amazon Rekognition
- E. Amazon Transcribe

### Q17.
규정에 따라 거의 조회하지 않는 감사 로그를 **7년간 보관**해야 한다. 데이터를 꺼내는 데 **최대 12시간**이 걸려도 괜찮다. **가장 비용 효율적인** 스토리지는 무엇인가?

- A. Amazon S3 Standard
- B. Amazon S3 Standard-IA
- C. Amazon S3 Glacier Deep Archive
- D. Amazon EBS 범용 SSD

### Q18. 🔁
운영 팀이 매일 밤 **Bash 스크립트**로 EBS 스냅샷을 생성하는 명령을 실행하려고 한다. 어떤 도구가 가장 적합한가?

- A. AWS SDK for Java
- B. AWS CLI
- C. AWS Management Console
- D. AWS Artifact

---

## 도메인 4. 결제·요금·지원

### Q19. 🔁
한 회사는 월말에 **마케팅팀과 개발팀이 각각 사용한 EC2 비용**을 나누어 경영진에게 보고해야 한다. 어떤 기능을 사용해야 하는가?

- A. AWS Pricing Calculator
- B. 비용 할당 태그 (cost allocation tags)
- C. AWS Trusted Advisor
- D. AWS Compute Optimizer

### Q20.
한 회사의 기간계 애플리케이션은 앞으로 **3년간 24시간 일정한 사용량**으로 실행된다. 컴퓨팅 비용을 **가장 많이 절감**하는 구매 옵션은 무엇인가?

- A. 온디맨드 인스턴스
- B. 스팟 인스턴스
- C. 3년 약정 Compute Savings Plans
- D. 전용 호스트 (온디맨드)

---

## 정답 및 해설

<details>
<summary>📌 다 풀었으면 클릭해서 채점하기</summary>

| 번호 | 정답 | 키워드 → 해설 |
|---|---|---|
| Q1 | **B** | "예측 어려움, 남는 서버" → **용량 추정 불필요** |
| Q2 | **C** | "자동 복구, 동적 확보" → **안정성(Reliability)** |
| Q3 | **B** | "코드와 데이터만 관리" → **PaaS** (OS를 직접 관리하면 IaaS) |
| Q4 | **B** | "모니터링, 장애 대응" → CAF **Operations** (기술 관점: Platform·Security·Operations) |
| Q5 | **C** | "변경 없이 그대로" → **Rehost** (Lift & Shift) |
| Q6 🔁 | **A, B** | **계정 자체** 작업 = 루트. S3 삭제, IAM 사용자 생성, CloudTrail 생성은 IAM 권한으로 가능 |
| Q7 | **C** | RDS는 관리형 서비스 → 엔진 패치·하드웨어·데이터센터는 AWS, **권한·보안 그룹·데이터**는 고객 |
| Q8 | **B** | "**누가** 언제 변경" → **CloudTrail** (API 감사) |
| Q9 | **B** | EC2 → 다른 서비스 접근 = **IAM 역할** (임시 자격 증명 자동 교체) |
| Q10 | **A** | "AWS의 규정 준수 **보고서**" → **Artifact** |
| Q11 | **C** | "SRT 24시간 지원 + 비용 보호" → **Shield Advanced** (Standard는 무료 기본 보호) |
| Q12 🔁 | **B** | "AZ 장애에도 유지" → **Multi-AZ**. 엣지 로케이션은 CDN 캐시용이라 EC2 배포 불가 |
| Q13 🔁 | **B** | "임계값 초과 → 알림" → **CloudWatch 경보 + SNS** |
| Q14 🔁 | **B** | "프라이빗, 나가기만, 들어오기 금지" → **NAT 게이트웨이** |
| Q15 | **B** | "업로드 이벤트, 서버 관리 없음" → **Lambda** |
| Q16 🔁 | **A, C** | 번역 = **Translate**, 감정 분석 = **Comprehend** (Polly = 음성 합성, Transcribe = 받아쓰기) |
| Q17 | **C** | "7년, 거의 조회 안 함, 12시간 허용, 최저 비용" → **Glacier Deep Archive** |
| Q18 🔁 | **B** | "**Bash 스크립트**" → **CLI** (애플리케이션 코드 안이면 SDK) |
| Q19 🔁 | **B** | "**팀별로** 이미 쓴 비용 나누기" → **비용 할당 태그** (Pricing Calculator는 사전 견적) |
| Q20 | **C** | "3년, 24시간 일정" → **Savings Plans / RI** (Spot은 중단될 수 있어 기간계에 부적합) |

### 채점 기준
- **16개 이상 (80%)**: 실전 준비 양호
- **14~15개 (70~75%)**: 합격권이지만 아슬아슬 → 틀린 도메인 보강
- **13개 이하**: 키워드 암기 시트(`../keyword-cheatsheet.md`) 다시 보기

### 🔁 반복 오답 개념 재확인
Q6, Q12, Q13, Q14, Q16, Q18, Q19를 모두 맞혔다면 반복 오답을 극복한 것입니다.
하나라도 틀렸다면 결과를 공유해 주세요. 오답 노트와 암기 시트에 반영하겠습니다.

</details>
