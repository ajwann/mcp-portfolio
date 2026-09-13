# adamwanninger.com

The home page, privacy policy, and terms of service for **Adam Wanninger's MCP Servers**,
served by GitHub Pages at <https://adamwanninger.com>.

Google's OAuth consent screen for the hosted servers links to these pages, so they must stay
online and accurate:

| Page | URL |
| --- | --- |
| Home page | <https://adamwanninger.com/> |
| Privacy policy | <https://adamwanninger.com/privacy/> |
| Terms of service | <https://adamwanninger.com/terms/> |

The hosted servers themselves each live in their own repository, on a subdomain, such as
`https://queenscoach.adamwanninger.com/mcp` ([ajwann/queenscoach](https://github.com/ajwann/queenscoach)).

## Layout

| Path | What it is |
| --- | --- |
| `index.html` | Home page: what the app is, each server, and how to connect |
| `privacy/index.html` | Privacy policy |
| `terms/index.html` | Terms of service |
| `tokens.css` | Solarized colour tokens, copied from the landing page; light or dark follows the system setting |
| `style.css` | The site stylesheet, matching the landing page |
| `CNAME` | The custom domain GitHub Pages serves |
| `.nojekyll` | Serve the files as they are, without a Jekyll build |

Plain HTML and CSS, with no build step and no JavaScript.

## Previewing

Serve the repository root with any static file server, then open <http://localhost:8000>:

```sh
python -m http.server 8000
```

## Publishing

GitHub Pages deploys from the `main` branch, root folder. The custom domain is
`adamwanninger.com`, with **Enforce HTTPS** on.

DNS is at Cloudflare, and every record below is **DNS only** (grey cloud), so GitHub can issue
the certificate:

| Type | Name | Value |
| --- | --- | --- |
| A | `@` | `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153` |
| AAAA | `@` | `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`, `2606:50c0:8003::153` |
| CNAME | `www` | `ajwann.github.io` |

## Adding a server

1. Add a section for it to `index.html`.
2. Add to `privacy/index.html` anything it collects or keeps that the policy doesn't already
   cover, and update the date.
3. Register its OAuth redirect URI with a new Web client in the branding project.

Each server's data handling must match its code. Check the privacy policy against the code
whenever either one changes.

## License

[MIT](LICENSE)
