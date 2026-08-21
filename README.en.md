# Reclame Aqui

### Reclame Aqui for Claude, ChatGPT and AI agents

Manage your company's complaints on Reclame Aqui through the Company Area account. You provide the company user and password and the platform logs into your account to list complaints, read details, check reputation and reply to consumers. It does not use the paid RA API, it uses the same area you already access on the site.

- 📊 **4 tools**
- 🔒 **Read-only**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → name `Reclame Aqui`, URL `https://api.mcp.ai/p_reclameaqui`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=reclameaqui&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9yZWNsYW1lYXF1aSJ9)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=reclameaqui&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_reclameaqui%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_reclameaqui
```

---

## 4 tools

| Tool | Description |
|---|---|
| `reclameaqui_listar_reclamacoes` | Lista as reclamações da sua empresa no Reclame Aqui (mais recentes primeiro). |
| `reclameaqui_reclamacao` | Detalhe de uma ou mais reclamações por id (conversa completa em treatments, avaliação, score, status). |
| `reclameaqui_responder` | Responde uma reclamação da sua empresa no Reclame Aqui. |
| `reclameaqui_reputacao` | Indicadores de reputação da sua empresa no Reclame Aqui (nota/rating e principais problemas reclamados). |

---

## Pricing

See [docs/precos.md](docs/precos.md) (PT-BR).

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_reclameaqui` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
