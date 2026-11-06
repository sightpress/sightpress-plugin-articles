# SightPress articles

`sightpress/plugin-articles`: the official SightPress plugin for blogging and
news. Licensed GPL-2.0-or-later.

> **Status:** M0 scaffolding in place (manifest, bundle, quality gates, CI);
> features arrive in milestone M7.

It adds:

- The **`article` content type**, through the core content pipeline (workflow,
  translations, revisions, the accessibility linter and publish gate, editors,
  widgets, layouts), so it reads exactly like a core page to screen-reader
  users and search engines.
- **Categories and tags**, with their own archive pages and feeds.
- An **`::articles` listing block** for any page or widget area, with
  pagination (never infinite scroll) and a labelled "load more" when wanted.
- **Author pages**, syndication feeds, and `Article`/`BlogPosting` structured
  data through core SEO.

It depends only on `sightpress/plugin-core`, never on `sightpress/core`
directly, and the site works with it disabled: articles simply stop appearing,
and no route or admin section is left behind.

## Development

```bash
composer install
vendor/bin/phpunit          # on PluginTestCase, enabled and disabled
vendor/bin/phpstan analyse
npx playwright test         # every manifest route, with axe-core
```

Check out `sightpress/core` as a sibling and require it with
`COMPOSER=composer.dev.json composer install` to run the test kernel.
