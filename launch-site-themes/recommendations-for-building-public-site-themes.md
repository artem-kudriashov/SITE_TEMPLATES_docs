# Recommendations for building public Site themes

Use the following recommendations when building a public Site theme.

### Build multiple themes for different business niches

One theme can satisfy merchants from different verticals with little tweaks and adjustments. The functionality of themes allows you to incorporate completely different setups, layouts, sections, and design choices for creating multiple themes out of the built assets.

We recommend you to try combining default Ecwid sections with some of your custom-built ones and tailor your website theme for merchants of different verticals. For example, if the app has 20 sections in the Crane project, you can make the following 3 themes:

* **My Theme — Bikes**:\
  The `template-bike.ts` uses 6 of your custom sections + 2 default sections. It has images and content that showcase a bike store.
* **My Theme — Cosmetics**:\
  The `template-cosmetics.ts` uses 10 of your custom sections + 1 default section. Its images and content reflect a cosmetics store.
* **My Theme — Apparel**:\
  The `template-apparel.ts` uses 15 of your custom sections. It can have images and content for showcasing shoes or a clothing store.

Depending on the installed theme, the merchant will see different sections in the website Editor. However, regardless installed theme, all 20 custom sections that you built as part of the theme will be available to the merchant in the **Add section** menu.

The order and content available in the sections also depend on the currently installed theme. Installing a new theme overrides all sections and their content. After that, the merchant can rearrange sections and change the content and design settings provided you defined them in the `content.ts` and `design.ts` files for each section.

### Create bright preview stores for themes

Before publishing your themes app, you’ll need to create a preview store for each of your themes. These stores are available for merchants through the **Preview Theme** button in the website Editor. Setting up exciting preview stores is a great opportunity to encourage clients to start with your design.

Combine it with the previous recommendation, and you get a handful of bright previews for your work, that can attract merchants with different needs and verticals.

### Name your themes right

Following the focus on the business solutions rather than general design or colors, name your themes by their niche or use case and not by their color scheme or layout.

For example, names **My theme - Light** and **My theme - Dark** are considered bad as they don't cover the merchant's need for an apparel store. Names specific to the verticals, for example, **My theme - Bikes** and **My theme - Home decor**, will attract more clients.

We recommend using the following format for all theme names: **Brand/dev name - Theme vertical**.

This way, merchants can clearly define your themes among others or even search them by your brand.
