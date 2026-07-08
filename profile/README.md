<!-- # ![Trip Baton](https://github.com/user-attachments/assets/b3db6ff1-3161-489e-ba68-2a08b732ca68) Trip Baton -->

# Trip Baton

## SSAFY 1학기 최종 관통 프로젝트

> **사용자가 여행을 재밌게 할 수 있도록 게이미피케이션 요소를 넣은 웹/앱 서비스**
> 본 프로젝트는 사용자가 쉽게 서비스에 접근할 수 있게 PWA를 사용하여 앱으로 사용할 수 있고 , 생성형 AI·배치 등을 활용하여 사용자에게 맞춤 정보를 제공하고 서비스 데이터를 자동화하는 환경으로 구현했습니다.

---

## 📌 프로젝트 소개

**Trip Baton**은 '여행'을 주제로 한 PWA(Progressive Web App) 서비스입니다.
생성형 AI와 배치 작업을 접목해 사용자에게 맞춤형 여행 정보를 제공하는 것을 목표로 했으며, 모바일 접근성을 높이기 위해 별도 앱 배포 없이 실제 앱처럼 설치·사용할 수 있도록 PWA로 구현했습니다.

프론트엔드는 FSD(Feature-Sliced Design) 구조로 웹/모바일 환경과 도메인을 분리하여 구현되었고, 백엔드는 일부 도메인 로직과 주기적인 데이터 갱신을 위한 배치 기능으로 구현되었으며, 프로젝트 일정은 Jira·Notion으로 관리되었습니다.

---

## 🖼️ 대표 이미지

<!-- 서비스 대표 스크린샷 / 로고 이미지를 추가해주세요 -->
<p align="center">
  <img src="" width="700" alt="Trip Baton 대표 이미지"/>
</p>

---

## 🏗️ 아키텍처

<!-- 시스템/서비스 아키텍처 다이어그램 이미지를 추가해주세요 -->
<p align="center">
  <img src="" width="900" alt="Trip Baton 아키텍처"/>
</p>

---

## 🛠️ Tech Stack

<p>
  <img src="https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black">
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white">
  <img src="https://img.shields.io/badge/Zustand-443E38?style=for-the-badge&logo=react&logoColor=white">
  <img src="https://img.shields.io/badge/PWA-5A0FC8?style=for-the-badge&logo=pwa&logoColor=white">
  <img src="https://img.shields.io/badge/OAuth2-000000?style=for-the-badge&logo=auth0&logoColor=white">
  <img src="https://img.shields.io/badge/JWT-black?style=for-the-badge&logo=jsonwebtokens&logoColor=white">
  <img src="https://img.shields.io/badge/Amazon_S3-FF9900?style=for-the-badge&logo=amazons3&logoColor=white">
  <img src="https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white">
  <img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white">
  <img src="https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white">
</p>

| 기술 | 선택 이유 |
|------|-----------|
| React + TypeScript | 컴포넌트 재사용성과 타입 안정성 확보 |
| FSD (Feature-Sliced Design) | 웹/모바일 환경 분기와 도메인별 응집도 확보, 유지보수성 강화 |
| PWA | 별도 앱 배포 없이 모바일 설치·네이티브 경험 제공 |
| Zustand (persist) | 경량 전역 상태 관리 + 새로고침 후에도 상태 유지 |
| OAuth + JWT | 카카오·구글 소셜 로그인으로 진입 장벽 최소화 |
| Presigned URL (S3) | 이미지 업로드를 서버 경유 없이 클라이언트가 직접 처리 |
| Spring Boot | 도메인 로직 및 배치 기능을 위한 백엔드 프레임워크 |
| AWS | S3 기반 이미지 저장 등 서비스 인프라 운영 |

---

## 📌 핵심 기능 (Core Features)

- **여행 릴레이** — 여러 사용자가 하나의 여행을 이어받아 함께 완성해가는 게이미피케이션 핵심 기능
- **소셜 로그인** — OAuth(카카오·구글) 기반 로그인, JWT 인증/인가
- **생성형 AI 연동** — OpenAI API 통신, 시스템 프롬프트 엔지니어링으로 응답 형식 일관성 확보
- **이미지 업로드** — Presigned URL로 클라이언트가 S3에 직접 업로드
- **배치** — 일정 주기마다 데이터 갱신 작업 수행
- **검색** — debounce 적용, 검색 컴포넌트화로 전 화면 재사용
- **PWA** — 모바일 환경에서 앱처럼 설치 가능, 네이티브 UX 지향

---

## 📂 폴더 구조 (FSD)

```
src/
├── app/           # 앱 진입, 전역 설정
├── pages/         # 라우트 단위 페이지
├── widgets/       # 페이지 조합 단위 UI
├── features/      # 도메인 기능 (ui / api / hook 분리)
├── entities/      # 도메인 모델
└── shared/        # 공통 유틸, 컴포넌트, 상태
```

> 도메인별로 `ui / api / hook` 폴더를 나눠 관심사를 분리하고 재사용 가능하도록 구성했습니다.

---

## 🤝 Collaboration

- **Jira** — 스프린트 일정 및 이슈 트래킹
- **Notion** — 프로젝트 문서화

---
