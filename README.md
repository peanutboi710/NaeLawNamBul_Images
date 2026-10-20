# 내Law남불 캐릭터 원본 이미지

내Law남불(공개 저장소 `prgrms-aibe-devcourse/AIBE7_FinalProject_Team2`)의 캐릭터 **원본 PNG**를 보관하는 저장소다. 웹에 넣는 webp 변환본은 이 저장소가 아니라 공개 저장소 `frontend/public/images/characters/`에 있다.

> **지금 올라간 이미지는 샘플이다.** 생성 모델이 프롬프트를 그대로 살리지 못하는 경우가 있어 화면 · 흐름 확인용으로 쓰고, 더 좋은 모델로 바꾸면 같은 프롬프트로 다시 만든다.

## 캐릭터

| 코드 | 이름 | 설명 |
| --- | --- | --- |
| `naero` | 내로 | 마스코트(고양이) |
| `nambul` | 남불 | 마스코트(불꽃) |
| `law-scale` | 로울 | 로(AI 판사) · 저울 머리 |
| `law-gavel` | 로봉 | 로(AI 판사) · 법봉 머리 |
| `law-book` | 로북 | 로(AI 판사) · 법전 머리 |

로는 판결 화면에서 이름 없이 "AI 판사"로만 보인다.

## 파일 이름 규칙

폴더를 보지 않아도 **파일 이름만으로 무슨 이미지인지** 알 수 있고, 저장소 안에서 이름이 겹치지 않는다.

```
{대상}_{종류}_{세부}.png
```

| 구분 | 값 |
| --- | --- |
| 대상 | `naero` · `nambul` · `law-scale` · `law-gavel` · `law-book` · `trio`(로 3인) · `compare`(내로 · 로울 · 남불 비교) · `reenact-common`(공용 재연, 두 번째 세트부터 `reenact-common-2`) · `reenact-case-{사건 id}`(사건별 재연) · `personality-{번호}_{캐릭터}`(성향 결과) · `all`(여럿이 함께 나오는 시트) |
| 종류 | `standing`(스탠딩) · `sheet`(시트) · `cut`(장면 컷) · `cut-cheek`(볼따구 컷) · `icon`(아이콘) |
| 세부 | 시트: `reference` · `acting` · `role-outfits` · `deform-ranma` · `deform-cheek` · `deform-cheek-slim` · `deform-ppg`, 컷: `{장면}-{감정}` (예: `guide-neutral`) |

예: `naero_standing.png` · `law-gavel_sheet_reference.png` · `nambul_cut_guide-neutral.png` · `naero_icon_face-cheer.png` · `personality-06_naero_pinky-promise.png` · `trio_cut_idle.png` · `reenact-common_cut_headline.png`

- **장면** `idle` · `guide` · `react` · `read` · `cheer` · `deliver`, **감정** `neutral` · `happy` · `surprised` · `thinking` · `sorry` · `cheer`. 화난 표정은 만들지 않는다.
- **성향 결과**: 번호 `01 ~ 16`은 유형에 고정되어 있다. 한 유형마다 내로 · 남불 두 장이 있다. 번호 · 유형명 · 기본 캐릭터는 공개 저장소의 성향 이미지 번호표를 본다.
- 이미지 안에는 글자 · 숫자 · 로고를 넣지 않는다.
- **웹용 이름은 다르다.** 웹 webp는 `{장면}-{감정}.webp`, `01.webp`처럼 별도 규칙이고, 이 저장소의 이름과 대응은 변환할 때 정한다.

## 폴더 구조

```
character/
├── standing/     스탠딩 일러스트 5장(기준 이미지) + 마스코트 버전 로 3장(`{로}_standing_deform-mascot.png`)
├── sheets/       시트(16:9, 신문지색 배경)
│   ├── {캐릭터}_sheet_reference.png   기준 시트(캐릭터마다 1장) · all_sheet_height-compare.png(키 비교)
│   ├── acting/        연기 시트
│   ├── wardrobe/      의상 시트(`{캐릭터}_sheet_wardrobe.png`, 내로 · 남불 · 로 3종 5장)
│   ├── props_sheet_catalog.png  소품 시트
│   ├── deform/        데포르메 대표 시트(ranma · cheek · ppg) · 옛 볼따구 컷 그림체 시트(`{캐릭터}_sheet_deform-cheek-slim.png`) · 마스코트 로 시트 3장(`{로}_sheet_deform-mascot.png`) · 5명 라인업 시트(`{캐릭터}_sheet_deform-lineup.png`)
│   └── role-outfits/  역할 의상 시트(내로 · 남불)
├── cuts/         화면에 쓰는 컷(투명 배경)
│   ├── {캐릭터}/base/   장면 컷(하위 폴더로 나눔) · {캐릭터}/icon/   아이콘
│   │   ├── scene/   장면 컷 `{캐릭터}_cut_{장면}-{감정}.png`
│   │   ├── cheek/   볼따구 컷 `{캐릭터}_cut-cheek_*.png` (내로 · 남불, 시트 `deform-cheek` 기준 · 만두형 몸통)
│   │   ├── cheek-slim/  옛 볼따구 컷 `{캐릭터}_cut-cheek-slim_*.png` (내로 · 남불, 호리호리한 몸통 · 옅은 볼 · 작은 눈 · 보존용)
│   │   ├── role/    재연 역할 컷 `{캐릭터}_cut-role-{judge|prosecutor|defense|actor|case-1}_idle-neutral.png` (내로 · 남불)
│   │   └── mascot/  마스코트 버전 로 컷 `{로}_cut-mascot_{장면}-{감정}.png` (로 3종)
│   ├── personality/     성향 결과 컷(16유형 × 2캐릭터)
│   ├── reenact/common/  사건 이미지가 없을 때 쓰는 공용 재연 컷(세트 1 · 2)
│   ├── reenact/case-{사건 id}/  사건별 재연 컷(`headline` · `sub-1` · `detail-1`)
│   ├── trio/            로 3인 합의 컷(`trio_cut_*` 기존 · `trio_cut-mascot_*` 마스코트 버전)
│   └── compare/         내로 · 로울 · 남불 비교 컷(`compare_cut_*` 기존 · `compare_cut-mascot_*` 마스코트 버전)
└── _original/    생성 직후 원본 백업(166장, `original_` 접두사)
```

- **쓸 때는 `standing/` · `sheets/` · `cuts/`의 파일을 쓴다.** `_original/`은 백업이다.
- 이름 끝의 **`_sample`**은 화면 흐름 확인용 샘플이라는 뜻이다. 정식본이 나오면 `_sample`을 뗀 이름으로 바꾼다.
- **공용 재연 세트 2**(`reenact-common-2_cut_*`, 실내에서 두 사람이 마주한 장면)는 10/14에 사건 1 샘플(`reenact-case-1_cut_*_sample`)로 만든 것을 10/15에 공용으로 옮긴 것이다. 사건 1 재연 컷은 10/19에 새로 만들어 `cuts/reenact/case-1/`에 넣었다(`headline` 다툼이 고조되는 순간 · `sub-1` 집으로 찾아옴 · `detail-1` 오래 이어진 변제 다툼).
  - 옛 경로 임시 사본(`cuts/reenact/case-1/reenact-case-1_cut_*_sample.png` 3장)은 프론트 경로를 고친 PR(COMMON-35, #149)이 머지된 10/16에 지웠다.
- **사건별 재연 역할 배정**(역할 순환): 사건 1(빌린 돈 문제로 찾아온 지인을 살해한 사건, 가상) = 남불 A씨(빌린 쪽) · 내로 B씨(빌려준 쪽). 의상은 사건마다 정하고 내로의 반다나는 뺀다. 다음 사건은 반대로 맡는다.
- `_original/`의 이름은 `original_` + 위 규칙이고, 같은 이미지를 다시 뽑은 이력은 `_v1` `_v2`로 구분한다(예: `original_personality-13_nambul_whiteboard_v3.png`). 정식 파일과 내용이 같은 사본이 대부분이고, 탈락본(예: `original_law-book_standing_a2-tall-book.png`)은 `_original/`에만 있다.
- 폐기한 시안(옛 시트 · 실패한 재생성 시도)은 이 저장소에 올리지 않는다.

## 형식

| 종류 | 비율 · 크기 | 배경 |
| --- | --- | --- |
| 장면 컷(`cuts/{캐릭터}/base/*`, `personality`) | 4:5, 1122 × 1402 | 투명 |
| 아이콘(`cuts/{캐릭터}/icon`) | 1:1, 1254 × 1254 | 투명 |
| 시트 · 재연 컷 | 16:9, 1672 × 941 | 지금 이미지는 신문지색 `#ECE2D4`. **10/15부터 새로 만드는 것은 투명**(신문 느낌은 후보정) |
| 합의 · 비교 컷(`trio`, `compare`) | 16:9, 1672 × 941 | 투명 |
| 스탠딩 | 로 971 × 1619, 내로 · 남불 1672 × 941 캔버스 | 투명 |

정식 해상도(장면 2048 × 2560, 아이콘 512 × 512)는 모델 교체 후 재생성 때 맞춘다. 일부 PNG에는 AI 생성 출처 표시(C2PA)가 들어 있다.

## 상태 (2026-10-14 기준)

> 10/19 추가: 마스코트 버전 로 스탠딩 · 기준 시트 6장, 사건 1 재연 컷 3장, 소품 시트, 일상 의상 시트 2장(COMMON-46).
>
> 10/20 추가: 로 의상 시트 3장, 5명 라인업 시트 5장, 마스코트 로 컷 9장, 마스코트 합의 · 비교 컷 3장, 내로 · 남불 역할 컷 10장. `cuts/{캐릭터}/base/`를 `scene` · `cheek` · `role` · `mascot` 하위 폴더로 나눴다. 로 데포르메 시트 중 cheek · ranma · ppg 9장은 아직 없다.
>
> 10/20 추가(2): 볼따구 컷을 시트 `deform-cheek` 기준(짧은 만두형 몸통 · 납작한 볼)으로 4장 다시 만들어 `base/cheek/`에 넣었다. 이전 컷 4장은 `base/cheek-slim/`(`cut-cheek-slim_*`)으로 이름을 바꿔 보존하고, 그 그림체의 시트 2장(`deform-cheek-slim`)을 새로 만들었다. 새 시트는 눈이 작고 볼 강조가 적은 옛 아기 캐릭터 느낌을 노렸지만 기존 시트와 차이가 크지 않다. 재생성 여부는 검수 후 정한다.

10/14에 검수한 이미지는 모두 통과했다(샘플 기준).

| 묶음 | 상태 |
| --- | --- |
| 기준 스탠딩 5장 | ✅ (로울 · 로봉 · 로북은 빈손, 로봉은 떡대 체형) |
| 기준 시트 5장 · 키 비교 시트 | ✅ (캐릭터마다 1장, 키 비교는 합성본) |
| 마스코트 컷 · 볼따구 컷 · 아이콘 | ✅ (`idle-neutral`은 스탠딩을 4:5로 변환) |
| 로 컷(로울 · 로봉 · 로북) · 합의 · 비교 컷 | ✅ |
| 성향 결과 32장(16유형 × 내로 · 남불) | ✅ |
| 공용 재연 컷 6장(세트 1 · 2) | ✅ (세트 2는 10/15 사건 1 샘플에서 옮김) |
| 연기 · 역할 의상 · 데포르메 시트 | ✅ (란마는 목표 약 5등신에 못 미침, 3 ~ 4등신) |

남은 일: 사건별 재연 컷(사건이 정해지면), 후순위 시트(로 cheek · ranma · ppg 데포르메). 최신 목록은 아래 기준 문서를 본다.

## 기준 문서

이름 규칙 · 감정 코드 · 검수 기준 · 이미지 목록은 공개 저장소 문서가 기준이다.

- `docs/character/character-image-checklist.md` — 이미지 목록 · 진행 상태 · 검수 기록 · 생성 프롬프트
- `docs/character/character-asset-architecture.md` — 에셋 아키텍처(이름 · 경로 · 크기)
- `docs/character/personality-image-numbers.md` — 성향 이미지 번호표 · 변형 규칙
- `docs/character/character-image-prompts.md` — 이미지 생성 프롬프트 모음
