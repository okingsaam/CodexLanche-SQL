# 🍔 CodexLanche-SQL

Sistema de gerenciamento de pedidos para uma lanchonete fictícia, desenvolvido com foco em modelagem e manipulação de banco de dados SQL.

---

## 📦 Estrutura do Projeto

Este repositório contém os scripts SQL para criação e manipulação das seguintes tabelas e funcionalidades:

- **`clientes`**: Armazena informações dos clientes.
- **`produtos`**: Armazena informações sobre os produtos disponíveis no cardápio.
- **`pedidos`**: Registra os pedidos feitos pelos clientes.
- **`itens_pedido`**: Relaciona os produtos aos pedidos.

Além disso, também inclui exemplos de consultas SQL para interação com as tabelas criadas.

---

## 🛠️ Tecnologias Utilizadas

- **SQL** (MySQL ou PostgreSQL)
- **Git & GitHub** para versionamento
- **Cmder / Terminal** para execução dos scripts
- **MySQL Workbench** ou **pgAdmin** para gerenciamento de banco de dados (opcional)

---

## 🚀 Como Usar

1. **Clone o repositório:**

   ```bash
   git clone https://github.com/okingsaam/CodexLanche-SQL.git
Importe os arquivos .sql no seu gerenciador de banco de dados.
Você pode fazer isso pelo MySQL Workbench, pgAdmin, ou diretamente pelo terminal, dependendo do seu SGBD preferido.

Execute os scripts na ordem abaixo para garantir que as dependências entre as tabelas sejam criadas corretamente:

db_codexlanche_clientes.sql

db_codexlanche_produtos.sql

db_codexlanche_pedidos.sql

db_codexlanche_itens_pedido.sql

Esses scripts irão criar as tabelas no banco de dados e garantir que os relacionamentos e dependências sejam configurados corretamente.

📊 Exemplo de Consulta
Após a execução dos scripts, você pode utilizar a seguinte consulta SQL para obter detalhes de um pedido, incluindo informações sobre o cliente e os produtos pedidos:

sql
Copiar código
SELECT 
    p.id AS id_pedido, 
    c.nome AS nome_cliente, 
    pr.nome AS nome_produto, 
    ip.quantidade
FROM 
    pedidos p
JOIN 
    clientes c ON p.id_cliente = c.id
JOIN 
    itens_pedido ip ON p.id = ip.id_pedido
JOIN 
    produtos pr ON ip.id_produto = pr.id;
Esse SELECT retorna o id do pedido, o nome do cliente, o nome do produto e a quantidade de cada item no pedido.
É útil para verificar todos os produtos de um pedido específico, juntamente com o cliente que fez a compra.

🧩 Relacionamento entre as Tabelas
As tabelas no banco de dados estão organizadas da seguinte maneira:

clientes: Contém informações sobre os clientes da lanchonete.

Chave primária: id

produtos: Contém informações sobre os produtos disponíveis no cardápio.

Chave primária: id

pedidos: Armazena os pedidos feitos pelos clientes.

Chave primária: id

Chaves estrangeiras: id_cliente (relaciona-se com a tabela clientes) e id_lojista (relaciona-se com a tabela lojistas)

itens_pedido: Relaciona os produtos aos pedidos.

Chave primária: id

Chaves estrangeiras: id_pedido (relaciona-se com a tabela pedidos) e id_produto (relaciona-se com a tabela produtos)

Essas tabelas são projetadas para manter o banco de dados normalizado e evitar duplicação de dados.

💡 Contribuindo
Sinta-se à vontade para contribuir com melhorias, sugestões ou correções. Para isso, basta seguir os seguintes passos:

Fork este repositório

Crie uma branch para sua nova feature (git checkout -b feature/nova-feature)

Commit suas alterações (git commit -m 'Adiciona nova feature')

Push para a branch (git push origin feature/nova-feature)

Abra um Pull Request

⚠️ Licença
Este projeto está licenciado sob a Licença MIT - consulte o arquivo LICENSE para mais detalhes.

📝 Notas Finais
Este repositório tem como objetivo mostrar um exemplo de modelagem de banco de dados relacional para um sistema simples de gerenciamento de pedidos. Ele pode ser estendido para sistemas mais complexos, com integração de outras funcionalidades e até mesmo diferentes tipos de clientes (ex: administradores, atendentes, etc.).

Esse modelo já está bem completo e contém todas as informações de configuração e uso, bem como exemplos prontos para facilitar a interação com o banco.
Basta copiar e colar no seu README.md e está pronto para ser compartilhado! 😊

Se precisar de mais algum ajuste ou adicionar algo, é só avisar!


Você disse:
como nota final coloque que esse projeto é um projeto de estudo do qual estou apenas testando meus conhecimentos e buscando melhorar 

O ChatGPT disse:
Claro! Aqui está o README atualizado com a sua nota final:

markdown
Copiar código
# 🍔 CodexLanche-SQL

Sistema de gerenciamento de pedidos para uma lanchonete fictícia, desenvolvido com foco em modelagem e manipulação de banco de dados SQL.

---

## 📦 Estrutura do Projeto

Este repositório contém os scripts SQL para criação e manipulação das seguintes tabelas e funcionalidades:

- **`clientes`**: Armazena informações dos clientes.
- **`produtos`**: Armazena informações sobre os produtos disponíveis no cardápio.
- **`pedidos`**: Registra os pedidos feitos pelos clientes.
- **`itens_pedido`**: Relaciona os produtos aos pedidos.

Além disso, também inclui exemplos de consultas SQL para interação com as tabelas criadas.

---

## 🛠️ Tecnologias Utilizadas

- **SQL** (MySQL ou PostgreSQL)
- **Git & GitHub** para versionamento
- **Cmder / Terminal** para execução dos scripts
- **MySQL Workbench** ou **pgAdmin** para gerenciamento de banco de dados (opcional)

---

## 🚀 Como Usar

1. **Clone o repositório:**

   ```bash
   git clone https://github.com/okingsaam/CodexLanche-SQL.git
Importe os arquivos .sql no seu gerenciador de banco de dados.
Você pode fazer isso pelo MySQL Workbench, pgAdmin, ou diretamente pelo terminal, dependendo do seu SGBD preferido.

Execute os scripts na ordem abaixo para garantir que as dependências entre as tabelas sejam criadas corretamente:

db_codexlanche_clientes.sql

db_codexlanche_produtos.sql

db_codexlanche_pedidos.sql

db_codexlanche_itens_pedido.sql

Esses scripts irão criar as tabelas no banco de dados e garantir que os relacionamentos e dependências sejam configurados corretamente.

📊 Exemplo de Consulta
Após a execução dos scripts, você pode utilizar a seguinte consulta SQL para obter detalhes de um pedido, incluindo informações sobre o cliente e os produtos pedidos:

sql
Copiar código
SELECT 
    p.id AS id_pedido, 
    c.nome AS nome_cliente, 
    pr.nome AS nome_produto, 
    ip.quantidade
FROM 
    pedidos p
JOIN 
    clientes c ON p.id_cliente = c.id
JOIN 
    itens_pedido ip ON p.id = ip.id_pedido
JOIN 
    produtos pr ON ip.id_produto = pr.id;
Esse SELECT retorna o id do pedido, o nome do cliente, o nome do produto e a quantidade de cada item no pedido.
É útil para verificar todos os produtos de um pedido específico, juntamente com o cliente que fez a compra.

🧩 Relacionamento entre as Tabelas
As tabelas no banco de dados estão organizadas da seguinte maneira:

clientes: Contém informações sobre os clientes da lanchonete.

Chave primária: id

produtos: Contém informações sobre os produtos disponíveis no cardápio.

Chave primária: id

pedidos: Armazena os pedidos feitos pelos clientes.

Chave primária: id

Chaves estrangeiras: id_cliente (relaciona-se com a tabela clientes) e id_lojista (relaciona-se com a tabela lojistas)

itens_pedido: Relaciona os produtos aos pedidos.

Chave primária: id

Chaves estrangeiras: id_pedido (relaciona-se com a tabela pedidos) e id_produto (relaciona-se com a tabela produtos)

Essas tabelas são projetadas para manter o banco de dados normalizado e evitar duplicação de dados.

💡 Contribuindo
Sinta-se à vontade para contribuir com melhorias, sugestões ou correções. Para isso, basta seguir os seguintes passos:

Fork este repositório

Crie uma branch para sua nova feature (git checkout -b feature/nova-feature)

Commit suas alterações (git commit -m 'Adiciona nova feature')

Push para a branch (git push origin feature/nova-feature)

Abra um Pull Request

⚠️ Licença
Este projeto está licenciado sob a Licença MIT - consulte o arquivo LICENSE para mais detalhes.

📝 Notas Finais
Este projeto é um projeto de estudo no qual estou apenas testando meus conhecimentos e buscando melhorar. O foco é entender e aplicar boas práticas de modelagem e manipulação de banco de dados. Não é um projeto em produção e ainda está em fase de aprendizado e testes.
