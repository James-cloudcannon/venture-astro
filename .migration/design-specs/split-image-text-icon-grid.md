# split-image-text-icon-grid

Split layout with content side containing eyebrow, heading, a row of icon+text feature items, and CTA button. Image fills the other side.

## Source Components
- `component-1774569027180-267` (index) - "A featured icons block" with 3 circle icons (smiley, heart, sparkle) and labels, barber shop photo on right

## Structure Tree
```
CustomSection (colorScheme="dark", backgroundColor="base", paddingVertical="none", paddingHorizontal="none")
  Split (distributionMode="half", verticalAlignment="stretch", gap="xs")
    [first column - content]
      Card (colorScheme="dark", backgroundColor="base", paddingHorizontal="2xl", paddingVertical="2xl")
        Heading (level="h3", text=eyebrow, size="xs")              [eyebrow]
        Heading (level="h2", text=heading)
        Grid (layout="center", minItemWidth=80, maxItemWidth=120, gap="lg")
          [For each feature in items:]
            GridItem
              Icon (name=iconName, size="2xl", alignX="center")
              SimpleText (text=label, alignX="center", size="sm")
        ButtonGroup (alignX="start")
          Button (text, link, variant="tertiary", iconName="arrow-right", iconPosition="after")
    [second column - image]
      Image (source, alt, background=true)
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| eyebrow | string | "Let your features shine" | From h3 eyebrow |
| heading | string | "A featured icons block" | From h2 heading |
| items | array | [{iconName, label}] | From 3 icon+text feature items |
| buttonText | string | "Book Now" | From CTA button |
| buttonLink | string | "/booking/" | From CTA href |
| image | object | {source, alt} | From right-side photo |

## Variations
Single source component. Items count is variable (3 in source).

## Extracted Styles

| Element | Property | Source Value | Toolkit Mapping |
|---------|----------|-------------|-----------------|
| container | background-color | rgb(27, 27, 29) | backgroundColor="base" in dark theme |
| icons | display | inline with circular outline borders | Icon with custom CSS for circle border |
| icons | arrangement | horizontal row of 3 | Grid with small minItemWidth for horizontal layout |
| h2 | font-size | ~39px | Default h2 |
| h3 (eyebrow) | text-transform | uppercase | Custom CSS eyebrow |
| h3 (eyebrow) | letter-spacing | 4px | Custom CSS eyebrow |

## CSS Notes
- Icons in the source have circular outline borders (not filled backgrounds). The Icon component has `background` prop but it creates a filled background, not an outline circle. Need custom CSS: `border: 1px solid var(--color-text); border-radius: 9999px; padding: 0.75em;`
- The icon+label items are arranged horizontally in a row - use Grid with small item widths
- Content side has internal padding managed by Card wrapper
- Split has no gap between columns (same pattern as feature-split)
- Image fills full height with background=true
