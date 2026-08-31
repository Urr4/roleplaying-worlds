# Rollenspiel-Welten

Dieses Repository ist ein [Quartz](https://quartz.jzhao.xyz/)-basiertes Wissensarchiv (Obsidian-Vault), das automatisch mit Weltfakten aus den Abenteuer-Transkripten des `roleplayer`-Tools gefüllt wird.

## Struktur

```
content/
└── worlds/
    └── <world-slug>/
        ├── index.md
        ├── Locations/*.md
        ├── People/*.md
        ├── Events/*.md
        └── Culture/*.md
```

Jede Welt bekommt einen eigenen Ordner unter `content/worlds/<slug>/`. Notizen einer Welt verweisen ausschließlich auf andere Notizen **derselben** Welt — es gibt keine Querverweise zwischen Welten.

Wenn im `roleplayer` ein Abenteuer beendet wird, analysiert eine lokal gehostete LLM (Ollama) das Transkript und committet neue/aktualisierte Notizen automatisch in den passenden Weltordner.

## Hosting

Der Build läuft über GitHub Actions (`.github/workflows/deploy.yml`) und wird auf GitHub Pages veröffentlicht (Settings → Pages → Source: GitHub Actions).

## Lokale Entwicklung

```
npm i
npx quartz build --serve
```
