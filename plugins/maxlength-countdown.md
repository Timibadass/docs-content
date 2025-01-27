---
title: Maxlength Countdown
description: easily add a visual countdown of remaining characters for text based fields
---

# Maxlength Countdown Plugin

:PageToc

Using the `createMaxLengthCountdownPlugin` function from `@formkit/addons` you can easily add a visual countdown of remaining characters for any `text` family (`text`, `email`, `password`, etc) or `textarea` FormKit input just by setting the `maxlength` prop.

## Installation

To install the maxlength countdown plugin we need to import it from `@formkit/addons`, add it our FormKit config, and include the supporting CSS styles (or provide your own).

The `createMaxLengthCountdownPlugin` has a few options you can configure: 

- **useAsDefault** *Boolean* Default: `false`, whether to apply this plugin to fields with the maxlength attr by default or can be enabled on a field by field basis
- **maxlengthRemainingText** *String* Default: `'remaining characters'`
- **fieldTypes** *Array* Default `['textarea']`

```js
// formkit.config.js
import { defaultConfig } from '@formkit/vue'
import { createMaxLengthCountdownPlugin } from '@formkit/addons'
import '@formkit/addons/css/maxlengthCountdown'

const config = defaultConfig({
  plugins: [
    createMaxLengthCountdownPlugin({
      useAsDefault: true, // defaults to false
    }),
  ],
})

export default config
```

## Usage

Once the plugin is included in the config, it can be enabled directly on a field if not set to use by default. There are also props that can override the global options set in the config on a field-by-field basis.

Available field props:

- **maxlength-countdown** *Boolean* Whether the plugin should explicityly execute for a given field. This can/will override the configs fieldTypes.
- **maxlength-remaining-text** *String* Override the remaining text for a specific field

::Example
---
name: "Maxlength Countdown Example"
file: [
'/\_content/_examples/maxlength-countdown/index.vue',
'/\_content/_examples/maxlength-countdown/formkit.config.js'
]
---
::