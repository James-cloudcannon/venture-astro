# hero-banner

Simple centered banner section with eyebrow, large h1 heading, and description text on dark background. No image, no CTA. Used as a page title/intro banner.

## Source Components
- `component-1774569159482-93` (terms-and-conditions) - "Terms and conditions" page title banner

## Structure Tree
```
CustomSection (colorScheme="dark", backgroundColor="base", paddingVertical="5xl", paddingHorizontal="xl", maxContentWidth="2xl")
  Heading (level="h3", text=eyebrow, alignX="center", size="xs")    [eyebrow]
  Heading (level="h1", text=heading, alignX="center", size="2xl")
  SimpleText (text=description, alignX="center", size="lg")
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| eyebrow | string | "Eyebrow Heading" | From h3 eyebrow |
| heading | string | "Terms and conditions" | From h1 heading |
| description | string | "Description text to complement the block." | From paragraph text |

## Variations
Single source component. No variations.

## Extracted Styles

| Element | Property | Source Value | Toolkit Mapping |
|---------|----------|-------------|-----------------|
| container | background-color | rgb(27, 27, 29) | backgroundColor="base" in dark theme |
| container | padding | generous vertical (~96px+) | paddingVertical="5xl" (6rem) or "6xl" (7rem) |
| container | text-align | center | alignX="center" on all elements |
| h1 | font-size | ~49px | size="2xl" (3.75rem = 60px) - heading level h1 default is 2xl anyway |
| h1 | color | rgb(249, 249, 251) | --color-text-strong |
| h3 (eyebrow) | text-transform | uppercase | Custom CSS eyebrow |
| h3 (eyebrow) | letter-spacing | 4px | Custom CSS eyebrow |
| h3 (eyebrow) | color | rgb(217, 217, 220) | --color-text (slightly dimmer than heading) |
| description | color | rgb(217, 217, 220) | --color-text |

## CSS Notes
- Very simple component - just centered text on dark background
- Eyebrow uses the same uppercase + letter-spacing pattern as all other components
- No buttons, no images, no grid elements
- Uses SimpleText for description (single paragraph with size control) rather than Text (block-level markdown)
- The description text appears slightly larger than body default, use size="lg"
