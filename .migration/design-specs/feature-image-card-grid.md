# feature-image-card-grid

Centered section with eyebrow, heading, description, followed by a 3-column grid of image cards. Each card has a photo on top with eyebrow, heading, and description text below.

## Source Components
- `component-1774569189282-132` (contact) - "An image card grid" with 3 cards

## Structure Tree
```
CustomSection (colorScheme="dark", backgroundColor="base", paddingVertical="4xl", paddingHorizontal="xl", maxContentWidth="2xl")
  Heading (level="h3", text=eyebrow, alignX="center", size="xs")    [eyebrow]
  Heading (level="h2", text=heading, alignX="center")
  SimpleText (text=description, alignX="center", size="md")
  Grid (layout="start", minItemWidth=280, gap="md")
    [For each card in items:]
      GridItem
        Card (colorScheme="dark", backgroundColor="surface", rounded=false, border=false)
          [beforeContentSections:]
            Image (source, alt, aspectRatio="landscape")
          [contentSections:]
            Heading (level="h4", text=cardEyebrow, size="xs")      [card eyebrow]
            Heading (level="h3", text=cardHeading, size="md")
            Text (text=cardDescription)
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| eyebrow | string | "Bite-Sized Information" | From h3 section eyebrow |
| heading | string | "An image card grid" | From h2 section heading |
| description | string | "These image cards combine..." | From section description |
| cards | array | [{image, cardEyebrow, cardHeading, cardDescription}] | From 3 card items |

## Variations
Single source component. Card count is variable (array prop).

## Extracted Styles

| Element | Property | Source Value | Toolkit Mapping |
|---------|----------|-------------|-----------------|
| container | background-color | rgb(27, 27, 29) | backgroundColor="base" |
| card body | background-color | darker than base (~#2b2b2d) | Card backgroundColor="surface" in dark theme |
| card | border-radius | slight rounding visible | Card rounded=false (or true with small radius) |
| card image | aspect-ratio | landscape (~4:3) | Image aspectRatio="landscape" |
| h4 (card eyebrow) | text-transform | uppercase | Custom CSS eyebrow |
| h4 (card eyebrow) | letter-spacing | 4px | Custom CSS eyebrow |
| h4 (card eyebrow) | font-size | ~14px | Heading size="xs" |
| h3 (card heading) | font-size | ~24px | Heading size="md" |
| grid | columns | 3 | Grid minItemWidth=280 |
| grid | gap | ~16px | Grid gap="md" |

## CSS Notes
- Cards use the Card component's beforeContentSections slot for the image (image sits above the padded content area)
- Card content area needs horizontal and vertical padding for the text content: paddingHorizontal="md", paddingVertical="md"
- Card eyebrow follows the same uppercase + letter-spacing pattern
- Cards have a slightly different background than the section (surface vs base in dark theme) creating visual separation
- No buttons on individual cards, no section-level CTA button
- The card images fill the full width of the card with no padding
