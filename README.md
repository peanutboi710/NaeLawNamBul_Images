# 내Law남불 캐릭터 원본 이미지

내Law남불(공개 저장소 `prgrms-aibe-devcourse/AIBE7_FinalProject_Team2`)의 캐릭터 **원본 PNG**를 보관하는 저장소다. 웹에 넣는 webp 변환본은 이 저장소가 아니라 공개 저장소 `frontend/public/images/characters/`에 있다.

> **지금 올라간 이미지는 샘플이다.** 생성 모델이 프롬프트를 그대로 살리지 못하는 경우가 있어 화면 · 흐름 확인용으로 쓰고, 더 좋은 모델로 바꾸면 같은 프롬프트로 다시 만든다. 검수 결과 고칠 곳이 남은 이미지도 있다(아래 "상태").

## 캐릭터

| 코드 | 이름 | 설명 |
| --- | --- | --- |
| `naero` | 내로 | 마스코트(고양이) |
| `nambul` | 남불 | 마스코트(불꽃) |
| `law-scale` | 로울 | 로(AI 판사) · 저울 머리 |
| `law-gavel` | 로봉 | 로(AI 판사) · 법봉 머리 |
| `law-book` | 로북 | 로(AI 판사) · 법전 머리 |

파일 · 폴더 이름에는 위 코드를 쓴다. 로는 판결 화면에서 이름 없이 "AI 판사"로만 보인다.

## 폴더 구조

```
character/
├── sheets/            시트(16:9, 신문지색 배경)
│   ├── character-sheet_*.png   기준 시트 · 키 비교(height_v3)
│   ├── acting/         연기 시트  {naero · nambul · law-scale · law-book}.png
│   ├── deform/         데포르메 대표 시트  {naero · nambul}-{ranma · cheek · ppg}.png
│   └── role-outfits/   역할 의상 시트(참고용)  {naero · nambul}.png
├── standing/          스탠딩 일러스트(투명 배경) — 기준 이미지 5장
│   └── envelope/       봉투를 든 이전 스탠딩
├── cuts/              화면에 쓰는 컷(투명 배경)
│   ├── {캐릭터}/base/{스타일-데포르메}/{장면}-{감정}.png
│   ├── {캐릭터}/icon/{스타일-데포르메}/face-{감정}.png
│   ├── personality/    성향 결과 컷  01 ~ 16.png
│   ├── reenact/common/ 사건 이미지가 없을 때 쓰는 공용 재연 컷  {headline · sub-1 · detail-1}.png
│   ├── trio/           로 3인 합의 컷  {trio-idle · trio-think}.png
│   └── compare/        내로 · 로울 · 남불 비교 컷  trio-thinking.png
└── _original/         생성 직후 임시 이름 원본 백업(70장)
```

- **쓸 때는 `sheets/` · `standing/` · `cuts/`의 파일을 쓴다.** `_original/`은 백업이다.
- `_original/`의 대부분은 이름을 바꿔 위 폴더에 같은 이미지가 들어 있어 **내용이 중복된다**. 이름 대응은 아래 표.
- 탈락한 이전 버전은 폴더로 올리지 않았다(`sheets/old/`, `standing/_alt/`). 다만 그중 `a2` · `A3` · `a4-3`은 임시 이름 원본으로 `_original/`에만 남아 있다.

### `_original/` 임시 이름 대응

| 임시 이름 | 지금 위치 · 이름 |
| --- | --- |
| `a1 gpt ver` | `sheets/character-sheet_law-book.png` (로북 기준 시트) |
| `a2` | 탈락본 — `_original/`에만 있음 |
| `A3` | 탈락본 — `_original/`에만 있음. 키 비교는 `sheets/character-sheet_height_v3.png`(합성) |
| `a4-1` · `a4-2` | `standing/standing_law-scale.png` · `standing_law-gavel.png` (빈손) |
| `a4-3` | 탈락본 — `_original/`에만 있음. 로북 스탠딩은 `standing/standing_law-book.png` |
| `b1-1` · `b1-2` | `cuts/law-scale/base/authority-adult/` idle-neutral · deliver-neutral |
| `b2-1` ~ `b2-5` | `cuts/naero/base/editorial-mascot/` guide-neutral · guide-happy · react-surprised · react-happy · react-sorry |
| `b3-1` ~ `b3-5` | `cuts/nambul/base/editorial-mascot/` (위와 같은 순서) |
| `b4-1` ~ `b4-4` | `cuts/{naero · nambul}/base/editorial-cheek/` idle-sorry · idle-thinking (내로 2 → 남불 2) |
| `b5-1` ~ `b5-12` | `cuts/{naero · nambul}/icon/editorial-ppg/face-*` (neutral · happy · surprised · thinking · sorry · cheer, 내로 6 → 남불 6) |
| `c1-1` · `c1-2` | `cuts/trio/` trio-idle · trio-think |
| `c2-1` · `c2-2` | `cuts/law-gavel/…/deliver-neutral` · `cuts/law-book/…/deliver-neutral` |
| `c3` | `cuts/compare/trio-thinking` |
| `d1-1` ~ `d1-16` | `cuts/personality/01 ~ 16` |
| `e1-1` ~ `e1-3` | `cuts/reenact/common/` headline · sub-1 · detail-1 |
| `f1-1` ~ `f1-4` | `sheets/acting/` naero · nambul · law-scale · law-book |
| `f2-1` · `f2-2` | `sheets/role-outfits/` naero · nambul |
| `f 3-1` ~ `f 3-6` | `sheets/deform/` naero-ranma · nambul-ranma · naero-cheek · nambul-cheek · naero-ppg · nambul-ppg |

## 이름 규칙

- 장면 컷: `{장면}-{감정}.png` — 장면 `idle` · `guide` · `react` · `deliver` 등, 감정 `neutral` · `happy` · `surprised` · `thinking` · `sorry` · `cheer`. **화난 표정은 만들지 않는다.**
- 스타일-데포르메 폴더: 내로 · 남불 `editorial-mascot`(기본) · `editorial-cheek`(볼따구) · `editorial-ppg`(카툰 아이콘), 로 `authority-adult`.
- 성향 결과: 번호 `01 ~ 16`(유형에 고정, 순서나 이름이 바뀌어도 번호는 그대로). 한 유형에 그림을 더 두면 `{번호}-{변형}`(예정: `-2` = 반대편 캐릭터).
- 이미지 안에는 글자 · 숫자 · 로고를 넣지 않는다.

## 형식

| 종류 | 비율 · 크기 | 배경 |
| --- | --- | --- |
| 장면 컷(`base/`, `personality/`) | 4:5, 1122 × 1402 | 투명 |
| 아이콘(`icon/`) | 1:1, 1254 × 1254 | 투명 |
| 시트 · 재연 컷 | 16:9, 1672 × 941 | 신문지색 `#ECE2D4` |
| 합의 · 비교 컷(`trio/`, `compare/`) | 16:9, 1672 × 941 | 투명 |
| 스탠딩 | 로 971 × 1619, 내로 · 남불 1672 × 941 캔버스 | 투명 |

정식 해상도(장면 2048 × 2560, 아이콘 512 × 512)는 모델 교체 후 재생성 때 맞춘다. 일부 PNG에는 AI 생성 출처 표시(C2PA)가 들어 있다.

## 상태 (2026-10-14 검수 기준)

| 묶음 | 상태 |
| --- | --- |
| 기준 스탠딩 5장 | ✅ (로울 · 로봉 · 로북은 빈손 버전) |
| 내로 · 남불 마스코트 컷 10장(guide · react) | ✅ |
| 아이콘 12장 | 🟨 일부 재생성 예정 |
| 볼따구 컷 4장(`editorial-cheek`) | 🟨 수정 예정 |
| 로 3인 합의 컷 · 비교 컷 | 🟨 보정 필요(초록 잔여 픽셀 · 비율) |
| 로 발표 컷(로봉 · 로북 `deliver`) | ✅ |
| 성향 결과 16장 | 🟨 9장 통과, 7장 재생성 예정 |
| 공용 재연 컷 3장 | 🟨 표정 · 의상 보정 권장 |
| 연기 시트 | ✅ 내로 · 남불 · 로울 / 🟨 로북 |
| 데포르메 시트 | ✅ 카툰 / 🟨 란마(그림체 미적용) · 볼따구 |
| 역할 의상 시트 | 🟨 보류(띠 색 · 소품 구분 방법 미정) |
| 키 비교 시트 | ✅ 합성본 |

앞으로 추가 예정: 캐릭터별 1인 기준 시트, 성향 결과 반대편 캐릭터 16장(`-2`), 응원 · 기록 읽기 컷 등. 최신 목록은 아래 기준 문서의 이미지 제작 목록을 본다.

## 기준 문서

이름 규칙 · 감정 코드 · 검수 기준 · 이미지 목록은 공개 저장소 문서가 기준이다.

- `docs/character/character-image-checklist.md` — 이미지 목록 · 진행 상태 · 생성 프롬프트
- `docs/character/character-asset-architecture.md` — 에셋 아키텍처(이름 · 경로 · 크기)
- `docs/character/personality-image-numbers.md` — 성향 이미지 번호표 · 변형 규칙
- `docs/character/character-image-prompts.md` — 이미지 생성 프롬프트 모음
