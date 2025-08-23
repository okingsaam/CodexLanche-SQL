# CodexLanche 🍔

Sistema de gerenciamento de pedidos para uma lanchonete. Este projeto contém a modelagem do banco de dados relacional em MySQL, com estrutura modular e dados de exemplo para facilitar testes e integração com o backend e frontend.

---

## 📦 Estrutura do Banco de Dados

### 1. clientes
Armazena os dados dos clientes.

| Campo       | Tipo           | Descrição                      |
|-------------|----------------|--------------------------------|
| id          | INT (PK)       | Identificador único            |
| nome        | VARCHAR(100)   | Nome do cliente                |
| telefone    | VARCHAR(20)    | Telefone de contato            |
| email       | VARCHAR(100)   | Email do cliente               |
| criado_em   | TIMESTAMP      | Data de criação do cadastro    |

---

### 2. produtos
Lista os produtos disponíveis para venda.

| Campo        | Tipo           | Descrição                          |
|--------------|----------------|------------------------------------|
| id           | INT (PK)       | Identificador único                |
| nome         | VARCHAR(100)   | Nome do produto                    |
| descricao    | TEXT           | Descrição detalhada                |
| preco        | DECIMAL(10,2)  | Preço unitário                     |
| categoria    | VARCHAR(50)    | Categoria (ex: lanche, bebida)     |
| estoque      | INT            | Quantidade disponível              |
| criado_em    | TIMESTAMP      | Data de cadastro                   |

---

### 3. pedidos
Registra os pedidos feitos pelos clientes.

| Campo       | Tipo           | Descrição                                  |
|-------------|----------------|--------------------------------------------|
| id          | INT (PK)       | Identificador do pedido                    |
| cliente_id  | INT (FK)       | Referência ao cliente                      |
| status      | ENUM           | Estado do pedido: 'pendente', 'em preparo', 'entregue', 'cancelado' |
| criado_em   | TIMESTAMP      | Data do pedido                             |

---

### 4. itens_pedido
Itens que compõem cada pedido.

| Campo           | Tipo           | Descrição                              |
|-----------------|----------------|----------------------------------------|
| id              | INT (PK)       | Identificador do item                  |
| pedido_id       | INT (FK)       | Referência ao pedido                   |
| produto_id      | INT (FK)       | Referência ao produto                  |
| quantidade      | INT            | Quantidade solicitada                  |
| preco_unitario  | DECIMAL(10,2)  | Preço do produto no momento do pedido |

---

## 🔗 Relacionamentos

- `pedidos.cliente_id` → `clientes.id`
- `itens_pedido.pedido_id` → `pedidos.id`
- `itens_pedido.produto_id` → `produtos.id`

---

## 📊 Consultas Úteis

### Total de um pedido:
```sql
SELECT 
    p.id AS pedido_id,
    c.nome AS cliente,
    SUM(ip.quantidade * ip.preco_unitario) AS total
FROM pedidos p
JOIN clientes c ON p.cliente_id = c.id
JOIN itens_pedido ip ON p.id = ip.pedido_id
WHERE p.id = 1
GROUP BY p.id, c.nome;
