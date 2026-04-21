# 18:00 · ein Pixel

Ein minimalistisches Mini-Spiel. Weißer Bildschirm. Jeden Tag um 18:00 Uhr lokaler Zeit wird ein einzelner Pixel grau. Wer seinen Cursor am nächsten an der Stelle hat, gewinnt.

Der Pixel ist jeden Tag an derselben Stelle für alle (deterministisch aus dem Datum berechnet) — relativ zur Bildschirm-Diagonale, d. h. jeder sieht ihn an der „gleichen Stelle" seines Screens.

## Spielregeln

1. Link öffnen, **vor 18:00**.
2. Cursor irgendwo auf dem Bildschirm positionieren. Optional: klicken, um die Position zu fixieren (sonst zählt die Cursor-Position zum Zeitpunkt 18:00:00.000).
3. Warten. Tiny countdown unten rechts.
4. Um 18:00:00 wird ein Pixel grau. Die Distanz zum Cursor wird angezeigt.
5. Ergebnis teilen, morgen wieder.

## URL-Parameter

- `?t=18:00` — Zeit überschreiben für Tests (z. B. `?t=14:30`)
- `?demo=10` — Reveal in 10 Sekunden ab jetzt
- Shortcut: **Taste `d` drücken** → triggert Reveal in 3 Sekunden

## Deployment auf Cloudflare Pages

```bash
cd pixel18
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin git@github.com:DEIN_USER/pixel18.git
git push -u origin main
```

Dann [dash.cloudflare.com](https://dash.cloudflare.com) → Workers & Pages → Create → Pages → Connect to Git:

- Framework preset: **None**
- Build command: *(leer)*
- Output dir: `/`

Fertig, nach ~30 s live auf `*.pages.dev`.

## Lokal testen

Einfach `index.html` im Browser öffnen, oder:

```bash
python3 -m http.server 8000
```
