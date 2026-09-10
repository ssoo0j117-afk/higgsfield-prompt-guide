# 하늘 배너 — 4캐릭터 (3D, 구름, 중앙 텍스트 여백)

- 날짜: 2026-09-10
- 요청(한국어): 레퍼런스 이미지(구도만 참고) 첨부 + "가운데 영역 50%는 텍스트가 들어갈거라서 비워줘 / 3d 스타일 / 1280 800 / 하늘 위 구름에 서있음 / 좌측 기분파(큰 연필 타고 나는 역동적 포즈)+인상파(뒤에 작게, 책 위, 엄지척) / 우측 다정파(책 더미 위 블록놀이)+분석파(뒤에 작게, 구름 위 게임)" →
  1차 피드백: "더 역동적으로(슝슝), 별 장식 제거, 구름 더 퐁신하게, 인상파는 펼쳐진 책 위로, 분석파 게임기 안 보임, 기분파도 더 역동적으로" →
  2차 피드백: 인상파 중복 생성 문제 발견 → 수정 →
  3차 피드백: "전체적으로 채도를 높혀서 그려줘"
- 렌더/비율: 3D / 3:2 (2k, 1280x800 타겟)
- Elements: 기분파(`9beb23f7-...` v2), 인상파(`db8b543d-...`), 다정파(`e6adcff1-...` v2), 분석파(`00e2d49f-...` v3)
- 결과: OK (4차 시도 — ①구도 확정 → ②역동성/구름/게임기 보정 → ③중복 캐릭터 수정 → ④채도 최종 확정)
- **채도 기준 업데이트**: 이 결과가 `2026-09-09-scattered-dynamic-poses-vivid.md`보다도 더 쨍한, 현재 기준 "적정 채도"의 최신 레퍼런스. Style 블록에 "EXTREMELY VIVID, MAXIMUM SATURATION, bold punchy poster-bright colors" 수준까지 강하게 써야 이 결과가 나온다.

## 최종 프롬프트
```
<<<9beb23f7-f94c-4cc6-96be-aeaec1af5c9f>>> <<<db8b543d-fbd4-4f7f-a15e-bb381746d6ef>>> <<<e6adcff1-bad0-48c5-8241-197da97bf2d7>>> <<<00e2d49f-490a-4f0a-9982-8399564d5dc6>>> # Sky Banner v4 (3D, fluffy clouds, dynamic motion, EXACTLY 4, ULTRA VIVID) — GIBUN, INSANG, DAJEONG, BUNSEOK

## Scene
EXACTLY FOUR characters total — 1 GIBUN + 1 INSANG + 1 DAJEONG + 1 BUNSEOK = 4. No duplicates anywhere.

Four mascot characters play high up in a bright blue sky full of soft, extremely fluffy clouds — no stars or sparkle decorations. On the LEFT: GIBUN rockets through the sky astride a giant pencil in a highly dynamic diagonal "whoosh" pose — body leaning far forward, ear decorations whipped backward by wind, one arm thrust forward triumphantly, big open laughing mouth, soft motion-streak lines trailing behind the pencil. Directly below GIBUN, sitting on a large OPEN book with pages spread flat, INSANG relaxes with legs dangling over the pages, one arm raised in a confident thumbs-up — the ONLY INSANG in the image. On the RIGHT: DAJEONG sits on a tall stack of picture books, happily playing with colorful toy building blocks, joyful open smile. Behind and smaller than DAJEONG, BUNSEOK sits on a fluffy cloud, holding a LARGE, clearly-visible handheld game console directly in front of his chest, angled flat toward the camera, console roughly head-width, unmistakably readable, high-contrast color against his body.

## Cast — EXACTLY these 4 characters, no one else, no duplicates
Only ONE of each: GIBUN, INSANG, DAJEONG, BUNSEOK.

COMMON STRUCTURE (applies to all 4): a single seamless rounded head-body block with NO visible neck. Head-to-body size ratio is roughly 2:1 (head clearly bigger). Head-body block is 80-92% of total height, legs the rest. Bright lighter-toned oval face patch on the front, ~75% width / 50-60% height. Facial features LIMITED to two simple eyes and a mouth in dark brownish-black #36322E; mouth interior #EB6153. NO nose of any kind. NO cheek blush of any kind on GIBUN, DAJEONG, or INSANG — only BUNSEOK has small freckle dots. Two short, thin oval limbs, darker tone, symmetrical. Limb length is SHORT and FIXED.

HANDS/FEET RULE (default NO fingers): every limb ends in a smooth digit-free mitten/paw. Exceptions: INSANG's thumbs-up hand, DAJEONG's hand holding a block, BUNSEOK's hands on the game console — each may show one small thumb nub.

GIBUN (yellow/orange, mood type): hood/outer color #FFD52B, face patch #FFF2BE. Forehead curl: small tightly-coiled spiral at top-center. Ear decorations: two branch-like appendages HIGH near the crown, forking into 2-3 rounded lobes, orange #F38200 with large bold clearly-visible polka-dot circles in #FCA500. Limbs orange #F38200. Bare cheeks, no blush. No nose. Pose: highly dynamic diagonal rocket pose astride the giant pencil, leaning far forward, wind-whipped ears/curl, one arm thrust forward, motion-streak lines trailing behind.

INSANG (purple, distinct-personality type) — APPEARS EXACTLY ONCE: hood/outer color #6350B2, face patch #B199E4. Hair: 2-3 tall pointed hair peaks, solid flat matte purple. Ears: long drooping oval/teardrop ears at mid-head height, striped dark purple #583799 to #4E2A91. Eyes ALWAYS a half-closed, flat, slightly downward-angled slit shape with a straight single-line eyebrow. No nose, no blush. Pose: sitting on a large OPEN book with pages spread flat, legs dangling, one arm raised in a confident thumbs-up. Left side of frame, below GIBUN.

DAJEONG (pink, affection type): hood/outer color warm pink #F582AF, face patch light pink #FFCDE4. Two large rounded bunny ears — outer deep pink #E65A91, lighter pink inner-ear patch — upright at the top of the head. Limbs deep pink #E65A91. Bare cheeks, no blush. No nose. Pose: sitting on a tall stack of picture books, happily stacking/holding colorful toy building blocks, joyful open smile. Larger scale, front-right of frame.

BUNSEOK (teal/green, analytical type): hood/outer color #40ADA3, face patch #A0D7D0. ALWAYS wears large round glasses with a dark near-black navy frame #0A2540. Antenna: thin stalk ALWAYS bent into a smooth curve, small ball tip. Ears: small rounded oval lobes at mid-head height with subtle horizontal stripe pattern in two closely related teal tones. Small freckle dots on both cheeks (BUNSEOK only). No nose. Pose: sitting on a fluffy cloud, holding a LARGE handheld game console flat and forward-facing directly in front of his chest, console roughly head-width, unmistakably readable, focused happy expression. Smaller scale than DAJEONG, upper-right.

## Props
GIANT PENCIL (GIBUN's): oversized chubby rounded pencil, flat bright-color body, soft rounded point, plain eraser cap, with soft motion-streak/speed lines trailing behind it.
OPEN BOOK (INSANG's): large book lying open, pages spread flat, rounded corners, thick colorful covers, no legible text.
STACKED BOOKS (DAJEONG's): small closed picture books, rounded corners, thick colorful covers, stacked tall, no legible text.
TOY BLOCKS (DAJEONG's): rounded-corner cube blocks in bright flat colors, no letters/numbers.
HANDHELD GAME CONSOLE (BUNSEOK's): LARGE, clearly-visible rounded rectangular handheld game device, white/light-gray body with colorful buttons, glowing screen, held flat facing the camera.
CLOUDS: extremely soft, naturalistic, voluminous, fluffy clouds like whipped cream, gentle soft shading. NO stars, NO sparkles.

## Text Reserved Area
The exact CENTER of the frame — middle 50% of the WIDTH, full height — stays completely clear of characters and props. Only sky and soft fluffy clouds. No overlay, no tint, no text.

## Environment
Bright daytime sky, soft gradient, large extremely fluffy naturalistic clouds, warm sunlight. NO stars, NO sparkles. No ground, no buildings.

## Camera / Composition
Wide horizontal composition, target 1280x800. GIBUN upper-left (dynamic diagonal), INSANG below him on the open book, left side. DAJEONG front-right on the books with blocks, BUNSEOK smaller behind/above her on a cloud with the game console, upper-right. Center 50% width stays open sky. Exactly four characters, none repeated.

## Style
Soft-matte 3D toy/figure render, smooth rounded surfaces, gentle soft-touch matte finish (not glossy), soft bright daylight, gentle soft contact shadows, collectible toy quality. Overall EXTREMELY VIVID, MAXIMUM SATURATION, bold punchy poster-bright colors — think saturated candy-bright primary and secondary hues, richly saturated blue sky, richly saturated character body colors, richly saturated prop colors — nothing desaturated, nothing muted, nothing pastel, nothing washed-out anywhere in the image, every color pushed toward its most vivid, eye-catching version while staying within the established brand hex colors. Round, soft, huggable silhouettes; nothing sharp, angular, or scary.

## Critical conditions (must all hold)
1. EXACTLY 4 characters total, no duplicates.
2. Head-to-body ratio 2:1; limb length fixed; no fingers except noted exceptions; no nose; NO blush except BUNSEOK's freckles.
3. GIBUN's pose is dramatically dynamic/diagonal with motion streaks.
4. INSANG sits on an OPEN, spread-page book, appears only once.
5. BUNSEOK's game console is LARGE, clearly visible, high-contrast, facing the camera.
6. Clouds soft/fluffy/naturalistic. NO stars or sparkles.
7. Center 50% of frame width stays completely clear.
8. Colors are MAXIMALLY vivid and saturated throughout the entire image — sky, clouds, characters, and props all read as bold and punchy, not soft or muted.

## Negative
duplicate character, second INSANG, cloned character, extra copy of a character, five characters, fingers, toes, nose, blush, cheek circles, visible neck, head smaller than body, long arms, stretched arms, straight antenna, faded polka dots, light glasses frame, text, watermark, glossy, mirror reflection, characters in center, props in center, MUTED COLORS, DULL COLORS, WASHED-OUT COLORS, LOW SATURATION, PASTEL COLORS, desaturated, faded colors, grayish tones, scary expression, cluttered center, stars, sparkles, flat plastic-looking clouds, static calm pose on GIBUN, closed book under INSANG, hidden or obscured game console, tiny game console
```

## 시행착오 메모
- 레퍼런스 이미지는 구도(좌우 그룹, 대소 배치, 중앙 여백)만 차용하고 캐릭터 디테일은 `style/characters.md` 스펙대로 새로 작성 (레퍼런스 자체는 비율이 이상해서 그대로 따라가면 안 됨).
- "역동적으로/슝슝" 피드백 → 모션 스트릭(motion-streak lines) 서술 + "leaning far forward, wind-whipped" 같은 구체적 동작 묘사 추가가 효과적이었음. 막연히 "dynamic"만 쓰면 부족.
- **중복 캐릭터 버그**: 소품(연필) 위에 탄 캐릭터 근처에 같은 캐릭터가 작게 한 번 더 그려지는 현상 발생. → Critical conditions 맨 앞에 "1 GIBUN + 1 INSANG + 1 DAJEONG + 1 BUNSEOK = 4" 식으로 **숫자를 명시적으로 더해서** 못박고, Negative에 `duplicate character, second INSANG, cloned character`처럼 구체적으로 추가하니 해결됨. (원본 `character-scene.md`의 "좌석표 덧셈 문장" 원칙과 동일한 효과)
- **채도**: "HIGHLY SATURATED, vivid and punchy" 정도로는 부족한 경우가 있었고, "EXTREMELY VIVID, MAXIMUM SATURATION, bold punchy poster-bright... every color pushed toward its most vivid version"까지 강하게 써야 확실히 쨍하게 나옴. 이 프롬프트가 현재 채도 기준의 최신 레퍼런스.
- 소품이 캐릭터 몸 색과 겹쳐서 안 보이는 문제(분석파 게임기) → 소품 색을 캐릭터 몸 색과 대비되는 색(흰색/밝은 회색)으로 명시하고 "head-width" 등 크기 기준을 숫자로 제시하니 해결.
