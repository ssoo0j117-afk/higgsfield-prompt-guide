# 다정파 — 별 껴안고 신나하는 포즈 (3D, 밝은 명도 기준)

- 날짜: 2026-09-11
- 요청(한국어): "다정파가 별을 끌어안고 신나하는 포즈를 그려줘" → 1차 결과에 "너무 명도가 어두운데? 채도도 확 낮고 별 색상이 너무 우울해" 피드백 → 명도/배경 수정 후 확정
- 렌더/비율: 3D / 3:4 (2k)
- Elements: 다정파(`e6adcff1-...` v2)
- 결과: OK (2차 시도 — ①포즈/구도 확정 → ②명도·배경·별 색상 보정)
- **명도 기준 업데이트**: 이 결과가 현재 "적정 명도"의 기준점 (밝은 하늘색 배경 + 선명한 노란 별).

## 최종 프롬프트
```
<<<e6adcff1-bad0-48c5-8241-197da97bf2d7>>> # DAJEONG hugging a star, excited (3D, bright high-key)

## Scene
DAJEONG hugs a big plump star tightly to her chest with both arms, bouncing with excitement, big wide joyful open-mouth smile, eyes scrunched happy, as if thrilled to have won or found the star.

## Cast — 1 character only
Only DAJEONG appears. No other characters.

COMMON STRUCTURE: a single seamless rounded head-body block with NO visible neck. Head-to-body size ratio is roughly 2:1 (head clearly bigger). Head-body block is 80-92% of total height, legs the rest. Bright lighter-toned oval face patch on the front, ~75% width / 50-60% height. Facial features LIMITED to two simple eyes and a mouth in dark brownish-black #36322E; mouth interior #EB6153. NO nose of any kind. NO cheek blush of any kind. Two short, thin oval limbs, darker tone, symmetrical. Limb length is SHORT and FIXED — hugging changes the ANGLE only, never the LENGTH.

HANDS/FEET RULE (default NO fingers): every limb ends in a smooth digit-free mitten/paw. Exception: the arms wrapped around the star may show a single small thumb nub on each hand where they meet/grip around the star. Feet stay plain mitten/paw.

DAJEONG (pink, affection type): hood/outer color warm pink #F582AF, face patch light pink #FFCDE4. Two large rounded bunny ears — outer deep pink #E65A91, lighter pink inner-ear patch — upright at the top of the head. Limbs deep pink #E65A91. Face shows ONLY simple dot eyes and mouth — NOTHING else, no nose, no blush. Pose: hugging a big star tightly with both arms wrapped around it, bouncing/leaning with excitement, one foot slightly lifted as if mid-bounce, big wide joyful open-mouth smile, eyes scrunched into happy curved arcs.

## Props
STAR: a plump, soft-edged five-pointed star shape almost as big as DAJEONG's own head-body block — points gently rounded rather than sharp and pointy, flat BRIGHT SATURATED sunny yellow color fill #FFD52B (a clean vivid yellow, NOT a dull mustard/gold tone), a few simple bright white sparkle marks nearby, soft-matte toy render matching DAJEONG's style.

## Environment
A clean, bright, high-key background — pure bright white or a light, cheerful, saturated sky-blue — evenly and brightly lit, NOT a dim warm gradient, NOT a moody or cozy glow. Simple soft contact shadow beneath DAJEONG, no other props or clutter.

## Camera / Composition
Vertical 3:4 composition, DAJEONG centered, full body visible head-to-toe, star held prominently in front of her chest.

## Style
Soft-matte 3D toy/figure render, smooth rounded surfaces, gentle soft-touch matte finish (not glossy), bright, even, HIGH-KEY studio lighting — no dim areas, no moody shadows, no warm dim glow, gentle soft contact shadow, collectible toy quality. Overall EXTREMELY VIVID, MAXIMUM SATURATION, HIGH BRIGHTNESS, bold punchy poster-bright colors — nothing muted, pastel, dull, washed-out, dim, or gloomy anywhere. Round, soft, huggable silhouette; nothing sharp, angular, or scary.

## Critical conditions (must all hold)
1. Only DAJEONG appears, no other characters.
2. Head-to-body ratio 2:1; limb length fixed even while hugging; no fingers except the two noted thumb-nub exceptions; no nose; no blush.
3. Ear shape/color fixed (outer deep pink, lighter pink inner-ear patch).
4. Pose clearly reads as an excited, bouncy hug — not a calm static hold.
5. Star is a clean bright vivid yellow #FFD52B, NOT dull/mustard/gold. Background and overall lighting are bright and high-key, NOT dim or moody.

## Negative
fingers, toes, nose, blush, cheek circles, visible neck, head smaller than body, long arms, stretched arms, extra characters, duplicated characters, wrong ear color, wrong hood color, text, watermark, glossy, mirror reflection, muted colors, dull colors, washed-out colors, pastel colors, dim lighting, moody lighting, low-key lighting, dark background, gloomy colors, mustard tones, dingy colors, warm dim gradient background, scary expression, calm static pose, sharp pointy star, cluttered background
```

## 시행착오 메모
- 1차 결과: "EXTREMELY VIVID, MAXIMUM SATURATION"까지 채도를 올린 상태였는데도 "명도가 어둡다/우울하다"는 피드백이 나왔다. 원인은 배경을 "softly glowing light background (pale warm gradient)"로만 서술해서 채도는 있어도 전체적으로 톤이 낮게(어둡게) 나왔던 것 — **채도와 명도는 별개 축**이라는 걸 재확인.
- 이 문제는 이 씬만의 문제가 아니라 **템플릿 공통 규칙 자체의 빈틈**이라 판단, `templates/character-scene.md`의 공통 Style 블록에 "HIGH BRIGHTNESS, HIGH-KEY lighting, NOT dim/moody" 조항을 영구 추가하고 기본 배경을 "밝은 화이트/채도 높은 플랫 컬러/밝은 대낮"으로 지정 (따뜻한 은은한 그라데이션은 명시적 요청 시에만). 이 글로벌 규칙 수정 덕에 2차 시도에서 바로 해결됨.
- 소품 색상도 "yellow"라고만 쓰면 겨자색/골드톤으로 빠질 수 있어, 이번처럼 **정확한 헥스값 + "NOT mustard/gold" 부정문**을 함께 쓰는 게 효과적이었다.
