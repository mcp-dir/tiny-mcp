# Tiny (Olist Tiny)

### Tiny (Olist Tiny) for Claude, ChatGPT and AI agents

Tiny (Olist Tiny) e-commerce ERP, one of the most used by online stores and marketplace sellers in Brazil. Query products and stock, sales orders, contacts, invoices and payables/receivables, and create contacts, via the official API. Pairs with the Banco MCP to reconcile orders and finances with the bank statement. Auth via token (generated in the Tiny account, in the Token API extension).

- 📊 **14 tools**
- ✏️ **Read and write**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → name `Tiny (Olist Tiny)`, URL `https://api.mcp.ai/p_tiny`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=tiny&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF90aW55In0=)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=tiny&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_tiny%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_tiny
```

---

## 14 tools

| Tool | Description |
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

---

## Pricing

See [docs/precos.md](docs/precos.md) (PT-BR).

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_tiny` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
