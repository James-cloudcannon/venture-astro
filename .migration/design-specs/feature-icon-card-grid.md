# feature-icon-card-grid

Centered section with eyebrow, heading, description, followed by a 3-column grid of icon cards. Each card has an icon, eyebrow, heading, and description. CTA button below the grid.

## Source Components
- `component-1774569210444-812` (booking) - "An icon card grid" with 3 puzzle-piece icon cards

## Structure Tree
```
CustomSection (colorScheme="dark", backgroundColor="surface", paddingVertical="4xl", paddingHorizontal="xl", maxContentWidth="2xl")
  Heading (level="h3", text=eyebrow, alignX="center", size="xs")    [eyebrow]
  Heading (level="h2", text=heading, alignX="center")
  SimpleText (text=description, alignX="center", size="md")
  Grid (layout="start", minItemWidth=280, gap="md")
    [For each card in items:]
      GridItem
        Card (colorScheme="dark", backgroundColor="base", paddingHorizontal="lg", paddingVertical="lg")
          Icon (name=iconName, size="2xl")
          Heading (level="h4", text=cardEyebrow, size="xs")        [card eyebrow]
          Heading (level="h3", text=cardHeading, size="md")
          Text (text=cardDescription)
  ButtonGroup (alignX="center")
    Button (text, link, variant="tertiary", iconName="arrow-right", iconPosition="after")
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| eyebrow | string | "Bite-Sized Information" | From h3 section eyebrow |
| heading | string | "An icon card grid" | From h2 section heading |
| description | string | "Sometimes you only need..." | From section description |
| cards | array | [{iconName, cardEyebrow, cardHeading, cardDescription}] | From 3 card items |
| buttonText | string | "Another optional button!" | From CTA button |
| buttonLink | string | "#" | From CTA href |

## Variations
Single source component. Card count variable via array.

## Extracted Styles

| Element | Property | Source Value | Toolkit Mapping |
|---------|----------|-------------|-----------------|
| container | background-color | rgb(59, 59, 61) | backgroundColor="surface" |
| card | background-color | darker (#1b1b1d or #2b2b2d) | Card backgroundColor="base" in dark theme |
| card | border-radius | none visible | Card rounded=false |
| icon | size | ~32px | Icon size="2xl" (2.25rem = 36px) |
| icon | color | white/inherit | Icon color="default" |
| h4 (card eyebrow) | text-transform | uppercase | Custom CSS eyebrow |
| h4 (card eyebrow) | letter-spacing | 4px | Custom CSS eyebrow |
| h3 (card heading) | font-size | ~24px | Heading size="md" |
| grid | columns | 3 | Grid minItemWidth=280 |
| grid | gap | ~24px | Grid gap="lg" |
| section button | variant | outline | variant="tertiary" |

## CSS Notes
- Very similar to feature-image-card-grid but with icons instead of images
- Cards use base background color, section uses surface - creating darker cards on lighter section
- Icon is positioned top-left within the card (default alignment)
- Card eyebrow follows the same uppercase + letter-spacing pattern
- The CTA button below the grid is centered
- Cards have generous internal padding (lg on both axes)
