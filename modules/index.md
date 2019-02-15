---
title: "Module reference"
layout: "reference"
children:
  - apostrophe-admin-bar
  - apostrophe-any-page-manager
  - apostrophe-areas
  - apostrophe-assets
  - apostrophe-attachments
  - apostrophe-browser-utils
  - apostrophe-caches
  - apostrophe-custom-pages
  - apostrophe-db
  - apostrophe-doc-type-manager
  - apostrophe-docs
  - apostrophe-email
  - apostrophe-express
  - apostrophe-files
  - apostrophe-files-widgets
  - apostrophe-global
  - apostrophe-groups
  - apostrophe-html-widgets
  - apostrophe-i18n
  - apostrophe-images
  - apostrophe-images-widgets
  - apostrophe-jobs
  - apostrophe-launder
  - apostrophe-locks
  - apostrophe-login
  - apostrophe-migrations
  - apostrophe-modal
  - apostrophe-module
  - apostrophe-notifications
  - apostrophe-oembed
  - apostrophe-pager
  - apostrophe-pages
  - apostrophe-permissions
  - apostrophe-pieces
  - apostrophe-pieces-pages
  - apostrophe-pieces-widgets
  - apostrophe-polymorphic-manager
  - apostrophe-push
  - apostrophe-rich-text-widgets
  - apostrophe-schemas
  - apostrophe-search
  - apostrophe-service-bridge
  - apostrophe-soft-redirects
  - apostrophe-tags
  - apostrophe-tasks
  - apostrophe-templates
  - apostrophe-ui
  - apostrophe-urls
  - apostrophe-users
  - apostrophe-utils
  - apostrophe-versions
  - apostrophe-video-fields
  - apostrophe-video-widgets
  - apostrophe-widgets
---
## Modules in Apostrophe

Every Apostrophe site is made up of modules. You can browse the complete list at left.

### Overview

Each module provides a particular feature, often including both front and back end code, as well as templates and stylesheets. For instance, the [apostrophe-assets](apostrophe-assets/index.html) module provides core services relating to assets like stylesheets.

Modules are implemented as [moog types](../glossary.html#moog-type), which provide a simple and clean way to write them in an object-oriented style while keeping async programming convenient and providing easy subclassing and overriding.

For convenience, the `apostrophe` npm module contains all of the "core" Apostrophe modules that are necessary for a functioning website.

Some of these, like [apostrophe-docs](apostrophe-docs/index.html), are initialized every time Apostrophe starts up; you can [see that list on github](https://github.com/punkave/apostrophe/blob/master/defaults.js). Those modules are initialized first, followed by those you configure in `app.js`, in the order you configure them.

Others, like [apostrophe-pieces](apostrophe-pieces/index.html) and [apostrophe-widgets](apostrophe-widgets/index.html), are "abstract base classes" you can extend to create new modules that provide content types.

[apostrophe-module](apostrophe-module/index.html) is the base class of **all** modules; it provides features that are convenient in almost any module, like [rendering a template from its `views` folder](apostrophe-module/index.html#render), or [pushing assets from its `public` folder](apostrophe-module/index.html#push-asset).

Modules can also be installed via npm, and multiple Apostrophe modules can be [shipped as a single npm module via moog bundles](../more-modules.html).

### Overriding, configuring and extending modules at "project level"

Any options you provide for a module via the `modules` property in `app.js` override the default configuration for a module, as seen in the [tutorials](../tutorials/index.html). And any configuration provided via the `modules` property in `data/local.js` overrides that, allowing for server-specific settings like API keys.

You can also provide your own templates in the `lib/modules/module-name/views` folder of your project (**not** in `node_modules`) to override the templates of `module-name`, and provide your own code in `lib/modules/module-name/index.js` to override methods and add functionality. *If your project-level `lib/modules` folder has a module by the same name as a core or npm module, any code you provide automatically subclasses and improves that module.*

