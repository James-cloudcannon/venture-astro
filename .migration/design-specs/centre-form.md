# centre-form

Centered section with eyebrow, heading, optional description, and a contact/booking form with input fields and submit button.

## Source Components
- `component-1774569185588-352` (contact) - "Contact us" form with full name, email, message fields
- `component-1774569204907-698` (booking) - "Booking form" with full name, email, phone, date picker, message fields

## Structure Tree
```
CustomSection (colorScheme="dark", backgroundColor="surface", paddingVertical="4xl", paddingHorizontal="xl", maxContentWidth="lg")
  Heading (level="h3", text=eyebrow, alignX="center", size="xs")    [eyebrow]
  Heading (level="h2", text=heading, alignX="center")
  SimpleText (text=description, alignX="center", size="md")          [optional]
  Form (formBlocks=formFields)
    [For each field in formFields:]
      Input (label, name, type, placeholder, required)
      OR Textarea (label, name, placeholder, required)
    Submit (text=submitText, variant="tertiary", iconName="arrow-right", iconPosition="after")
```

## Props

| Prop | Type | Default | Derivation |
|------|------|---------|------------|
| eyebrow | string | "Eyebrow Heading" | From h3 eyebrow |
| heading | string | "Contact us" | From h2 heading |
| description | string | "Invite your customers..." | Optional description (present in contact, absent in booking - actually both have it) |
| formFields | array | [{type, label, name, placeholder, required}] | From form inputs |
| submitText | string | "Submit" | From submit button text |
| formAction | string | "/" | Form action URL |

## Variations
- **component-352** (contact): 3 fields (full name, email, message textarea), description present, submit says "Submit"
- **component-698** (booking): 5 fields (full name, email, phone, date picker, message textarea), no description text shown, submit says "Book Now"
- Field count varies - handled by formFields array
- The date picker field uses Input with type="date" and has a calendar icon (iconName="calendar", iconPosition="before")
- Both have a white horizontal bar element below the form fields and above the submit button - this appears to be a decorative Divider or Spacer

## Extracted Styles

| Element | Property | Source Value | Toolkit Mapping |
|---------|----------|-------------|-----------------|
| container | background-color | rgb(59, 59, 61) | backgroundColor="surface" |
| container | padding | ~96px vertical | paddingVertical="4xl" or "5xl" |
| container | text-align | center (headings) | alignX="center" on headings |
| h2 | font-size | ~39px | Default h2 |
| h2 | text-align | center | alignX="center" |
| h3 (eyebrow) | text-transform | uppercase | Custom CSS eyebrow |
| h3 (eyebrow) | letter-spacing | 4px | Custom CSS eyebrow |
| form inputs | border | 1px solid | Default Input border styling |
| form inputs | background | transparent | Dark theme form fields |
| form inputs | color | light text | Dark theme text color |
| submit button | variant | outline | variant="tertiary" |
| submit button | border-radius | 0px | Theme override |

## CSS Notes
- Form fields have transparent backgrounds with visible borders (matching the dark theme)
- The white horizontal bar below the form fields appears to be a decorative element - possibly a Divider with custom color override or a styled Spacer
- Submit button uses the same outline/tertiary style with arrow icon as all other buttons
- Form max-width is constrained to keep fields at a readable width (~600-700px)
- The form itself is centered within the section (Form has width: 100% and the section constrains via maxContentWidth)
- Input fields use the toolkit's Input component which handles label, placeholder, and validation
- The date field in the booking form has a calendar icon - use Input with iconName and type="date"
