# feature-split

Split layout section with content on one side (eyebrow, heading, description, button) and image on the other. Content and image sides can be swapped.

## Source Components
- `component-1774568782999-293` (index) - Image left, content right: "A component to showcase your brand"
- `component-1774568787663-170` (index) - Content left, image right: testimonial quote "Their customer service is second to none."

## Structure Tree
```
CustomSection (colorScheme="dark", backgroundColor="base", paddingVertical="none", paddingHorizontal="none")
  Split (distributionMode="half", verticalAlignment="stretch", gap="none", reverse={reverse})
    [first column - content]
      Card (colorScheme="dark", backgroundColor="base", paddingHorizontal="2xl", paddingVertical="2xl")
        Heading (level="h3", text=eyebrow, size="xs")          [eyebrow]
        Heading (level="h2", text=heading)
        Text (text=description)
        ButtonGroup (alignX="start")
          Button (text, link, variant="tertiary", iconName="arrow-right", iconPosition="after")
    [second column - image]
      Image (source, alt, background=true)
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| eyebrow | string | "Tag or label headline" | From h3 eyebrow |
| heading | string | "A component to showcase your brand" | From h2 heading |
| description | string | "Description text..." | From paragraph text |
| buttonText | string | "Book now" | From CTA button |
| buttonLink | string | "/booking/" | From CTA href |
| image | object | {source, alt} | From split image |
| reverse | boolean | false | false=image left/content right, true=content left/image right |

## Variations
- **component-293**: Image on LEFT, content on RIGHT (reverse=false in Split means first=content, but here image is first so we need to put image in first slot and content in second, OR use reverse=true with content first)
  - Actually: Looking at the screenshots, component-293 has image LEFT, text RIGHT. Component-170 has text LEFT, image RIGHT. The Split first/second columns map to left/right. So we need the content to be placeable in either column.
  - Solution: `reverse` prop swaps which side gets the image vs content. When reverse=false, first=image, second=content. When reverse=true, first=content, second=image.
- **component-170**: Has a testimonial-style quote instead of a standard heading. The heading text is the quote itself with the attribution as the description. Same structural pattern though.

## Extracted Styles

| Element | Property | Source Value | Toolkit Mapping |
|---------|----------|-------------|-----------------|
| container | height | 700px | Split with verticalAlignment="stretch", min-height via CSS |
| container | background-color | transparent | CustomSection with no explicit bg (inherits dark) |
| h2 (heading) | font-size | 39.056px | Heading level="h2" default (2.875rem = 46px) or size="lg" (2.25rem = 36px). Closest: default h2 |
| h2 (heading) | color | rgb(217, 217, 220) = #d9d9dc | --color-text (not --color-text-strong). Custom CSS or theme adjustment |
| h3 (eyebrow) | font-size | 16px | Heading size="xs" (1.125rem = 18px) - close enough |
| h3 (eyebrow) | text-transform | uppercase | Custom CSS eyebrow class |
| h3 (eyebrow) | letter-spacing | 4px | Custom CSS eyebrow class |
| h3 (eyebrow) | color | rgb(217, 217, 220) | --color-text |
| p | font-size | 16px | Text default md |
| button | border-radius | 0px | Theme override --radius-xs: 0 |
| button | background | transparent | variant="tertiary" |
| split image | height | 700px | verticalAlignment="stretch" fills height |

## CSS Notes
- No gap between split columns (gap="none" on Split is not a valid value - use gap="xs" and set custom `--grid-spacing: 0`)
- Actually, looking at the toolkit: gap smallest is "xs" = 0.25rem. Need custom CSS to set gap to 0.
- The content side needs vertical centering of its text block - use Card with vertical padding to center, or flex centering
- Eyebrow pattern: `text-transform: uppercase; letter-spacing: 4px; font-size: 1rem` - reusable across all components
- Image fills the full height of the split with object-fit: cover (Image background=true handles this)
- The content column has internal padding (~80-100px) managed by the Card wrapper
- Section has no outer padding (CustomSection paddingVertical="none")
- Split has gap="xs" with custom override to 0
