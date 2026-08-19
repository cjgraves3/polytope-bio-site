# polytope.bio

Static placeholder landing page. One file: `index.html`.

## Deploy

GitHub Pages serves this repo's root from `main`. Push to `main` and it's live in ~1 minute.

`CNAME` pins the custom domain to `polytope.bio` — GitHub rewrites this file if you change the
domain in Settings, so edit it in one place or the other, not both.

## Domains

`polytope.bio` is the canonical site. The other four 301-redirect to it at the registrar / DNS
layer, because GitHub Pages supports only one custom domain per repo:

| Domain | Registrar | Role |
|---|---|---|
| `polytope.bio` | — | canonical, served by Pages |
| `polytope-bio.ai` | — | redirect |
| `polytopebio.ai` | — | redirect |
| `polytope-bio.com` | — | redirect |
| `polytopebio.com` | — | redirect |

## DNS for the canonical domain

Apex `polytope.bio` — four A records and four AAAA records pointing at GitHub Pages:

```
A     @   185.199.108.153
A     @   185.199.109.153
A     @   185.199.110.153
A     @   185.199.111.153
AAAA  @   2606:50c0:8000::153
AAAA  @   2606:50c0:8001::153
AAAA  @   2606:50c0:8002::153
AAAA  @   2606:50c0:8003::153
CNAME www cjgraves3.github.io.
```

If this domain sits on Cloudflare DNS, these records must be **DNS only** (grey cloud). Proxying
them blocks GitHub's Let's Encrypt HTTP-01 challenge and "Enforce HTTPS" never becomes available.

## Local preview

Just open `index.html` in a browser — there's no build step.
