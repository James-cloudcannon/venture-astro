# open-text

Full-width centered section with a heading followed by long-form rich text content (multiple sections, sub-headings, paragraphs). Used for legal/policy pages.

## Source Components
- `component-1774569160918-607` (terms-and-conditions) - "Provide all the necessary information" with extensive legal text

## Structure Tree
```
CustomSection (colorScheme="dark", backgroundColor="base", paddingVertical="4xl", paddingHorizontal="xl", maxContentWidth="lg")
  Heading (level="h2", text=heading)
  Text (text=bodyContent)
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| heading | string | "Provide all the necessary information." | From h2 heading |
| bodyContent | string | (long markdown text) | From rich text body - multiple paragraphs, sub-headings, lists |

## Variations
Single source component. The body content is a rich text field that can contain any markdown.

## Extracted Styles

| Element | Property | Source Value | Toolkit Mapping |
|---------|----------|-------------|-----------------|
| container | background-color | rgb(27, 27, 29) | backgroundColor="base" |
| container | padding | 96px vertical | paddingVertical="5xl" |
| h2 | font-size | ~39px | Default h2 |
| h2 | font-weight | 700 | Default bold |
| h2 | text-align | start | Default left-aligned |
| body text | font-size | 16px | Text default md |
| body text | line-height | 24px (1.5) | Default body line-height |
| body text | color | rgb(217, 217, 220) | --color-text |

## CSS Notes
- Very simple component structurally - just heading + rich text block
- Text component handles the markdown rendering (sub-headings within the rich text become h3/h4 elements)
- Content max-width should be constrained to ~768px (maxContentWidth="lg") for readability
- The rich text content in the source is very long (full terms and conditions document)
- No eyebrow, no buttons, no grid - simplest possible content section
- Left-aligned text (not centered like the banner above it)
