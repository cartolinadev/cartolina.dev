# Session Log

## 2026-04-23

- `cartolina.dev` is a Jekyll documentation site for the `cartolina-js` library; both repos live side by side under `/home/prochazka/src/cartolina/`.
- The Jekyll site uses a custom `_data/navigation.yml` for nav and example pages are under `pages/examples/`. Tilde-suffixed files (e.g. `_config.yml~`) appear throughout — these are editor backup files and are not part of the build; `.gitignore` was recently updated (uncommitted change as of this session).
- A `cartolina-js/docs/wiki` directory is also mounted as an additional working directory, suggesting wiki content may be managed separately from the main docs site.
- **Ruby environment conflict:** The system has snap Ruby 4.0 (`/snap/bin/bundle`) and apt Ruby 3.0 (`/usr/bin/bundle3.0`). The `github-pages` gem's `ffi` dependency requires Ruby < 3.5, so snap Ruby breaks `bundle install`. Always use `/usr/bin/bundle3.0` explicitly. Also requires `ruby3.0-dev` apt package for native extensions (bigdecimal, ffi, commonmarker, eventmachine). Bundle path is set locally to `vendor/bundle` (gitignored) to avoid needing sudo. README updated to reflect this.
- **`examples.md` ordering convention:** implemented example links must come before unimplemented placeholder lines.
- **`vendor/` must be in Jekyll's exclude list** (`_config.yml`): Jekyll would otherwise try to parse gem template files inside `vendor/bundle` as posts, failing with an invalid-date error on a `.markdown.erb` file. Added `vendor/` to the `exclude:` key.
