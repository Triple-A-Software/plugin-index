# Neleto Plugin Index

The official plugin repository for [Neleto](https://neleto.io), the CMS by Triple-A Software.
Neleto reads [`index.json`](index.json) to discover which plugins and versions are available to install.

## Plugins

| Plugin | Source |
| --- | --- |
| `ui-blocks` | [uiblocks-plugin](https://github.com/Triple-A-Software/uiblocks-plugin) |
| `google-reviews` | [google-reviews-plugin](https://github.com/Triple-A-Software/google-reviews-plugin) |
| `blog-comments` | [blogcomment-plugin](https://github.com/Triple-A-Software/blogcomment-plugin) |
| `site-search` | [sitesearch-plugin](https://github.com/Triple-A-Software/sitesearch-plugin) |
| `media-gallery` | [mediagallery-plugin](https://github.com/Triple-A-Software/mediagallery-plugin) |
| `site-health` | [sitehealth-plugin](https://github.com/Triple-A-Software/sitehealth-plugin) |
| `form-plugin` | [form-plugin](https://github.com/Triple-A-Software/form-plugin) |
| `cookie-banner` | [cookiebanner-plugin](https://github.com/Triple-A-Software/cookiebanner-plugin) |
| `event-registration` | [event-registration](https://github.com/Triple-A-Software/event-registration) |

## Format

`index.json` holds a `plugins` array with one entry per released version, validated by
[`plugin_repository_schema.json`](plugin_repository_schema.json):

| Field | Required | Description |
| --- | --- | --- |
| `plugin_name` | yes | Plugin identifier |
| `version` | yes | SemVer version |
| `url` | yes | Download URL of the release `.tar.gz` |
| `hash` | yes | `sha256:<hex>` digest of the `.tar.gz` |
| `published_at` | yes | RFC 3339 timestamp |
| `description` | no | Short description shown in Neleto |
| `hero_image_url` | no | Preview image shown in Neleto |

## Publishing a new version

1. Create a GitHub release in the plugin's repository with the `.tar.gz` attached.
2. Compute its hash:
   ```sh
   shasum -a 256 <plugin>-<version>.tar.gz
   ```
3. Add an entry to `index.json` above the plugin's previous versions (newest first).

---

Built for [Neleto](https://neleto.io).
