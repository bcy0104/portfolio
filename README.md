# 변채연 포트폴리오

가천대학교 컴퓨터공학과 | byeanchaeyeon@gmail.com

백엔드 인증 구현과 AI 분류 실험을 경험한 컴퓨터공학 전공생입니다. 실무에서 협업과 개발 프로세스를 배우고 싶습니다.

## 프로젝트

### 1. Music Check: 책 분위기 기반 음악 추천 앱

- 기간: 2025.11 ~ 2025.12 (4인 팀, 백엔드 담당)
- 기술: Java, Spring Boot, Spring Security, JPA, PostgreSQL, Git/GitHub
- 소개: 책 줄거리와 어울리는 음악을 추천하고, 좋아요/싫어요 피드백을 반영하는 모바일 앱
- 팀 저장소: https://github.com/musiccheck/musiccheck-be

**제가 구현한 것** (AI 도구의 도움을 받아 구현)

- Spring Security 기반 OAuth2 소셜 로그인 (구글, 카카오, 네이버)
  - 제공사별로 사용자 정보 응답 구조가 달라 읽는 방식을 분기 처리했습니다. (카카오는 `kakao_account`, 네이버는 `response` 안에 정보가 있음)
- JWT 발급 및 검증 필터 구현, 접근 권한 설정
- 추천 음악 좋아요/싫어요 토글 API, 사용자 프로필·닉네임 기능
- Spotify 계정 연동 (OAuth 인증, 콜백 처리)

**로그인 흐름**

```
앱 로그인 요청 → 구글/카카오/네이버 인증 → 사용자 정보 정리(제공사별 분기)
              → JWT 발급 → API 요청마다 JWT 검증
```

### 2. clipit: OCR/CNN 기반 스크린샷 정보 구조화 앱

- 기간: 2026.03 ~ 2026.05 (4인 팀, AI 파트)
- 기술: Python, EasyOCR, PyTorch(사전학습 모델 특징 추출), scikit-learn, Flask, Gemini API
- 소개: 스크린샷을 OCR과 CNN으로 분석해 카테고리를 자동 분류하고 제목·요약·날짜를 추출하는 앱
- 문제 정의: 설문 75명 중 77.3%가 저장한 스크린샷을 찾기 어려웠던 경험이 있다고 답했습니다.

**제가 한 것**

- AI 경험자가 없는 팀에서 AI 파트를 맡았습니다. 팀원들이 만든 OCR, CNN 개별 코드를 AI 도구로 결합해 테스트하고, 단독 방식과 같은 데이터·지표로 성능을 비교했습니다.
- 채택된 코드를 수정했습니다. (OCR 텍스트 정제, 핵심 키워드 가중치) 이미지 전처리도 직접 적용해 봤지만 효과가 없어 제외했습니다.
- 최종 모델과 Gemini API를 Flask 서버로 구성해 백엔드(Spring Boot) 및 앱과 연동했습니다. 수정 전후 점수 비교는 기록하지 못했습니다.

**성능 비교** (1,020장: 학습 960장 / 평가 60장, 10개 카테고리)

| 방식 | Accuracy | Macro F1 |
| --- | --- | --- |
| OCR 단독 | 0.7833 | 0.7878 |
| CNN 단독 (MobileNetV3) | 0.7000 | 0.6987 |
| OCR + CNN 결합 | 0.8167 | 0.8171 |

**한계와 배운 점**

- 평가 데이터가 60장이라 결과를 확정하기 어렵고, 교차검증과 데이터 확대가 필요합니다.
- 프로젝트 초기에 목표와 범위를 문서로 합의하는 것이 방향이 어긋나지 않게 하는 데 중요하다는 것을 배웠습니다.

## 기술 스택

- 사용 경험 있음: Python, Java, Spring Boot, Spring Security, PostgreSQL, Git/GitHub
- 프로젝트에서 활용: OAuth2, JWT, REST API, JPA, Flask, scikit-learn, EasyOCR

## 연락처

byeanchaeyeon@gmail.com
