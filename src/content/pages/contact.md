---
title: Contact | Venture
pageSections:
  - _component: page-sections/heroes/hero-split
    colorScheme: inherit
    backgroundColor: none
    eyebrow: Eyebrow Heading
    heading: Contact us
    description: Add some description text to complement the block.
    image:
      source: /src/assets/images/a-rhUUAz0z-400.jpeg
      alt: Barber shop bench with tools sitting on it
    buttonText: Contact us
    buttonLink: /#contact-form
  - _component: page-sections/info-blocks/centre-form
    colorScheme: inherit
    backgroundColor: none
    eyebrow: Eyebrow Heading
    heading: Contact us
    description: Invite your customers to get in touch with you.
    formFields:
      - _component: building-blocks/forms/input
        label: Full name
        name: full_name
        type: text
        placeholder: John Smith
        required: true
        value: null
        iconName: null
        iconPosition: before
      - _component: building-blocks/forms/input
        label: Email address
        name: email
        type: email
        placeholder: mybusiness@example.com
        required: true
        value: null
        iconName: null
        iconPosition: before
      - _component: building-blocks/forms/textarea
        label: Message
        name: message
        placeholder: Leave your message here
        required: false
        value: null
      - _component: building-blocks/forms/submit
        text: Submit
        variant: tertiary
        size: md
        iconName: arrow-right
        iconPosition: after
        hideText: false
        disabled: false
    formAction: /
  - _component: page-sections/features/feature-image-card-grid
    colorScheme: inherit
    backgroundColor: none
    eyebrow: Bite-sized information
    heading: An image card grid
    description: These image cards combine a short written message and a strong visual image.
    cards:
      - image:
          source: /src/assets/images/24wk6smwSc-400.jpeg
          alt: Three people at a table laughing and using their laptops
        cardEyebrow: Eyebrow Heading
        cardHeading: Primary Heading
        cardDescription: These versatile cards can be used to talk about your services or products, or anything else you are keen to share with your audience.
      - image:
          source: /src/assets/images/YFM_NmeWPi-400.jpeg
          alt: Pouring milk into a coffee in a café
        cardEyebrow: Eyebrow Heading
        cardHeading: Primary Heading
        cardDescription: These versatile cards can be used to talk about your services or products, or anything else you are keen to share with your audience.
      - image:
          source: /src/assets/images/NW1Yy2Ujuv-400.jpeg
          alt: Person smiling at laptop
        cardEyebrow: Eyebrow Heading
        cardHeading: Primary Heading
        cardDescription: These versatile cards can be used to talk about your services or products, or anything else you are keen to share with your audience.
  - _component: page-sections/features/split-contact-map
    colorScheme: inherit
    backgroundColor: none
    heading: A contact block
    description: This is a simple yet powerful block to display not only your location by using OpenStreetMaps, but also any other contact details you wish to share with your customers.
    mapEmbed: ""
    socialLinks:
      - iconName: social/youtube
        link: https://www.youtube.com/
      - iconName: social/facebook
        link: https://www.facebook.com/
      - iconName: social/linkedin
        link: https://www.linkedin.com/
      - iconName: social/x
        link: https://www.twitter.com/
      - iconName: social/instagram
        link: https://www.instagram.com/
    contactItems:
      - iconName: envelope
        text: "Email address: mybusiness@example.com"
      - iconName: phone
        text: "Phone number: 312 325 326"
      - iconName: map-pin
        text: "Address: 1 Fake St, Faketown"
      - iconName: clock
        text: "Opening hours: 9-5pm, Monday to Friday"
    buttonSections:
      - _component: building-blocks/core-elements/button
        text: Contact us
        hideText: false
        link: /#contact-form
        iconName: arrow-right
        iconPosition: after
        variant: tertiary
        size: md
---
