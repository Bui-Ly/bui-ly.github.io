# Per-app website template

Copy this directory to `apps/<stable-app-slug>/`, then replace every placeholder before publishing.

Required public routes:

- `apps/<stable-app-slug>/` — product and support page
- `apps/<stable-app-slug>/privacy/` — app-specific privacy policy
- `apps/<stable-app-slug>/account-deletion/` — deletion request instructions when the app has accounts or server-side user data

Release checklist:

1. Audit the shipped app, backend, SDKs, permissions, store privacy disclosures, ads, purchases, and account behavior.
2. Replace all placeholders and remove the `noindex` metadata in the copied pages.
3. Add the app to `/apps/`, `/privacy/`, `/account-deletion/`, and `sitemap.xml`.
4. Confirm every relative link, email subject, canonical URL, icon, and policy effective date.
5. Keep the app slug stable after the URL is entered in Google Play or App Store Connect.
