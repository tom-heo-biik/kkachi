---
name: kkachi-tech
description: AI 일정 비서 '까치'의 기술 결정 스킬입니다. 확정 스택(Expo·Supabase·Claude API), 데이터 방침(자체 DB + 구글 캘린더 양방향 동기화), 아키텍처 초안 상태를 담고 있습니다. 까치의 개발·설계·인프라 작업 맥락에서 반드시 읽고 사용합니다.
---

## Tech


### 확정된 스택 (2026-07-24 결정)
- 앱: Expo(React Native, TypeScript). EAS Build로 양대 스토어 빌드·제출. UI는 kkachi-design 스킬의 토큰·컴포넌트 스펙을 따릅니다.
- 백엔드: Supabase — Postgres, Auth(애플·구글 로그인), Edge Functions.
- AI: Claude API. 호출은 서버(Edge Function)에서만 합니다. API 키를 앱에 절대 내리지 않습니다.
- 알림: Expo Push(APNs/FCM).

선정 이유: 1인 개발로 연내 양대 스토어 출시가 목표이므로, TypeScript 단일 언어와 관리형 백엔드로 개발·운영 부담을 최소화합니다. Flutter+Firebase안, 자체 백엔드안과 비교 후 결정했습니다.


### 데이터 방침
- 자체 DB(Supabase Postgres)가 기본 저장소이고, 구글 캘린더와 양방향 동기화합니다.
- 사용자의 현재 습관이 구글 캘린더 중심이므로, 동기화 품질이 곧 제품 신뢰입니다.


### AI 에이전트 방향
- Claude tool use로 일정 CRUD 도구(등록·조회·검색·수정·삭제, 리마인더 생성·완료)를 제공합니다.
- 시스템 프롬프트에 까치 브랜드 보이스(kkachi-brand)와 현재 시각·타임존·오늘 일정 컨텍스트를 주입합니다.
- "말하면 바로 실행" 원칙에 따라 도구 실행에 확인 절차를 두지 않되, 되돌리기 경로를 함께 설계합니다.


### 아키텍처 초안 (미승인 — 참고용)
아래는 2026-07-24 설계 대화에서 제시된 초안입니다. 아직 승인되지 않았으므로 구현 전 재검토가 필요합니다.

- 데이터 모델: profiles(타임존·브리핑 시각·설정), events(일정, google_event_id·etag 포함), reminders, conversations·messages(대화 이력), google_accounts(암호화 토큰·sync token), briefings(발송 기록)
- Edge Functions: chat(대화 + tool use), calendar-sync(양방향 동기화), briefing(브리핑 생성·발송)
- 스케줄: pg_cron으로 브리핑 시각·리마인더 발송·동기화 폴링 처리
- 동기화: sync token 기반 증분 동기화, etag 충돌은 최신 수정 우선(last-write-wins)으로 단순화

재검토 메모 (2026-07-24): 제품 결정 '브리핑 = 홈의 아침 상태'에 따라 briefing Edge Function과 briefings 테이블(발송 기록)의 생성·발송 모델은 재검토가 필요합니다. 홈의 '까치의 한마디'는 진입 시마다 에이전트가 생성할 수 있는 구조라, 호출 비용·캐싱·지연 설계도 함께 검토해야 합니다.
