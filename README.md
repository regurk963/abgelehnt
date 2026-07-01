# abgelehnt! — Legal & Support site

Static legal/support pages for the **abgelehnt!** app (Privacy, Terms, Support, Impressum) in German + English.
Published at **https://abgelehnt.regurk.ie**. Publisher: REGURK LIMITED.

## Structure
```
/                index.html        (bilingual landing)
/style.css       shared styles
/CNAME           abgelehnt.regurk.ie   ← required, keep at repo root
/impressum.html  shared legal notice
/de/             privacy.html · terms.html · support.html
/en/             privacy.html · terms.html · support.html
```

## Deploy (GitHub Pages + Cloudflare)

1. Create a **public** repo named `abgelehnt` and upload everything in this folder to the repo **root** (so `index.html` and `CNAME` sit at the top level — not inside a subfolder).
2. GitHub → repo **Settings → Pages** → *Build and deployment* → Source: **Deploy from a branch**, Branch: `main` / `/ (root)` → Save.
3. Still under Pages → **Custom domain**: enter `abgelehnt.regurk.ie` → Save. (The included `CNAME` file already sets this.)
4. **Cloudflare DNS** (regurk.ie zone) → add a record:
   - Type **CNAME**, Name **abgelehnt**, Target **`<your-github-username>.github.io`**
   - Set it to **DNS only (grey cloud)** at first so GitHub can issue the HTTPS certificate. Once Pages shows the cert is ready, tick **Enforce HTTPS** in the Pages settings. You can switch the record to proxied (orange) afterwards **only if** Cloudflare SSL/TLS mode is **Full** (not Flexible), otherwise you'll get a redirect loop.
5. Wait for the cert (a few minutes to ~an hour), then check **https://abgelehnt.regurk.ie**.

## URLs for the Play Store listing
- Privacy (DE): `https://abgelehnt.regurk.ie/de/privacy.html`
- Privacy (EN): `https://abgelehnt.regurk.ie/en/privacy.html`
- Support: `https://abgelehnt.regurk.ie/de/support.html` · `/en/support.html`

© 2026 REGURK LIMITED
