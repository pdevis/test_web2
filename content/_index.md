---
title: 'Home'
date: 2023-10-24
type: landing

design:
  # Default section spacing
  spacing: "6rem"

sections:
  - block: hero
    content:
      title: CoMet
      text: Uncertainties made easy!
      primary_action:
        text: Get Started
        url: user-guide/getting-started
        icon: rocket-launch
      # secondary_action:
      #   text: Read the docs
      #   url: https://docs.hugoblox.com
      announcement:
        text: "For the latest updates"
        link:
          text: "click here"
          url: "latest-news/"
    design:
      spacing:
        padding: [300, 100, 300, 100]
        margin: [0, 0, 0, 0]
      # For full-screen, add `min-h-screen` below
      css_class: "dark"
      background:
        color: "navy"
        image:
          # Add your image background to `assets/media/`.
          filename: background.jpg
          filters:
            brightness: 0.5
  # - block: stats
  #   content:
  #     items:
  #       - statistic: "1M+"
  #         description: |
  #           Websites built  
  #           with Hugo Blox
  #       - statistic: "10k+"
  #         description: |
  #           GitHub stars  
  #           since 2016
  #       - statistic: "3k+"
  #         description: |
  #           Discord community  
  #           for support
    # design:
    #   # Section background color (CSS class)
    #   css_class: "bg-gray-100 dark:bg-gray-900"
    #   # Reduce spacing
    #   spacing:
    #     padding: ["1rem", 0, "1rem", 0]
  - block: cta-image-paragraph
    id: about
    content:
      items:
        - title: Community Metrology Toolkit
          text: An open-source software project for assessing data uncertainties.
          feature_icon: check
          features:
            - "Handle, propagate & store measurement uncertainties"
            - "Take into account error-correlation information"
          # Upload image to `assets/media/` and reference the filename here
          image: build-website.png
          caption: 'Image credit: [**Unsplash**](https://unsplash.com)'
          button:
            text: Learn More
            url: about/
            icon: rocket-launch
  - block: features
    id: tools
    content:
      title: Tools
      text: A list of tools which abstract away the complexity of dealing with uncertainties.
      items:
        - name: punpy
          icon: punpy
          icon_pack: custom
          description: propagates uncertainties on input quantities through any python function, evaluating the uncertainty on the output
          url: tools/punpy     
        - name: obsarray
          icon: obsarray
          icon_pack: custom
          description: an extension to xarray for defining, storing and interfacing with uncertainty and measurement error-covariance information in NetCDF files using standardised metadata
          url: tools/obsarray
        - name: comet_maths
          icon: comet_maths
          icon_pack: custom
          description: useful mathematical algorithms, including interpolation with uncertainties
          url: tools/comet_maths
    design:
    #   # Section background color (CSS class)
      css_class: "bg-gray-100 dark:bg-gray-900"

  # - block: buttons
  #   content:
  #     buttons:
  #       - title: comet_maths
  #         icon: code-bracket
  #         url: tools/comet_maths
  #       - title: punpy
  #         icon: star
  #         url: tools/punpy
  #       - title:  obsarray
  #         icon: sparkles
  #         url:  tools/obsarray
          
    design:
    #   # Section background color (CSS class)
      css_class: "bg-gray-100 dark:bg-gray-900"

  - block: cta-image-paragraph
    id: examples
    content:
      items:
        - title: Exploring the possibilities!
          text: CoMet can be used to
          feature_icon: bolt
          features:
            - "Propagate uncertainties"
            - "Handle error-correlation/error-covariance matrices"
            - "Create digital effects tables"
            - "Validate measurements"
          # Upload image to `assets/media/` and reference the filename here
          image: coffee.jpg
          caption: 'Image credit: [**Unsplash**](https://unsplash.com)'
          button:
            text: More applications
            url: user-guide/examples/
            icon: rocket-launch
---
