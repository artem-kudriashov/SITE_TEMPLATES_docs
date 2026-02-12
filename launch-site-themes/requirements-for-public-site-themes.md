# Requirements for public Site themes

All Site themes built for publishing must meet the list of requirements described below before submitting for technical review.

### Text localization

**Lightspeed eCom (Ecwid)** officially supports **English**, **French**, and **Dutch** languages. Although more languages are available in the control panel of E-Series, you are only required to keep your localization requirements for three official languages:

* The main dev store for developing themes must be in **English**.
* Any documentation provided with the theme must be available in official languages.
* The description of the theme or any non-name words inside the theme name must be available in official languages.
* All settings for your custom sections users can see in Instant Site Editor must be available in the three official languages.
* Any major updates to the theme should be referenced in a changelog available in official languages. The changelog can be published on your side or in the theme description visible in the website editor.
* When displaying product prices, themes must use the correct currency symbol or currency code and support any active advanced discounts and "Compare to" prices.

{% hint style="info" %}
Find the actual product price in the `defaultDisplayedPriceFormatted` field available with the [Get Product](https://app.gitbook.com/s/G9n5VxMY9T0Ob3D56PSD/rest-api/products/get-product) call.
{% endhint %}

### Storefront availability

Requirements for website design ensure Ecwid users do not miss website functionality and their customers can navigate storefronts without problems.

* The following storefront elements must be available directly or through the menu on all pages: Cart icon, Search bar, "Sign in" link, Legal Pages links, and supported languages list/selector.
* All storefront elements should have sufficient contrast — 4.5:1 or better as per W3C AA standards.
* All storefront elements must be properly aligned.
* Any text fields added by the theme must be able to handle long text values.
* The website design must be responsive and optimized for mobile view: button and text sizes should adjust automatically to make mobile navigation easier.

If the app has several themes, every theme must:

* Use different color palettes.
* Have a configured navigation bar with working links (categories, website sections).
* Use some of your custom sections. In total, all of your custom sections must be used in at least one theme file.
* Have its own preview store, where merchants can check its feels and looks.

### Instant Site Editor

Requirements for the Instant Site Editor ensure that users have great UX while building websites:

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
