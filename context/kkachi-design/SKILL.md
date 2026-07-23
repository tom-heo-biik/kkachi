---
name: kkachi-design
description: "까치의 디자인 시스템 스킬입니다. 컬러·타이포(Pretendard typo 스케일)·radius(squircle)·shadow·space 토큰과 버튼·토글 스위치·체크박스·라디오 컴포넌트 스펙(상태·모션 포함), 다크모드 TODO, 운용 규칙을 담고 있습니다. 까치의 UI를 구현하거나 디자인하는 맥락에서 반드시 읽고 사용합니다."
---

## Colors


### Brand Color
blue-subtle: 
#DAF0FF(L 0.944 · C 0.031 · H 237.5°)
blue-soft: 
#65C3FC(L 0.782 · C 0.121 · H 237.7°)
blue-vivid(PANTONE 2194 C): 
#0086D6(L 0.601 · C 0.154 · H 246.0°)
blue-standard: 
#00499B(L 0.419 · C 0.148 · H 256.9°)
blue-deep(PANTONE 2768 C): 
#071D49(L 0.245 · C 0.087 · H 262.0°)


### Neutral Color
neutral-0:   #FFFFFF(L 1.000 · C 0.000)
neutral-20:  #F8F8F8(L 0.979 · C 0.000)
neutral-50:  #EEEEEE(L 0.949 · C 0.000)
neutral-100: #DEDEDE(L 0.901 · C 0.000)
neutral-200: #BEBEBE(L 0.802 · C 0.000)
neutral-300: #9E9E9E(L 0.699 · C 0.000)
neutral-400: #808080(L 0.600 · C 0.000)
neutral-500: #636363(L 0.500 · C 0.000)
neutral-600: #484848(L 0.402 · C 0.000)
neutral-700: #2E2E2E(L 0.301 · C 0.000)
neutral-800: #161616(L 0.200 · C 0.000)
neutral-900: #030303(L 0.097 · C 0.000)


### Status Color
red-error(PANTONE 485 C): 
#DA291C(L 0.575 · C 0.213 · H 29.6°)
green-success(PANTONE 354 C): 
#00B140(L 0.662 · C 0.197 · H 147.0°)


## Typography (Pretendard)
typo-9: 48/900/1.1/-0.04em
typo-8: 40/800/1.2/-0.04em
typo-7: 32/700/1.3/-0.04em
typo-6: 28/600/1.4/-0.04em
typo-5: 24/600/1.5/-0.03em
typo-4: 20/500/1.6/-0.02em
typo-3: 16/500/1.6/-0.01em
typo-2: 14/400/1.6/0em
typo-1: 12/400/1.6/0.01em


## Radius (Squircle: https://github.com/bejarcode/cornerkit)
squircle-xsmall: radius 8 / smoothing 1.0
squircle-small: radius 12 / smoothing 1.0
squircle-medium: radius 16 / smoothing 1.0
squircle-large: radius 20 / smoothing 1.0
squircle-xlarge: radius 24 / smoothing 1.0


## Shadow
shadow-low: 0 1px 2px rgba(0, 134, 214, 0.04), 0 3px 6px rgba(7, 29, 73, 0.02)
shadow-mid: 0 2px 4px rgba(0, 134, 214, 0.08), 0 6px 12px rgba(7, 29, 73, 0.04)
shadow-high: 0 3px 6px rgba(0, 134, 214, 0.12), 0 9px 18px rgba(7, 29, 73, 0.06)


## Space
space-0: 0px
space-4: 4px
space-8: 8px
space-12: 12px
space-16: 16px
space-20: 20px
space-24: 24px
space-32: 32px
space-40: 40px


## Buttons


### Size
| Size | Height | Radius | Typography |
|---|---|---|---|
| sm | 44pt | squircle-small | typo-2 |
| md | 48pt | squircle-medium | typo-3 |
| lg | 52pt | squircle-large | typo-4 |


### Motion
| 타입 | Press-in | Press-out | Pressed scale | Easing | 사용 버튼 |
|---|---:|---:|---:|---|---|
| Primary motion | 160ms | 200ms | 0.98 | cubic-bezier(0, 0, 0.1, 1) | Primary |
| Secondary motion | 40ms | 50ms | 0.99 | cubic-bezier(0, 0, 0.1, 1) | Secondary |
| Soft motion | 80ms | 100ms | 0.985 | cubic-bezier(0, 0, 0.1, 1) | Soft |


### Action Buttons


#### Brand Buttons


##### Brand Primary Button
| 상태 | Background | Text | Border | Shadow |
|---|---|---|---|---|
| Default | blue-vivid `#0086D6` | neutral-0 `#FFFFFF` | transparent | shadow-high |
| Pressed | blue-standard `#00499B` | neutral-0 `#FFFFFF` | transparent | none |
| Loading | blue-standard `#00499B` | neutral-0 `#FFFFFF` | transparent | none |
Motion: Primary motion


##### Brand Secondary Button
| 상태 | Background | Text | Border | Shadow |
|---|---|---|---|---|
| Default | neutral-0 `#FFFFFF` | blue-vivid `#0086D6` | rgba(0, 134, 214, 0.22) | shadow-low |
| Pressed | blue-subtle `#DAF0FF` | blue-standard `#00499B` | transparent | none |
| Loading | blue-subtle `#DAF0FF` | blue-standard `#00499B` | transparent | none |
Motion: Secondary motion


##### Brand Soft Button
| 상태 | Background | Text | Border | Shadow |
|---|---|---|---|---|
| Default | blue-subtle `#DAF0FF` | blue-standard `#00499B` | transparent | shadow-low |
| Pressed | blue-soft `#65C3FC` | blue-deep `#071D49` | transparent | none |
| Loading | blue-soft `#65C3FC` | blue-deep `#071D49` | transparent | none |
Motion: Soft motion


#### Neutral Buttons


##### Neutral Primary Button
| 상태 | Background | Text | Border | Shadow |
|---|---|---|---|---|
| Default | neutral-800 `#161616` | neutral-0 `#FFFFFF` | transparent | shadow-high |
| Pressed | neutral-900 `#030303` | neutral-0 `#FFFFFF` | transparent | none |
| Loading | neutral-900 `#030303` | neutral-0 `#FFFFFF` | transparent | none |
Motion: Primary motion


##### Neutral Secondary Button
| 상태 | Background | Text | Border | Shadow |
|---|---|---|---|---|
| Default | neutral-0 `#FFFFFF` | neutral-800 `#161616` | neutral-100 `#DEDEDE` | shadow-low |
| Pressed | neutral-20 `#F8F8F8` | neutral-900 `#030303` | neutral-100 `#DEDEDE` | none |
| Loading | neutral-20 `#F8F8F8` | neutral-900 `#030303` | neutral-100 `#DEDEDE` | none |
Motion: Secondary motion


##### Neutral Soft Button
| 상태 | Background | Text | Border | Shadow |
|---|---|---|---|---|
| Default | neutral-20 `#F8F8F8` | neutral-800 `#161616` | transparent | shadow-low |
| Pressed | neutral-50 `#EEEEEE` | neutral-900 `#030303` | transparent | none |
| Loading | neutral-50 `#EEEEEE` | neutral-900 `#030303` | transparent | none |
Motion: Soft motion


#### Disabled Buttons
| 종류 | Background | Text | Border | Shadow |
|---|---|---|---|---|
| Brand Disabled | blue-subtle `#DAF0FF` | blue-soft `#65C3FC` | transparent | none |
| Neutral Disabled | neutral-50 `#EEEEEE` | neutral-300 `#9E9E9E` | transparent | none |


## Toggle Switch


### Shape
| 상태 | Track | Thumb | Track size | Thumb size |
|---|---|---|---|---|
| Off | neutral-100 `#DEDEDE` | neutral-0 `#FFFFFF` + shadow-low | 56×32 | 28 |
| On  | blue-vivid `#0086D6` | neutral-0 `#FFFFFF` + shadow-low | 56×32 | 28 |
Thumb travel: 24pt


### Motion
| 단계 | Duration | Delay | Easing | 효과 |
|---|---:|---:|---|---|
| Track | 200ms | 0 | (0, 0, 0.1, 1) | background |
| Thumb | 200ms | 0 | (0, 0, 0.1, 1) | translateX 0 → 24 |


## Checkbox


### Shape
| 상태 | Background | Check | Border | Size | Radius |
|---|---|---|---|---|---|
| Off | neutral-0 `#FFFFFF` | none | neutral-200 `#BEBEBE` 1.5 | 24×24 | squircle-xsmall |
| On  | blue-vivid `#0086D6` | neutral-0 `#FFFFFF` | transparent | 24×24 | squircle-xsmall |


### Motion
| 단계 | Duration | Delay | Easing | 효과 |
|---|---:|---:|---|---|
| Box fill | 200ms | 0 | (0, 0, 0.1, 1) | background · border |
| Bounce | 360ms | 0 | (0.34, 1.56, 0.64, 1) | scale 1 → 1.10 → 1 (peak @45%) |
| Draw | 240ms | 90ms | (0.5, 0, 1, 1) | stroke-dashoffset 28 → 0 |


## Radio


### Shape
| 상태 | Background | Border | Inner Dot | Size |
|---|---|---|---|---|
| Off | neutral-0 `#FFFFFF` | neutral-200 `#BEBEBE` 1.5 | none | 24×24 |
| On  | neutral-0 `#FFFFFF` | blue-vivid `#0086D6` 3 | blue-vivid `#0086D6` 10×10 | 24×24 |


### Motion
| 단계 | Duration | Delay | Easing | 효과 |
|---|---:|---:|---|---|
| Border | 200ms | 0 | (0, 0, 0.1, 1) | width 1.5 → 3, color neutral-200 → blue-vivid |
| Dot | 200ms | 0 | (0, 0, 0.1, 1) | scale 0 → 1, opacity 0 → 1 |


## Dark Mode (TODO)
다크모드 지원이 확정되었습니다(2026-07-24, kkachi-product 개인 탭의 화면 테마 참조 — 시스템/라이트/다크). 현재 토큰은 라이트 기준이므로 다크 토큰 세트(컬러 매핑, shadow 대응)가 필요합니다. 아직 제작 전입니다.


## 운용 규칙
컴포넌트 스펙은 운영자가 하나씩 확정해 이 문서에 추가합니다. 스펙이 아직 없는 컴포넌트(탭 바, 카드, 리스트, 입력창, 채팅 말풍선 등)는 위 토큰 범위 안에서 임시로 구현하되, 임의로 스펙을 확정해 이 문서에 적지 않습니다.