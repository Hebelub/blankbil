# Blank Bil – blankbil.no

Statisk én-sides nettside (`index.html` + `favicon.svg`). Ingen byggesteg.

## 1. Push til GitHub
```bash
cd blankbil
git init && git add index.html favicon.svg README.md
git commit -m "Blank Bil nettside"
git branch -M main
git remote add origin https://github.com/<brukernavn>/blankbil.git
git push -u origin main
```
(Opprett først et tomt repo `blankbil` på github.com.)

## 2. Deploy på Vercel
1. Logg inn på vercel.com med GitHub.
2. **Add New → Project** → velg `blankbil`-repoet → Import.
3. Framework Preset: **Other**. La Build Command og Output Directory stå tomme → **Deploy**.
Hver ny push til `main` publiseres automatisk.

## 3. Koble til blankbil.no
1. Vercel → Project → **Settings → Domains** → legg til `blankbil.no` og `www.blankbil.no`.
2. Hos domeneregistraren (f.eks. Domeneshop), legg inn DNS:
   | Type  | Navn | Verdi                  |
   |-------|------|------------------------|
   | A     | @    | `76.76.21.21`          |
   | CNAME | www  | `cname.vercel-dns.com` |
3. Vent på DNS (minutter til noen timer). Vercel lager HTTPS automatisk.

## Endre innhold
- **Bilder før/etter:** legg bilder i `bilder/` og bytt en `<div class="tile">…Bilde kommer</div>` med
  `<div class="tile"><img src="/bilder/for1.jpg" alt="Bil før vask"></div>`.
- **Omtaler:** bytt eksempeltekstene og fjern `<span class="example">EKSEMPEL</span>`.
- **Priser:** i seksjonen `id="priser"` og i JSON-LD øverst. Priser: 299 kr per vask, 499 kr komplett.
