# Tiny (Olist Tiny)

### Tiny (Olist Tiny) para Claude, ChatGPT e agentes de IA

ERP de e-commerce Tiny (Olist Tiny), um dos mais usados por lojas virtuais e sellers de marketplace no Brasil. Consulta produtos e estoque, pedidos de venda, contatos, notas fiscais e contas a pagar/receber, e cadastra contatos, via API oficial. Pareia com o Banco MCP pra conciliar pedidos e financeiro com o extrato. Autenticação por token (gerado na conta Tiny, na extensão Token API).

- 📊 **14 ferramentas**
- ✏️ **Leitura e escrita**
- 💬 **Funciona com qualquer cliente MCP**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Login via magic-link (sem senha)**

[English version](README.en.md) · [Documentação completa](docs/) · [Skill pra agentes](skills/)

---

## Instalar em 1 clique

### Claude (Web e Desktop)

A Anthropic unificou a instalação de MCPs em `claude.ai/customize/connectors`. **O mesmo link serve pra Claude Web e Claude Desktop** (basta estar logado):

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

**Manual** (se o deeplink não abrir): [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → cole **Nome** `Tiny (Olist Tiny)` e **URL** `https://api.mcp.ai/p_tiny`.

### Cursor

[➕ Instalar Tiny (Olist Tiny) no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=tiny&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF90aW55In0=)

### VS Code (Copilot Chat)

[➕ Instalar Tiny (Olist Tiny) no VS Code](vscode:mcp/install?name=tiny&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_tiny%22%7D)

### ChatGPT, Manus, OpenClaw e mais 40+ clientes

Funciona em qualquer cliente MCP que suporte **MCP over HTTP**. A URL do servidor é sempre:

```
https://api.mcp.ai/p_tiny
```

Detalhes por cliente: [INSTALL.md](INSTALL.md).

---

## Exemplos de uso

```
Quais pedidos de venda entraram nos últimos 7 dias?
Qual o estoque do produto SKU ABC?
Liste as contas a receber em aberto pra conciliar com o banco
```

---

## 14 ferramentas disponíveis

| Tool | Descrição |
|---|---|
| `tiny_list_accounts` | Lista as empresas (CNPJ) Tiny conectadas a este install — id, label. |
| `tiny_list_products` | Pesquisa produtos (produtos.pesquisa.php). |
| `tiny_get_product` | Detalha um produto pelo `id` (produto.obter.php). |
| `tiny_get_product_stock` | Saldo de estoque de um produto pelo `id` (produto.obter.estoque.php). |
| `tiny_list_orders` | Pesquisa pedidos de venda (pedidos.pesquisa.php). |
| `tiny_get_order` | Detalha um pedido pelo `id` (pedido.obter.php). |
| `tiny_list_contacts` | Pesquisa contatos (contatos.pesquisa.php). |
| `tiny_get_contact` | Detalha um contato pelo `id` (contato.obter.php). |
| `tiny_create_contact` | Cadastra um contato (cliente/fornecedor) — contato.incluir.php. |
| `tiny_list_invoices` | Pesquisa notas fiscais (notas.fiscais.pesquisa.php). |
| `tiny_get_invoice` | Detalha uma nota fiscal pelo `id` (nota.fiscal.obter.php). |
| `tiny_list_payables` | Lista contas a pagar (contas.pagar.pesquisa.php). |
| `tiny_list_receivables` | Lista contas a receber (contas.receber.pesquisa.php). |
| `tiny_list_sellers` | Pesquisa vendedores (vendedores.pesquisa.php). |

Detalhe de cada tool: [docs/ferramentas.md](docs/ferramentas.md)

---

## Preços

Planos a partir do tier grátis. Veja [docs/precos.md](docs/precos.md).

---

## Privacidade & LGPD

- **Sub-processadores**: Tiny (Olist), o LLM host que você escolher (Claude, ChatGPT, Cursor, agente próprio). Lista completa em [docs/privacidade-lgpd.md](docs/privacidade-lgpd.md).
- Os dados retornados pelas tools são enviados ao **LLM host que você escolher**, sub-processador fora do nosso controle. Recomendamos planos com opt-out de treinamento.

---

## Perguntas frequentes

**O servidor é open source?**
O servidor é proprietário (hosted). Este repositório é o wrapper público com manifestos, docs e skills — tudo MIT.

**Posso usar com agente próprio (não Claude/Cursor)?**
Sim — qualquer cliente que suporte MCP over HTTP. URL: `https://api.mcp.ai/p_tiny`.


---

## Suporte

- 📧 [tiny@mcp.ai](mailto:tiny@mcp.ai)
- 🐛 [GitHub Issues](https://github.com/mcp-dir/tiny-mcp/issues)
- 📄 [docs/](docs/)

---

## Licença

MIT — veja [LICENSE](LICENSE). O servidor MCP em `api.mcp.ai/p_tiny` é proprietário (hosted); este repositório (manifestos, docs, skills) é MIT.
