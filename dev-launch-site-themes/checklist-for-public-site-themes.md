# Checklist for public Site themes

All Site themes eligible for publishing must meet our minimum technical and design requirements. We prepared a checklist so you can self-review your theme before submitting it to the Ecwid API team.

Checklist includes both technical and design requirements:

* [ ] Structural stability
* [ ] Text localization
* [ ] Image tolerance and quality
* [ ] Storefront availability
* [ ] Storefront performance

Find the detailed checklists for each section below.&#x20;

### Structural stability&#x20;

Ensure your themes look good with different content or without any in some places. Structural stability requirements ensure themes are ready for real merchants — each with their own unique content.

* [ ] Theme grids and layouts keep shape under real content.
* [ ] Columns don’t jump, spacing stays balanced.
* [ ] No section breaks when text or image changes.
* [ ] Long/short headlines don’t break layout.
* [ ] CTAs fit both short and long labels.
* [ ] Descriptions can be minimal or rich — no overflow.

### Merchant-friendly text rules

Store owners should be able to deduce the functionality of your sections/themes from the design, without reading any smaller texts. At the same time, all texts and headings must have a meaning and a clear structure.

* [ ] No Lorem Ipsum or meaningless filler text.
* [ ] Tone stays neutral and broadly usable (no slang, niche language, cultural assumptions, hype tone).
* [ ] Headings concise; paragraphs short (2–4 lines).
* [ ] CTAs are action-based (“Shop Now”, “Learn More”, no jokes or long phrases).
* [ ] Clean hierarchy: a clear primary heading structure, consistent use of large and secondary headings (H1/H2/H3), and well-structured paragraphs.
* [ ] Optional content must be clearly labeled (“Optional: Add a subtitle”).
* [ ] No fictional brand identity, invented stories, jokes, rhymes, or over-personalized copy. Keep the fictional brand narrative short and easy to replace.

### Text localization

**Lightspeed eCom (Ecwid)** officially supports **English**, **French**, and **Dutch**. Although more languages are available in the control panel of E-Series, you are only required to keep your localization requirements for the three official languages:

* [ ] The main dev store for developing themes must be in **English**.
* [ ] All theme descriptions and documentation are available in official languages.
* [ ] All settings for your custom sections users can see in Instant Site Editor must be available in the three official languages.
* [ ] When displaying product prices, themes must use the correct currency symbol or currency code and support any active advanced discounts and "Compare to" prices.

{% hint style="info" %}
Find the actual product price in the `defaultDisplayedPriceFormatted` field available with the [Get Product](https://app.gitbook.com/s/G9n5VxMY9T0Ob3D56PSD/rest-api/products/get-product) call.
{% endhint %}

* [ ] Any major updates to the theme should be referenced in a changelog available in official languages.\
  \
  The changelog can be published on your side or in the theme description visible in the website editor.

### Image tolerance and quality

Real customers will most certainly replace default images with their own. Therefore, your sections/themes must support any user images, even if low-quality ones, with different proportions and styles.

* [ ] The theme should work with images of different proportions (1:1, 3:4, 16:9), different colors, and styles.
* [ ] When default images are changed, theme elements like product cards must keep their proportions and alignment.&#x20;
* [ ] Theme layout and design survives not-the-best-quality photos (phone-shot, inconsistent ratios and lightning, etc.).

### Storefront availability

Requirements for website design ensure Ecwid users do not miss website functionality and their customers can navigate storefronts without problems.

* The following storefront elements must be available directly or through the menu on all pages: Cart icon, Search bar, "Sign in" link, Legal Pages links, and supported languages list/selector.
* All storefront elements should have sufficient contrast — 4.5:1 or better as per W3C AA standards.
* All storefront elements must have a visible focus state.
* No color-only meaning.
* The website design must be responsive and optimized for mobile view: button and text sizes should adjust automatically to make mobile navigation easier.

Full typography Reference: [https://www.w3.org/WAI/WCAG21/quickref/](https://www.w3.org/WAI/WCAG21/quickref/)

### Instant Site Editor

Themes must provide users of Instant Site editor with a stable and thorough UX:

* All settings have titles, descriptions, and placeholder texts where possible. Such texts should explain the setting clearly and in a detailed manner.
* All colors in section settings must be customizable through section design settings.
* Design and content settings inside your section should have a clear outline and categorization.
* If the app has several themes, every theme must have a clear screenshot for the Instant Site Editor listing (`cover_image` attribute inside the theme file).

### Storefront performance

All themes must meet performance requirements to ensure that applying the theme doesn't slow down the website.

* All sections used in the theme must be W3C validated. Link to the validator: [https://validator.w3.org/](https://validator.w3.org/)
* Google PageSpeed score should be **above 70**, preferably in the **Pass** category. Link to the PageSpeed Insights: [https://pagespeed.web.dev/](https://pagespeed.web.dev/)
* The theme and its sections must not cause any errors in the browser console upon rendering. This includes warning messages on JS or HTML errors.
* If the theme adds structured data, there should not be any Google Structured Data errors in it. Link to the Structured Data test tools: [https://developers.google.com/search/docs/appearance/structured-data](https://developers.google.com/search/docs/appearance/structured-data)
