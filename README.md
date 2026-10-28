# datainsight.ro – pagină de prezentare

Site static, un singur fișier (`public/index.html`), fără build. Servit ca static assets
dintr-un Cloudflare Worker (config în `wrangler.jsonc`).

## Publicare pe Cloudflare Workers (DNS-ul e deja pe Cloudflare)

1. Repo-ul e pe GitHub: `Ghinduta/data-insight`, branch `main`.
2. Cloudflare Dashboard → Workers & Pages → Create application → Continue with GitHub → alege repo-ul → Deploy.
   - Build command: (gol) · Deploy command: `npx wrangler deploy`
3. După primul deploy: Worker → Settings → Domains & Routes → Add → Custom domain:
   `datainsight.ro` și `www.datainsight.ro`. Cloudflare creează singur înregistrările DNS (domeniul e în același cont).
4. Orice `git push` pe `main` republică automat în ~1 minut.

Verificare locală fără deploy: `npx wrangler deploy --dry-run`.
