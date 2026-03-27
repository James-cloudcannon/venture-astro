---
_schema: default
title: Booking | Venture
description: ''
pageSections:
  - _component: page-sections/heroes/hero-split
    eyebrow: Tag or label headline
    heading: A hero for a booking form page
    description: >-
      Here are a few options to use above the fold. Customize these elements to
      display your products or services in the best way possible.
    buttonText: Add an optional button
    buttonLink: /
    image:
      source: /src/assets/images/9asRE9UOKJ-800.jpeg
      alt: Person wearing a black hat and smiling
    colorScheme: inherit
    backgroundColor: none
  - _component: page-sections/info-blocks/centre-form
    eyebrow: Eyebrow Heading
    heading: Booking form
    description: Invite your customers to get in touch with you.
    formFields:
      - _component: building-blocks/forms/input
        label: Full name
        name: full_name
        type: text
        placeholder: John Smith
        required: true
        value:
        iconName:
        iconPosition: before
      - _component: building-blocks/forms/input
        label: Email address
        name: email
        type: email
        placeholder: mybusiness@example.com
        required: true
        value:
        iconName:
        iconPosition: before
      - _component: building-blocks/forms/input
        label: Phone number
        name: phone
        type: tel
        placeholder: 123 456 78910
        required: false
        value:
        iconName:
        iconPosition: before
      - _component: building-blocks/forms/date
        label: Choose a date
        name: choose_a_date
        required: true
        value:
        min:
        max:
      - _component: building-blocks/forms/textarea
        label: Message
        name: message
        required: false
        placeholder: Any helpful information we should know about.
        value:
      - _component: building-blocks/forms/submit
        text: Book Now
        variant: tertiary
        size: md
        iconName: arrow-right
        iconPosition: after
        hideText: false
        disabled: false
    formAction: /
    colorScheme: inherit
    backgroundColor: surface
  - _component: page-sections/features/feature-faq
    eyebrow: Eyebrow Heading
    heading: A simple text block for your FAQs
    items:
      - question: How do I use the service?
        answer: >-
          Customers want to know all the information before making a final
          decision. Make sure you provide it to them.
      - question: How do I pay for the service?
        answer: Let your customers know if they can pay by EFTPOS or credit card.
    colorScheme: inherit
    backgroundColor: none
  - _component: page-sections/features/feature-icon-card-grid
    eyebrow: Bite-sized information
    heading: An icon card grid
    description: >-
      Sometimes you only need a small amount of text. An icon section within a
      card grid is a great option to showcase your content.
    cards:
      - iconName: puzzle-piece
        cardEyebrow: icon card
        cardHeading: Heading
        cardDescription: >-
          These versatile cards can be used to talk about your services or
          products, or anything else you are keen to share with your audience.
      - iconName: puzzle-piece
        cardEyebrow: icon card
        cardHeading: Heading
        cardDescription: >-
          These versatile cards can be used to talk about your services or
          products, or anything else you are keen to share with your audience.
      - iconName: puzzle-piece
        cardEyebrow: icon card
        cardHeading: Heading
        cardDescription: >-
          These versatile cards can be used to talk about your services or
          products, or anything else you are keen to share with your audience.
    buttonSections:
      - _component: building-blocks/core-elements/button
        text: Another optional button!
        hideText: false
        link: /
        iconName: arrow-right
        iconPosition: after
        variant: tertiary
        size: md
    colorScheme: inherit
    backgroundColor: surface
  - _component: page-sections/features/feature-large-centre-media
    eyebrow: Eyebrow Heading
    heading: Large image or video block
    description: >-
      Have a strong visual element you want to share? This component gives you
      the flexibility to either add a YouTube video or an image.
    videoType: youtube
    videoId: gVUloujNd_I
    videoTitle: ''
    buttonText: Book Now
    buttonLink: /#booking-form
    colorScheme: inherit
    backgroundColor: none
---
