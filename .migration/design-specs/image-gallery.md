# image-gallery

Centered section with eyebrow and heading, followed by a 3-column grid of images with rounded corners, and a "Load more" CTA button.

## Source Components
- `component-1774569016914-23` (index) - "Image Gallery" with 6 images in 3x2 grid

## Structure Tree
```
CustomSection (colorScheme="dark", backgroundColor="surface", paddingVertical="5xl", paddingHorizontal="xl", maxContentWidth="2xl")
  Heading (level="h3", text=eyebrow, alignX="center", size="xs")    [eyebrow]
  Heading (level="h2", text=heading, alignX="center")
  Grid (layout="start", minItemWidth=300, gap="md")
    [For each image in items:]
      GridItem
        Image (source, alt, aspectRatio="portrait", rounded=true)
  ButtonGroup (alignX="center")
    Button (text, link, variant="tertiary", iconName="arrow-down", iconPosition="after")
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| eyebrow | string | "A Simple Gallery" | From h3 eyebrow |
| heading | string | "Image Gallery" | From h2 heading |
| images | array | [{source, alt}] | From grid of images (6 in source) |
| buttonText | string | "Load more" | From CTA button |
| buttonLink | string | "#" | From CTA href |

## Variations
Single source component. Image count is variable (array).

## Extracted Styles

| Element | Property | Source Value | Toolkit Mapping |
|---------|----------|-------------|-----------------|
| container | background-color | rgb(59, 59, 61) | backgroundColor="surface" |
| container | text-align | center | alignX="center" on headings |
| h2 | font-size | 39.056px | Default h2 size |
| h3 (eyebrow) | text-transform | uppercase | Custom CSS eyebrow |
| h3 (eyebrow) | letter-spacing | 4px | Custom CSS eyebrow |
| images | border-radius | visible rounded corners | Image rounded=true (16px radius) |
| images | aspect-ratio | portrait-ish (~3:4) | aspectRatio="portrait" |
| grid | gap | visible ~16px gap | Grid gap="md" (1rem) |
| grid | columns | 3 columns | Grid minItemWidth=300 with layout="start" |

## CSS Notes
- Images have rounded corners (Image rounded=true applies 16px radius)
- Grid uses 3 columns at desktop, should collapse to 2 then 1 on mobile
- Grid layout="start" with minItemWidth=300 will create auto-fill columns that approximate 3 columns at 1280px content width
- The "Load more" button has a down-arrow icon rather than right-arrow
- Images appear to use portrait aspect ratio (~3:4)
