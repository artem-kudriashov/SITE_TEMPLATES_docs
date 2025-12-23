# template-name.ts

The `template-name.ts` file describes the pre-configured website layout and design for Instant Site users. Build the template by listing sections in the order they should appear on the storefront. There is no limitation on the number of sections you include in the template, but any template must have a header, footer, and at least one custom section.

The `template-name.ts` uses **Typescript** language and consists of two main entities called `metadata` and `sections`:

* `metadata` object defines the name and description of the template visible in the Instant Site Editor.
* sections array defines the actual content of the template. Sections order from this array is applied to the template when users install it.

### `Metadata`

It is an object with the following fields:

| Name                                                                                                   | Type   | Description                                                                                                                                                                                  |
| ------------------------------------------------------------------------------------------------------ | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| name                                                                                                   | string | <p>Template name displayed in the IS Editor.</p><p><br><strong>Required field</strong></p>                                                                                                   |
| description                                                                                            | string | <p>Template description displayed in the IS Editor.</p><p><br><strong>Required field</strong></p>                                                                                            |
| <p>cover_image{<br>  set{<br>    ORIGINAL{<br>      url: '<code>VALUE</code>'<br>    }<br>  }<br>}</p> | string | <p><code>VALUE</code> is the filename of the cover image used in the template. Place the image into the<code>/templates/assets/</code> folder.</p><p><br><strong>Optional field</strong></p> |

Code example:

```ts
  metadata: {
    name: 'My Template Name',
    description: 'My Template Description',
    cover_image: {
      set: {
        ORIGINAL: {
          url: 'template_cover_image.png',
        },
      }
    }
```

### `Sections`

It is an array of objects, where each object represents a specific section. Each section inside the array contains the following fields:

| Name         | Type   | Description                                                                                                                                                                                                                                                                                                                                                                                        |
| ------------ | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| type         | string | <p></p><p>Section type. Available values:</p><ul><li><code>default</code>: One of the default Ecwid sections.</li><li><code>custom</code>: One of the custom sections available in the same app.</li></ul><p><strong>Required field</strong></p>                                                                                                                                                   |
| id           | string | <p></p><p>Section ID. Value here depends on the section <code>type</code>:</p><ul><li><code>default</code> type: ID from the list of default Ecwid sections</li><li><code>custom</code> type: name of the section defined in the same app. You can find it in the package.json file or as a name of the sections <code>section-name</code> folder.</li></ul><p><strong>Required field</strong></p> |
| showcase\_id | string | <p>Specific showcase for the section. Both default and custom sections can have several showcases.</p><p><br><strong>Optional field</strong></p>                                                                                                                                                                                                                                                   |

Code example:

```ts
  sections: [
    {
      type: 'default',
      id: 'header'
    },
    {
      type: 'default',
      id: 'slider'
      showcase_id: '001',
    },
    {
      type: 'custom',
      id: 'example-section'
      showcase_id: '005',
    },
    {
      type: 'custom',
      id: 'favorite-images-section'
    },
    {
      type: 'default',
      id: 'footer'
    }
  ]
```

List of `default` sections:

| Type               | IDs                                                                                                                                                                                                                                                                                                                                                                    | Description                                                                                                                                                                                                                                     |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Cover              | `cover_002`, `cover_005`, `cover_007`, `cover_009`, `cover_010`, `cover_011`, `cover_012`, `cover_013`, `cover_014`, `cover_015`.                                                                                                                                                                                                                                      | Serves as a brief intro to the store's business and brand. It works best as the first section of the site and can be used to grab customers’ attention.                                                                                         |
| Announcement       | `announcement_bar_001`, `announcement_bar_002`, `announcement_bar_004`, `announcement_bar_005`, `announcement_bar_007`, `announcement_bar_008`                                                                                                                                                                                                                         | Adds a top bar to the website. Use it for announcements about promotions, sales, unique selling points, or store updates.                                                                                                                       |
| Store              | `store_002`, `store_003`, `store_004`, `store_005`, `store_006`                                                                                                                                                                                                                                                                                                        | Represents store catalog by highlighting a wide assortment, drawing customer attention to most actual collections, or bringing bestsellers into the spotlight.                                                                                  |
| Slider             | `slider_001`, `slider_002`                                                                                                                                                                                                                                                                                                                                             | Adds a carousel slider to promote special deals, discounts, or highlight your brand features.                                                                                                                                                   |
| Video              | `video_001`, `video_002`, `video_003`, `video_004`, `video_005`, `video_006`                                                                                                                                                                                                                                                                                           | Introduces store brand or a product via video. Use it to tell customers about store brand’s mission, show how the products are made or how to use them.                                                                                         |
| Special Offer      | `special_offer_007`, `special_offer_008`, `special_offer_009`, `special_offer_010`, `special_offer_011`, `special_offer_012`, `special_offer_013`, `special_offer_014`                                                                                                                                                                                                 | Adds a section to promote special offers, such as seasonal sales, discount coupons, or free delivery.                                                                                                                                           |
| Customer Review    | `customer_review_001`, `customer_review_002`, `customer_review_003`, `customer_review_004`, `customer_review_006`, `customer_review_007`, `customer_review_008`, `customer_review_009`, `customer_review_010`, `customer_review_011`                                                                                                                                   | Use this section to demonstrate feedback store customers have shared about its products and services. Customer reviews are a good way to gain potential customers’ trust.                                                                       |
| Company Info       | `company_info_001`, `company_info_003`, `company_info_004`, `company_info_009`, `company_info_013`, `company_info_014`, `company_info_015`, `company_info_016`, `company_info_017`, `company_info_018`, `company_info_019`, `company_info_020`, `company_info_021`, `company_info_022`, `company_info_023`, `company_info_024`, `company_info_025`, `company_info_026` | Use this section to show why store business stands out from the competition: describe production process, show the benefits of products, or write about the history of the company.                                                             |
| Delivery & payment | `shipping_payment_001`, `shipping_payment_002`, `shipping_payment_003`, `shipping_payment_005`, `shipping_payment_006`, `shipping_payment_007`                                                                                                                                                                                                                         | This section contains information about delivering orders and accepting payments. Use it to tell about shipping and payment methods available, delivery services the store works with, return policies, and provide any other relevant details. |
| Location           | `location_001`, `location_002`, `location_003`, `location_004`, `location_005`, `location_006`                                                                                                                                                                                                                                                                         | Use this section to provide store contact information and the physical location where the goods can be purchased or ordered.                                                                                                                    |

### Coming soon

The `header` and `footer` sections don’t have any customization settings. We’ll add such settings and describe them here.
