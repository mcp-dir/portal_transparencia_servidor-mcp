---
name: portal_transparencia_servidor-mcp
description: Skill da REST API do Portal da Transparência: Servidor Público na MCP.AI: 1 endpoint em /api/portal_transparencia_servidor. Portal da Transparência: Servidor Público, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Portal da Transparência: Servidor Público — REST API skill

Você tem acesso à **Portal da Transparência: Servidor Público** REST API na MCP.AI.

> Portal da Transparência: Servidor Público, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/portal_transparencia_servidor
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
curl -X POST https://api.mcp.ai/api/portal_transparencia_servidor/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/portal_transparencia_servidor/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `portal_transparencia_servidor_consultar`

Portal da Transparência: Servidor Público, consulta em fonte oficial. _(POST /api/portal_transparencia_servidor/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `cpf` | string | Não | Parâmetro de consulta "cpf". |
| `nome` | string | Não | Parâmetro de consulta "nome". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_portal_transparencia_servidor` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
