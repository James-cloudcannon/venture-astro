# split-contact-map

Split layout with an embedded map on the left and contact details on the right, including social media icons, heading, description, and icon+text contact info items. Optional CTA button.

## Source Components
- `component-1774569072945-771` (index) - Map left, contact info right, no CTA button
- `component-1774569191877-581` (contact) - Same layout but with "Contact us" CTA button at bottom

## Structure Tree
```
CustomSection (colorScheme="dark", backgroundColor="surface", paddingVertical="4xl", paddingHorizontal="xl")
  Split (distributionMode="half", verticalAlignment="center", gap="2xl")
    [first column - map]
      Embed (html=mapIframe, aspectRatio="square")
    [second column - contact info]
      List (items=socialIcons, direction="horizontal", listType="icon", size="lg")
      Heading (level="h2", text=heading)
      Text (text=description)
      [For each contact item:]
        List (items=[{iconName, text}], direction="vertical", listType="icon", size="md")
      ButtonGroup (alignX="start")                               [optional]
        Button (text, link, variant="tertiary", iconName="arrow-right", iconPosition="after")
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| heading | string | "A contact block" | From h2 heading |
| description | string | "This is a simple yet powerful..." | From paragraph text |
| mapEmbed | string | "<iframe...>" | From map embed HTML |
| socialLinks | array | [{iconName, link}] | From social media icon row (YouTube, Facebook, LinkedIn, X, Instagram) |
| contactItems | array | [{iconName, text}] | From 4 contact detail items (email, phone, address, hours) |
| buttonText | string | null | Optional CTA - present in contact page variant, absent in index |
| buttonLink | string | null | Optional CTA href |

## Variations
- **component-771** (index): No CTA button at bottom
- **component-581** (contact): Has "Contact us" outline button at bottom
- Difference handled by optional buttonText/buttonLink props (when null, ButtonGroup is not rendered)

## Extracted Styles

| Element | Property | Source Value | Toolkit Mapping |
|---------|----------|-------------|-----------------|
| container | background-color | rgb(59, 59, 61) | backgroundColor="surface" |
| h2 | font-size | ~39px | Default h2 |
| social icons | display | horizontal row with ~48px spacing | List direction="horizontal" |
| social icons | size | ~24px | Icon size="lg" |
| contact icons | display | circular outline borders | Custom CSS for circle border on icons |
| contact items | spacing | ~48px between items | Custom CSS or Spacer between items |
| map | aspect-ratio | roughly square | Embed aspectRatio="square" |

## CSS Notes
- Social media icons are displayed in a horizontal row at the top of the contact column
- Contact info items each have a circular outlined icon (like the icons in split-image-text-icon-grid) - border: 1px solid, border-radius: 9999px, padding
- The map embed fills the left column. It appears as a grey placeholder in the screenshot (map not loaded)
- Contact items are spaced with generous vertical gaps between them (~2-3rem)
- The social icons use filled SVG style (Icon component auto-detects social/ prefix icons)
- Each contact item is an icon+text pair arranged horizontally (icon left, text right)
- Use a List component for each contact item with icon list type, or custom flex layout
