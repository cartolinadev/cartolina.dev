# Cartolina — Minimal Mistakes defaults (logo, tabs, single copyright)

## Local dev
```bash
gem install --user-install bundler jekyll-include-cache
export PATH="$HOME/.gem/ruby/$(ruby -e 'print RUBY_VERSION[/^\d+\.\d+/]')/bin:$PATH"
bundle install
bundle exec jekyll serve --livereload --config _config.yml,_config.dev.yml --force_polling --livereload
# http://127.0.0.1:4000
```

## Deploy
- Push to `main`. GitHub → **Settings → Pages → Source = GitHub Actions**.
- Set `cartolina.dev`, DNS A/AAAA (optional CNAME `www`), **Enforce HTTPS**.

## Notes
- Top-left logo: `_config.yml` → `logo: /assets/images/cartolina-logo-bw.png`.
- Tabs across top: `_data/navigation.yml` → `main:` list.
- Left sidebar (optional): in any page front matter add `sidebar: { nav: main }`.
- Right sticky ToC: enabled globally (`toc: true`), disable per-page with `toc: false`.
- Single copyright: `_includes/footer/custom.html` (feed button hidden via `atom_feed.hide: true`).
