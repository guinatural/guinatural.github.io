# Portfólio — Guilherme Barreto

**Site:** https://guinatural.github.io  
**Pasta no PC:** `C:\Users\barre\Documents\Codex\2026-08-15\me-ajude\work\portfolio`

**Mapa de todos os projetos (Holocron, Wayfinder, estudos):** [MAPA.md](MAPA.md)

## Páginas

- `index.html` — Landing
- `wayfinder.html` — Case Wayfinder Cloud (Config 24/7)
- `holocron.html` — Case Holocron Sentinel (agente sob demanda)
- `labs.html` — 23 labs SAA-C03
- `curriculo.html` — CV para impressão / PDF

## Publicar

```powershell
cd "C:\Users\barre\Documents\Codex\2026-08-15\me-ajude\work\portfolio"
git add .
git commit -m "feat(portfolio): case Holocron + mapa de pastas"
git push origin main
```

Settings → Pages → Source: **GitHub Actions** (workflow `deploy.yml`).

## Não confundir

| Pasta | O que é |
|---|---|
| Esta (`work\portfolio`) | Site público |
| `...\04_CODE\Holocron-Sentinel-V2` | Código do agente (scanners) |
| `...\work\holocron` | Rascunho MCP + docs — não é a fonte de verdade |
