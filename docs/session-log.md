# Session Log

## 2026-04-23

- `cartolina.dev` is a Jekyll documentation site for the `cartolina-js` library; both repos live side by side under `/home/prochazka/src/cartolina/`.
- The Jekyll site uses a custom `_data/navigation.yml` for nav and example pages are under `pages/examples/`. Tilde-suffixed files (e.g. `_config.yml~`) appear throughout — these are editor backup files and are not part of the build; `.gitignore` was recently updated (uncommitted change as of this session).
- A `cartolina-js/docs/wiki` directory is also mounted as an additional working directory, suggesting wiki content may be managed separately from the main docs site.
- **Ruby environment conflict:** The system has snap Ruby 4.0 (`/snap/bin/bundle`) and apt Ruby 3.0 (`/usr/bin/bundle3.0`). The `github-pages` gem's `ffi` dependency requires Ruby < 3.5, so snap Ruby breaks `bundle install`. Always use `/usr/bin/bundle3.0` explicitly. Also requires `ruby3.0-dev` apt package for native extensions (bigdecimal, ffi, commonmarker, eventmachine). Bundle path is set locally to `vendor/bundle` (gitignored) to avoid needing sudo. README updated to reflect this.
- **`examples.md` ordering convention:** implemented example links must come before unimplemented placeholder lines.
- **`vendor/` must be in Jekyll's `exclude:` list** (`_config.yml`): Jekyll
  would otherwise try to parse gem template files inside `vendor/bundle` as
  posts, failing with an invalid-date error on a `.markdown.erb` file.
- **Relief-lab Style tab** (implemented, branch `feature/relief-lab-style-tab`,
  commit `6783e83`): 4th tab added to the relief-lab panel. Shows the live
  cartolina-js style JSON reconstructed from the demo's `state` object.
  Updates on every `applyIllumination`, `applyAtmosphere`,
  `applyVerticalExaggeration`, `applyRenderingOptions` call. VE output uses
  `scaleRamp`/`elevationRamp` (current format); `heightRamp`/
  `viewExtentProgression` is `@deprecated` and not used. Illumination and
  atmosphere keys are omitted when their respective toggles are off. Copy
  button uses `navigator.clipboard.writeText()` and flashes "Copied!" for
  1.5 s. No cartolina-js library changes needed; demo stays on CDN. Full
  plan at `~/.claude/plans/humble-moseying-liskov.md`.
- **Style tab — icon + panel width** (commit `995a02d`, branch
  `feature/relief-lab-style-tab`): Equal-width tab approach degraded the UX
  (cramped labels). Instead: replaced the "Style" label with a small `{ }`
  SVG icon (`title="Style JSON"`) and widened the panel from
  `min(430px, 30vw)` to `min(470px, 32vw)`. Original three tabs keep their
  full size; icon tab gets `padding: 0 12px`. Branch ready to merge to main
  (ask user first).
- **Playwright MCP:** the browser context dies between sessions and needs a
  manual relaunch. When the MCP browser is unavailable, use
  `cd cartolina-js && node -e "..."` with the cartolina-js node/Playwright
  env as a fallback for DOM inspection.
