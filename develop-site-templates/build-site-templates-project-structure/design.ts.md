# design.ts

This file defines section **design** settings available to users in the Instant Site Editor. If some design settings like text size or font, or element color should be **modifiable**, you must add these settings to the `design.ts` file.

Each setting is defined as the `element_id` object with its properties inside. You can add multiple elements of the same `type` to the file. If some of the content settings should also have design settings, use the same `element_id` to link them.

How it looks in the Editor:

<figure><img src="../../.gitbook/assets/8188396-Screenshot_2024-08-01_at_15.57.16 (1).png" alt=""><figcaption></figcaption></figure>

Find the full list of **design types** and their configs below:

### `TEXT`

Configuration for text elements.

| Setting           | Type             | Description                                                                                                                                                                                         |
| ----------------- | ---------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| type              | string           | <p>Type of the setting that defines its functionality. In this case, has <code>TEXT</code> value.<br><br>Works only with <code>INPUTBOX</code> and <code>TEXTAREA</code> content element types.</p> |
| label             | string           | Element name. Use `$label` to add translations.                                                                                                                                                     |
| colors            | array of strings | An array of colors in the HEX code to choose from. Maximum: 7 colors.                                                                                                                               |
| enableAlphaColor  | boolean          | Defines if the element can be transparent.                                                                                                                                                          |
| enableAutoColor   | boolean          | Defines if Ecwid should select a matching color for the text automatically.                                                                                                                         |
| hideVisibleToggle | boolean          | Defines if the element visibility toggle is available in the Editor.                                                                                                                                |
| sizes             | array of numbers | An array of text sizes to choose from. Maximum: 7 sizes.                                                                                                                                            |
| hideSize          | boolean          | Defines if the element size menu is hidden in the Editor. Set `true` to hide.                                                                                                                       |
| defaults          | object           | Default element settings applied when users install a section.                                                                                                                                      |

The `defaults` object contains the following fields:

| Setting | Type    | Description                                                                                            |
| ------- | ------- | ------------------------------------------------------------------------------------------------------ |
| font    | string  | Default text font. We recommend leaving `global.fontFamily.body` here to match the current store font. |
| size    | number  | Default text size.                                                                                     |
| bold    | boolean | Defines if the text is **bold** by default.                                                            |
| italic  | boolean | Defines if the text is _italicized_ by default.                                                        |
| color   | string  | Default text color in HEX code.                                                                        |
| visible | boolean | Defines if the element is visible on the storefront.                                                   |

Code example for 'design.ts':

```ts
element_id: {  
	type: 'TEXT',
	label: '$label.element_id.label', 
	colors: ['#FFFFFF66', '#0000004D', '#00000099', '#64C7FF66', '#F9947266', '#C794CD66', '#FFD17466'],
	sizes: [12, 13, 14, 15, 16, 17, 18, 20],
	defaults: {
		font: 'global.fontFamily.body',
		size: 16,
		bold: false,
		italic: true,
		color: '#333',
}
```

### `BUTTON`

Configuration for button element.

| Setting           | Type             | Description                                                                                                                                                                  |
| ----------------- | ---------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| type              | string           | <p>Type of the setting that defines its functionality. In this case, has <code>BUTTON</code> value.<br><br>Works only with the <code>BUTTON</code> content element type.</p> |
| label             | string           | Element name. Use `$label` to add translations.                                                                                                                              |
| colors            | array of strings | An array of colors in the HEX code for the button background to choose from. Maximum: 7 colors.                                                                              |
| enableAlphaColor  | boolean          | Defines if the element can be transparent.                                                                                                                                   |
| enableAutoColor   | boolean          | Defines if Ecwid should select a matching color for the button automatically.                                                                                                |
| hideVisibleToggle | boolean          | Defines if the element visibility toggle is available in the Editor.                                                                                                         |
| hideSize          | boolean          | Defines if the element size menu is hidden in the Editor. Set `true` to hide.                                                                                                |
| defaults          | object           | Default element settings applied when users install a section.                                                                                                               |

The `defaults` object contains the following fields:

| Setting    | Type    | Description                                                                                            |
| ---------- | ------- | ------------------------------------------------------------------------------------------------------ |
| appearance | string  | Default button appearance. Available values: `SOLID`, `OUTLINE`, `TEXT`.                               |
| shape      | string  | Default button shape. Available values: `PILL`, `RECTANGLE`, `ROUND_CORNER`.                           |
| size       | string  | Default button size. Available values: `SMALL`, `MEDIUM`, `LARGE`.                                     |
| font       | string  | Default text font. We recommend leaving `global.fontFamily.body` here to match the current store font. |
| color      | string  | Default text color in HEX code.                                                                        |
| visible    | boolean | Defines if the element is visible on the storefront.                                                   |

Code example for 'design.ts':

```ts
element_id: {  
	type: 'BUTTON',
	label: '$label.element_id.label',
	colors: ['#FFFFFF66', '#0000004D', '#00000099', '#64C7FF66', '#F9947266', '#C794CD66', '#FFD17466'],
	defaults: { 
		font: 'global.fontFamily.body',
		size: 'MEDIUM',
		appearance: 'OUTLINE',
		shape: 'PILL',
		color: '#333',
	},  
}
```

### `IMAGE`

Configuration for image uploader element.

| Setting           | Type             | Description                                                                                                                                                                |
| ----------------- | ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| type              | string           | <p>Type of the setting that defines its functionality. In this case, has <code>IMAGE</code> value.<br><br>Works only with the <code>IMAGE</code> content element type.</p> |
| label             | string           | Element name. Use `$label` to add translations.                                                                                                                            |
| colors            | array of strings | An array of colors in the HEX code for the image background to choose from. Maximum: 7 colors.                                                                             |
| enableAlphaColor  | boolean          | Defines if the element can be transparent.                                                                                                                                 |
| hideVisibleToggle | boolean          | Defines if the element visibility toggle is available in the Editor.                                                                                                       |
| defaults          | object           | Default element settings applied when users install a section.                                                                                                             |

The `defaults` object contains the following fields:

| Setting | Type    | Description                                                                                             |
| ------- | ------- | ------------------------------------------------------------------------------------------------------- |
| overlay | object  | Default image overlay settings. Available settings: `COLOR`, `GRADIENT`, `NONE`.                        |
| color   | boolean | One (`string` type) or two (`array` with two strings inside) colors for default image overlay settings. |

Code example for 'design.ts':

```ts
element_id: {  
	type: 'IMAGE',
	label: '$label.element_id.label',
	colors: ['#FFFFFF66', '#0000004D', '#00000099', '#64C7FF66', '#F9947266', '#C794CD66', '#FFD17466'],
	defaults: { 
		overlay: 'COLOR',
		color: '#fff000',
	},  
}
```

### `TOGGLE`

Configuration for toggle element.

| Setting     | Type   | Description                                                                                                                                                                  |
| ----------- | ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| type        | string | <p>Type of the setting that defines its functionality. In this case, has <code>TOGGLE</code> value.<br><br>Works only with the <code>TOGGLE</code> content element type.</p> |
| label       | string | Element name. Use `$label` to add translations.                                                                                                                              |
| description | string | Element description displayed in the Instant Site Editor under the element.                                                                                                  |
| defaults    | object | Default element settings applied when users install a section.                                                                                                               |

The `defaults` object contains the following fields:

| Setting | Type    | Description                                                                            |
| ------- | ------- | -------------------------------------------------------------------------------------- |
| enabled | boolean | Defines of the toggle is enabled when users install the section. Set `true` to enable. |

Code example for 'design.ts':

```ts
element_id: {  
	type: 'TOGGLE', 
	label: '$label.element_id.label',
	description: '$label.toggle.description', 
	defaults: {
		enabled: true,
	},  
}
```

### `SELECTBOX`

Configuration for the "selectbox" element that creates a drop-down list in the Editor.

| Setting     | Type             | Description                                                                                                                                                                        |
| ----------- | ---------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| type        | string           | <p>Type of the setting that defines its functionality. In this case, has <code>SELECTBOX</code> value.<br><br>Works only with the <code>SELECTBOX</code> content element type.</p> |
| label       | string           | Element name. Use `$label` to add translations.                                                                                                                                    |
| description | string           | Description under the drop-down.                                                                                                                                                   |
| options     | array of objects | List of options available in the drop-down list.                                                                                                                                   |
| defaults    | object           | Default element settings applied when users install a section.                                                                                                                     |

The `options` is an array where each object contains the following fields:

| Setting | Type   | Description                      |
| ------- | ------ | -------------------------------- |
| value   | string | Option value.                    |
| label   | string | Text label for the option value. |

The `defaults` object contains the following fields:

| Setting | Type   | Description                                                 |
| ------- | ------ | ----------------------------------------------------------- |
| value   | string | Default option value selected when users install a section. |

Code example for 'design.ts':

```ts
element_id: {  
	type: 'SELECTBOX',
	label: '$label.element_id.label',
	description: '$label.element_id.description',
	options: [
		{  
			value: 'one',
			label: '$label.element_id.one.label',
		},  
		{  
			value: 'two',  
			label: '$label.element_id.two.label',  
		},  
	],  
	defaults: { 
		value: 'two',
	},  
}
```

### `BACKGROUND`

Configuration for the section background which is not an element type defined in the 'content.ts' file.

| Setting          | Type             | Description                                                                                                                                               |
| ---------------- | ---------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| type             | string           | <p>Type of the setting that defines its functionality. In this case, has <code>BACKGROUND</code> value.<br><br>Has no matching content element types.</p> |
| label            | string           | Element name. Use `$label` to add translations.                                                                                                           |
| colors           | array of strings | An array of colors in the HEX code for the background to choose from. Maximum: 7 colors.                                                                  |
| enableAlphaColor | boolean          | Defines if the element can be transparent.                                                                                                                |
| enableAutoColor  | boolean          | Defines if Ecwid should select a matching color for the button automatically.                                                                             |
| defaults         | object           | Default element settings applied when users install a section.                                                                                            |

The `defaults` object contains the following fields:

| Setting | Type         | Description                                                                                                    |
| ------- | ------------ | -------------------------------------------------------------------------------------------------------------- |
| style   | string       | Background type. Available values: `COLOR` (single color background) or `GRADIENT` (background with gradient). |
| color   | string/array | One (`string` type) or two (`array` with two strings inside) colors for default image overlay settings.        |

The `background` object contains the following fields:

The `gradient` object contains the following fields:

Code example for 'design.ts':

```ts
element_id: {  
	type: 'BACKGROUND',
	label: '$label.element_id.label',
	colors: ['#FFFFFF66', '#0000004D', '#00000099', '#64C7FF66', '#F9947266', '#C794CD66', '#FFD17466'],
	defaults: {
		style: 'COLOR',
		color: '#fff000'
	}, 
}
```

### `DIVIDER`

Allows you to add a divider line between elements of content/design settings. It only affects the appearance of your section settings on the Editor page and doesn't change how the section is displayed on the storefront in any way.

List of properties:

| Name | Type   | Description                                                                                                                                                                                                                                  |
| ---- | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| type | string | <p>Type of the setting that defines its functionality. In this case, has <code>DIVIDER</code> value.<br><br>Divider doesn't have any additinal settings, so it's the only field that should be here.<br></p><p><strong>Required</strong></p> |

Code example:

```typescript
element_id: {
    type: 'DIVIDER',
    label: '$label.element_id.label',
    description: '$label.element_id.description',
    button: {
        label: '$label.element_id.button.label',
        link: 'https://example.com',
    },
}
```
