# Mapa — onde cada coisa está (outubro 2026)

Estudos SAA-C03 estão **pausados**. Este arquivo é o ponto único para não misturar pastas.

---

## 1. Portfólio (trabalho ativo)

| | |
|---|---|
| **PC** | `C:\Users\barre\Documents\Codex\2026-08-15\me-ajude\work\portfolio` |
| **GitHub** | [github.com/guinatural/guinatural.github.io](https://github.com/guinatural/guinatural.github.io) |
| **Site** | [https://guinatural.github.io](https://guinatural.github.io) |

| Arquivo | Papel |
|---|---|
| `index.html` | Landing |
| `wayfinder.html` | Case study Wayfinder |
| `holocron.html` | Case study Holocron |
| `labs.html` | 23 labs SAA-C03 |
| `curriculo.html` | CV para imprimir |
| `.github/workflows/deploy.yml` | GitHub Pages |

**Atenção:** se `labs.html` der 404 no ar, o push local ainda não foi publicado. Faça `git push origin main` nesta pasta.

---

## 2. Holocron — código que vale (não confundir)

O Kiro diagnosticou `app/` vazia em **outra pasta**. O agente com scanners reais está aqui:

| | |
|---|---|
| **Código V2 (scanners, FileSessionManager, UI)** | `C:\Users\barre\AWS-reStart-Compliance-Portfolio\02 - ESTUDOS\AWS-re-Start\P - Holocron-Sentinel\04_CODE\Holocron-Sentinel-V2` |
| Arquivos-chave | `01_AGENT_CORE\scanners.py`, `main.py`, `holocron_ui_v2.py` |
| **GitHub público** | [Holocron-Sentinel-AWS-AgentCore](https://github.com/guinatural/Holocron-Sentinel-AWS-AgentCore) |

### Pasta Codex (rascunho / MCP) — não é o produto

`C:\Users\barre\Documents\Codex\2026-08-15\me-ajude\work\holocron`

- Tem `mcp\audit_event.py`, `generate_report.py`, `process_user_data.py` (wrappers Lambda)
- Tem muita documentação (`docs\`) e `.venv`
- `app/` vazia — **não use esta pasta como fonte de verdade do Sentinel**

### Workspace Cursor “P - Holocron-Sentinel”

`C:\Users\barre\AWS-reStart-Compliance-Portfolio\AWS-re-Start\P - Holocron-Sentinel`

- Clone de samples AgentCore + apontamento para o capstone
- Não é o site do portfólio

---

## 3. Wayfinder

Código: repositório [wayfinder-cloud](https://github.com/guinatural/wayfinder-cloud)  
Narrativa no site: `wayfinder.html`

**Holocron vs Wayfinder (para entrevista):**

- **Holocron** = agente **sob demanda** (prompt → Boto3 + Bedrock → relatório)
- **Wayfinder** = **vigilância 24/7** (AWS Config + EventBridge + Lambda + Terraform)

---

## 4. Estudos (pausado)

`C:\Users\barre\AWS-reStart-Compliance-Portfolio\02 - ESTUDOS\ARCHITECT_SAA-C03`  
Diário GitHub: [saa-c03-journey](https://github.com/guinatural/saa-c03-journey)  
Fork do material: [aws-solution-architect-study-material](https://github.com/guinatural/aws-solution-architect-study-material)

---

## 5. Próximo passo (portfólio)

1. Abrir a pasta **portfolio** no Cursor (não o Holocron-Sentinel samples)
2. Conferir localmente: `index`, `labs`, `holocron`, `wayfinder`, `curriculo`
3. Push para `guinatural.github.io` quando estiver ok
4. Código do agente: trabalhar em `Holocron-Sentinel-V2`, não em `work\holocron`
