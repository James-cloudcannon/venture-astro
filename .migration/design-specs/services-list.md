# services-list

Centered section with eyebrow, heading, description, followed by grouped price list items (product/service name with dotted separator and price), and a CTA button.

## Source Components
- `component-1774568785406-861` (index) - "List your services or products" with 2 groups of 3 items each

## Structure Tree
```
CustomSection (colorScheme="dark", backgroundColor="surface", paddingVertical="4xl", paddingHorizontal="xl", maxContentWidth="lg")
  Heading (level="h3", text=eyebrow, alignX="center", size="xs")    [eyebrow]
  Heading (level="h2", text=heading, alignX="center")
  Text (text=description, alignX="center")
  [For each group in items array:]
    Heading (level="h4", text=groupHeading, alignX="center")
    [For each item in group.items:]
      custom price-list-item (label + separator + price)
  ButtonGroup (alignX="center")
    Button (text, link, variant="tertiary", iconName="arrow-right", iconPosition="after")
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| eyebrow | string | "Eyebrow Heading" | From h3 eyebrow |
| heading | string | "List your services or products" | From h2 heading |
| description | string | "Whether your business..." | From paragraph text |
| groups | array | [{heading, items: [{label, price}]}] | From price list structure |
| buttonText | string | "Book now" | From CTA button |
| buttonLink | string | "/booking/" | From CTA href |

## Variations
Single source component. The number of groups and items per group are variable (array props).

## Extracted Styles

| Element | Property | Source Value | Toolkit Mapping |
|---------|----------|-------------|-----------------|
| container | padding-top/bottom | 96px | paddingVertical="4xl" (5rem = 80px) - close, could use "5xl" (6rem = 96px) |
| container | background-color | rgb(59, 59, 61) | backgroundColor="surface" in dark theme |
| container | text-align | center | alignX="center" on text elements |
| h2 | font-size | 39.056px | Heading default h2 |
| h2 | text-align | center | alignX="center" |
| h3 (eyebrow) | text-transform | uppercase | Custom CSS |
| h3 (eyebrow) | letter-spacing | 4px | Custom CSS |
| h3 (eyebrow) | text-align | center | alignX="center" |

## CSS Notes
- The price list items are a custom pattern not covered by any building block. Each item is a flex row with:
  - Left: product/service name (text)
  - Middle: dotted separator line (flex: 1, border-bottom: dotted)
  - Right: price text
- This needs custom HTML/CSS within the page section. Use a `<dl>` or custom div structure
- The dotted separator uses `border-bottom: 1px dotted` with flex-grow to fill the space
- Group headings (h4) separate groups of items
- Content max-width appears to be ~768px based on layout
- Padding vertical is 96px = 6rem = "5xl"
