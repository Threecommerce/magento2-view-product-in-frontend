# Changelog

All notable changes to this module are documented here.
The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.2] - 2026-10-12

### Fixed
- The storefront link was built by hand (`base URL + url_key + suffix`), so it
  ignored URL rewrites and always pointed to the Admin's store. It now uses the
  product URL model of the selected store view (store switcher), falling back
  to the default store view.
- The button is no longer shown for products without a storefront page
  (disabled, not visible in catalog, or without URL key), which used to open a 404.
- The URL is JSON-encoded inside the `onclick` handler instead of being
  concatenated into the JavaScript string.

### Changed
- Depends on `ProductRepositoryInterface` instead of the concrete repository.
- Renamed the UI component button from the copy-pasted `clear_cache` to `view_in_front`.
- Removed the hardcoded `"version"` field from `composer.json`: Composer/Satis
  honour it over the git tag, so new tags could be published with an old version.
  The version is now derived from the git tag.
- Removed the `repositories` entry pointing to the private GitHub repository of
  `m2-base` (the package is served by the Composer repository).
- Added README and CHANGELOG.

## [1.0.1] - 2026-06-01

- Raised the PHP requirement to PHP 8.1 or later.

## [1.0.0] - 2024-11-21

- First release: **View in front** button on the product edit page.
