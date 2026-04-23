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
- **Style tab — config flags bug** (branch `feature/relief-lab-style-tab`):
  `buildCurrentStyle()` was copying `originalStyle` verbatim, so
  `config.mapShadingSlope`, `config.mapShadingAspect` (and lambertian,
  atmosphere, normalMaps, diffuseMaps, specularMaps, bumpMaps, shadows,
  labels) never reflected the current UI toggle state. Fixed by always
  writing all controlled flags from `state` unconditionally. Config key
  names: `mapShadingLambertian`, `mapShadingSlope`, `mapShadingAspect`,
  `mapFlagNormalMaps`, `mapFlagDiffuseMaps`, `mapFlagSpecularMaps`,
  `mapFlagBumpMaps`, `mapFlagAtmosphere`, `mapFlagShadows`, `mapFlagLabels`.
- **Default position updated:** relief-lab default camera position changed
  to `obj,15.302410,50.700302,fix,591.49,55.69,-50.14,0.00,49182.93,30.00`;
  old position commented out in code for easy rollback.
- **VE style output fix:** `buildCurrentStyle` was always writing
  `"vertical-exaggeration": {}` when both ramps were disabled — an empty
  object is truthy so cartolina would enter the deprecated `setSuperElevation`
  path. Fixed to omit the key entirely when neither ramp is active.
- **URL position tracking:** `positionInUrl` is now `false` by default;
  append `?trackpos` to opt in to URL-tracked navigation.

## 2026-04-24

- **Relief-lab default VE ramp values updated** (commit `1d6b0bd`): hardcoded
  fallback knob positions in `state.ve` changed to match a representative
  real-world style (`scaleRamp` min `[40000, 1]` / max `[53937538, 13.5]`;
  `elevationRamp` min `[1700, 2]` / max `[4000, 1.3]`).
- **`setAtmosphere` bug found in cartolina-js** (backlog entry added): on styles
  without an `atmosphere` section (e.g. `harrachov.json`), `map.setAtmosphere()`
  is silently discarded because `this._map.atmosphere` is null and the
  optional-chain short-circuits. `getAtmosphere()` returns null both before and
  after the call, giving no feedback. Enabling `mapFlagAtmosphere` has no visual
  effect in this case. Workaround applied in the relief-lab demo: inject a
  default atmosphere object into the style before passing to `cartolina.map()`
  (only when the style has no atmosphere section, and only on the copy passed to
  the engine — `originalStyle` is kept unmodified). Comment added to
  `src/browser/viewer.ts:setAtmosphere`.
