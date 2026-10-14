# 내Law남불 캐릭터 원본 이미지

내Law남불(공개 저장소 `prgrms-aibe-devcourse/AIBE7_FinalProject_Team2`)의 캐릭터 **원본 PNG**를 보관하는 저장소다. 웹에 넣는 webp 변환본은 이 저장소가 아니라 공개 저장소 `frontend/public/images/characters/`에 있다.

> 지금 올라간 이미지는 **샘플**이다. 생성 모델이 프롬프트를 그대로 살리지 못하는 경우가 있어 화면 · 흐름 확인용으로 쓰고, 더 좋은 모델로 바꾸면 같은 프롬프트로 다시 만든다.

## 캐릭터

| 코드 | 이름 | 설명 |
| --- | --- | --- |
| `naero` | 내로 | 마스코트 |
| `nambul` | 남불 | 마스코트 |
| `law-scale` | 로울 | 로(AI 판사) · 저울 |
| `law-gavel` | 로봉 | 로(AI 판사) · 법봉 |
| `law-book` | 로북 | 로(AI 판사) · 법전 |

파일 · 폴더 이름에는 위 코드를 쓴다.

## 폴더 구조

```
character/
├── sheets/        기준 시트 · 키 비교 시트
│   ├── acting/        연기 시트
│   ├── deform/        데포르메 대표 시트  {naero · nambul}-{ranma · cheek · ppg}.png
│   └── role-outfits/  역할 의상 시트
├── standing/      스탠딩 일러스트
│   └── envelope/      봉투를 든 이전 스탠딩
└── cuts/          장면 · 아이콘 · 성향 · 재연 컷
    ├── {캐릭터}/base/{스타일-데포르메}/{장면}-{감정}.png
    ├── {캐릭터}/icon/{스타일-데포르메}/face-{감정}.png
    ├── personality/   성향 결과 컷  01 ~ 16.png
    ├── reenact/common/ 사건 이미지가 없을 때 쓰는 공용 컷
    ├── trio/ · compare/ 내로 · 남불 · 로 함께 나오는 컷
    └── _original/     생성 직후 임시 이름(b1-1 등) 원본
```

- `cuts/_original/`은 **백업용**이다. 같은 이미지가 이름을 바꿔 다른 폴더(`naero/`, `nambul/`, `personality/` 등)에 들어 있어 내용이 중복된다. 쓸 때는 다른 폴더의 파일을 쓴다.
- 폐기한 이전 버전(`sheets/old/`, `standing/_alt/`)은 올리지 않았다.

## 형식

- 장면 컷은 4:5, 아이콘은 1:1, 시트는 16:9 신문지색(`#ECE2D4`) 배경이다. 컷 PNG는 4:5(1122 × 1402)로 캔버스를 맞췄다.
- 이미지 안에는 글자 · 숫자 · 로고를 넣지 않는다.
- 일부 PNG에는 AI 생성 출처 표시(C2PA)가 들어 있다.

## 기준 문서

이름 규칙 · 감정 코드 · 검수 기준은 공개 저장소 문서가 기준이다.

- `docs/character/character-asset-architecture.md` — 에셋 아키텍처
- `docs/character/character-image-checklist.md` — 이미지 목록 · 진행 상태
- `docs/character/personality-image-numbers.md` — 성향 이미지 번호표
