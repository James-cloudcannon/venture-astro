# hero-split

Split hero section with content on the left (eyebrow, large h1, description, CTA button) and a full-height image on the right. Used as page-level hero banners.

## Source Components
- `component-1774569181162-11` (contact) - "Contact us" with barber shop mirror photo
- `component-1774569201469-591` (booking) - "A hero for a booking form page" with portrait photo, italic heading

## Structure Tree
```
CustomSection (colorScheme="dark", backgroundColor="base", paddingVertical="none", paddingHorizontal="none")
  Split (distributionMode="half", verticalAlignment="stretch", gap="xs")
    [first column - content]
      Card (colorScheme="dark", backgroundColor="base", paddingHorizontal="2xl", paddingVertical="2xl")
        Heading (level="h3", text=eyebrow, size="xs")              [eyebrow]
        Heading (level="h1", text=heading, size="2xl")
        Text (text=description)
        ButtonGroup (alignX="start")
          Button (text, link, variant="tertiary", iconName="arrow-right", iconPosition="after")
    [second column - image]
      Image (source, alt, background=true)
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| eyebrow | string | "Eyebrow Heading" | From h3 eyebrow |
| heading | string | "Contact us" | From h1 heading |
| description | string | "Add some description text..." | From paragraph text |
| buttonText | string | "Contact us" | From CTA button |
| buttonLink | string | "#" | From CTA href |
| image | object | {source, alt} | From right-side photo |

## Variations
- **component-11** (contact): Standard heading style, barber shop image
- **component-591** (booking): Heading appears italic ("A hero for a booking form page" in italic serif). Same structural layout.
- Both use h1 level heading with large size, content left, image right
- The heading font-style difference (italic vs normal) could be a prop or handled via markdown in the heading text

## Extracted Styles

| Element | Property | Source Value | Toolkit Mapping |
|---------|----------|-------------|-----------------|
| container | background-color | rgb(27, 27, 29) | backgroundColor="base" |
| container | padding | none (edge-to-edge) | paddingVertical="none", paddingHorizontal="none" |
| h1 | font-size | ~49px | size="2xl" |
| h1 | font-weight | 700 | Default bold |
| h1 | font-family | Lato, serif | Theme heading font |
| h3 (eyebrow) | text-transform | uppercase | Custom CSS eyebrow |
| h3 (eyebrow) | letter-spacing | 4px | Custom CSS eyebrow |
| button | border-radius | 0px | Theme override |
| button | variant | outline/transparent bg | variant="tertiary" |
| image | object-fit | cover | Image background=true |

## CSS Notes
- Structurally very similar to feature-split but uses h1 instead of h2 (hero-level heading)
- Content is vertically centered within the left column - Card padding provides this
- The booking variant heading appears to use italic font-style - this can be achieved via inline markdown in the heading text prop (*italic text*)
- Same zero-gap split pattern as feature-split
- Content side has generous internal padding (~80-100px horizontal, centered vertically)
- Image fills full height on the right side
- The left column content is positioned toward the bottom-center of the available space
