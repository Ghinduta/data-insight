# datainsight.ro – pagină de prezentare

Site static, un singur fișier (`index.html`), fără build.

## Publicare pe Cloudflare Pages (DNS-ul e deja pe Cloudflare)

1. Push repo-ul pe GitHub (vezi mai jos).
2. Cloudflare Dashboard → Workers & Pages → Create → Pages → Connect to Git → alege repo-ul.
   - Framework preset: None · Build command: (gol) · Build output directory: `/`
3. După primul deploy: Pages → proiect → Custom domains → Add `datainsight.ro` și `www.datainsight.ro`.
   Cloudflare creează singur înregistrările CNAME (domeniul e în același cont).
4. Orice `git push` pe `main` republică automat în ~1 minut.

## Prima publicare pe GitHub

```bash
git init -b main
git add .
git commit -m "Pagina de prezentare"
gh repo create datainsight-site --public --source=. --push
# sau, fără gh: creează repo pe github.com, apoi
# git remote add origin git@github.com:<user>/datainsight-site.git && git push -u origin main
```
