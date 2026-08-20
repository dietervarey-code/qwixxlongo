# Qwixx Longo · digitaal scoreblad (PWA)

Fan-made, interactief en volledig offline te gebruiken digitaal scoreblad voor Qwixx Longo.
Installeerbaar als app op Android, iOS/iPadOS, en desktop (Chrome/Edge).

## Lokaal testen

Open gewoon `index.html` in de browser, of start een lokale server:

```bash
python3 -m http.server 8080
```

en ga naar `http://localhost:8080`.

> Let op: `beforeinstallprompt` (de "Installeer app"-knop) en de service worker
> werken pas correct via **https** of **localhost** — niet via `file://`.

## Op GitHub Pages zetten

1. Maak een nieuwe repository aan op GitHub (bv. `qwixx-longo-pwa`).
2. Push deze bestanden naar de `main`-branch:

   ```bash
   git init
   git add .
   git commit -m "Qwixx Longo PWA"
   git branch -M main
   git remote add origin https://github.com/<jouw-gebruikersnaam>/qwixx-longo-pwa.git
   git push -u origin main
   ```

3. Ga naar **Settings → Pages** in de repo.
4. Bij **Source**: kies branch `main`, map `/ (root)`.
5. Na ~1 minuut is de app live op:
   `https://<jouw-gebruikersnaam>.github.io/qwixx-longo-pwa/`

## App installeren

- **Android (Chrome):** open de link → tik op "⬇ Installeer app" bovenaan,
  of via het browsermenu → "App installeren".
- **iOS/iPadOS (Safari):** open de link → deel-icoon → "Zet op beginscherm".
- **Desktop (Chrome/Edge):** klik op het install-icoontje in de adresbalk.

## Bestanden

- `index.html` — de volledige app (HTML/CSS/JS, geen build-stap nodig)
- `manifest.json` — app-naam, icons, kleuren voor installatie
- `service-worker.js` — cachet de app zodat hij offline werkt
- `icons/` — app-iconen (192px, 512px, maskable)

## Later: gedeelde scores

Deze versie werkt volledig lokaal (localStorage), er is nog geen synchronisatie
tussen spelers. Voor een "kamercode" waarmee jullie elkaars scores live zien
is een klein back-end nodig (bv. Firebase Realtime Database) — dat kan als
volgende stap bovenop deze PWA gebouwd worden.
