# Junhyuk Portfolio

Spring Boot 백엔드 · React 풀스택 개발 포트폴리오입니다. 제조 운영 데이터를 다루는 분석 플랫폼과 대시보드를 설계부터 구현까지 직접 개발한 경험을 정리했습니다.

이 포트폴리오의 저장소들은 실제 운영·배포된 시스템의 아키텍처와 워크플로를 기반으로, 공개용 데모로 재구성한 것입니다.

운영 소스코드, 운영 데이터, 고객 정보, 인증 정보, 인프라 구성, 로그, 인증서, 비공개 환경값, 비공개 Git 히스토리는 포함하지 않습니다.

공개 데모에 사용된 모든 데이터는 합성 또는 익명화된 데이터입니다.

## 미리보기

**ML Studio / Insight View** — AI 운영 개요 대시보드

![ML Studio AI Overview](https://raw.githubusercontent.com/junhyuk-99/ml-studio-insight-view-demo/main/screenshots/ai-overview.png)

**CNC/MCT Analytics Dashboard** — 커맨드 센터 개요

![CNC Command Center](https://raw.githubusercontent.com/junhyuk-99/cnc-mct-analytics-dashboard-demo/main/screenshots/dashboard-command-overview.png)

## 주요 프로젝트

| 프로젝트 | 설명 | 역할 | 저장소 |
| --- | --- | --- | --- |
| ML Studio / Insight View | 이상 탐지, 지도학습 결과 검토, 임계값 알림, AI 운영 모니터링, 제조 데이터 탐색을 제공하는 제조 AI 분석 플랫폼 데모 | 풀스택 / 백엔드 API / AI 연동 | [GitHub](https://github.com/junhyuk-99/ml-studio-insight-view-demo) |
| CNC/MCT Analytics Dashboard | 설비 가동률, 가동시간/절삭시간 분석, 알람 이력, 설비 상태 분포, KPI 모니터링을 제공하는 CNC/MCT 제조 대시보드 데모 | 풀스택 / 백엔드 API / 대시보드 설계 | [GitHub](https://github.com/junhyuk-99/cnc-mct-analytics-dashboard-demo) |

## 프로젝트 비교

| 항목 | ML Studio / Insight View | CNC/MCT Analytics Dashboard |
| --- | --- | --- |
| 핵심 목적 | 제조 AI 분석 플랫폼 | 제조 설비 분석 대시보드 |
| 도메인 | 열처리 / 제조 AI 워크플로 | CNC/MCT 설비 모니터링 |
| 구조 | 모노레포 3-tier (web / api / ai-server) | 2-tier (frontend / backend) |
| Frontend | React + TypeScript | React + TypeScript |
| Backend | Spring Boot (Java 17) | Spring Boot (Java 17) |
| AI Server | FastAPI + scikit-learn | 없음 |
| Database | MongoDB | MongoDB |
| 시각화 | 차트 기반 대시보드 | Recharts 기반 대시보드 |
| 핵심 기능 | 이상 탐지, 지도학습 결과, 임계값 알림, AI 운영 상태, 데이터 탐색 | 설비 가동률, 가동시간/절삭시간 비율, 알람 이력, 상태 분포, 추세 차트 |
| 데모 데이터 | 합성 / 익명화 데이터 | 합성 샘플 데이터 |

## 프로젝트 요약

### ML Studio / Insight View

운영 중인 제조 AI 분석 플랫폼을 공개용으로 재구성한 데모입니다. 모노레포 3-tier 구조(React 웹 / Spring Boot API / FastAPI AI 서버)로, 제조 운영 데이터 분석부터 AI 모델 실행, 이상 탐지 결과 모니터링, 지도학습 결과 검토, 임계값 알림까지 제조 AI 분석 워크플로 전체를 설계·구현했습니다.

주요 구현 영역:

- 원천 데이터 탐색 → 전처리 → 피처 엔지니어링 → 알고리즘 선택 → 모델 실행 → 결과 검토로 이어지는 분석 파이프라인
- Isolation Forest / AutoEncoder 기반 비지도 이상 탐지
- 지도학습 결과 및 평가 지표 시각화
- 임계값 기반 알림 모니터링
- FastAPI AI 서버와 Spring Boot API 연동 (polyglot 구조)
- MongoDB 스키마 설계 및 합성 시드 데이터

저장소: [ml-studio-insight-view-demo](https://github.com/junhyuk-99/ml-studio-insight-view-demo)

### CNC/MCT Analytics Dashboard

운영 중인 CNC/MCT 설비 대시보드를 공개용으로 재구성한 데모입니다. 설비 가동률, 가동시간 대비 절삭시간 비율, 알람 이력, 설비 상태 분포, 일별 추세, KPI 시각화를 설계·구현했습니다.

주요 구현 영역:

- 설비 가동률 분석
- 가동시간(RunTime) 대비 절삭시간(CutTime) 비율 계산
- 알람 이력 분석 및 설비 상태 분포 시각화
- 일별 추세 및 KPI 카드
- 요약 데이터(daily summary) 설계를 통한 대시보드 조회 성능 최적화

저장소: [cnc-mct-analytics-dashboard-demo](https://github.com/junhyuk-99/cnc-mct-analytics-dashboard-demo)

## 담당 역할

두 데모 프로젝트 모두 실제 운영 시스템 개발 경험을 바탕으로, 설계부터 구현까지 직접 진행했습니다.

- Frontend 대시보드 설계 및 구현
- Backend REST API 설계 및 구현
- MongoDB 스키마 및 집계(aggregation) 설계
- 제조 설비 데이터 모델링
- AI 분석 워크플로 설계
- FastAPI AI 서버 연동
- 대시보드 KPI 및 차트 구현
- 합성 / 익명화 데모 데이터 준비
- 보안을 고려한 문서화 및 정보 공개 범위 통제

## 핵심 기술 스택

`React 18` · `TypeScript` · `Spring Boot 3` · `Java 17` · `FastAPI` · `Python` · `scikit-learn` · `MongoDB` · `SQL Server` · `Docker`

## AI 활용 / 개발 워크플로

AI 도구를 단순 보조가 아니라 개발 워크플로와 시스템 설계에 통합해 사용합니다. 일상적으로 활용 중인 도구와, 제조 AI 시스템 적용을 위해 검증 중인 기술을 구분해 정리합니다.

**활용 중** — 실제 개발 과정에 사용

| 도구 | 활용 방식 |
| --- | --- |
| Claude Code · Codex CLI | 두 에이전트를 병렬로 사용하는 코딩 워크플로. 설계·구현·리뷰 단계 분담 |
| NotebookLM | 기술 문서·레퍼런스 정리 및 학습 자료 구조화 |

**검증 중** — 제조 AI 프로젝트 적용 전 연구·테스트 단계

| 기술 | 검증 목적 |
| --- | --- |
| Hermes Agent | 실시간 이상 탐지 이후의 진단·스킬 자동화 계층(Tier 2) 적용 가능성 검증 |
| OpenClaw | 에이전트 프레임워크의 제조 환경 통합 가능성 테스트 |

제조 이상 탐지에는 **2-Tier 아키텍처**(결정론적 실시간 Tier 1 + 에이전트 기반 진단 Tier 2)를 선호하는 방향으로 검토 중입니다. LLM 에이전트를 실시간 핫패스(hot path)에 두지 않고, 탐지 이후 진단·자동화 계층에 배치하는 구조입니다.

## 보여주는 역량

- 제조 AI 시스템 설계
- 산업용 대시보드 아키텍처
- 풀스택 웹 애플리케이션 개발
- React 대시보드 UI 개발
- Spring Boot REST API 개발
- FastAPI AI 서비스 연동
- MongoDB 스키마 설계 및 집계
- 이상 탐지 및 지도학습 워크플로 설계
- 요약 데이터 설계를 통한 대시보드 성능 최적화
- 합성 / 익명화 데이터 기반 공개 데모 재구성
- 보안을 고려한 문서화 및 정보 공개 통제

## 공개 데모 정책

이 저장소들은 운영 소스코드를 그대로 복사한 것이 아닙니다. 실제 프로젝트의 아키텍처, 워크플로, 엔지니어링 경험을 기반으로 공개용으로 재구성한 데모입니다.

다음 항목은 의도적으로 제외했습니다:

- 운영 소스코드 / 운영 DB 연결 / 비공개 Git 히스토리
- 고객 데이터 / 실제 설비 이력
- 서버 IP / 인증 정보 / 인증서 / 로그
- 비공개 환경값 / 내부 배포 스크립트

## 바로가기

| 프로젝트 | README | 문서 | 스크린샷 / 케이스 스터디 |
| --- | --- | --- | --- |
| ML Studio / Insight View | [README](https://github.com/junhyuk-99/ml-studio-insight-view-demo) | [docs](https://github.com/junhyuk-99/ml-studio-insight-view-demo/tree/main/docs) | [screenshots](https://github.com/junhyuk-99/ml-studio-insight-view-demo/tree/main/screenshots) |
| CNC/MCT Analytics Dashboard | [README](https://github.com/junhyuk-99/cnc-mct-analytics-dashboard-demo) | [docs](https://github.com/junhyuk-99/cnc-mct-analytics-dashboard-demo/tree/main/docs) | [case study](https://github.com/junhyuk-99/cnc-mct-analytics-dashboard-demo/blob/main/docs/CASE_STUDY_CNC_MCT_DASHBOARD.md) |

## 비고

이 프로젝트들은 포트폴리오 검토 및 로컬 실행을 목적으로 설계되었습니다. 보안 및 기밀 유지를 위해 운영 환경의 인증 정책, 인프라 구성, 고객별 비즈니스 로직, 운영 데이터, 비공개 배포 정보는 공개 저장소에 포함하지 않았습니다.
