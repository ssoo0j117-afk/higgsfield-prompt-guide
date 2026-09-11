# 템플릿: 캐릭터 장면 (Character Scene) — 초등 학습 서비스용

`character-scene.md`(교육자료 원본) 골격 + `company-characters.md`(우리 캐릭터 사전)을 결합해
**초등학생 대상 학습 콘텐츠**에 맞게 조정한 버전이다.

**전제**
- 대상: 초등학생 — 항상 밝고 친근하고 안전한 톤. 무섭거나 위협적인 요소 절대 금지
- 등장인원: 1~4명 유동적 (다정파/기분파/분석파/인상파 중 필요한 만큼만 사용)
- 용도: 앱·웹 일러스트 / SNS·마케팅 / 굿즈·이벤트 — 렌더 스타일만 아래 Style 섹션에서 스위치
- 텍스트/말풍선이 자주 들어가지만 **AI가 텍스트를 직접 생성하지 않는다** — 자리만 비워서 나중에 편집으로 텍스트를 얹는 방식

---

## 프롬프트 골격

```
<<<element-id-1>>> <<<element-id-2>>> ... # {장면 제목}

## Scene
{장소·상황·핵심 액션을 3~5문장. 누가 무엇을 설명/가리키고 있는지, 나머지는 어떤 반응인지,
모두 바닥에 서 있는지 등 물리적 배치까지 명시.}

## Cast — EXACTLY these {N} characters, no one else
Only {NAME1}, {NAME2}, ... appear. No additional people, no background bystanders, no duplicates.
{company-characters.md의 "공통 구조 규칙" 블록 복사}
{등장 캐릭터별 영문 외형 블록 복사 — company-characters.md에서, 각자 Expression/Pose 한 줄 추가}

## Text Reserved Area (해당 씬에 텍스트 요소가 있을 때만 포함)
Leave a clearly-defined empty region at {위치, 예: upper-right / top banner strip /
lower third}, sized roughly {대략적 크기, 예: about 1/3 of the frame width}. This area
stays completely blank / plain flat fill matching the surrounding palette — reserved
empty space for text to be added later in editing. Do NOT render any letters,
words, characters, or symbols inside it. (모양은 씬마다 다르므로 말풍선/배너 등 특정
형태를 강제하지 않는다 — 그냥 "빈 영역"으로만 지정한다.)

## Environment
{배경 디테일: 장소, 조명, 소품, 시선이 가는 포인트}

## Camera / Composition
Stable, balanced, eye-level {shot type}. All figures clearly framed and grounded,
none cut off. {주인공 배치 설명}. Calm, orderly composition.

## Style — 아래 중 렌더 방식에 맞는 ONE만 사용
{2D 또는 3D 블록 — 아래 "Style 스위치" 참고}

## Critical conditions (must all hold)
1. ONLY these {N} characters appear — no extra people or duplicates.
2. Each character's locked features (company-characters.md 기준) are preserved exactly.
3. If a text/speech area is specified: it stays COMPLETELY EMPTY — no rendered text, letters, or symbols of any kind inside it.
4. Overall silhouette and mood stay round, soft, and cheerful — nothing sharp, angular, or intimidating.
5. {이번 장면 고유의 제약 — 포즈 대비, 소품 위치 등}
6. Stable, grounded, balanced composition — no unstable or scattered framing.

## Negative
{아래 "공통 Negative"} + {"텍스트 영역 Negative" (해당 시)} + {"캐릭터별 Negative"} + {이번 장면 고유 Negative}
```

---

## Style 스위치 (한 프롬프트에는 하나만 사용)

### 2D — 앱/웹 UI 일러스트용
```
Flat vector-style illustration, bold clean smooth outlines, simple rounded soft
shapes, bright cheerful flat color fills with minimal shading (a single soft
one-directional shadow at most), playful and simple, consistent with in-app/web
UI illustration style. No painterly texture, no complex gradients, no realistic
shading.
```

### 3D — 굿즈/피규어용
```
Soft-matte 3D toy/figure render, smooth rounded surfaces, gentle soft-touch matte
finish (NOT glossy, NOT high specular — soft diffused studio lighting only, no
harsh reflections or mirror-like highlights), gentle contact shadows, collectible
toy quality, clean simple background unless scene specifies otherwise.
```

### 공통 (2D/3D 모두 항상 추가)
```
Overall EXTREMELY VIVID, MAXIMUM SATURATION, HIGH BRIGHTNESS, bold punchy
poster-bright color palette — think saturated candy-bright primary and
secondary hues under bright, clean, HIGH-KEY lighting (NOT dim, NOT moody,
NOT a soft low-lit glow). Richly saturated AND brightly lit background
colors, character body colors, and prop colors — nothing desaturated,
nothing muted, nothing pastel, nothing washed-out, nothing dim or shadowy
anywhere in the scene. Every color pushed toward its most vivid, brightest,
eye-catching version while staying within the established brand hex colors.
Backgrounds default to clean bright white, bright saturated flat colors, or
bright daylight — NOT warm dim gradients, NOT soft glowing "cozy" vignettes
unless a scene explicitly asks for a nighttime/cozy mood. Round, soft,
huggable silhouettes on every character and prop; warm and friendly mood
throughout; nothing sharp, angular, dark, or scary anywhere in the scene.
```
**Negative 추가 (항상):** `muted colors, dull colors, washed-out colors, low saturation, pastel colors, desaturated, faded colors, grayish tones, dim lighting, moody lighting, low-key lighting, dark background, gloomy colors, mustard tones, dingy colors`

> ⚠️ **시행착오 (2026-09-09 → 2026-09-10 → 2026-09-11 재조정):** "HIGHLY SATURATED" → "EXTREMELY VIVID, MAXIMUM SATURATION"까지 올렸는데도 "명도가 어둡다/우울하다"는 피드백이 다시 나왔다. 원인 분석: **채도(saturation)만 강조하고 명도(brightness/value)는 따로 명시하지 않아서**, 배경을 "soft glowing warm gradient"처럼 묘사하면 채도는 있어도 전체적으로 어둡고 칙칙하게(예: 별이 겨자색으로) 나오는 문제가 있었다. → Style 블록에 **"HIGH BRIGHTNESS", "HIGH-KEY lighting", "NOT dim, NOT moody"**를 채도 문구와 별도로 명시하고, 기본 배경을 "clean bright white / bright saturated flat color / bright daylight"로 지정 (따뜻한 은은한 그라데이션은 명시적으로 요청했을 때만). Negative에도 `dim lighting, moody lighting, dark background, gloomy colors, mustard tones`를 추가. **채도와 명도는 별개로 챙겨야 한다** — 앞으로 색감 피드백이 오면 어느 쪽(채도 vs 명도) 문제인지 구분해서 조정할 것.

---

## 공통 Negative (모든 씬에 항상 포함 — 짧게 유지)

```
extra characters, duplicated characters, unstable framing, fingers, toes,
visible neck, head smaller than body, nose, blush, long arms,
stretched arms, scary expression, text, watermark, low quality
```

**3D 씬에서만 추가:** `glossy, mirror reflection`

> ⚠️ **Negative는 절대 길게 늘어놓지 않는다.** 2026-09-08 실측: 동의어를 여러 개 나열한 긴 Negative(예: `separated fingers, individual toes, detailed hand anatomy, five fingers, claws`)를 쓴 씬에서 오히려 손가락이 잘 생기고, 캐릭터 시그니처(안테나 곡률, 눈 모양, 귀 위치 등)가 흐트러지는 현상이 반복 관찰됐다. nano-banana 계열 모델은 진짜 negative embedding이 아니라 Negative 섹션도 텍스트로 읽기 때문에, 단어를 반복 나열할수록 그 단어에 대한 "주의"만 더 끌 수 있다. → **Negative는 핵심 단어 위주로 짧게, 원하는 상태는 캐릭터 블록·Critical conditions에 강한 긍정문으로 서술**하는 쪽을 기본 전략으로 삼는다.

## 텍스트 영역 Negative (해당 씬에 텍스트 요소가 있을 때 추가)

```
text, letters, words inside the reserved area
```

## 캐릭터별 필수 Negative (해당 캐릭터 등장 시 `style/characters.md`에서 가져와 추가 — 각 캐릭터당 1~2개로 압축)
- 다정파: `blush`
- 기분파: `faded polka dots, ear at side of head`
- 분석파: `straight antenna, no glasses`
- 인상파: `flame, curved happy eyes`

---

## 자주 쓰는 학습 소품 프롭 블록 (프롭 언급 시 불러와 사용)

### 선물 상자 (GIFT BOX)
```
**GIFT BOX:** a small rounded-corner gift box with a soft-matte flat color body
and a single wide ribbon wrapped around it, tied in a simple rounded bow on top.
Same bright, cheerful color palette as the scene. Soft rounded silhouette, no
sharp corners. Same render style as the characters (flat 2D or soft-matte 3D,
matching the chosen Style section) — NOT photorealistic.
```

### 책 (BOOK)
```
**BOOK:** a small closed or slightly-open storybook with rounded corners and a
thick friendly-looking cover in a bright flat color. If open, the pages are
blank or show soft wavy lines suggesting text — NEVER render actual legible
words or letters on the pages. Rounded, soft, toy-like proportions.
```

### 연필 (PENCIL)
```
**PENCIL:** a short, chubby, rounded pencil with a flat bright-color body, a
simple pointed tip (no sharp realistic graphite point — keep it soft and
rounded), and a plain eraser cap. Toy-like proportions, no fine realistic
detail.
```

### 별 (STAR)
```
**STAR:** a plump, soft-edged five-pointed star shape — points are gently
rounded rather than sharp and pointy. Flat bright color fill (commonly yellow
or gold-tone within the scene's palette), optional simple sparkle marks nearby.
```

### 트로피 (TROPHY)
```
**TROPHY:** a small rounded, chubby-proportioned trophy cup with a simple
stem and base, no fine engraved detail or realistic metallic reflections.
Flat or soft-matte gold-tone color fill matching the render style (2D flat
color or 3D soft-matte — never a sharp mirror-like metallic finish).
```

**소품 공통 제약 (5종 모두):**
- 항상 캐릭터와 동일한 렌더 스타일(2D 플랫 벡터 또는 3D 무광)로 통일 — 소품만 사실적으로 튀지 않게 (Negative: `photorealistic prop, realistic material, sharp metallic reflection on prop`)
- 항상 둥글고 부드러운 실루엣 — 날카로운 모서리 금지 (Negative: `sharp corners on prop, pointy edges`)
- 책 페이지·소품 위에 읽을 수 있는 글자를 렌더링하지 않음 (Negative: `legible text on book, letters on prop, words on gift box`)

---

## 인원수 규칙 (최대 4명이라 좌석표까지는 불필요)

`character-scene.md` 원본은 5명 이상·좌석 배치가 있는 장면에서 "좌석표"를 요구하지만,
우리는 최대 4명이라 아래 정도면 충분하다.

- **"EXACTLY these N characters"** 문구 + Negative에 `extra characters, duplicated characters` 중복 기재로 인원수 고정
- **기본 크기 관계**: 4종은 전부 동일 체급의 마스코트 — 별도 요청이 없으면 전원 동일 크기로 생성.
  주인공을 부각하고 싶을 때만 예외를 명시 (예: "DAJEONG is slightly in front and slightly larger as the focal character")
  Negative: `size mismatch between characters, one character oversized, one character undersized` (예외 지정 시에는 제외)
- 3~4명이 동시에 등장하는 씬에서는 각 캐릭터의 위치를 한 줄씩 짧게 지정하는 걸 권장 (좌석표만큼 엄격할 필요는 없음)
  예: `DAJEONG on the left pointing at the board, BUNSEOK in the center holding a book, GIBUN on the right smiling and waving.`

---

## 작성 요령 (교육 서비스 반영 + 원본 시행착오 요약)

- **가이드/설명 컷**은 캐릭터가 무언가를 가리키거나(pointing), 들고 있거나(holding/presenting), 설명하는(explaining) 포즈를 Scene 문장에 명시한다.
- **텍스트 자리는 항상 "완전히 빈 상태"로 명시** — Critical conditions와 Negative 양쪽에 중복 기재해야 텍스트 생성 시도가 억제된다 (원본의 "3중 방어" 원칙: 블록 내 강조 + Critical + Negative).
- 초등학생 대상이므로 **무섭거나 날카로운 요소는 공통 Negative에 상시 포함**.
- 2D는 앱/웹 UI에 맞춰 플랫 벡터, 3D는 굿즈용 무광 피규어로 완전히 다른 렌더 모듈 — Style 섹션에서 한쪽만 선택해서 사용, 섞지 않는다.
- 주인공(핵심 액션을 하는 캐릭터) 먼저 서술하고 배경은 나중에 — 순서가 바뀌면 주인공이 생성에서 빠지는 경향 (원본 실측).
- 캐릭터를 가구 위에 올리지 않는다 → "All characters stand on the FLOOR" + Negative `character on desk/furniture`.
- **중복 캐릭터 방지**: 소품(탈것 등)에 탄 캐릭터 주변에 같은 캐릭터가 작게 한 번 더 생기는 버그가 관찰됨. → Critical conditions 맨 앞에 "1 A + 1 B + 1 C + 1 D = N명" 식 덧셈 문장을 넣고 Negative에 `duplicate character, second {NAME}, cloned character`를 구체적으로 추가.
- **소품이 캐릭터 몸 색에 묻히는 문제**: 소품 색이 들고 있는 캐릭터의 몸 색과 비슷하면 소품이 잘 안 보인다. → 소품 색을 캐릭터 몸 색과 대비되는 색으로 명시하고, 크기 기준을 "머리 너비만큼" 처럼 숫자/비유로 제시.

---

## 비율/사이즈

용도마다 다르므로 고정 기본값을 두지 않는다 — **씬마다 실제 배치될 화면 크기를 프롬프트에 명시**한다.

- **팝업**: `1280x800` (기본값으로 자주 씀 — 약 8:5 비율)
- 그 외(앱 일러스트, SNS, 굿즈 등)는 실제 배치되는 화면/인쇄 크기를 그때그때 확인해서 지정
- 프롬프트 Camera/Composition 섹션에 `Target output size: {WxH}` 한 줄로 명시해두면 좌우 여백·인물 크기 배분이 그 비율에 맞게 잡힘

---

## 완료된 결정 사항 (요약)
- 텍스트 영역은 말풍선 등 특정 모양을 강제하지 않고 **위치·대략 크기만 지정한 빈 영역**으로 처리
- 학습 소품 5종(선물 상자·책·연필·별·트로피) 프롭 블록 확정 (위 섹션)
- 비율/사이즈는 씬마다 지정, 팝업만 `1280x800` 기본값 사용
