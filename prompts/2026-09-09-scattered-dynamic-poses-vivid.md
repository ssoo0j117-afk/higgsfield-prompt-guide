# 4캐릭터 대각선 플라잉 포즈 (3D, 흰 배경)

- 날짜: 2026-09-09
- 요청(한국어): "여기있는 구도와 포즈로 4마리의 캐릭터를 입혀서 그려줘" (스캐터드 대각선 포즈 레퍼런스 이미지 첨부) → "분석파,인상파는 오른쪽으로 나는 느낌, 기분파,다정파는 왼쪽으로 나는 느낌으로" → "채도 높혀줘 + 다정파 다리를 뒤로 확 빠진 느낌으로, 포즈가 너무 정적임" → "채도는 이렇게 선명해야 해서 이 기준으로 로그 업데이트"
- 렌더/비율: 3D / 16:9 (2k)
- Elements: 다정파(`e6adcff1-...` v2), 기분파(`9beb23f7-...` v2), 분석파(`00e2d49f-...` v3), 인상파(`db8b543d-...`)
- 결과: OK (3차 시도 — ①구도/포즈 확정 → ②좌우 방향 수정 → ③채도+다정파 포즈 확정)
- **이 결과가 채도 기준(레퍼런스)**: `templates/character-scene.md` 공통 Style 블록의 "HIGHLY SATURATED, vivid and punchy" 문구가 만들어낸 결과물. 앞으로 색감 관련 피드백이 있으면 이 로그를 기준점으로 비교한다.

## 최종 프롬프트
```
<<<e6adcff1-bad0-48c5-8241-197da97bf2d7>>> <<<9beb23f7-f94c-4cc6-96be-aeaec1af5c9f>>> <<<00e2d49f-490a-4f0a-9982-8399564d5dc6>>> <<<db8b543d-fbd4-4f7f-a15e-bb381746d6ef>>> # Scattered Dynamic Poses v3 (3D, white background, vivid) — DAJEONG, BUNSEOK, INSANG, GIBUN

## Scene
Four mascot characters float scattered across a plain white background, each leaping/flying diagonally, split into two directional pairs. GIBUN (upper-left) and DAJEONG (lower-left) both lean and fly diagonally TOWARD THE LEFT. BUNSEOK (upper-right) and INSANG (lower-right) both lean and fly diagonally TOWARD THE RIGHT. DAJEONG's pose is especially dynamic: her whole body arcs forward, both legs kicked sharply BACKWARD and UP behind her (like a mid-air leap/dive), not a static floating pose — much more energetic than the other three.

## Cast — EXACTLY these 4 characters, no one else
Only GIBUN, DAJEONG, BUNSEOK, and INSANG appear. No additional people, no duplicates, no floor, no background props other than the two listed below.

COMMON STRUCTURE (applies to all 4): a single seamless rounded head-body block with NO visible neck. Head-to-body size ratio is roughly 2:1 (head clearly bigger). Head-body block is 80-92% of total height, legs the rest. Bright lighter-toned oval face patch on the front, ~75% width / 50-60% height. Facial features LIMITED to two simple eyes and a mouth in dark brownish-black #36322E; mouth interior #EB6153. NO nose of any kind. NO cheek blush unless a character's block says otherwise. Two short, thin oval limbs, darker tone, symmetrical. Limb length is SHORT and FIXED — each arm/leg is roughly the same length as the head is tall, never longer, in ANY pose — kicking legs back changes the ANGLE only, never the LENGTH.

HANDS/FEET RULE (default NO fingers): every limb ends in a smooth digit-free mitten/paw. Exceptions: DAJEONG's hands hugging the gift box, and INSANG's hands holding the book, may each show one small thumb nub.

GIBUN (yellow/orange, mood type): hood/outer color #FFD52B, face patch #FFF2BE. Forehead curl: small tightly-coiled spiral at top-center. Ear decorations: two branch-like appendages HIGH near the crown, angled outward/upward, forking into 2-3 lobes, orange #F38200 with large bold clearly-visible polka-dot circles in #FCA500. Limbs orange #F38200. No nose, no blush. Pose: flying diagonally TOWARD THE LEFT, limbs trailing behind to the right, big open laughing mouth. Upper-left of frame.

DAJEONG (pink, affection type): hood/outer color warm pink #F582AF, face patch light pink #FFCDE4. Two large rounded bunny ears — outer deep pink #E65A91, lighter pink inner-ear patch — upright at the top of the head. Limbs deep pink #E65A91. Face shows ONLY simple dot eyes and mouth — no nose, no blush. Pose: dynamic mid-air leap arcing toward the LEFT, both legs kicked sharply backward and upward behind her (dramatic diving/leaping silhouette, NOT a calm floating pose), both arms hugging a small wrapped gift box to her chest, big joyful open smile, body arched forward. Lower-left of frame, below GIBUN.

BUNSEOK (teal/green, analytical type): hood/outer color #40ADA3, face patch #A0D7D0. ALWAYS wears large round glasses with a dark near-black navy frame #0A2540 — never removed. Antenna: thin stalk ALWAYS bent into a smooth curve, never straight, small ball tip. Ears: small rounded oval lobes at mid-head height with a subtle horizontal stripe pattern in two closely related teal tones. Small freckle dots on both cheeks. No nose. Pose: flying diagonally TOWARD THE RIGHT, limbs trailing behind to the left, excited open smile. Upper-right of frame.

INSANG (purple, distinct-personality type): hood/outer color #6350B2, face patch #B199E4. Hair: 2-3 tall pointed hair peaks, solid flat matte purple — NOT fire, NOT flames. Ears: long drooping oval/teardrop ears at mid-head height, striped dark purple #583799 to #4E2A91. Eyes ALWAYS a half-closed, flat, slightly downward-angled slit shape with a straight single-line eyebrow. No nose, no blush. Pose: flying diagonally TOWARD THE RIGHT, same direction as BUNSEOK, limbs trailing left, holding a small open book with both hands. Lower-right of frame, below BUNSEOK.

## Props
GIFT BOX (DAJEONG's): small rounded-corner gift box, soft-matte flat color body (cream/white with a red ribbon bow).
BOOK (INSANG's): small open book, rounded corners, solid bright blue cover, blank/wavy-line pages, no legible text.

## Environment
Plain, clean white background, no floor, no walls. Generous open empty space between all four characters. A soft, subtle drop shadow beneath each character.

## Camera / Composition
Wide 16:9 composition. GIBUN upper-left, DAJEONG lower-left (both flying left, DAJEONG especially dynamic), BUNSEOK upper-right, INSANG lower-right (both flying right). Large open negative space in the middle. None overlap.

## Style
Soft-matte 3D toy/figure render, smooth rounded surfaces, gentle soft-touch matte finish (not glossy), soft even studio lighting, gentle soft contact shadow, collectible toy quality. Overall bright, cheerful, HIGHLY SATURATED, vivid and punchy color palette — vibrant, not muted, not pastel, not washed-out. Round, soft, huggable silhouettes; nothing sharp, angular, or scary.

## Critical conditions (must all hold)
1. ONLY these 4 characters appear.
2. Head-to-body ratio 2:1 on all 4; limb length stays short and fixed even in dynamic poses; no fingers except the two noted exceptions; no nose; no blush except BUNSEOK's freckles.
3. GIBUN and DAJEONG both lean/fly LEFT; BUNSEOK and INSANG both lean/fly RIGHT.
4. DAJEONG's legs are kicked sharply BACKWARD and UP in a dynamic leaping silhouette — clearly more energetic/dynamic than a simple floating pose.
5. Colors read as vivid and highly saturated throughout — no dull, muted, or pastel tones anywhere.
6. INSANG's eyes stay flat half-closed slits; hair plain pointed peaks. BUNSEOK's antenna curved, ears striped, glasses dark navy. GIBUN's ear polka dots large and visible.
7. Plain white background, no environment clutter.

## Negative
fingers, toes, nose, blush, visible neck, head smaller than body, long arms, stretched arms, extra characters, duplicated characters, straight antenna, faded polka dots, light glasses frame, text, watermark, glossy, mirror reflection, floor, background scenery, cluttered background, scary expression, GIBUN or DAJEONG leaning right, BUNSEOK or INSANG leaning left, DAJEONG static pose, DAJEONG legs hanging down, muted colors, dull colors, washed-out colors, low saturation, pastel colors
```

## 시행착오 메모
- 1차: 사용자가 첨부한 스캐터드 대각선 포즈 레퍼런스 사진 자체는 캐릭터 비율이 무너져 있어서, **구도/포즈만 차용하고 캐릭터 디테일은 `style/characters.md` 스펙대로 새로 작성**하는 방식으로 진행. (참고 이미지를 그대로 레퍼런스 이미지로 넣지 않고 텍스트로만 구도를 재현 — Element 바인딩 방식 유지)
- 2차: 좌우 방향 지정 누락 → "분석파·인상파는 오른쪽, 기분파·다정파는 왼쪽"으로 페어별 방향을 Critical conditions에 명시하고 Negative에도 반대 방향을 넣어 고정.
- 3차: 채도 부족 + 다정파 포즈가 밋밋함 → **이 두 피드백은 재사용 가능한 규칙이라 판단**, `templates/character-scene.md`의 공통 Style 블록을 "HIGHLY SATURATED, vivid and punchy"로 영구 수정 (전 세션 커밋 `d234e98`). 다정파의 "다리를 뒤로 확 차올리는" 포즈는 이 씬 전용이라 캐릭터 공통 규칙에는 반영하지 않고, 이 로그에만 기록.
- **채도 기준**: 이 로그의 결과 이미지가 "적정 채도"의 기준점. 이후 색감이 흐리다는 피드백이 다시 나오면 이 프롬프트의 Style 문구보다 더 강하게 조정이 필요하다는 신호.
