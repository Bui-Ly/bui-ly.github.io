# BuiLy Apps website

Static GitHub Pages website for apps and games published by Nguyen Bui Ly.

Live site: <https://bui-ly.github.io/>

## Public structure

- `/` — simple published-app directory with official store links
- `/apps/` — compatibility redirect to the home app directory
- `/support/` — general support
- `/privacy/` — privacy policy directory
- `/privacy.html` — website privacy notice and preserved legacy URL
- `/account-deletion/` — account and data deletion directory
- `/app-ads.txt` — shared authorized-seller declaration at the root domain
- `/apps/<app-slug>/` — permanent support page for one app
- `/apps/<app-slug>/privacy/` — privacy policy for one app
- `/apps/<app-slug>/account-deletion/` — deletion instructions for one app

## Add a new app

1. Copy `apps/template/` to `apps/<stable-app-slug>/`.
2. Replace all placeholders and audit the actual app, backend, SDKs, store disclosures, account behavior, and data retention.
3. Remove `noindex` from the copied pages.
4. Add the app card and verified App Store or Google Play link to `/`.
5. Add the app to the privacy and deletion directories and to `sitemap.xml` when those routes apply.
6. Test every public route before entering it in Google Play or App Store Connect.

Do not rename a published app slug after its URLs are used in a store listing. Preserve old policy URLs with a working page or redirect.
