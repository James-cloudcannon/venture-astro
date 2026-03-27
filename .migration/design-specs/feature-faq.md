# feature-faq

Section with eyebrow, large heading, followed by a series of question-and-answer pairs. Questions are displayed as h3 headings with paragraph answers below.

## Source Components
- `component-1774569207217-73` (booking) - "A simple text block for your FAQs" with 2 Q&A pairs

## Structure Tree
```
CustomSection (colorScheme="dark", backgroundColor="base", paddingVertical="4xl", paddingHorizontal="xl", maxContentWidth="2xl")
  Heading (level="h3", text=eyebrow, size="xs")                    [eyebrow]
  Heading (level="h2", text=heading)
  [For each faq in items:]
    Spacer (size="xl")
    Heading (level="h3", text=question)
    Text (text=answer)
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| eyebrow | string | "Eyebrow Heading" | From h3 eyebrow |
| heading | string | "A simple text block for your FAQs" | From h2 heading |
| items | array | [{question, answer}] | From Q&A pairs (2 in source) |

## Variations
Single source component. Item count is variable.

## Extracted Styles

| Element | Property | Source Value | Toolkit Mapping |
|---------|----------|-------------|-----------------|
| container | background-color | rgb(27, 27, 29) | backgroundColor="base" |
| container | padding | ~96px vertical | paddingVertical="4xl" or "5xl" |
| h2 (main heading) | font-size | ~49px | size="2xl" or default h2 (2.875rem) |
| h3 (eyebrow) | text-transform | uppercase | Custom CSS eyebrow |
| h3 (eyebrow) | letter-spacing | 4px | Custom CSS eyebrow |
| h3 (question) | font-size | ~31px | Default h3 (2.25rem = 36px) - close enough |
| h3 (question) | font-weight | 700 | Default bold |
| h3 (question) | color | rgb(249, 249, 251) | --color-text-strong |
| p (answer) | font-size | 16px | Default md |
| p (answer) | color | rgb(217, 217, 220) | --color-text |

## CSS Notes
- This is essentially a simple stacked text layout, not an accordion (all Q&A pairs are visible)
- Could alternatively use the Accordion component for interactive collapse behavior, but the source shows all items expanded/visible
- Questions use h3 level but note the eyebrow also uses h3 - the eyebrow should use a smaller size override while questions use the default h3 size
- Spacing between Q&A pairs is generous (~2-3rem) - use Spacer between pairs
- Left-aligned text throughout (not centered)
- No buttons, no images, no cards
- Content is constrained to a readable width
