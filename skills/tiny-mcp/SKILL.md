---
name: tiny-mcp
description: Skill da REST API do Tiny (Olist Tiny) na MCP.AI: 14 endpoints em /api/tiny. ERP de e-commerce Tiny (Olist Tiny), um dos mais usados por lojas virtuais e sellers de marketplace no Brasil. Consulta produtos e estoque, pedidos de venda, contatos, notas fiscais e contas a pagar/receber, e cadastra contatos, via API oficial. Pareia com o Banco MCP pra conciliar pedidos e financeiro com o extrato. Autenticação por token (gerado na conta Tiny, na extensão Token API). Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Tiny (Olist Tiny) — REST API skill

Você tem acesso à **Tiny (Olist Tiny)** REST API na MCP.AI.

> ERP de e-commerce Tiny (Olist Tiny), um dos mais usados por lojas virtuais e sellers de marketplace no Brasil. Consulta produtos e estoque, pedidos de venda, contatos, notas fiscais e contas a pagar/receber, e cadastra contatos, via API oficial. Pareia com o Banco MCP pra conciliar pedidos e financeiro com o extrato. Autenticação por token (gerado na conta Tiny, na extensão Token API).

## Base URL

```
https://api.mcp.ai/api/tiny
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
curl -X POST https://api.mcp.ai/api/tiny/create/contact \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"data":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/tiny/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (14)

#### `tiny_create_contact`

Cadastra um contato (cliente/fornecedor) — contato.incluir.php. _(POST /api/tiny/create/contact)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `data` | string | Sim | Payload do contato como JSON string |
| `account` | string | Não | Quando há múltiplas empresas Tiny conectadas: id ou label da conexão. Veja tiny_list_accounts. |

#### `tiny_get_contact`

Detalha um contato pelo `id` (contato.obter.php). _(POST /api/tiny/get/contact)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `id` | string|number | Sim | Id do registro no Tiny (ex.: id do produto/pedido/contato/nota). |
| `account` | string | Não | Quando há múltiplas empresas Tiny conectadas: id ou label da conexão. Veja tiny_list_accounts. |
| `ids` | string|number[] | Não | Bulk mode: multiple values for id |

#### `tiny_get_invoice`

Detalha uma nota fiscal pelo `id` (nota.fiscal.obter.php). _(POST /api/tiny/get/invoice)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `id` | string|number | Sim | Id do registro no Tiny (ex.: id do produto/pedido/contato/nota). |
| `account` | string | Não | Quando há múltiplas empresas Tiny conectadas: id ou label da conexão. Veja tiny_list_accounts. |
| `ids` | string|number[] | Não | Bulk mode: multiple values for id |

#### `tiny_get_order`

Detalha um pedido pelo `id` (pedido.obter.php). _(POST /api/tiny/get/order)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `id` | string|number | Sim | Id do registro no Tiny (ex.: id do produto/pedido/contato/nota). |
| `account` | string | Não | Quando há múltiplas empresas Tiny conectadas: id ou label da conexão. Veja tiny_list_accounts. |
| `ids` | string|number[] | Não | Bulk mode: multiple values for id |

#### `tiny_get_product`

Detalha um produto pelo `id` (produto.obter.php). _(POST /api/tiny/get/product)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `id` | string|number | Sim | Id do registro no Tiny (ex.: id do produto/pedido/contato/nota). |
| `account` | string | Não | Quando há múltiplas empresas Tiny conectadas: id ou label da conexão. Veja tiny_list_accounts. |
| `ids` | string|number[] | Não | Bulk mode: multiple values for id |

#### `tiny_get_product_stock`

Saldo de estoque de um produto pelo `id` (produto.obter.estoque.php). _(POST /api/tiny/get/product/stock)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `id` | string|number | Sim | Id do registro no Tiny (ex.: id do produto/pedido/contato/nota). |
| `account` | string | Não | Quando há múltiplas empresas Tiny conectadas: id ou label da conexão. Veja tiny_list_accounts. |
| `ids` | string|number[] | Não | Bulk mode: multiple values for id |

#### `tiny_list_accounts`

Lista as empresas (CNPJ) Tiny conectadas a este install — id, label. _(POST /api/tiny/list/accounts)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Tiny conectadas: id ou label da conexão. Veja tiny_list_accounts. |

#### `tiny_list_contacts`

Pesquisa contatos (contatos.pesquisa.php). _(POST /api/tiny/list/contacts)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `search` | string | Não | Termo de pesquisa (nome, código, etc.). Vai no param `pesquisa` do Tiny. |
| `page` | integer | Não | Página (default 1) |
| `filters` | string | Não | Filtros extras como JSON string, mesclados nos params da chamada Tiny (ex.: {"dataInicial":"01/01/2026","dataFinal":"31/01/2026","situacao":"aberto"}). Datas no padrão Tiny DD/MM/AAAA. |
| `account` | string | Não | Quando há múltiplas empresas Tiny conectadas: id ou label da conexão. Veja tiny_list_accounts. |

#### `tiny_list_invoices`

Pesquisa notas fiscais (notas.fiscais.pesquisa.php). _(POST /api/tiny/list/invoices)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `search` | string | Não | Termo de pesquisa (nome, código, etc.). Vai no param `pesquisa` do Tiny. |
| `page` | integer | Não | Página (default 1) |
| `filters` | string | Não | Filtros extras como JSON string, mesclados nos params da chamada Tiny (ex.: {"dataInicial":"01/01/2026","dataFinal":"31/01/2026","situacao":"aberto"}). Datas no padrão Tiny DD/MM/AAAA. |
| `account` | string | Não | Quando há múltiplas empresas Tiny conectadas: id ou label da conexão. Veja tiny_list_accounts. |

#### `tiny_list_orders`

Pesquisa pedidos de venda (pedidos.pesquisa.php). _(POST /api/tiny/list/orders)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `search` | string | Não | Termo de pesquisa (nome, código, etc.). Vai no param `pesquisa` do Tiny. |
| `page` | integer | Não | Página (default 1) |
| `filters` | string | Não | Filtros extras como JSON string, mesclados nos params da chamada Tiny (ex.: {"dataInicial":"01/01/2026","dataFinal":"31/01/2026","situacao":"aberto"}). Datas no padrão Tiny DD/MM/AAAA. |
| `account` | string | Não | Quando há múltiplas empresas Tiny conectadas: id ou label da conexão. Veja tiny_list_accounts. |

#### `tiny_list_payables`

Lista contas a pagar (contas.pagar.pesquisa.php). _(POST /api/tiny/list/payables)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `search` | string | Não | Termo de pesquisa (nome, código, etc.). Vai no param `pesquisa` do Tiny. |
| `page` | integer | Não | Página (default 1) |
| `filters` | string | Não | Filtros extras como JSON string, mesclados nos params da chamada Tiny (ex.: {"dataInicial":"01/01/2026","dataFinal":"31/01/2026","situacao":"aberto"}). Datas no padrão Tiny DD/MM/AAAA. |
| `account` | string | Não | Quando há múltiplas empresas Tiny conectadas: id ou label da conexão. Veja tiny_list_accounts. |

#### `tiny_list_products`

Pesquisa produtos (produtos.pesquisa.php). _(POST /api/tiny/list/products)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `search` | string | Não | Termo de pesquisa (nome, código, etc.). Vai no param `pesquisa` do Tiny. |
| `page` | integer | Não | Página (default 1) |
| `filters` | string | Não | Filtros extras como JSON string, mesclados nos params da chamada Tiny (ex.: {"dataInicial":"01/01/2026","dataFinal":"31/01/2026","situacao":"aberto"}). Datas no padrão Tiny DD/MM/AAAA. |
| `account` | string | Não | Quando há múltiplas empresas Tiny conectadas: id ou label da conexão. Veja tiny_list_accounts. |

#### `tiny_list_receivables`

Lista contas a receber (contas.receber.pesquisa.php). _(POST /api/tiny/list/receivables)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `search` | string | Não | Termo de pesquisa (nome, código, etc.). Vai no param `pesquisa` do Tiny. |
| `page` | integer | Não | Página (default 1) |
| `filters` | string | Não | Filtros extras como JSON string, mesclados nos params da chamada Tiny (ex.: {"dataInicial":"01/01/2026","dataFinal":"31/01/2026","situacao":"aberto"}). Datas no padrão Tiny DD/MM/AAAA. |
| `account` | string | Não | Quando há múltiplas empresas Tiny conectadas: id ou label da conexão. Veja tiny_list_accounts. |

#### `tiny_list_sellers`

Pesquisa vendedores (vendedores.pesquisa.php). _(POST /api/tiny/list/sellers)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `search` | string | Não | Termo de pesquisa (nome, código, etc.). Vai no param `pesquisa` do Tiny. |
| `page` | integer | Não | Página (default 1) |
| `filters` | string | Não | Filtros extras como JSON string, mesclados nos params da chamada Tiny (ex.: {"dataInicial":"01/01/2026","dataFinal":"31/01/2026","situacao":"aberto"}). Datas no padrão Tiny DD/MM/AAAA. |
| `account` | string | Não | Quando há múltiplas empresas Tiny conectadas: id ou label da conexão. Veja tiny_list_accounts. |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_tiny` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
