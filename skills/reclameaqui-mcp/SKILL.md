---
name: reclameaqui-mcp
description: Skill da REST API do Reclame Aqui na MCP.AI: 4 endpoints em /api/reclameaqui. Gerencie as reclamações da sua empresa no Reclame Aqui pela conta da Área da Empresa. Você informa o usuário e a senha da empresa e a plataforma entra na sua conta para listar reclamações, ler o detalhe, ver a reputação e responder os consumidores. Não usa a RA API paga, usa a mesma área que você já acessa no site. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Reclame Aqui — REST API skill

Você tem acesso à **Reclame Aqui** REST API na MCP.AI.

> Gerencie as reclamações da sua empresa no Reclame Aqui pela conta da Área da Empresa. Você informa o usuário e a senha da empresa e a plataforma entra na sua conta para listar reclamações, ler o detalhe, ver a reputação e responder os consumidores. Não usa a RA API paga, usa a mesma área que você já acessa no site.

## Base URL

```
https://api.mcp.ai/api/reclameaqui
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/reclameaqui/listar/reclamacoes \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/reclameaqui/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (4)

#### `reclameaqui_listar_reclamacoes`

Lista as reclamações da sua empresa no Reclame Aqui (mais recentes primeiro). _(POST /api/reclameaqui/listar/reclamacoes)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `status` | string | Não | Filtro de status. Default: todas. (todas, nao_respondidas, respondidas, avaliadas, replicas) |
| `limit` | integer | Não | Quantas reclamações por página (default 10, máx 50). |
| `index` | integer | Não | Deslocamento para paginação (default 0). |
| `order` | string | Não | Campo de ordenação (default: created). |
| `order_type` | string | Não | Direção da ordenação (default: desc). (asc, desc) |

#### `reclameaqui_reclamacao`

Detalhe de uma ou mais reclamações por id (conversa completa em treatments, avaliação, score, status). _(POST /api/reclameaqui/reclamacao)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `ids` | string[] | Não | IDs das reclamações (resolve N numa chamada). |
| `id` | string | Não | ID de uma única reclamação (alternativa a ids). |

#### `reclameaqui_reputacao`

Indicadores de reputação da sua empresa no Reclame Aqui (nota/rating e principais problemas reclamados). _(POST /api/reclameaqui/reputacao)_

#### `reclameaqui_responder`

Responde uma reclamação da sua empresa no Reclame Aqui. _(POST /api/reclameaqui/responder)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `id` | string | Sim | ID da reclamação a responder. |
| `mensagem` | string | Sim | Texto da resposta ao consumidor. |
| `privada` | boolean | Não | Se true, envia como mensagem privada em vez de resposta pública. Default false. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_reclameaqui` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
