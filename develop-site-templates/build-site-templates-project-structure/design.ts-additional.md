---
hidden: true
noIndex: true
---

# design.ts (additional)

### `COLOR_PICKER`

Configuration for a color picker which is not an element type defined in the 'content.ts' file.

| Setting          | Type             | Description                                                                                                                                                 |
| ---------------- | ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| type             | string           | <p>Type of the setting that defines its functionality. In this case, has <code>COLOR_PICKER</code> value.<br><br>Has no matching content element types.</p> |
| label            | string           | Element name. Use `$label` to add translations.                                                                                                             |
| description      | string           | Description under the color picker.                                                                                                                         |
| colors           | array of strings | An array of colors in the HEX code to choose from. Maximum: 7 colors.                                                                                       |
| enableAlphaColor | boolean          | Defines if the element can be transparent.                                                                                                                  |
| enableAutoColor  | boolean          | Defines if Ecwid should select a matching color for the button automatically.                                                                               |
| defaults         | object           | Default element settings applied when users install a section.                                                                                              |

The `defaults` object contains the following fields:

| Setting | Type   | Description                                                                                            |
| ------- | ------ | ------------------------------------------------------------------------------------------------------ |
| color   | object | Default color picker settings. Contains an object of either `STRUCTURED_COLOR` or `GLOBAL_COLOR` type. |

The `GLOBAL_COLOR` object contains the color specified with the following field:

<table><thead><tr><th width="222">Setting</th><th>Type</th><th>Description</th></tr></thead><tbody><tr><td>raw</td><td>string</td><td>Color specified with raw format: <code>black</code>, <code>red</code>, <code>green</code>, etc.</td></tr></tbody></table>

The `STRUCTURED_COLOR` object contains the color specified with one of the following fields:

| Setting | Type   | Description                                                    |
| ------- | ------ | -------------------------------------------------------------- |
| raw     | string | Color specified with raw format: `black`, `red`, `green`, etc. |
| hex     | string | Color in HEX format.                                           |
| rgba    | object | Color in RGBA format.                                          |
| hsl     | object | Color in HSLA format.                                          |
| auto    | string | Color is automatically picked by Ecwid.                        |

The `rgba` object contains the following fields:

| Setting | Type   | Description    |
| ------- | ------ | -------------- |
| r       | string | R-channel.     |
| g       | string | G-channel.     |
| b       | object | B-channel.     |
| a       | object | Alpha-channel. |

The `hsl` object contains the following fields:

| Setting | Type   | Description         |
| ------- | ------ | ------------------- |
| h       | string | Color _hue_.        |
| s       | string | Color _saturation_. |
| l       | object | Color _lightness_.  |
| a       | object | Alpha-channel.      |

Code example for 'design.ts':

```ts
element_id: {  
	type: 'COLOR_PICKER',
	label: '$label.element_id.label',
	description: '$label.element_id.description',
	colors: ['#FFFFFF66', '#0000004D', '#00000099', '#64C7FF66', '#F9947266', '#C794CD66', '#FFD17466'],
	defaults: {
		color: {
    	raw: 'green',
    },
	},  
}
```

### `RATING`

Configuration for the rating element.

| Setting           | Type             | Description                                                                                                                                           |
| ----------------- | ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| type              | string           | <p>Type of the setting that defines its functionality. In this case, has <code>RATING</code> value.<br><br>Has no matching content element types.</p> |
| label             | string           | Element name. Use `$label` to add translations.                                                                                                       |
| colors            | array of strings | An array of colors in the HEX code to choose from. Maximum: 7 colors.                                                                                 |
| enableAlphaColor  | boolean          | Defines if the element can be transparent.                                                                                                            |
| enableAutoColor   | boolean          | Defines if Ecwid should select a matching color for the button automatically.                                                                         |
| hideVisibleToggle | boolean          | Defines if the element visibility toggle is available in the Editor.                                                                                  |
| options           | object           | Defines a list of options.                                                                                                                            |
| defaults          | object           | Default element settings applied when users install a section.                                                                                        |

The `options` object contains the following fields:

| Setting | Type   | Description                      |
| ------- | ------ | -------------------------------- |
| value   | string | Option value.                    |
| label   | string | Text label for the option value. |

The `defaults` object contains the following fields:

| Setting | Type    | Description                                                                                                     |
| ------- | ------- | --------------------------------------------------------------------------------------------------------------- |
| style   | string  | Background color style. Available values: `COLOR`                                                               |
| visible | boolean | Defines if the element is visible on the storefront.                                                            |
| color   | object  | Default color settings for the element. Contains an object of either `STRUCTURED_COLOR` or `GLOBAL_COLOR` type. |

The `GLOBAL_COLOR` object contains the color specified with the following field:

| Setting | Type   | Description                                                    |
| ------- | ------ | -------------------------------------------------------------- |
| raw     | string | Color specified with raw format: `black`, `red`, `green`, etc. |

The `STRUCTURED_COLOR` object contains the color specified with one of the following fields:

| Setting | Type   | Description                                                    |
| ------- | ------ | -------------------------------------------------------------- |
| raw     | string | Color specified with raw format: `black`, `red`, `green`, etc. |
| hex     | string | Color in HEX format.                                           |
| rgba    | object | Color in RGBA format.                                          |
| hsl     | object | Color in HSLA format.                                          |
| auto    | string | Color is automatically picked by Ecwid.                        |

The `rgba` object contains the following fields:

| Setting | Type   | Description    |
| ------- | ------ | -------------- |
| r       | string | R-channel.     |
| g       | string | G-channel.     |
| b       | object | B-channel.     |
| a       | object | Alpha-channel. |

The `hsl` object contains the following fields:

| Setting | Type   | Description         |
| ------- | ------ | ------------------- |
| h       | string | Color _hue_.        |
| s       | string | Color _saturation_. |
| l       | object | Color _lightness_.  |
| a       | object | Alpha-channel.      |

Code example for 'design.ts':

```ts
element_id: {  
	type: 'RATING', 
	label: '$label.element_id.label',
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
}
```

### `SOCIAL_PROFILES`

Configuration for the social profile element.

| Setting           | Type             | Description                                                                                                                                                    |
| ----------------- | ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| type              | string           | <p>Type of the setting that defines its functionality. In this case, has <code>SOCIAL_PROFILES</code> value.<br><br>Has no matching content element types.</p> |
| label             | string           | Element name. Use `$label` to add translations.                                                                                                                |
| colors            | array of strings | An array of colors in the HEX code to choose from. Maximum: 7 colors.                                                                                          |
| enableAlphaColor  | boolean          | Defines if the element can be transparent.                                                                                                                     |
| enableAutoColor   | boolean          | Defines if Ecwid should select a matching color for the button automatically.                                                                                  |
| hideVisibleToggle | boolean          | Defines if the element visibility toggle is available in the Editor.                                                                                           |
| options           | object           | Defines a list of options.                                                                                                                                     |
| defaults          | object           | Default element settings applied when users install a section.                                                                                                 |

The `options` object contains the following fields:

| Setting | Type   | Description                      |
| ------- | ------ | -------------------------------- |
| value   | string | Option value.                    |
| label   | string | Text label for the option value. |

The `defaults` object contains the following fields:

| Setting    | Type    | Description                                                                                                     |
| ---------- | ------- | --------------------------------------------------------------------------------------------------------------- |
| appearance | string  | Background color style. Available values: `COLOR`                                                               |
| visible    | boolean | Defines if the element is visible on the storefront.                                                            |
| color      | object  | Default color settings for the element. Contains an object of either `STRUCTURED_COLOR` or `GLOBAL_COLOR` type. |

The `GLOBAL_COLOR` object contains the color specified with the following field:

| Setting | Type   | Description                                                    |
| ------- | ------ | -------------------------------------------------------------- |
| raw     | string | Color specified with raw format: `black`, `red`, `green`, etc. |

The `STRUCTURED_COLOR` object contains the color specified with one of the following fields:

| Setting | Type   | Description                                                    |
| ------- | ------ | -------------------------------------------------------------- |
| raw     | string | Color specified with raw format: `black`, `red`, `green`, etc. |
| hex     | string | Color in HEX format.                                           |
| rgba    | object | Color in RGBA format.                                          |
| hsl     | object | Color in HSLA format.                                          |
| auto    | string | Color is automatically picked by Ecwid.                        |

The `rgba` object contains the following fields:

| Setting | Type   | Description    |
| ------- | ------ | -------------- |
| r       | string | R-channel.     |
| g       | string | G-channel.     |
| b       | object | B-channel.     |
| a       | object | Alpha-channel. |

The `hsl` object contains the following fields:

| Setting | Type   | Description         |
| ------- | ------ | ------------------- |
| h       | string | Color _hue_.        |
| s       | string | Color _saturation_. |
| l       | object | Color _lightness_.  |
| a       | object | Alpha-channel.      |

Code example for 'design.ts':

```ts
element_id: {  
	type: 'SOCIAL_PROFILES', 
	label: '$label.element_id.label',
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
}
```
