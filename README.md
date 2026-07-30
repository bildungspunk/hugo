# BildungsPunk Hugo

Neue, wartbare Quelle für bildungspunk.de. Die bisher auffindbare GitHub-Pages-Arbeitskopie enthält nur den generierten Stand; deshalb liegt diese Hugo-Quelle bewusst in einem getrennten Verzeichnis.

## Lokal starten

```sh
hugo server --disableFastRender
```

## Produktions-Build prüfen

Immer in ein leeres Zielverzeichnis bauen:

```sh
preview_dir="$(mktemp -d)"
hugo --environment production --destination "$preview_dir"
```

Die Veröffentlichung darf nicht pauschal über die bestehende `gh-pages`-Arbeitskopie synchronisiert werden. Insbesondere diese Pfade gehören nicht zur BildungsPunk-Seite und müssen unverändert bleiben:

- `care/`
- `.well-known/apple-app-site-association`

Vor einer Veröffentlichung werden nur ausdrücklich freigegebene BildungsPunk-Dateien übernommen und die geschützten Dateien per Prüfsumme kontrolliert.

