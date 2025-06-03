# section-name.vue

The `section-name.vue` is the main file of the section. It contains all of the custom code and logic. You need to add multi-language support and mobile adaptability to this file as it loads on the storefront.

If you added user-defined settings in `content.ts` and `design.ts` files, you can easily import these settings to the main file. Import methods will dynamically receive user settings when the section code is loaded in the Instant Site Editor or on the storefront:

```ts
import { useImageElementDesign, useSelectboxElementDesign, useTextElementDesign } from '@lightspeed/crane';
import { useImageElementContent, useInputboxElementContent, useTextareaElementContent } from '@lightspeed/crane';

const imageText1 = useTextareaElementContent<Content>('image_text_1');
const imageContent4 = useImageElementContent<Content>('image_content_4');
const imageLink1 = useInputboxElementContent<Content>('image_link_1');

const textDesign = useTextElementDesign<Design>('image_text');
const imageDesign = useImageElementDesign<Design>('image_content');
const positionDesign = useSelectboxElementDesign<Design>('image_text_position');
```

IDE should highlight syntax and show fields available inside constants declared this way.
