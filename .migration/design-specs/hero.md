# hero

Full-width hero section with background image, dark overlay, eyebrow heading, large h1, and outline CTA button.

## Source Components
- `component-1774568778080-172` (index) - Barista photo background, "Empower your business" heading

## Structure Tree
```
CustomSection (colorScheme="dark", backgroundImage={source, alt}, paddingVertical="5xl", paddingHorizontal="3xl", maxContentWidth="2xl")
  Heading (level="h3", text=eyebrow, alignX="start")         [eyebrow]
  Heading (level="h1", text=heading, size="2xl", alignX="start")
  ButtonGroup (alignX="start")
    Button (text, link, variant="tertiary", iconName="arrow-right", iconPosition="after")
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| eyebrow | string | "A Small Business Template" | From h2 eyebrow text in source |
| heading | string | "Empower your business..." | From h1 heading text |
| backgroundImage | object | {source, alt} | From full-bleed background photo |
| buttonText | string | "Our services" | From CTA button label |
| buttonLink | string | "/" | From CTA button href |

## Variations
Only one source component. No variations to handle.

## Extracted Styles

| Element | Property | Source Value | Toolkit Mapping |
|---------|----------|-------------|-----------------|
| container | background-color | rgb(59, 59, 61) | colorScheme="dark", backgroundColor="surface" |
| container | font-family | Lato, sans-serif | Theme font override |
| container | padding-top/bottom | 0px (image fills) | paddingVertical="5xl" (content area needs generous padding) |
| h2 (eyebrow) | font-size | 16px | Heading level="h3", size not set (use default h3 sizing would be too large, use size="xs") |
| h2 (eyebrow) | text-transform | uppercase | Custom CSS: `.eyebrow { text-transform: uppercase; }` |
| h2 (eyebrow) | letter-spacing | 4px | Custom CSS: `.eyebrow { letter-spacing: 4px; }` |
| h2 (eyebrow) | font-weight | 700 | Heading default bold |
| h2 (eyebrow) | color | rgb(249, 249, 251) | --color-text-strong (dark theme) |
| h1 | font-size | 48.832px | Heading size="2xl" (3.75rem = 60px desktop) - close match |
| h1 | font-weight | 700 | Default heading weight |
| h1 | font-family | Lato, serif | Theme heading font override |
| h1 | color | rgb(249, 249, 251) | --color-text-strong |
| button (a) | padding | 16px 12px | Button size="md" default |
| button (a) | border-radius | 0px | Custom CSS override on .button-inner |
| button (a) | background-color | transparent | Button variant="tertiary" |
| button (a) | font-weight | 700 | Button default semibold (600), needs override to 700 |
| button (a) | gap | 8px | Button default gap |

## CSS Notes
- Eyebrow heading needs custom class for `text-transform: uppercase` and `letter-spacing: 4px` - this is a site-wide pattern
- Button border-radius should be 0px (square corners) across the entire site - override `--radius-xs` to `0` in theme
- The background image needs a dark overlay - use CustomSection backgroundImage with the image, plus a CSS pseudo-element or overlay div for the dark tint
- Content is positioned in the lower-left area of the hero; use `display: flex; flex-direction: column; justify-content: flex-end; min-height: 70vh` on the content wrapper
- Max content width for the text block appears to be ~566px based on computed h1 width
