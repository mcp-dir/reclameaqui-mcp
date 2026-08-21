# Reclame Aqui

### Reclame Aqui para Claude, ChatGPT e agentes de IA

Gerencie as reclamações da sua empresa no Reclame Aqui pela conta da Área da Empresa. Você informa o usuário e a senha da empresa e a plataforma entra na sua conta para listar reclamações, ler o detalhe, ver a reputação e responder os consumidores. Não usa a RA API paga, usa a mesma área que você já acessa no site.

- 📊 **4 ferramentas**
- 🔒 **Somente leitura**
- 💬 **Funciona com qualquer cliente MCP**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Login via magic-link (sem senha)**

[English version](README.en.md) · [Documentação completa](docs/) · [Skill pra agentes](skills/)

---

## Instalar em 1 clique

### Claude (Web e Desktop)

A Anthropic unificou a instalação de MCPs em `claude.ai/customize/connectors`. **O mesmo link serve pra Claude Web e Claude Desktop** (basta estar logado):

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

**Manual** (se o deeplink não abrir): [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → cole **Nome** `Reclame Aqui` e **URL** `https://api.mcp.ai/p_reclameaqui`.

### Cursor

[➕ Instalar Reclame Aqui no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=reclameaqui&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9yZWNsYW1lYXF1aSJ9)

### VS Code (Copilot Chat)

[➕ Instalar Reclame Aqui no VS Code](vscode:mcp/install?name=reclameaqui&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_reclameaqui%22%7D)

### ChatGPT, Manus, OpenClaw e mais 40+ clientes

Funciona em qualquer cliente MCP que suporte **MCP over HTTP**. A URL do servidor é sempre:

```
https://api.mcp.ai/p_reclameaqui
```

Detalhes por cliente: [INSTALL.md](INSTALL.md).

---

## Exemplos de uso

```
Quais reclamações ainda não foram respondidas?
Me mostra o detalhe da última reclamação
Como está a reputação da minha empresa no Reclame Aqui?
```

---

## 4 ferramentas disponíveis

| Tool | Descrição |
|---|---|
| `reclameaqui_listar_reclamacoes` | Lista as reclamações da sua empresa no Reclame Aqui (mais recentes primeiro). |
| `reclameaqui_reclamacao` | Detalhe de uma ou mais reclamações por id (conversa completa em treatments, avaliação, score, status). |
| `reclameaqui_responder` | Responde uma reclamação da sua empresa no Reclame Aqui. |
| `reclameaqui_reputacao` | Indicadores de reputação da sua empresa no Reclame Aqui (nota/rating e principais problemas reclamados). |

Detalhe de cada tool: [docs/ferramentas.md](docs/ferramentas.md)

---

## Preços

Planos a partir do tier grátis. Veja [docs/precos.md](docs/precos.md).

---

## Privacidade & LGPD

- **Somente leitura**, nenhuma ferramenta altera dados na origem.
- **Sub-processadores**: Reclame Aqui (RA Trust Company), o LLM host que você escolher (Claude, ChatGPT, Cursor, agente próprio). Lista completa em [docs/privacidade-lgpd.md](docs/privacidade-lgpd.md).
- Os dados retornados pelas tools são enviados ao **LLM host que você escolher**, sub-processador fora do nosso controle. Recomendamos planos com opt-out de treinamento.

---

## Perguntas frequentes

**O servidor é open source?**
O servidor é proprietário (hosted). Este repositório é o wrapper público com manifestos, docs e skills — tudo MIT.

**Posso usar com agente próprio (não Claude/Cursor)?**
Sim — qualquer cliente que suporte MCP over HTTP. URL: `https://api.mcp.ai/p_reclameaqui`.


---

## Suporte

- 📧 [reclameaqui@mcp.ai](mailto:reclameaqui@mcp.ai)
- 🐛 [GitHub Issues](https://github.com/mcp-dir/reclameaqui-mcp/issues)
- 📄 [docs/](docs/)

---

## Licença

MIT — veja [LICENSE](LICENSE). O servidor MCP em `api.mcp.ai/p_reclameaqui` é proprietário (hosted); este repositório (manifestos, docs, skills) é MIT.
