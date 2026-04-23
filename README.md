This repo holds the source for the [cartolina.dev](https://cartolina.dev/) website.

## Local dev
```bash
# One-time: install Ruby dev headers (needed to compile native gems)
sudo apt-get install -y ruby3.0-dev

# One-time: configure bundle to install gems locally (avoids needing sudo)
/usr/bin/bundle3.0 config set --local path 'vendor/bundle'
/usr/bin/bundle3.0 install

# Serve (use bundle3.0 to ensure system Ruby 3.0 is used, not snap Ruby 4.0)
/usr/bin/bundle3.0 exec jekyll serve --host 0.0.0.0 --livereload --config _config.yml,_config.dev.yml --force_polling --livereload
# http://127.0.0.1:4000
```

> **Note:** The `github-pages` gem requires Ruby < 3.5. If your system has multiple Ruby versions, `bundle` may resolve to an incompatible one. Use `bundle3.0` (or whichever versioned binary matches your Ruby 3.x install) to be explicit.

## Deploy
- Push to `main`. GitHub → **Settings → Pages → Source = GitHub Actions**.
- Set `cartolina.dev`, DNS A/AAAA (optional CNAME `www`), **Enforce HTTPS**.

## Notes
- Top-left logo: `_config.yml` → `logo: /assets/images/cartolina-logo-bw.png`.
- Tabs across top: `_data/navigation.yml` → `main:` list.
- Left sidebar (optional): in any page front matter add `sidebar: { nav: main }`.
- Right sticky ToC: enabled globally (`toc: true`), disable per-page with `toc: false`.
- Single copyright: `_includes/footer/custom.html` (feed button hidden via `atom_feed.hide: true`).
