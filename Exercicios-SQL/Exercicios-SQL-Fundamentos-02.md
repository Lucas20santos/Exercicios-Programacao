# Fundamentos de Banco de dados

## Perguntas sobre Bancos de Dados: Relacionais e Não Relacionais

### I. Fundamentos de Banco de Dados (30 Perguntas)

#### Teoria

1. O que é um **Sistema Gerenciador de Banco de Dados (SGBD)**?
1. Qual a principal diferença entre **dados** e **informação**?
1. O que é um **esquema** de banco de dados?
1. Explique o conceito de **modelo de dados**.
1. Qual a importância da **integridade dos dados** em um banco de dados?
1. O que é um **transação** em um contexto de banco de dados?
1. Cite e explique brevemente as propriedades **ACID** das transações.
1. O que é um **índice** e qual sua finalidade?
1. Qual a diferença entre um **índice clusterizado** e um **não clusterizado**?
1. O que é **normalização** em bancos de dados relacionais? Qual seu objetivo principal?
1. Explique o conceito de **desnormalização**. Quando é apropriado usá-la?
1. O que é um **problema de concorrência** (concurrency issue) em bancos de dados?
1. Qual o papel de um **bloqueio (lock)** em um sistema de banco de dados?
1. Diferencie **bloqueio pessimista** de **bloqueio otimista**.
1. O que é um **deadlock** e como SGBDs tentam evitá-lo ou resolvê-lo?
1. Explique o conceito de **backup e recuperação** em bancos de dados.
1. O que é um **log de transações (transaction log)**?
1. Qual a diferença entre **OLTP** (Online Transaction Processing) e **OLAP** (Online Analytical Processing)?
1. O que é um **data warehouse**?
1. Defina **escalabilidade** em bancos de dados.
1. O que é **alta disponibilidade** em um contexto de banco de dados?
1. Explique o termo **durabilidade** em bancos de dados.
1. O que é **consistência** em sistemas de banco de dados distribuídos?
1. Qual a diferença entre **failover** e **fallback**?
1. O que são **metadados** em um banco de dados?
1. Explique o conceito de **visão (view)** em um banco de dados relacional.
1. O que é um **gatilho (trigger)** em banco de dados?
1. Qual a finalidade de uma **stored procedure** (procedimento armazenado)?
1. O que é um **cursor** em SQL?
1. Defina **schemaless** e diga em que tipo de banco de dados é mais comum.

-----

### II. Bancos de Dados Relacionais (SQL) (70 Perguntas)

#### Teoria Parte II

1. Quais os componentes básicos de um **modelo relacional**?
1. O que é uma **tabela (table)**?
1. O que é uma **coluna (column)** e uma **linha (row)**?
1. Defina **chave primária (Primary Key)**. Quais suas características?
1. Defina **chave estrangeira (Foreign Key)**. Qual sua função?
1. Qual a diferença entre **PRIMARY KEY** e **UNIQUE constraint**?
1. Explique a **Primeira Forma Normal (1FN)**.
1. Explique a **Segunda Forma Normal (2FN)**.
1. Explique a **Terceira Forma Normal (3FN)**.
1. O que é **BCNF (Forma Normal de Boyce-Codd)**? Quando é usada?
1. Quais são os tipos de **relacionamento** entre tabelas (1:1, 1:N, N:N)? Dê um exemplo para cada.
1. O que é **SQL** (Structured Query Language)?
1. Diferencie **DDL (Data Definition Language)**, **DML (Data Manipulation Language)**, **DCL (Data Control Language)** e **TCL (Transaction Control Language)**.
1. Qual a diferença entre `DELETE`, `TRUNCATE` e `DROP`?
1. O que é um **JOIN**?
1. Diferencie **INNER JOIN**, **LEFT JOIN**, **RIGHT JOIN** e **FULL JOIN**.
1. O que é um **SELF JOIN**?
1. Explique o conceito de **subquery** (subconsulta).
1. Qual a diferença entre `UNION` e `UNION ALL`?
1. O que são **funções de agregação**? Cite exemplos.
1. Qual a função da cláusula `GROUP BY`?
1. Qual a diferença entre `WHERE` e `HAVING`?
1. O que é um **índice de cobertura (covering index)**?
1. Como a **performance** de uma consulta SQL pode ser otimizada?
1. O que é um **plano de execução de consulta (query execution plan)**?
1. Quais são os principais desafios ao trabalhar com grandes volumes de dados em bancos relacionais?
1. Explique o conceito de **replica (réplica)** em bancos de dados.
1. Qual a diferença entre **replicação síncrona** e **assíncrona**?
1. O que é um **cluster** de banco de dados?
1. Como você lidaria com a evolução do esquema de um banco de dados em produção?

#### Prática (Exemplos em SQL)

Considere as seguintes tabelas para os exercícios práticos:

**`Clientes`**

- `id_cliente` (INT, PRIMARY KEY)
- `nome` (VARCHAR)
- `email` (VARCHAR, UNIQUE)
- `data_registro` (DATE)

**`Pedidos`**

- `id_pedido` (INT, PRIMARY KEY)
- `id_cliente` (INT, FOREIGN KEY REFERENCES Clientes(id\_cliente))
- `data_pedido` (DATE)
- `valor_total` (DECIMAL)

**`Produtos`**

- `id_produto` (INT, PRIMARY KEY)
- `nome_produto` (VARCHAR)
- `preco` (DECIMAL)
- `estoque` (INT)

**`Itens_Pedido`**

- `id_item` (INT, PRIMARY KEY)
- `id_pedido` (INT, FOREIGN KEY REFERENCES Pedidos(id\_pedido))
- `id_produto` (INT, FOREIGN KEY REFERENCES Produtos(id\_produto))
- `quantidade` (INT)
- `preco_unitario_na_compra` (DECIMAL)

<!-- end list -->

1. Escreva um SQL para criar a tabela `Clientes`.
1. Escreva um SQL para inserir dois clientes na tabela `Clientes`.
1. Escreva um SQL para atualizar o email de um cliente.
1. Escreva um SQL para deletar um cliente da tabela `Clientes`.
1. Selecione todos os clientes.
1. Selecione o nome e email de clientes registrados após '2023-01-01'.
1. Conte quantos clientes existem na tabela.
1. Selecione clientes cujo nome começa com 'A'.
1. Encontre o cliente com o ID `5`.
1. Selecione todos os pedidos, ordenados do mais recente para o mais antigo.
1. Calcule o valor total de todos os pedidos.
1. Encontre o pedido com o maior `valor_total`.
1. Selecione o nome do cliente e o `id_pedido` para todos os pedidos.
1. Selecione o nome do cliente e a quantidade de pedidos que cada cliente fez.
1. Liste os clientes que não fizeram nenhum pedido.
1. Encontre todos os produtos com estoque menor que 10.
1. Calcule a média de preço dos produtos.
1. Atualize o estoque de um produto específico.
1. Selecione os produtos que foram pedidos pelo menos uma vez.
1. Liste os nomes dos produtos e a quantidade total vendida de cada um.
1. Encontre os 5 produtos mais vendidos (em termos de quantidade).
1. Selecione os clientes que fizeram pedidos em um determinado mês (ex: Junho).
1. Calcule o valor total de pedidos por cliente.
1. Encontre o cliente que gastou mais em pedidos.
1. Selecione todos os pedidos feitos por clientes com nome 'João'.
1. Crie uma view que mostre o nome do cliente, id do pedido e valor total do pedido.
1. Crie um índice na coluna `data_registro` da tabela `Clientes`.
1. Escreva um SQL que calcule o valor total de vendas para cada produto.
1. Encontre clientes que têm mais de 2 pedidos.
1. Selecione os nomes dos produtos que nunca foram pedidos.
1. Faça um `FULL JOIN` entre `Clientes` e `Pedidos` para ver todos os clientes e todos os pedidos, incluindo aqueles sem correspondência.
1. Use uma subquery para encontrar o nome dos clientes que fizeram um pedido com `valor_total` superior a R$ 500.
1. Calcule a soma total de `quantidade` de `Itens_Pedido` para cada `id_pedido`.
1. Encontre o `id_pedido` que tem a maior quantidade de itens diferentes.
1. Crie uma `stored procedure` que insira um novo cliente.
1. Crie um `trigger` que, ao inserir um novo pedido, diminua o `estoque` dos produtos envolvidos.
1. Escreva um SQL para listar os produtos e o número de pedidos em que cada um aparece, mesmo que não tenha aparecido em nenhum.
1. Selecione o nome do cliente e a data do último pedido que ele fez.
1. Encontre clientes que fizeram pedidos em dias consecutivos.
1. Implemente um `ranking` dos clientes por `valor_total` gasto.

-----

### III. Bancos de Dados Não Relacionais (NoSQL) (70 Perguntas)

#### Teoria Parte 3

1. O que significa **NoSQL**?
1. Quais as principais motivações para usar um banco de dados NoSQL em vez de um relacional?
1. Quais as quatro categorias principais de bancos de dados NoSQL? Dê um exemplo para cada.
1. Explique o conceito de **CAP Theorem**. Quais as três propriedades e o que elas significam?
1. O que é **consistência eventual (eventual consistency)**?
1. Quais os principais casos de uso para bancos de dados **chave-valor**?
1. Descreva o modelo de dados de um banco de dados **colunar (column-family)**.
1. Quais as vantagens e desvantagens de um banco de dados **documento (document-oriented)**?
1. O que é um **documento JSON**?
1. Explique a diferença entre **esquema flexível (schemaless)** e **esquema explícito**.
1. Em que situações bancos de dados de **grafo (graph database)** são mais adequados?
1. O que é uma **aresta (edge)** e um **nó (node)** em um banco de dados de grafo?
1. O que é **sharding** em NoSQL? Qual seu propósito?
1. Qual a diferença entre **sharding** e **replicação**?
1. O que é **vertical scaling** e **horizontal scaling**? Qual o NoSQL favorece?
1. Explique o conceito de **agregação de dados** em NoSQL.
1. O que é **MapReduce** e como ele se relaciona com NoSQL?
1. Quais as desvantagens de usar um banco de dados NoSQL?
1. O que é **TTL (Time To Live)** em NoSQL?
1. Explique o conceito de **particionamento (partitioning)** em NoSQL.
1. Qual a diferença entre **consistência forte** e **consistência eventual**?
1. O que é um **replicaset** em MongoDB?
1. Qual a diferença entre `collection` e `document` em MongoDB?
1. O que é um `primary key` equivalente em um banco de dados de documentos?
1. Como o MongoDB lida com transações ACID (versões mais recentes)?
1. Explique o modelo de dados de Cassandra.
1. O que é um **supercoluna (super column)** em Cassandra?
1. Quais as características de um banco de dados de séries temporais?
1. O que é um **vector database** e para que servem?
1. Como os bancos de dados NoSQL geralmente lidam com a consistência em um ambiente distribuído?

#### Prática (Exemplos em MongoDB - Foco Documento)

Considere a seguinte estrutura de dados para os exercícios práticos:

**`collection: produtos`**

```json
[
  {
    "_id": ObjectId("65328e469e38d7b0f7e4a1b2"),
    "nome": "Smartphone X",
    "descricao": "Celular avançado com câmera de alta resolução.",
    "preco": 1200.00,
    "estoque": 50,
    "categorias": ["eletrônicos", "celulares"],
    "fornecedor": {
      "nome": "TechCorp",
      "contato": "contato@techcorp.com"
    },
    "avaliacoes": [
      { "usuario": "Alice", "nota": 5, "comentario": "Ótimo produto!" },
      { "usuario": "Bob", "nota": 4, "comentario": "Bateria poderia ser melhor." }
    ],
    "data_adicao": ISODate("2024-01-15T10:00:00Z")
  },
  {
    "_id": ObjectId("65328e469e38d7b0f7e4a1b3"),
    "nome": "Laptop Pro",
    "descricao": "Notebook potente para trabalho e jogos.",
    "preco": 2500.00,
    "estoque": 20,
    "categorias": ["eletrônicos", "computadores"],
    "fornecedor": {
      "nome": "GlobalGadgets",
      "contato": "suporte@globalgadgets.net"
    },
    "avaliacoes": [
      { "usuario": "Charlie", "nota": 5, "comentario": "Perfeito para minhas necessidades." }
    ],
    "data_adicao": ISODate("2024-02-01T14:30:00Z")
  },
  {
    "_id": ObjectId("65328e469e38d7b0f7e4a1b4"),
    "nome": "Fone de Ouvido Bluetooth",
    "descricao": "Fone sem fio com cancelamento de ruído.",
    "preco": 150.00,
    "estoque": 100,
    "categorias": ["acessórios", "áudio"],
    "fornecedor": {
      "nome": "AudioSense",
      "contato": "info@audiosense.co"
    },
    "avaliacoes": [],
    "data_adicao": ISODate("2024-03-10T09:15:00Z")
  }
]
```

1. Como você inseriria um novo produto na coleção `produtos`?
1. Selecione todos os produtos.
1. Selecione o produto com o nome "Smartphone X".
1. Selecione produtos com preço menor que 200.
1. Selecione produtos com estoque maior que 30.
1. Selecione produtos que estejam na categoria "eletrônicos".
1. Selecione produtos que estejam nas categorias "eletrônicos" E "celulares".
1. Selecione produtos que tenham pelo menos uma avaliação.
1. Selecione produtos que tenham o fornecedor "TechCorp".
1. Selecione produtos com avaliações onde a nota é 5.
1. Atualize o preço do "Smartphone X" para 1150.00.
1. Adicione a categoria "promoção" ao produto "Laptop Pro".
1. Remova a categoria "acessórios" do "Fone de Ouvido Bluetooth".
1. Adicione uma nova avaliação ao "Smartphone X".
1. Remova todas as avaliações do "Fone de Ouvido Bluetooth".
1. Aumente o estoque do "Smartphone X" em 10 unidades.
1. Exclua o produto "Fone de Ouvido Bluetooth".
1. Conte quantos produtos existem na coleção.
1. Conte quantos produtos têm a categoria "eletrônicos".
1. Selecione os produtos, ordenando pelo preço de forma decrescente.
1. Limite a consulta para retornar apenas 1 produto.
1. Pule o primeiro produto e retorne os próximos 2.
1. Selecione o nome e o preço de todos os produtos.
1. Encontre produtos onde o nome do fornecedor é "TechCorp" e o estoque é maior que 40.
1. Selecione produtos que não tenham nenhuma avaliação.
1. Encontre produtos que foram adicionados após '2024-02-01'.
1. Use `$exists` para encontrar produtos que não têm o campo `descricao`.
1. Use `$size` para encontrar produtos com exatamente 2 categorias.
1. Calcule o preço médio de todos os produtos (Aggregation Pipeline).
1. Encontre a soma total do estoque de todos os produtos (Aggregation Pipeline).
1. Agrupe os produtos por fornecedor e conte quantos produtos cada fornecedor tem.
1. Agrupe os produtos por categoria e calcule o preço médio para cada categoria.
1. Desfaça (unwind) o array de categorias e conte quantos produtos existem por categoria única.
1. Encontre os produtos que têm uma avaliação com nota igual ou superior a 4.
1. Projete (`$project`) apenas o nome do produto e a primeira avaliação (se existir).
1. Adicione um índice para a coluna `nome` na coleção `produtos`.
1. Adicione um índice para a coluna `fornecedor.nome` na coleção `produtos`.
1. Faça um `lookup` (join) com uma coleção `pedidos_cliente` hipotética para listar produtos comprados por um cliente específico (desafio mais avançado).
1. Implemente uma atualização que adicione um campo `ultima_atualizacao` com a data atual a um produto.
1. Como você faria um backup de uma coleção MongoDB?

-----

### IV. Tópicos Avançados e Comparativos (30 Perguntas)

#### Teoria Parte IV

1. Qual a diferença fundamental na forma como **escalabilidade** é abordada em bancos de dados relacionais vs. NoSQL?
1. Quando um modelo de dados **denormalizado** é preferível, e quais os trade-offs?
1. Quais são os desafios de **gerenciamento de esquemas** em bancos de dados NoSQL versus relacionais?
1. O que é um **ORM (Object-Relational Mapping)**? Dê exemplos para linguagens como Python e Java.
1. Quais os benefícios e desvantagens de usar um ORM?
1. Explique o conceito de **polimorfismo de banco de dados (database polymorphism)**.
1. O que é **event sourcing** e como ele se relaciona com bancos de dados?
1. Diferencie **transações distribuídas** em bancos de dados relacionais e em NoSQL.
1. O que é **multi-tenancy** em um contexto de banco de dados?
1. Explique **CDN (Content Delivery Network)** e como ela pode otimizar o acesso a dados.
1. O que é **cache de banco de dados**? Onde e como é usado?
1. Qual a diferença entre **read replica** e **write replica**?
1. O que são **serviços de banco de dados gerenciados (Managed Database Services)**? Cite exemplos.
1. Quais as vantagens de usar um serviço de banco de dados gerenciado?
1. O que é **serverless database**?
1. Explique o conceito de **CQRS (Command Query Responsibility Segregation)**.
1. O que é **federated database**?
1. Como a segurança (autenticação, autorização) é tipicamente gerenciada em bancos de dados?
1. Quais as preocupações de **privacidade de dados** (ex: GDPR, LGPD) em relação a bancos de dados?
1. O que são **testes de carga (load testing)** para bancos de dados?

#### Prática / Cenários

1. Você está construindo uma aplicação de e-commerce. Quando você usaria um banco de dados relacional e quando um NoSQL para diferentes partes do sistema?
1. Para uma aplicação de rede social com muitos relacionamentos entre usuários, qual tipo de banco de dados você consideraria e por quê?
1. Você precisa armazenar dados de sensores de IoT em alta velocidade e volume. Qual tipo de banco de dados é mais adequado?
1. Como você projetaria um sistema para garantir **alta disponibilidade** para um banco de dados relacional crítico?
1. Descreva um cenário onde a **consistência eventual** seria aceitável.
1. Você identificou que uma consulta SQL está muito lenta. Quais seriam seus primeiros passos para otimizá-la?
1. Como você faria a migração de dados de um banco de dados relacional para um NoSQL (documento)? Quais os desafios?
1. Explique como você implementaria um mecanismo de **versionamento de esquema** para um banco de dados relacional em um ambiente de CI/CD.
1. Para um sistema de análise em tempo real (dashboard), qual a melhor abordagem para o armazenamento e consulta de dados?
1. Você está projetando um sistema de recomendações baseado em comportamento do usuário. Como você usaria um banco de dados para armazenar e processar esses dados?
