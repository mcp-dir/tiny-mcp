# Ferramentas

Tiny (Olist Tiny) expõe 14 ferramentas.

### 1. `tiny_list_accounts`
**Input**: `account` (opcional)

Lista as empresas (CNPJ) Tiny conectadas a este install — id, label.

### 2. `tiny_list_products`
**Input**: `search` (opcional), `page` (opcional), `filters` (opcional), `account` (opcional)

Pesquisa produtos (produtos.pesquisa.php).

### 3. `tiny_get_product`
**Input**: `id`, `account` (opcional), `ids` (opcional)

Detalha um produto pelo `id` (produto.obter.php).

### 4. `tiny_get_product_stock`
**Input**: `id`, `account` (opcional), `ids` (opcional)

Saldo de estoque de um produto pelo `id` (produto.obter.estoque.php).

### 5. `tiny_list_orders`
**Input**: `search` (opcional), `page` (opcional), `filters` (opcional), `account` (opcional)

Pesquisa pedidos de venda (pedidos.pesquisa.php).

### 6. `tiny_get_order`
**Input**: `id`, `account` (opcional), `ids` (opcional)

Detalha um pedido pelo `id` (pedido.obter.php).

### 7. `tiny_list_contacts`
**Input**: `search` (opcional), `page` (opcional), `filters` (opcional), `account` (opcional)

Pesquisa contatos (contatos.pesquisa.php).

### 8. `tiny_get_contact`
**Input**: `id`, `account` (opcional), `ids` (opcional)

Detalha um contato pelo `id` (contato.obter.php).

### 9. `tiny_create_contact`
**Input**: `data`, `account` (opcional)

Cadastra um contato (cliente/fornecedor) — contato.incluir.php.

### 10. `tiny_list_invoices`
**Input**: `search` (opcional), `page` (opcional), `filters` (opcional), `account` (opcional)

Pesquisa notas fiscais (notas.fiscais.pesquisa.php).

### 11. `tiny_get_invoice`
**Input**: `id`, `account` (opcional), `ids` (opcional)

Detalha uma nota fiscal pelo `id` (nota.fiscal.obter.php).

### 12. `tiny_list_payables`
**Input**: `search` (opcional), `page` (opcional), `filters` (opcional), `account` (opcional)

Lista contas a pagar (contas.pagar.pesquisa.php).

### 13. `tiny_list_receivables`
**Input**: `search` (opcional), `page` (opcional), `filters` (opcional), `account` (opcional)

Lista contas a receber (contas.receber.pesquisa.php).

### 14. `tiny_list_sellers`
**Input**: `search` (opcional), `page` (opcional), `filters` (opcional), `account` (opcional)

Pesquisa vendedores (vendedores.pesquisa.php).

## Prompts de exemplo

```
Quais pedidos de venda entraram nos últimos 7 dias?
Qual o estoque do produto SKU ABC?
Liste as contas a receber em aberto pra conciliar com o banco
```
