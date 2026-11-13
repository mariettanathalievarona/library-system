# Library System Landing Page

The public landing page for the Library System. It is hosted with GitHub Pages at
[library-system.online](https://library-system.online/).

The page links to the Django library platform at
[ndkc.library-system.online](https://ndkc.library-system.online). Before opening the platform,
it calls the public `/healthz/` endpoint and requires a `200` JSON response identifying the
`ndkc-library-system` service. If the endpoint is unreachable or returns anything else, the
page shows an accessible dialog instead of continuing to the platform.

The check uses a CORS request rather than `no-cors`. An opaque `no-cors` response resolves for
any HTTP response, including Cloudflare's custom 5xx error page, which would incorrectly mark
the platform as online. Cloudflare error pages either fail CORS or return a non-JSON body, so
they are treated as offline.

## Local preview

The page is plain HTML, CSS, and JavaScript with no build step. Serve the repository root:

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000/>.

## Deployment

Pushes to `main` deploy the repository root through the GitHub Pages workflow in
`.github/workflows/static.yml`. No generated files or manual build are required.

Keep the GitHub Pages custom domain set to `library-system.online` for both the apex and `www`
hosts.

## Files

- `index.html` — landing page markup, styles, and the platform availability check.
- `favicon.svg` — generic book icon from [Heroicons](https://heroicons.com/).
- `assets/screenshots/` — desktop, tablet, and mobile promotional screenshots of the
  student portal. Desktop, tablet, and mobile cards loop short GIFs showing main-menu,
  quick-action, and catalog navigation, with static PNG fallbacks for reduced-motion
  preferences.

## Repository

<https://github.com/mariettanathalievarona/library-system>
