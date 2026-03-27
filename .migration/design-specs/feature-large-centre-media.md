# feature-large-centre-media

Centered section with eyebrow, heading, description, a large video/image embed, and a CTA button below.

## Source Components
- `component-1774569214208-821` (booking) - "Large image or video block" with YouTube embed and "Book Now" button

## Structure Tree
```
CustomSection (colorScheme="dark", backgroundColor="base", paddingVertical="4xl", paddingHorizontal="xl", maxContentWidth="2xl")
  Heading (level="h3", text=eyebrow, alignX="center", size="xs")    [eyebrow]
  Heading (level="h2", text=heading, alignX="center")
  SimpleText (text=description, alignX="center", size="md")
  Video (type="youtube", id=videoId, title=videoTitle)
  ButtonGroup (alignX="center")
    Button (text, link, variant="tertiary", iconName="arrow-right", iconPosition="after")
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| eyebrow | string | "Eyebrow Heading" | From h3 eyebrow |
| heading | string | "Large image or video block" | From h2 heading |
| description | string | "Have a strong visual element..." | From paragraph text |
| videoType | string | "youtube" | From video embed type |
| videoId | string | "" | From YouTube video ID |
| videoTitle | string | "" | For accessibility |
| buttonText | string | "Book Now" | From CTA button |
| buttonLink | string | "/booking/" | From CTA href |

## Variations
Single source component. Could support both Video and Image as the media element (the name suggests flexibility). For now, the source uses a YouTube video.

## Extracted Styles

| Element | Property | Source Value | Toolkit Mapping |
|---------|----------|-------------|-----------------|
| container | background-color | rgb(27, 27, 29) | backgroundColor="base" |
| container | text-align | center | alignX="center" |
| h2 | font-size | ~39px | Default h2 |
| h3 (eyebrow) | text-transform | uppercase | Custom CSS eyebrow |
| h3 (eyebrow) | letter-spacing | 4px | Custom CSS eyebrow |
| video embed | aspect-ratio | widescreen (16:9) | Video component handles this natively |
| video embed | width | ~80% of section | Max-width constraint or custom CSS |
| button | variant | outline | variant="tertiary" |

## CSS Notes
- The video embed takes up most of the section width but not the full width - appears to be ~80% or constrained within the content max-width
- Video component (lite-youtube) handles the embed natively with responsive sizing
- CTA button is centered below the video
- Simple centered layout - headings, description, media, button all centered
- If an Image is used instead of Video, the Image component with aspectRatio="widescreen" would work
