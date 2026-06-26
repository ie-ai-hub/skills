---
name: ie-brand
description: >
  Apply IE University's corporate brand, design system, and digital accessibility standards to any output —
  UI components, HTML/CSS code, documents, presentations, emails, images, or any digital asset.
  Use this skill whenever you are creating, reviewing, or auditing anything for IE University:
  if the request mentions IE University visuals, colors, fonts, tokens, logo, brand, design system,
  corporate identity, accessibility compliance, WCAG, European Accessibility Act, or simply asks to
  "follow IE style" or "use IE brand". This skill encodes the full IE University design system
  (colors, typography, tokens, logo) and the mandatory accessibility requirements
  (WCAG 2.1 AA and EU Directive 2019/882). Always apply it when generating IE-branded content,
  even if the user does not explicitly ask for "brand compliance" or "accessibility".
---

# IE Brand — IE University Design System

This skill ensures all outputs conform to IE University's corporate identity and comply with
**WCAG 2.1 Level AA** and the **European Accessibility Act (EU Directive 2019/882)**,
mandatory for digital services from 28 June 2025.

## Quick Reference

| | Value |
|---|---|
| Primary color | `#000066` (Ocean Blue) |
| Main font | Montserrat (UI/interface) |
| Editorial font | PT Serif |
| Logo (default) | [Logo_Corporate_Blue_Filled.svg](https://static.ie.edu/IT/logos/Corporate/Logo_Corporate_Blue_Filled.svg) |
| Min contrast (normal text) | **4.5:1** |
| Min contrast (large text) | **3:1** |

---

## 1. Logo

Always use the **Blue Filled** variant on white or light grey backgrounds.
Use the **Full White** variant on dark or Ocean Blue (`#000066`) backgrounds.
Prefer **SVG** format; use PNG as a fallback.

**Minimum size:** When the logo appears at the top of a web page, email, or any corporate communication, its height must be at least **60px** (or `4rem` using a 16px base). Never render it smaller in those contexts.

| Variant | Format | URL |
|---|---|---|
| Blue Filled *(default)* | SVG | `https://static.ie.edu/IT/logos/Corporate/Logo_Corporate_Blue_Filled.svg` |
| Blue Filled | PNG | `https://static.ie.edu/IT/logos/Corporate/Logo_Corporate_Blue_Filled.png` |
| White + Blue | SVG | `https://static.ie.edu/IT/logos/Corporate/Logo-white-blue.svg` |
| White + Blue | PNG | `https://static.ie.edu/IT/logos/Corporate/Logo-white-blue.png` |
| Full White | SVG | `https://static.ie.edu/IT/logos/Corporate/Logo_Corporate_Full_White_Filled.svg` |
| Full White | PNG | `https://static.ie.edu/IT/logos/Corporate/Logo_Corporate_Full_White_Filled.png` |

Always add meaningful `alt` text or `aria-label` when embedding the logo.
Decorative-only logos use `alt=""`.

---

## 2. Color

### 2.1 Corporate Palette

| CSS Token | Name | Hex | Use |
|---|---|---|---|
| `--color-primary-oceanblue` | Ocean Blue | `#000066` | Primary brand, buttons, headings |
| `--color-primary-seablue` | Sea Blue | `#47BFFF` | Accent only — **never use for text** |
| `--color-secondary-marineblue` | Marine Blue | `#0032A0` | Deep accent, headings |
| `--color-secondary-marineblue2` | Marine Blue 2 | `#0000A0` | Deep accent |
| `--color-secondary-electricblue` | Electric Blue | `#0000DB` | Strong interactive accent |
| `--color-secondary-lightblue` | Light Blue | `#BDE8FF` | Surfaces, backgrounds |

### 2.2 Greys

| CSS Token | Name | Hex | Use |
|---|---|---|---|
| `--color-grey-ieblack` | IE Black | `#0F0F0F` | **Primary text** on all backgrounds |
| `--color-grey-darkgrey` | Dark Grey | `#434445` | Secondary text |
| `--color-grey-middlegrey` | Middle Grey | `#888A8C` | Placeholders, disabled |
| `--color-grey-lightgrey` | Light Grey | `#BFC1C3` | Borders, inactive UI |
| `--color-grey-softgrey` | Soft Grey | `#F8F8F8` | Soft page backgrounds |
| `--color-grey-iewhite` | IE White | `#F4F4F4` | Page backgrounds |
| `--color-grey-white` | White | `#FFFFFF` | Base background |

### 2.3 School Colors

| CSS Token | School | Hex |
|---|---|---|
| `--color-school-business` | IE Business School | `#0097DC` |
| `--color-school-law` | IE Law School | `#D90011` |
| `--color-school-archdesign` | IE School of Architecture & Design | `#921AD4` |
| `--color-school-snt` | IE School of Science & Technology | `#6DC201` |
| `--color-school-sntdark` | S&T Dark | `#1F3700` |
| `--color-school-spega` | IE School of Politics, Economics & Global Affairs | `#60080F` |
| `--color-school-humanities` | IE School of Humanities | `#FF5C00` |

Each school logo uses its corresponding color for section backgrounds and accents.

> **School logo URLs** — each school has its own logo family (Default, Accent negative, Full color, Full color negative) in both horizontal and vertical orientations. See `references/school-logos.md` for the complete URL list. Always choose the variant whose contrast works against the intended background, following the same light/dark rules as the corporate logo.

### 2.4 Semantic / Status Colors

| CSS Token | Hex | Use |
|---|---|---|
| `--color-semantic-accept` | `#23CE6B` | Success (always pair with text + icon) |
| `--color-semantic-alert` | `#F31233` | Error/alert (always pair with text + icon) |
| `--color-semantic-lemonyellow` | `#FBCA1E` | Warning |
| `--color-semantic-tangerine` | `#FF7B31` | Special / highlight |
| `--color-semantic-winered` | `#7E1103` | Special |
| `--color-semantic-iceblue` | `#E6F7FF` | Info background |
| `--color-semantic-alumniblue` | `#1B1A43` | Alumni contexts |
| `--color-semantic-midnight` | `#23207E` | Dark accent |

### 2.5 Validated Contrast Pairs

These combinations have been pre-validated against WCAG AA requirements.

| Foreground | Background | Ratio | Result |
|---|---|---|---|
| `#0F0F0F` | `#FFFFFF` | 19.17:1 | ✅ Normal & large text |
| `#0F0F0F` | `#F4F4F4` (IE White) | ~17:1 | ✅ Normal & large text |
| `#0F0F0F` | `#F8F8F8` (Soft Grey) | ~17:1 | ✅ Normal & large text |
| `#000066` | `#FFFFFF` | 17.62:1 | ✅ Normal & large text |
| `#0032A0` | `#FFFFFF` | 10.69:1 | ✅ Normal & large text |
| `#0000DB` | `#FFFFFF` | 10.38:1 | ✅ Normal & large text |
| `#434445` | `#FFFFFF` | ~8.5:1 | ✅ Normal & large text |
| `#47BFFF` | `#FFFFFF` | 2.07:1 | ❌ Fails — do not use for text |
| `#BFC1C3` | `#FFFFFF` | 1.81:1 | ❌ Fails — do not use for text |
| `#23CE6B` | `#FFFFFF` | 2.08:1 | ❌ Fails — do not use for text |
| `#F31233` | `#FFFFFF` | 4.25:1 | ❌ Fails AA for normal text |

**Default text rule:** Use `#0F0F0F` for body text on white/light grey backgrounds.
For headings, you may alternate between `#0F0F0F` and `#000066`.
Never use Sea Blue (`#47BFFF`) as a text color.

---

## 3. Typography

### 3.1 Primary: Montserrat
All UI, navigation, buttons, labels, and interface content.
Fallback stack: `"Montserrat", Arial, Helvetica, sans-serif`

**Headings**

| Style | Size | Line-height | Weight | Use |
|---|---|---|---|---|
| H1 | 64px | 65px | 500 | Hero / main page title |
| H2 | 48px | 55px | 500 | Section heading |
| H3 | 36px | 40px | 500 | Sub-section |
| H4 | 24px | 26px | 500 | Module / block |

**Body**

| Style | Size | Line-height | Weight | Token suffix |
|---|---|---|---|---|
| Body XL | 22px | 30px | 400 / 700 | `body-xl` |
| Body L | 20px | 28px | 400 / 700 | `body-l` |
| Body M | 18px | 26px | 400 / 700 | `body-m` |
| Body S | 16px | 24px | 400 / 700 | `body-s` ← **minimum for main content** |
| Body XS | 14px | 20px | 400 / 700 | `body-xs` |

**UI Components**

| Component | Size | Weight | Use |
|---|---|---|---|
| Title XL | 22px / 700 | 700 | Module title |
| Title L | 18px | 700 | Sub-module title |
| Title M | 16px | 700 | Block label |
| Title S | 14px | 700 | Compact heading |
| Button Small | 11px | 800 | Compact button |
| Button Medium | 13px | 800 | Standard button |
| Button Large | 15px | 800 | Primary CTA |
| Label Small | 11px | 500 | Compact label |
| Label Medium | 12px | 500 | Standard label |
| Label Large | 14px | 500 | Extended label |
| Label XL | 16px | 500 | Featured label |
| Nav S | 11px | 800 | Compact navigation |
| Nav M | 13px | 800 | Standard navigation |
| Link S | 11px | 400 | Support link |
| Link M Regular | 13px | 400 | Standard link |
| Link M Strong | 14px | 600 | Emphasized link |
| Link L | 18px | 600 | Featured link |
| Tabs | 12px | 700 | Tab navigation |

### 3.2 Secondary: PT Serif
Reserved for editorial and long-form reading contexts.
Fallback stack: `"PT Serif", Georgia, 'Times New Roman', serif`

| Style | Size | Line-height | Weight |
|---|---|---|---|
| H1 | 64px | 70px | 400 / 700 |
| H2 | 48px | 60px | 400 / 700 |
| H3 | 36px | 45px | 400 / 700 |
| H4 | 24px | 30px | 400 / 700 |
| Body XL | 22px | 30px | 400 / 700 |
| Body L | 20px | 30px | 400 / 700 |
| Body M | 18px | 26px | 400 / 700 |
| Body S | 16px | 24px | 400 / 700 |
| Body XS | 14px | 140% | 400 / 700 |
| Body XXS | 13px | 140% | 400 / 700 |

### 3.3 Typography Rules
- Body text in main content must never go below **16px**
- Never apply `text-transform: uppercase` on long paragraphs
- Never skip heading levels (H1 → H3 without H2 is invalid)
- Apply correct CSS fallback fonts to all font-family declarations

---

## 4. Design Tokens

The system uses three layers:

1. **Base tokens** — atomic values: colors, sizes, weights, spacing, font families
2. **Semantic tokens** — define usage context: headings, body, buttons, states
3. **Component level** — components consume only semantic tokens, never raw values

Token files are in `ie_university_design_tokens.json` (source of truth) and
`ie_university_design_tokens.css` (ready-to-use CSS variables).

### CSS Usage Pattern
```css
/* Import or copy the :root block from ie_university_design_tokens.css */
body {
  font-family: var(--typography-fontfamilies-primary), Arial, Helvetica, sans-serif;
  font-size: var(--typography-primary-body-s-fontsize, 16px);
  line-height: var(--typography-primary-body-s-lineheight, 24px);
  color: var(--color-grey-ieblack);
  background-color: var(--color-grey-white);
}

.btn-primary {
  font-family: var(--typography-fontfamilies-primary);
  font-weight: var(--typography-fontweights-extrabold); /* 800 */
  background-color: var(--color-primary-oceanblue);
  color: var(--color-grey-white);
}
```

### React Pattern
```tsx
// Map CSS classes to semantic tokens — never inline raw values
export function PrimaryButton({ children }: { children: React.ReactNode }) {
  return <button className="btn-primary">{children}</button>;
}
```

### Token Rules
- Never use raw hex values inside components — always reference a token
- Never set manual px sizes when an equivalent token exists
- Components consume semantic tokens, not base tokens directly
- Update tokens first, then update components — never the other way round

---

## 5. Accessibility — WCAG 2.1 AA & EU 2019/882

### 5.1 Contrast Minimums (WCAG 1.4.3 / 1.4.11)
- **Normal text** (< 18px regular or < 14px bold): **4.5:1 minimum**
- **Large text** (≥ 18px regular or ≥ 14px bold): **3:1 minimum**
- **Non-text UI elements** (icons, input borders, focus rings, interactive state indicators): **3:1 minimum**

### 5.2 Pre-Publish Checklist

Run this checklist before delivering any IE University digital output:

- [ ] **Heading hierarchy** — H1 → H2 → H3, no skipped levels
- [ ] **Form labels** — every `<input>` has a programmatically associated `<label>`; never rely on placeholder text alone
- [ ] **Contrast** — every text/background pair validated (see §2.5)
- [ ] **Keyboard navigation** — all interactive elements reachable and operable without a mouse
- [ ] **Focus indicator** — visible, consistent, and not obscured
- [ ] **Color independence** — state or meaning is never communicated by color alone (always add text or icon)
- [ ] **Error states** — include text description + icon + color (three signals, never just one)
- [ ] **200% zoom** — content reflows, no loss of content or horizontal overflow
- [ ] **Touch targets** — all interactive targets ≥ 24×24 CSS px (WCAG 2.5.8)
- [ ] **Images of text** — avoided except for logos or truly essential cases
- [ ] **Text spacing** — layout does not break when user adjusts line-height, letter-spacing, or word-spacing
- [ ] **Alt text** — all meaningful images have descriptive `alt`; purely decorative images use `alt=""`
- [ ] **ARIA** — all controls expose correct `name`, `role`, and `value` to assistive technologies

### 5.3 Key WCAG Criteria Reference

| Criterion | Requirement |
|---|---|
| 1.4.3 Contrast (Minimum) | 4.5:1 normal text / 3:1 large text |
| 1.4.4 Resize Text | Content usable at 200% zoom |
| 1.4.5 Images of Text | Avoid text in images (logo exceptions apply) |
| 1.4.10 Reflow | No horizontal scroll at 320 CSS px wide |
| 1.4.11 Non-text Contrast | 3:1 for UI component borders and states |
| 1.4.12 Text Spacing | Layout survives user text-spacing overrides |
| 2.1.1 Keyboard | Full keyboard operability — no mouse required |
| 2.4.7 Focus Visible | Focus indicator always visible |
| 2.4.11 Focus Not Obscured | Focus not hidden by sticky elements |
| 2.5.8 Target Size (Minimum) | 24×24 CSS px minimum touch target |
| 3.3.1 Error Identification | Errors described in text |
| 3.3.2 Labels or Instructions | Instructions clear before form submission |
| 4.1.2 Name, Role, Value | Controls compatible with assistive technology |

### 5.4 Vendor / Procurement Requirements

When a third-party tool or service is being evaluated or procured:
- Require WCAG 2.2 AA declaration of conformity
- Request VPAT or ACR (Accessibility Conformance Report) for software or SaaS
- Require evidence of keyboard, screen reader, and 200% zoom testing
- Request a list of exceptions with a remediation plan and timeline
- Include accessibility as a formal acceptance criterion at delivery
- Require that version updates preserve conformance or document any regression

---

## 6. Summary Rules

1. **Logo** — Blue Filled SVG on light backgrounds; Full White on dark/Ocean Blue backgrounds
2. **Text colors** — use `#0F0F0F` for body, `#000066` or `#0032A0` for headings; never `#47BFFF` for text
3. **Fonts** — Montserrat for UI, PT Serif for editorial; minimum 16px for main body text
4. **Tokens** — always use design tokens; never hardcode hex values or px sizes
5. **Contrast** — validate every text/background pair before output (see validated pairs in §2.5)
6. **Accessibility** — run the §5.2 checklist on every deliverable
7. **Error & status states** — always three signals: text + icon + color
8. **Governance** — token changes propagate to components; components never drive token values
