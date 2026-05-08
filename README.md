# UnboxEleven Asset CDN

Public CDN für UE-Deliverables (Email-Signaturen, Visitenkarten, Reports) über GitHub Pages auf `cdn.unboxeleven.com`.

## Struktur

```
allpersona/    Cert-Logos für Allpersona-Email-Signatur (IZS, GVP, TÜV ISO 9001, BB50, KURIER Top Berater AT)
```

Pro Kunde ein Subfolder. Asset-URLs lauten `https://cdn.unboxeleven.com/<kunde>/<file>`.

## Stabilität

- **Public** — alle Assets sind brand-frei verteilbar (Verband-Logos, Auszeichnungen).
- **Free** — GitHub Pages auf public Repo, keine Kosten, keine Server-Maintenance.
- **CDN** — globale Latenz via GitHub-Edge-Network.
- **Versions-tracked** — jede Asset-Änderung als Git-Commit nachvollziehbar.

## Asset-Update-Workflow

```bash
# Datei ersetzen oder hinzufügen
cp neue-version.png allpersona/

# Commit + Push
git add allpersona/
git commit -m "update: <kunde> <was geändert>"
git push origin main
```

Roll-out auf Live-CDN: ~1-2 Minuten nach Push.

## Cache-Invalidation

Bei Asset-Update bleibt URL gleich, GitHub-Pages cached aber. Browser-/Outlook-Cache kann älteren Stand zeigen. Empfehlung: bei breaking changes URL versionieren (`bb50-logo-v2.png`).

## Verbundene Deliverables

- **Allpersona Email-Signatur-Builder** — `Allpersona_E-Mail-Signatur_2026-05.html` lädt Cert-Logos via Toggle `ASSET_BASE = 'https://cdn.unboxeleven.com/allpersona'`.

## Operator

Babu · UnboxEleven · `babu@unboxeleven.com`
