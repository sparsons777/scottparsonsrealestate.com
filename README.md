# scottparsonsrealestate.com

Static site, hosted free on GitHub Pages. No build step. Edit the HTML, commit, and it's live in about a minute.

## Folder map
- `index.html` — home page with the five panels
- `buyers/`, `sellers/`, `both/`, `fsbo/`, `home-value/` — one page each
- `open-house/<address>/index.html` — one folder per open house; copy `3733-harding` for the next one
- `assets/` — shared stylesheet, photos, logos, and the two guide PDFs
- `CNAME` — tells GitHub Pages the custom domain. Do not delete.

## Setup (one time, about 20 minutes)
1. On GitHub, create a new **public** repository named `scottparsonsrealestate.com` under `sparsons777`.
2. Upload everything in this folder to the repo (drag the whole folder contents into "uploading an existing file", or push with git). The `CNAME` file must be at the top level.
3. Repo → Settings → Pages → Source: "Deploy from a branch", Branch: `main`, folder `/ (root)`. Save.
4. On the same Pages screen, Custom domain: `scottparsonsrealestate.com` → Save. Tick "Enforce HTTPS" once it lets you (may take up to an hour).
5. At Squarespace Domains (where the domain lives now) → DNS settings. Delete the existing A record and the www CNAME that point to Squarespace. Add:

   | Type  | Host | Value                  |
   |-------|------|------------------------|
   | A     | @    | 185.199.108.153        |
   | A     | @    | 185.199.109.153        |
   | A     | @    | 185.199.110.153        |
   | A     | @    | 185.199.111.153        |
   | CNAME | www  | sparsons777.github.io  |

   Leave every MX and TXT record alone — that's your email.
6. Wait 15–60 minutes. Visit https://scottparsonsrealestate.com.

## Adding an open house
Copy `open-house/3733-harding/` to `open-house/<new-address>/`, edit the `L = {...}` block near the bottom of `index.html` (price, beds, photos, etc.) and the address text, commit. Then generate a QR code for `https://scottparsonsrealestate.com/open-house/<new-address>/`.
