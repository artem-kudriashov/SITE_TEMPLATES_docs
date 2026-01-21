---
hidden: true
---

# Deep dive into theme project structure

{% hint style="info" %}
We **highly recommend** setting up a working example theme before jumping into this guide: [quickstart-with-a-site-theme-example.md](quickstart-with-a-site-theme-example.md "mention")
{% endhint %}

Congratulations on getting a working template example!&#x20;

Now that you have a theme project, follow us through this article, and you'll end up with an understanding of how theme apps work and which parts require your dev attention.&#x20;

Let's dive into its structure to answer the following questions:

* _Which files define user settings and default configurations?_
* _Where do you write the actual storefront code?_
* _How are user settings imported into the storefront?_

### How to make themes work

Instant Site theme is a **schema-driven rendering system** based on [Vue.js](https://vue.jshttps/vuejs.org/) and [TypeScript](https://www.typescriptlang.org/). So as a developer, you need to:

* Define user settings so users can customize your theme for their business needs.
* Build storefront blocks called sections.
* Combine several blocks into a theme.

Each of these functionalities lies within its own folder or specific files. Therefore, you need to work **on specific files** to extend the basic starting example into a highly customized theme.

To understand which files and folders you need, let's cover the basic folder structure of the project.

### Learn folder structure

You can find the following directories in any theme project:

* **`templates/`**: This folder holds theme files that define the structure of your site. Theme files in this folder do not contain the actual HTML code of the blocks, but rather the _configuration_ (the "DNA") that tells Ecwid the order in which sections should be loaded on different website pages.
* **`sections/`**: This folder contains building blocks of your theme. Every folder inside represents a drag-and-drop section in the Store Editor. They are self-contained, meaning they hold their own logic, styles, and settings schema.
* **`headers/`**  and **`footers/`**: These two folders define global `<head>` and `<footer>` sections that appear on every page. They follow the same file structure as `sections/`, but are assigned globally in the `configuration.ts` file.
* **`layouts/`**: Unlike sections (stacked one after another), layouts wrap the _entire content area_ of dynamic pages (like a Product Details page). They use special placeholders called "slots" to determine where the platform should inject dynamic content (like the product price, description, and "Add to Cart" button).
* **`shared/`**: To avoid repeating code, any logic (composables) or UI (components) used by more than one section is stored here. For example, if five different sections use a slider, the slider logic resides in `shared/composables/useCarousel.ts`.
* **`dist/, node_modules/, preview/`**: System folders required for building, running, and previewing the theme. Treat these as generated or dependency artifacts. **Do not modify them.**

Now that the folders are covered, we can jump into specific files.

### Project files that require dev attention

Any theme for Ecwid Instant Site technically is a combination of **sections**.

Each section is a reusable UI block with its own set of user settings, storefront implementation, and showcases for the Section/Theme Markets built into the Ecwid admin.

A typical section looks like this:

```
sections/my-section/
├─ MySection.vue
├─ client.ts
├─server.ts
├─type.ts
├─ settings/
├─ showcases/
└─ assets/

```

#### - `MySection.vue`

This is the **visual implementation** of the section. Visitors see this content on the website, and store owner's settings apply to it.

This file is written as a Vue Single File Component. It contains the template, styles, and component logic, but does **not** define any "user settings" (design/content settings available to the store owner).

What it does:

* Reads resolved content values
* Reads resolved design values
* Renders markup accordingly

What it does **not** do:

* Declare schemas
* Fetch data on the storefront
* Decide editor behavior

{% hint style="info" %}
Think of this file as a pure renderer. The configuration is already resolved when it runs.
{% endhint %}

Learn more about building section **Vue** files:

{% content-ref url="build-site-themes-project-structure/section-name.vue.md" %}
[section-name.vue.md](build-site-themes-project-structure/section-name.vue.md)
{% endcontent-ref %}

#### - `server.ts`

This file is the **server-side entrypoint** for the section.

Purpose:

* Register the section for server-side rendering
* Produce initial HTML

Characteristics:

* Runs in a Node environment
* Uses the section’s Vue component
* Is generic and usually very small

{% hint style="info" %}
Every section that renders on the server **must** have this file.
{% endhint %}

#### - `client.ts`

This file is the **browser entrypoint** for the section.

Purpose:

* Attach interactivity
* Enhance or hydrate server-rendered markup

Characteristics:

* Runs in the browser
* Uses the same Vue component as the server
* Assumes HTML already exists

{% hint style="info" %}
If your section has **no interactivity**, this file may be minimal — but the contract still exists.
{% endhint %}

#### - `type.ts`

This file connects **schemas** to **rendering code**.

Purpose:

* Derive TypeScript types from schemas
* Ensure rendering stays in sync with configuration

Typical responsibilities:

* Export `Content` type
* Export `Design` type

{% hint style="info" %}
This prevents schema drift. If the schema changes, TypeScript forces the UI to update.
{% endhint %}

#### - `settings/`

This directory defines **what can be customized**. Design and content settings defined in the files stored inside will be available to the store owner in the Ecwid admin UI.

```
settings/
├─ content.ts
├─ design.ts
└─ translations.ts

```

{% hint style="info" %}
These files are **schemas**, not implementations.
{% endhint %}

#### - `settings/content.ts`

Defines **editable content**. With these settings, store owners can tailor texts, images, etc., to their business needs.

For example, you can define customizable:

* Texts
* Images
* Buttons

{% hint style="info" %}
If some section content (like a text) is not declared as a setting here, it cannot be edited.
{% endhint %}

Learn more about available content settings:

{% content-ref url="build-site-themes-project-structure/content.ts.md" %}
[content.ts.md](build-site-themes-project-structure/content.ts.md)
{% endcontent-ref %}

#### - `settings/design.ts`

Defines **design controls**. With these, store owners can apply changes to the theme/section appearance on their website.

Examples:

* Colors
* Typography
* Spacing
* Visibility toggles
* Variants

{% hint style="info" %}
This exposes **design tokens**, not raw CSS.
{% endhint %}

Learn more about available design settings:

{% content-ref url="build-site-themes-project-structure/design.ts.md" %}
[design.ts.md](build-site-themes-project-structure/design.ts.md)
{% endcontent-ref %}

#### - `settings/translations.ts`

Defines **human-readable labels and descriptions** for schemas. Any texts shown in the Ecwid admin UI can have several translations, and this file sets these.

Used by:

* Editor UI
* Schema metadata

{% hint style="info" %}
All schema labels must be translated to all specified languages.
{% endhint %}

Learn more about adding translations to section settings:

{% content-ref url="build-site-themes-project-structure/translations.ts.md" %}
[translations.ts.md](build-site-themes-project-structure/translations.ts.md)
{% endcontent-ref %}

#### - `showcases/`

Showcases define **example instances** of a section. This folder is optional.

```
showcases/
├─ 1.ts
└─ translations.ts

```

Purpose:

* Provide preview data
* Show how the section looks with real values
* Populate galleries or demos

{% hint style="info" %}
Showcases are **not defaults**. They are merely examples shown when users select which section to add in the Ecwid admin UI.
{% endhint %}

Learn more about section showcases:

{% content-ref url="build-site-themes-project-structure/showcases-1.ts.md" %}
[showcases-1.ts.md](build-site-themes-project-structure/showcases-1.ts.md)
{% endcontent-ref %}

#### - `assets/`

Contains assets used by the section, for example:

* Default images
* Preview images
* Icons

Assets may be:

* Referenced by schemas (defaults)
* Used by showcases
* Imported by the Vue component

### Schema for an example theme

Use this example schema as a helping tool to ensure your project has all of the required files to function properly. &#x20;

```
my-theme-project/
├── crane.config.json                  # Links local code to the Ecwid/Lightspeed platform
├── package.json                       # Manages dependencies (Vue, Vite, Crane CLI)
├── dist/                              # Production build output (generated automatically)
│
├── templates/                         # THEME CONFIGURATION ("The Brain")
│   └── casual-clothes-template/       # Your specific theme folder
│       ├── configuration.ts           # Global settings: Name, Preview URL, Default Header/Footer IDs
│       └── pages/                     # Page-specific section configurations
│           ├── home.ts                # Defines section order for Homepage
│           ├── product.ts             # Defines section order for Product Details Page
│           └── catalog.ts             # Defines section order for Catalog/Grid Page
│
├── sections/                          # INDEPENDENT UI BLOCKS (Stacked vertically on pages)
│   └── hero-banner/                   # Example Section
│       ├── HeroBanner.vue             # The visual Vue component
│       ├── server.ts                  # SSR Entry: Renders static HTML for SEO
│       ├── client.ts                  # Client Entry: Hydrates HTML for interactivity
│       ├── type.ts                    # TypeScript types inferred from settings
│       ├── settings/                  # Editor Schema Configuration
│       │   ├── content.ts             # Data inputs (Text, Images, Links)
│       │   ├── design.ts              # Style inputs (Colors, Fonts, Spacing)
│       │   └── translations.ts        # Localization for Editor labels
│       └── showcases/                 # "Add Section" Presets
│           └── 1.ts                   # Default data for the first preset
│
├── layouts/                           # PAGE WRAPPERS (Wraps dynamic content)
│   ├── category/                      # Layout for Category pages
│   │   └── example-category/
│   │       ├── Main.vue               # Wrapper component using <slot> for product grid
│   │       └── settings/              # Settings for the layout background/padding
│   └── product/                       # Layout for Product pages
│
├── headers/                           # GLOBAL STORE HEADERS
│   └── store-header/                  # Follows same structure as sections
│       ├── CustomHeader.vue           # Main Header component
│       ├── components/                # Internal components (Navigation, Cart, Search)
│       │   ├── NavigationMenu.vue     #
│       │   └── Cart.vue               #
│       └── composables/               # Logic specific to this header (e.g., mobile toggle)
│
├── footers/                           # GLOBAL STORE FOOTERS
│   └── clothes-footer/                # Follows same structure as sections
│
├── shared/                            # SHARED UTILITIES (DRY Code)
│   ├── components/                    # UI used across multiple sections
│   │   └── SectionHeader.vue          # Standardized title/subtitle component
│   ├── composables/                   # Logic used across multiple sections
│   │   └── useCarousel.ts             # Slider state logic
│   └── utils/                         # Pure helper functions
│       └── colors.ts                  # Color conversion utilities
│
└── scripts/                           # DEVELOPER TOOLS
```

