# 회사 캐릭터 4종 (Higgsfield 프롬프트 가이드)

기준 소스: `character-signature-lock.md`(시그니처 락 표) + 2D/3D 레퍼런스 이미지 + 추가 구두 지시사항.
작성 방식은 기존 `characters.md`(교육자료) 관리 체계를 그대로 따른다 — **영문 외형 블록 + 항상 적용되는 제약(Negative prompt)** 이중 구조.

> ⚠️ **Element는 등록되어 있으나 이름이 전부 `char_2d`/`char_3d`로 중복 저장되어 있었다** (2D 4개 전부 `char_2d`, 3D 2개는 `char_3d`). 이름만으로 캐릭터 구분이 불가능해서 이미지를 직접 열어 색상·시그니처로 대조 후 아래처럼 매핑했다.
> **힉스필드 워크스페이스에서 이름을 `다정파-2D`처럼 캐릭터명이 드러나게 리네이밍 권장** — 지금 상태로는 신규 Element 추가 시 다시 헷갈릴 수 있다.

| 캐릭터 | 2D Element ID | 3D Element ID |
|---|---|---|
| 다정파 | `0505220e-441d-4460-a443-cb2e5175e8b2` | `0068c3c9-8e50-40a9-907d-453aed2f855e` |
| 기분파 | `88c417cd-693f-49fe-8999-06ff912cb9b9` | `0bb1246c-5e9b-4ac3-828b-e586f5f93fc3` |
| 분석파 | `94fe7ad2-8b83-40af-997b-d20644f3941c` | `73a3f49e-ea1b-44f3-9488-72449e474782` (v2, 귀 줄무늬 추가) |
| 인상파 | `c1fde0e3-6de2-4ebb-8689-724c28b3716d` | `db8b543d-fbd4-4f7f-a15e-bb381746d6ef` |

`characters.md`의 실측 결론(→ 텍스트만으로는 비율이 절대 안 잡히고, Element 바인딩이 유일하게 확실한 방법)이 이 4종에도 그대로 적용된다. 아래 각 캐릭터 블록을 사용할 때는 프롬프트 맨 앞에 렌더 방식에 맞는 Element ID를 `<<<element-id>>>` 토큰으로 바인딩하고, 영문 블록을 그대로 병기한다 (이중 안전장치).

---

## 0. 공통 구조 규칙 (4종 전체 동일 적용)

```
**COMMON STRUCTURE (applies to all 4 characters, every generation):**
A single seamless rounded head-body block with NO visible neck — head and torso
read as one continuous egg/teardrop-shaped mass. Within this block, the HEAD
(round face section) is ALWAYS clearly larger than the lower body/torso section
beneath it — head-to-body size ratio is roughly 2:1. This head-body block
occupies roughly 80-92% of the character's total height; the legs are the
remaining 8-20%. A bright, lighter-toned oval face patch sits on the front of
the block, covering roughly 75% of the block's width and 50-60% of its height.
Facial features are LIMITED to two simple eyes and a mouth, drawn in dark
brownish-black `#36322E`; the inside of an open mouth is `#EB6153`. There is NO
nose of any kind — the area between the eyes and mouth stays completely bare,
no nose shape, no nostrils, no nose shading. There is no cheek blush of any
kind unless a specific character's block below says otherwise. Two short, thin
oval limbs, in a tone darker than the main body color, are attached
symmetrically left and right at the base of the block.
```

**항상 적용되는 제약 (4종 공통 — Negative는 짧고 핵심만):**
- 머리:몸통 비율 2:1 고정, 목 없음 (Negative: `head smaller than body, visible neck`)
- 코 없음, 캐릭터별로 명시 안 된 블러셔 없음 (Negative: `nose, blush`)

> ⚠️ **Negative는 짧게 유지한다.** 2026-09-08 실측: Negative 리스트가 길고 동의어를 중복 나열할수록(예: `separated fingers, individual toes, detailed hand anatomy, five fingers, claws`) 오히려 그 요소가 더 잘 생성되는 역효과가 관찰됐다 (nano_banana 계열은 진짜 negative embedding이 아니라 텍스트로 읽기 때문으로 추정). Negative는 핵심 단어 1~3개로 짧게, 대신 **Critical conditions와 블록 본문에서 원하는 상태를 강하게(긍정문으로) 서술**하는 쪽에 무게를 둔다.

---

## 1. 2D / 3D 공통 제약 (렌더 방식 무관하게 항상 적용)

```
**HANDS/FEET RULE (mandatory, all renders — DEFAULT IS NO FINGERS):** By
default, every limb ends in a smooth rounded mitten/paw shape with ZERO
fingers, ZERO toes, no individual digits at all — this is the default for
every character in every generation regardless of pose, not an occasional
choice. The ONLY exception: if the scene explicitly requires one specific hand
to grip or hold an object, that ONE hand may show a single small rounded
thumb-like nub — every other hand and every foot stays a plain digit-free
mitten/paw.
```
**Negative (짧게):** `fingers, toes`
**시행착오 (2026-09-08):** 여러 장 동시 등장 씬에서 "그립이 필요할 때만 허용"이라는 예외 조건이 기본값처럼 해석되어 전원 손가락이 생기는 문제가 있었다. → 규칙을 "기본값은 항상 손가락 없음"으로 더 단정적으로 재작성하고, Negative도 동의어 나열 대신 `fingers, toes` 두 단어로 축소.

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
deep pink `#E65A91`, inner ear a lighter pink inner-ear patch — attached
upright at the top of the head. Limbs in the deep pink `#E65A91` point color.
The face shows ONLY simple dot-style eyes and a soft curved mouth in the
common face-line color — NOTHING else: no nose, no blush, no cheek marks of
any kind, plain smooth face patch otherwise. Face patch starts a little lower
than GIBUN's (roughly 15-25% down from the top of the block).
```
**항상 적용되는 제약:**
- 귀 형태·색상(외곽 진한 핑크 + 안쪽 라이트 핑크)은 고정 — 접히거나 아래로 처지는 각도 변화는 허용 (Negative: `wrong ear color`)
- 후드/페이스패치 컬러 헥스 고정, **블러셔·볼터치 절대 없음** (Negative: `wrong hood color, blush`)
- **시행착오 (2026-09-08):** 여러 캐릭터 동시 등장 씬에서 다정파에게 없던 분홍 볼 블러셔가 생기는 문제 발생 (분석파의 주근깨가 번진 것으로 추정). → 블록 본문에 "NOTHING else: no nose, no blush"를 명시적으로 못박고 Negative에도 `blush` 추가.

### 기분파 (GIBUN)
Element ID: 2D `88c417cd-693f-49fe-8999-06ff912cb9b9` / 3D `0bb1246c-5e9b-4ac3-828b-e586f5f93fc3`

```
**GIBUN (yellow/orange, mood type):** hood/outer color `#FFD52B`, face patch
`#FFF2BE`. **Forehead curl:** a single small, tightly-coiled spiral curl of
hair (like a tiny spring or snail shell), positioned exactly at the top-center
of the face patch, right where it meets the hood — small, roughly 15% of the
head's width, centered left-right, never drifting to one side, never enlarged.
**Ear decorations:** two branch-like appendages attached HIGH on the LEFT and
RIGHT sides of the head near the crown (angled outward and slightly upward
like small antlers — NOT hanging at normal ear-height), each forking into 2-3
rounded lobes. Outer color orange `#F38200`, with 2-4 rounded polka-dot
circles in `#FCA500` clearly visible and readable on each lobe at all times —
the dots must never fade or disappear into the base orange. Limbs in the
orange `#F38200` point color. No nose, no blush. Face patch sits highest among
the four characters, starting roughly 10-15% down from the top of the block.
```
**항상 적용되는 제약:**
- 귀(날개)는 정수리 근처 좌우 높은 위치, 안테나처럼 위/바깥으로 뻗은 형태 고정 (Negative: `ear at side of head`)
- 땡땡이 무늬는 항상 선명하게 보여야 함 (Negative: `faded polka dots`)
- 이마 스월은 작고 중앙 고정 (Negative: `oversized forehead curl, off-center curl`)
- **시행착오 (2026-09-08):** "귀 모양이 이상하다"는 피드백 발생 — 원인은 귀 위치를 "옆(side)"으로만 서술해서 일반 동물 귀처럼 처졌던 것으로 추정. → 정수리 근처에서 위/바깥으로 뻗는 안테나형 부착 위치를 명시적으로 추가. 땡땡이 무늬도 흐려지는 문제가 있어 "항상 선명하게" 문구 추가.

### 분석파 (BUNSEOK)
Element ID: 2D `94fe7ad2-8b83-40af-997b-d20644f3941c` / 3D `73a3f49e-ea1b-44f3-9488-72449e474782` (v2)

> ⚠️ 기존 3D Element(`54ff10cb-f287-4dc9-8fb6-da0a0c8a3cbc`)는 **귀에 줄무늬가 없는 구버전**이었다.
> 시그니처 락 표에는 "귀의 위치와 모양 유지, 줄무늬 무늬 유지"라고 돼 있었지만 실제 등록된 Element 자체에 줄무늬가 없어서 생성 결과에도 계속 반영이 안 됐던 것 — 2026-09-08에 귀 줄무늬를 추가한 새 버전(`73a3f49e-...`, 이름 `분석파-3D-v2`)을 생성해 재등록했다. **앞으로는 이 v2 ID를 사용한다.** 구버전 ID는 참고용으로만 남겨둠.

```
**BUNSEOK (teal/green, analytical type):** hood/outer color `#40ADA3`, face
patch `#A0D7D0`. **ALWAYS wears large round glasses with a dark navy frame
`#0F4155`** — never removed in any generation. **Antenna:** a thin stalk
rising from the top of the head that is ALWAYS bent into one smooth curve
(like a wave or a hook) — it must NEVER be drawn straight or rigid — ending in
a small round ball tip. **Ears:** small rounded oval lobes attached to the
sides of the head at roughly mid-head height (same attachment height as
DAJEONG's and INSANG's ears, not moved to the top of the head), with a subtle
horizontal stripe pattern in two closely related teal tones; position, size,
and shape stay fixed every time. Small freckle dots on both cheeks — freckles
belong ONLY to BUNSEOK, no other character. When the mouth is open, exactly
one small white tooth is visible. No nose.
```
**항상 적용되는 제약:**
- 안경 필수 (Negative: `no glasses`)
- 안테나는 항상 곡선/구부러진 형태 — 직선 금지 (Negative: `straight antenna`)
- 귀는 머리 옆쪽 중간 높이 고정, 정수리로 이동 금지 (Negative: `ear moved to top of head`)
- 주근깨는 분석파 전용 — 다른 캐릭터에 번지면 안 됨
- 이빨은 1개만 노출 (Negative: `multiple visible teeth`)
- **시행착오 (2026-09-08):** 안테나가 가끔 직선으로 나오고, 귀 위치가 흔들리는 문제 발생 → "ALWAYS bent" 강조 문구 추가, 귀 높이를 다른 캐릭터와 동일 기준으로 명시.

### 인상파 (INSANG)
Element ID: 2D `c1fde0e3-6de2-4ebb-8689-724c28b3716d` / 3D `db8b543d-fbd4-4f7f-a15e-bb381746d6ef`

```
**INSANG (purple, distinct-personality type):** hood/outer color `#6350B2`,
face patch `#B199E4`. **Hair:** a small cluster of 2-3 tall POINTED hair peaks
rising from the crown — one slightly taller center peak curving gently to one
side, flanked by two shorter pointed peaks. Describe this ONLY as pointed hair
peaks, solid flat matte purple, identical material to the rest of the hood —
NOT fire, NOT flames, NO flame texture, NO glow, NO orange/red/yellow color of
any kind in the hair. **Ears:** long drooping oval/teardrop-shaped ears
hanging down at the sides of the head past the widest point of the head — same
general silhouette and attachment position (mid-head height) as the other
three characters' ears — striped in dark purple tones `#583799` to `#4E2A91`,
stripe pattern and position preserved at all times. **Eyes are ALWAYS in a
half-closed, sassy/unimpressed shape: both eyes read as flat, slightly
downward-angled slits, paired with a straight single-line eyebrow.** This is
NOT a curved happy smiling-eye shape, NOT a "^_^" shape, NOT fully open or
round — it is a flat, unimpressed, half-closed look, locked in every
generation regardless of the character's mood or pose. No nose, no blush.
```
**항상 적용되는 제약:**
- 반쯤 감긴 눈(플랫한 사선 슬릿) + 일자 눈썹 항상 유지 — 웃는 곡선(^_^) 눈으로 바뀌면 안 됨 (Negative: `curved happy eyes, smiling crescent eyes`)
- 머리술은 "불꽃(flame/fire)"이 아니라 뾰족한 봉우리 형태로만 서술 — 실제 불 텍스처/발광 금지 (Negative: `flame, fire, glowing hair`)
- 귀는 다른 캐릭터와 동일한 중간 높이에서 아래로 늘어진 물방울형, 줄무늬 고정 (Negative: `ear shape changed, missing ear stripes`)
- **시행착오 (2026-09-08):** "불꽃 모양 머리술"을 영어로 그대로 "flame-shaped"라고 쓰니 실제 불꽃/발광 텍스처로 생성됨 → "flame"이라는 단어 자체를 빼고 "뾰족한 봉우리 3개" 형태로만 기하학적으로 재서술. 눈도 "half-closed"만으로는 부족해서 곡선 웃는눈으로 자꾸 바뀜 → "flat downward-angled slits, NOT curved happy eyes"로 구체화. 귀 모양/위치도 흔들려서 다른 캐릭터와 동일 기준 높이임을 명시.

---

## 4. 관리 메모
- 4종 모두 Element 등록 완료 (2D×4, 3D×4) — 단, 힉스필드 워크스페이스 내 이름이 `char_2d`/`char_3d`로 중복이라 리네이밍 권장 (위 표 참고)
- 캐릭터별 "고정 요소"는 시그니처 락 표(`character-signature-lock.md`)와 이 문서 양쪽에 동기화 유지
- 재수정 피드백으로 새 규칙이 나오면 해당 캐릭터 블록 아래 "시행착오" 형태로 추가 (`characters.md` 관례 참고)
- 3D 확장 시 재질 변형(위 2번 섹션)을 캐릭터 블록과 함께 사용

### 2026-09-08 — 4명 동시 등장 씬(여름 바다) 1차 생성 실패 사례
4종 전원이 등장하는 3D 여름 바다 씬에서 아래 문제가 한꺼번에 나타났다:
1. 손가락이 기본적으로 생성됨 (그립이 필요 없는데도)
2. Negative 리스트가 너무 길어서 오히려 문제 요소를 강화시킨 것으로 추정
3. 머리:몸통 비율이 명시돼 있지 않아 비율이 흐트러짐
4. 공통 규칙에 "코 없음"이 명시돼 있지 않아 코가 생김
5. 다정파에게 없던 블러셔 발생 (분석파 주근깨가 번진 것으로 추정)
6. 인상파 머리술을 "flame-shaped"로 영역했더니 실제 불꽃 텍스처로 생성됨 + 귀 모양/위치 흔들림
7. 분석파 안테나가 가끔 직선으로, 귀 위치도 흔들림
8. 기분파 귀(날개) 모양이 무너지고 이마 스월 위치도 흔들림

→ 위 8개 전부 원인 규칙을 0~3번 섹션 및 각 캐릭터 블록에 영구 반영 완료 (손 규칙 단정화, Negative 축소, 머리:몸통 2:1 명시, 코 없음 공통 규칙 추가, 다정파 블러셔 금지 명시, 인상파 "flame" 단어 제거 후 기하학적 재서술, 분석파 안테나 "ALWAYS bent" 명시, 기분파 귀 부착 위치 명시).
