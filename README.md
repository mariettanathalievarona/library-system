# Library System Landing Page

The public landing page for the Library System. It is hosted with GitHub Pages at
[library-system.online](https://library-system.online/).

The page links to the Django library platform at
[ndkc.library-system.online](https://ndkc.library-system.online). Before opening the platform,
it checks whether the host is reachable and shows an accessible dialog if the platform is down.

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
  student portal.

## Repository

<https://github.com/mariettanathalievarona/library-system>
