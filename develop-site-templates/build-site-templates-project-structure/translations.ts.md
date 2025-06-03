# translations.ts

The `tranlations.ts` file defines text translations for labels added across the template project. Text labels are used independently in two places:

* Text labels explain content and design settings to users in the IS Editor. Settings inside `content.ts` and `design.ts` files have the `label` field. The `tranlations.ts` file adds text values for these labels in one or several languages.
* Text labels in showcase files like `1.ts` are used to display section previews in several languages.

Users will see texts defined in `tranlations.ts` files in the matching language in the Instant Site Editor. If the language is not available, they'll see the English translation.

Therefore, `translations.ts` files have the following requirements:

* The `en` translations are required for all section texts.
* Each section requires two `translation.ts` files in the `settings` and `showcases` folders.
* All labels defined in files in the `settings` and `showcases` folders must have text values, in all languages defined in the `translation.ts` file.

To create a `translations.ts` file, declare object named with a language code (ISO 639-1) for every translation you want to add and put `'$label': 'text'` pairs inside.

Code example:

```ts
en: {
	'$label.inputbox_1_name': 'Title',
	'$label.inputbox_1_desc': 'Description',
	'$label.color_picker_name': 'Select color for the navigation arrows',
},
es: {
	...
},
nl: {
	...
}
```

Check out the example section from the `crane` tool. It has working 'translations.ts' files for both "settings" and "showcases" folders.
