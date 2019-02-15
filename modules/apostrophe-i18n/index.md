---
title: "apostrophe-i18n (module)"
layout: reference
module: true
namespaces:

children:

---
## Inherits from: [apostrophe-module](../apostrophe-module/index.html)
This module makes an instance of the [i18n](https://npmjs.org/package/i18n) npm module available
as `apos.i18n`. Apostrophe also makes this available in Nunjucks templates via the
usual `__()` helper function. Any options passed to this module are passed on to `i18n`.

By default i18n locale files are generated in the `locales` subdirectory of the project.

## Options

`localesDir`: if specified, the locale `.json` files are stored here, otherwise they
are stored in the `locales` subdirectory of the project root.


