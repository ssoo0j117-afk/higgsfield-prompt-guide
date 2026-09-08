# 회사 캐릭터 4종 (Higgsfield 프롬프트 가이드)

기준 소스: `character-signature-lock.md`(시그니처 락 표) + 2D/3D 레퍼런스 이미지 + 추가 구두 지시사항.
작성 방식은 기존 `characters.md`(교육자료) 관리 체계를 그대로 따른다 — **영문 외형 블록 + 항상 적용되는 제약(Negative prompt)** 이중 구조.

> ⚠️ **Element는 등록되어 있으나 이름이 전부 `char_2d`/`char_3d`로 중복 저장되어 있었다** (2D 4개 전부 `char_2d`, 3D 2개는 `char_3d`). 이름만으로 캐릭터 구분이 불가능해서 이미지를 직접 열어 색상·시그니처로 대조 후 아래처럼 매핑했다.
> **힉스필드 워크스페이스에서 이름을 `다정파-2D`처럼 캐릭터명이 드러나게 리네이밍 권장** — 지금 상태로는 신규 Element 추가 시 다시 헷갈릴 수 있다.

| 캐릭터 | 2D Element ID | 3D Element ID |
|---|---|---|
| 다정파 | `0505220e-441d-4460-a443-cb2e5175e8b2` | `0068c3c9-8e50-40a9-907d-453aed2f855e` |
| 기분파 | `88c417cd-693f-49fe-8999-06ff912cb9b9` | `0bb1246c-5e9b-4ac3-828b-e586f5f93fc3` |
| 분석파 | `94fe7ad2-8b83-40af-997b-d20644f3941c` | `54ff10cb-f287-4dc9-8fb6-da0a0c8a3cbc` |
| 인상파 | `c1fde0e3-6de2-4ebb-8689-724c28b3716d` | `db8b543d-fbd4-4f7f-a15e-bb381746d6ef` |

`characters.md`의 실측 결론(→ 텍스트만으로는 비율이 절대 안 잡히고, Element 바인딩이 유일하게 확실한 방법)이 이 4종에도 그대로 적용된다. 아래 각 캐릭터 블록을 사용할 때는 프롬프트 맨 앞에 렌더 방식에 맞는 Element ID를 `<<<element-id>>>` 토큰으로 바인딩하고, 영문 블록을 그대로 병기한다 (이중 안전장치).

---

## 0. 공통 구조 규칙 (4종 전체 동일 적용)

```
**COMMON STRUCTURE (applies to all 4 characters, every generation):**
A single seamless rounded head-body block with NO visible neck — head and torso
read as one continuous egg/teardrop-shaped mass. This head-body block occupies
roughly 80-92% of the character's total height; the legs are the remaining
8-20%. A bright, lighter-toned oval face patch sits on the front of the block,
covering roughly 75% of the block's width and 50-60% of the block's height,
starting roughly 10-30% down from the top of the block (character-specific
vertical position noted per character below). Facial feature line color is
dark brownish-black `#36322E`; the inside of an open mouth is `#EB6153`. Two
short, thin oval limbs, in a tone darker than the main body color, are attached
symmetrically left and right at the base of the block.
```

**항상 적용되는 제약 (4종 공통 Negative):**
- 비율 필수 고정 — 머리-몸통 블록 80~92% : 다리 비율이 깨지면 안 됨 (Negative: `stretched proportions, elongated legs, tiny head, oversized head, changed head-to-body ratio`)
- 목 생성 금지 — 머리와 몸통은 하나의 이어진 덩어리 (Negative: `visible neck, neck gap, separated head and body`)

---

## 1. 2D / 3D 공통 제약 (렌더 방식 무관하게 항상 적용)

```
**HANDS/FEET RULE (mandatory, all renders):** the limb ends are smooth rounded
mitten/paw shapes with NO individually separated fingers or toes. At most, a
single small rounded thumb-like nub may appear on a hand ONLY when the pose
specifically requires gripping or holding something — never as a default, and
never on feet.
```
**Negative 필수:** `separated fingers, individual toes, detailed hand anatomy, five fingers, claws`

- **표정은 자유** — 캐릭터별 "고정 요소"(아래 표 참고)만 지키면 눈/입 표정 변화는 허용
- **비율은 위 공통 구조 규칙을 항상 우선** — 포즈가 바뀌어도 블록:다리 비율 유지

---

## 2. 3D 전용 제약 (3D 렌더에서만 추가)

```
**3D RENDER FINISH (use only for 3D output — overrides any glossy/vinyl description):**
Soft, smooth matte surface with a gentle, natural sheen — like soft-touch matte
PVC or soft rubber, NOT a glossy or reflective plastic. Diffused, soft studio
lighting. Highlights are soft and subtle, never sharp or mirror-like.
```
**항상 적용되는 제약 (3D):**
- 과도한 광택/반사 금지 (Negative: `high gloss, glossy plastic, mirror-like specular highlight, wet-look shine, hard reflection, chrome-like surface`)
- 재질은 부드럽고 자연스러운 질감 유지 (Negative: `hard plastic sheen, glass-like surface`)
- 배경은 순백 `#FFFFFF` (2번 표 "기준 베이스 샷" 참고), 카메라 앵글은 연출컷마다 유동적

> 참고: `characters.md`의 PVC 블록은 "semi-gloss / specular highlight"를 의도적으로 넣지만, 이 프로젝트는 정반대(무광·저광택)로 확정되어 있으므로 그 블록을 그대로 가져오지 말 것.

---

## 3. 캐릭터별 영문 외형 블록

### 다정파 (DAJEONG)
Element ID: 2D `0505220e-441d-4460-a443-cb2e5175e8b2` / 3D `0068c3c9-8e50-40a9-907d-453aed2f855e`

```
**DAJEONG (pink, affection type):** hood/outer color warm pink `#F582AF`,
face patch light pink `#FFCDE4`. Two large rounded bunny ears — outer surface
deep pink `#E65A91`, inner ear a lighter pink inner-ear patch. Limbs in the
deep pink `#E65A91` point color. Simple dot-style eyes and a soft curved mouth
using the common face-line color. Face patch starts a little lower than
GIBUN's (roughly 15-25% down from the top of the block).
```
**항상 적용되는 제약:**
- 귀 형태·색상(외곽 진한 핑크 + 안쪽 라이트 핑크)은 고정 — 접히거나 아래로 처지는 각도 변화는 허용 (Negative: `wrong ear shape, ear color swapped, missing inner ear patch`)
- 후드/페이스패치/포인트 컬러 헥스 고정 (Negative: `wrong hood color, wrong face patch color, off-brand pink`)

### 기분파 (GIBUN)
Element ID: 2D `88c417cd-693f-49fe-8999-06ff912cb9b9` / 3D `0bb1246c-5e9b-4ac3-828b-e586f5f93fc3`

```
**GIBUN (yellow/orange, mood type):** hood/outer color `#FFD52B`, face patch
`#FFF2BE`. A curly swirl tuft of hair rises from the center of the forehead.
Two wing-shaped ear decorations attach on either side, outer color orange
`#F38200` with a polka-dot pattern in `#FCA500` printed inside each wing shape.
Limbs in the orange `#F38200` point color. Face patch sits highest among the
four characters, starting roughly 10-15% down from the top of the block.
```
**항상 적용되는 제약:**
- 귀(날개) 모양과 내부 땡땡이 무늬는 고정 — 귀가 위/아래로 처지는 각도 변화는 허용 (Negative: `missing polka dots, wrong ear shape, plain ear without pattern`)
- 이마 스월 헤어는 항상 유지 (Negative: `missing forehead swirl, straight hair`)

### 분석파 (BUNSEOK)
Element ID: 2D `94fe7ad2-8b83-40af-997b-d20644f3941c` / 3D `54ff10cb-f287-4dc9-8fb6-da0a0c8a3cbc`

```
**BUNSEOK (teal/green, analytical type):** hood/outer color `#40ADA3`, face
patch `#A0D7D0`. **ALWAYS wears large round glasses with a dark navy frame
`#0F4155`** — never remove them in any generation. A slightly curved antenna
with a small ball tip rises from the top of the head. Small freckle dots on
both cheeks. When the mouth is open, exactly one small white tooth is visible.
Ears keep their established position and shape, with their stripe pattern
preserved.
```
**항상 적용되는 제약:**
- 안경 필수 — 어떤 표정/포즈에서도 벗기지 않음 (Negative: `no glasses, missing glasses, glasses removed`)
- 귀의 위치·모양·줄무늬 고정 (Negative: `changed ear position, ear stripe missing, plain ear`)
- 이빨은 1개만 노출 (Negative: `multiple visible teeth, full tooth row`)

### 인상파 (INSANG)
Element ID: 2D `c1fde0e3-6de2-4ebb-8689-724c28b3716d` / 3D `db8b543d-fbd4-4f7f-a15e-bb381746d6ef`

```
**INSANG (purple, distinct-personality type):** hood/outer color `#6350B2`,
face patch `#B199E4`. A flame-shaped tuft of hair rises from the crown. Ears
are striped in dark purple tones `#583799` to `#4E2A91`, stripe pattern
preserved at all times. **Eyes are ALWAYS in a half-closed, sassy/unimpressed
shape paired with a straight single-line eyebrow — this eye shape is locked
and must not be drawn as fully open or round in any generation.**
```
**항상 적용되는 제약:**
- 반쯤 감긴 눈 + 일자 눈썹은 항상 유지 — 표정을 바꿔도 이 눈 형태는 고정 (Negative: `fully open eyes, round wide eyes, surprised eyes, curved eyebrows`)
- 귀 줄무늬 무늬 고정, 귀 위치는 고정하되 위로 올라가거나 처지는 각도 변화는 허용 (Negative: `missing ear stripes, plain solid ear`)
- 정수리 불꽃 머리술 항상 유지 (Negative: `missing flame hair tuft, flat head`)

---

## 4. 관리 메모
- 4종 모두 Element 등록 완료 (2D×4, 3D×4) — 단, 힉스필드 워크스페이스 내 이름이 `char_2d`/`char_3d`로 중복이라 리네이밍 권장 (위 표 참고)
- 캐릭터별 "고정 요소"는 시그니처 락 표(`character-signature-lock.md`)와 이 문서 양쪽에 동기화 유지
- 재수정 피드백으로 새 규칙이 나오면 해당 캐릭터 블록 아래 "시행착오" 형태로 추가 (`characters.md` 관례 참고)
- 3D 확장 시 재질 변형(위 2번 섹션)을 캐릭터 블록과 함께 사용
