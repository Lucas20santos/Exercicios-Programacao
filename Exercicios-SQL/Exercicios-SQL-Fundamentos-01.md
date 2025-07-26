# Exercícios de Banco de Dados

## Exercícios de Banco de Dados - Fundamentos e SQL

### I. Fundamentos Essenciais (30 Questões)

#### Teoria - Parte I

1. O que é um banco de dados? Qual o seu propósito principal em uma aplicação?
1. Diferencie **abstração de dados** e **independência de dados**.
1. O que é uma **linguagem de consulta (Query Language)**?
1. Qual a diferença entre um **banco de dados em memória (in-memory)** e um **banco de dados em disco (on-disk)**?
1. Explique o que é **atomicidade** no contexto das propriedades ACID.
1. Explique o que é **consistência** no contexto das propriedades ACID.
1. Explique o que é **isolamento** no contexto das propriedades ACID. Quais os níveis de isolamento mais comuns?
1. Explique o que é **durabilidade** no contexto das propriedades ACID.
1. O que é um **modelo de dados hierárquico**?
1. O que é um **modelo de dados em rede (network model)**?
1. Qual a função de um **Dicionário de Dados**?
1. O que é **granularidade** de dados?
1. Defina **cardinalidade** em um relacionamento de dados.
1. O que é um **hot backup** e um **cold backup**?
1. Qual a diferença entre **disponibilidade (Availability)** e **consistência (Consistency)** no Teorema CAP?
1. Explique o que é **tolerância à partição (Partition Tolerance)** no Teorema CAP.
1. O que é o princípio **BASE (Basically Available, Soft state, Eventual consistency)**?
1. Qual a diferença entre **replicação master-slave** e **master-master**?
1. O que significa dizer que um banco de dados é "tipado"?
1. Qual o papel do **otimizador de consulta (query optimizer)** em um SGBD?
1. O que é um **lock de leitura (shared lock)** e um **lock de escrita (exclusive lock)**?
1. Defina **visão materializada (materialized view)**. Qual a sua vantagem sobre uma view normal?
1. O que é um **Data Lake**? Qual a sua diferença para um Data Warehouse?
1. Explique o que é **ETL (Extract, Transform, Load)**.
1. O que são **constraints (restrições)** em um banco de dados? Dê exemplos.
1. Qual a diferença entre **autenticação** e **autorização** em um SGBD?
1. O que é um **pool de conexões** e por que é importante para a performance de uma aplicação?
1. Qual a finalidade de um **heartbeat** em um cluster de banco de dados?
1. Defina **throughput** em um contexto de banco de dados.
1. O que é **latência** de consulta?

-----

### II. Bancos de Dados Relacionais (SQL) - Aprofundado (70 Questões)

#### Teoria - Parte II

1. O que é uma **relação** no modelo relacional?
1. Qual a importância de se ter um **tipo de dado** bem definido para cada coluna?
1. O que é uma **chave candidata**?
1. Explique o conceito de **dependência funcional**.
1. Qual a finalidade da **Quarta Forma Normal (4FN)**?
1. O que é uma **anomalia de inserção**? Dê um exemplo.
1. O que é uma **anomalia de exclusão**? Dê um exemplo.
1. O que é uma **anomalia de atualização**? Dê um exemplo.
1. O que é uma **chave composta (composite key)**?
1. Diferencie `LEFT JOIN` de `LEFT OUTER JOIN`.
1. Para que serve a cláusula `CASE` em SQL?
1. O que são **funções de janela (window functions)**? Dê um exemplo de uso.
1. Qual a diferença entre as funções `RANK()`, `DENSE_RANK()` e `ROW_NUMBER()`?
1. O que é uma **Common Table Expression (CTE)**? Qual a sua vantagem sobre uma subquery?
1. O que é um **índice B-Tree**? Como ele funciona?
1. O que é um **índice hash**? Quando ele é mais vantajoso que um B-Tree?
1. O que é **seletividade** de um índice? Por que ela é importante?
1. O que é **fragmentação de índice**? Como isso pode ser resolvido?
1. Qual o impacto de um `INSERT` ou `UPDATE` em uma tabela com muitos índices?
1. Explique o que é **sharding** em um banco de dados relacional.
1. Diferencie **sharding vertical** de **sharding horizontal**.
1. O que é uma **tabela particionada**?
1. Para que serve a cláusula `EXPLAIN` (ou `EXPLAIN PLAN`)?
1. O que é um **full table scan** e por que geralmente deve ser evitado?
1. Como o uso de `OR` em uma cláusula `WHERE` pode afetar o uso de índices?
1. O que é uma **transação aninhada (nested transaction)**?
1. O que é um **savepoint** em uma transação?
1. O que é **SQL Injection**? Como pode ser prevenido?
1. Qual a diferença entre `VARCHAR` e `CHAR`?
1. Para que servem os tipos de dados `BLOB` e `CLOB`?

#### **Prática (Exemplos em SQL)**

Considere o seguinte esquema para uma plataforma de blog:

* **`Autores`**: `id_autor` (PK), `nome`, `email` (UNIQUE), `data_cadastro`
* **`Posts`**: `id_post` (PK), `id_autor` (FK), `titulo`, `conteudo`, `data_publicacao`, `status` ('publicado', 'rascunho')
* **`Comentarios`**: `id_comentario` (PK), `id_post` (FK), `nome_usuario`, `texto_comentario`, `data_comentario`
* **`Tags`**: `id_tag` (PK), `nome_tag` (UNIQUE)
* **`Posts_Tags`**: `id_post` (FK), `id_tag` (FK)

<!-- end list -->

1. Escreva uma query para criar a tabela `Posts`, incluindo as chaves primária e estrangeira
1. Escreva uma query para encontrar todos os posts do autor com `id_autor = 10`.
1. Liste o `titulo` dos posts e o `nome` de seus autores.
1. Conte quantos posts cada autor publicou. Exiba o nome do autor e a contagem.
1. Encontre todos os posts publicados no mês de julho de 2025.
1. Liste os autores que ainda não publicaram nenhum post.
1. Encontre o post mais recente (com a maior `data_publicacao`).
1. Liste todos os comentários do post com `titulo` "Introdução ao SQL".
1. Conte quantos comentários cada post possui. Exiba o `titulo` do post e a contagem.
1. Encontre os posts que não possuem nenhum comentário.
1. Liste todos os posts que possuem a tag "Tecnologia".
1. Conte quantas tags cada post possui.
1. Encontre as tags que não estão associadas a nenhum post.
1. Encontre os autores que escreveram posts com a tag "Python".
1. Liste os 5 autores com mais posts publicados.
1. Selecione o título de todos os posts e o texto do comentário mais recente de cada um.
1. Atualize o `status` de todos os posts do autor 'João Silva' para 'rascunho'.
1. Delete todos os comentários feitos antes de '2024-01-01'.
1. Usando uma CTE, encontre os posts que têm mais de 10 comentários.
1. Liste o nome de cada autor e a data de seu primeiro post.
1. Encontre posts cujo `conteudo` contenha a palavra "performance".
1. Para cada autor, mostre o número total de comentários recebidos em todos os seus posts.
1. Liste as tags mais populares (as que aparecem em mais posts).
1. Encontre autores que publicaram posts em mais de 3 tags diferentes.

1. Crie uma `view` que mostre o título do post, nome do autor e a quantidade de comentários.
1. Adicione uma `constraint` `CHECK` na tabela `Posts` para que o `status` só possa ser 'publicado' ou 'rascunho'.
1. Escreva uma `stored procedure` que aceite um `id_autor` e retorne o número de posts dele.
1. Crie um `trigger` que, ao deletar um `Post`, delete todos os `Comentarios` associados a ele.
1. Usando uma `window function`, calcule a média móvel de comentários por dia.
1. Encontre o "par" de tags que mais aparece junto nos mesmos posts.

-----

### III. Bancos de Dados Não Relacionais (NoSQL) - Aprofundado (70 Questões)

#### Teoria Parte III

1. Qual é a principal diferença na modelagem de dados para um banco relacional versus um de documentos?
1. O que significa "agregar" ou "embutir" (embed) dados em um documento NoSQL? Quais as vantagens?
1. O que significa "referenciar" (linking) dados em NoSQL? Quando essa abordagem é melhor?
1. Explique o modelo de dados de um banco de dados **chave-valor**. Cite um caso de uso.
1. Qual a diferença entre Redis e Memcached?
1. Explique o modelo de dados de um banco de dados **colunar**. Qual a vantagem para queries analíticas?
1. O que é uma **"wide column store"**?
1. Em bancos de grafos, qual a diferença entre um grafo de propriedades e um grafo RDF?
1. O que é a linguagem de consulta **Cypher**, usada pelo Neo4j?
1. Explique o que é um **índice invertido (inverted index)** e sua importância em bancos de dados de busca como o Elasticsearch.
1. O que é **consistência tunável (tunable consistency)**, como vista em Cassandra?
1. Explique o que é **read repair** e **hinted handoff** em sistemas distribuídos.
1. O que é um **bloom filter** e como pode ser usado para otimizar consultas?
1. Como o sharding é gerenciado em MongoDB?
1. Qual o papel do `_id` em um documento MongoDB?
1. O que é a **Aggregation Pipeline** do MongoDB?
1. Qual a diferença entre um **índice composto** e **múltiplos índices de campo único** em NoSQL?
1. O que é um **índice geoespacial**?
1. O que é um **índice TTL (Time-to-Live)**?
1. Como bancos NoSQL lidam com "JOINs"?
1. O que são **operações atômicas em nível de documento**?
1. O que é um **padrão de projeto "schema versioning"** em bancos de documentos?
1. Explique o **"subset pattern"** para otimizar documentos grandes.
1. O que é o **"bucket pattern"**, comumente usado em bancos de séries temporais?
1. Como você lidaria com a falta de transações multi-documento em versões mais antigas do MongoDB?
1. Qual a diferença entre DynamoDB (AWS) e MongoDB?
1. O que é um **"conflict-free replicated data type" (CRDT)**?
1. O que é **quorum** em um cluster NoSQL?
1. Como o Zookeeper é frequentemente utilizado em conjunto com sistemas NoSQL (como HBase, Solr)?
1. Quais são os desafios de fazer backup e restauração em um banco de dados NoSQL massivamente distribuído?

### Prática (Exemplos em MongoDB)

Considere a seguinte coleção `inventario` para uma loja:

```json
{
  "_id": ObjectId("..."),
  "sku": "LAP-MAC-M2-SLV",
  "nome_produto": "Laptop Pro M2",
  "departamento": "Eletrônicos",
  "quantidade": 15,
  "detalhes": {
    "marca": "Apple",
    "modelo": "MacBook Pro 14"
  },
  "localizacao": {
    "armazem": "A1",
    "corredor": "C4",
    "prateleira": 2
  },
  "historico_precos": [
    { "preco": 12000.00, "data_inicio": ISODate("2024-01-01T..."), "data_fim": ISODate("2024-06-30T...") },
    { "preco": 11500.00, "data_inicio": ISODate("2024-07-01T..."), "data_fim": null }
  ],
  "ultima_atualizacao": ISODate("2025-07-17T...")
}
```

1. Escreva um comando para inserir um novo item no inventário.
1. Encontre todos os produtos do departamento "Eletrônicos".
1. Encontre produtos com `quantidade` menor que 10.
1. Selecione os produtos da marca "Apple" usando a notação de ponto (`.`) para acessar o campo aninhado.
1. Encontre todos os produtos localizados no armazém "A1".
1. Selecione produtos cujo preço atual (o último do histórico) seja maior que 1000.
1. Atualize a `quantidade` do produto com `sku` "LAP-MAC-M2-SLV" para `12`.
1. Adicione um novo registro de preço ao `historico_precos` de um produto.
1. Remova um produto do inventário pelo seu `_id`.
1. Use `$inc` para decrementar a `quantidade` de um produto em 1.
1. Encontre todos os produtos que foram atualizados hoje.
1. Liste apenas o `nome_produto` e a `quantidade` de todos os itens.
1. Crie um índice de texto no campo `nome_produto`.
1. Use a Aggregation Pipeline para contar quantos produtos existem em cada `departamento`.
1. Calcule a `quantidade` total de itens em todo o inventário.
1. Encontre o preço médio atual de todos os produtos do departamento "Eletrônicos".
1. Usando a Aggregation Pipeline, liste os 5 produtos com maior `quantidade` em estoque.
1. Desconstrua (`$unwind`) o array `historico_precos` e encontre o preço mais alto já registrado para qualquer produto.
1. Projete (`$project`) a saída para mostrar o `nome_produto` e o `preco` atual.
1. Como você garantiria que o campo `sku` seja sempre único?

-----

### IV. Tópicos Avançados, Arquitetura e Cenários (60 Questões)

1. Descreva a arquitetura Lambda. Como ela utiliza diferentes sistemas de dados?
1. Descreva a arquitetura Kappa. Qual sua principal vantagem sobre a Lambda?
1. Em um sistema de microserviços, qual é a abordagem recomendada para bancos de dados: um banco compartilhado ou um banco por serviço? Quais os prós e contras?
1. O que é o padrão de projeto **Saga** para gerenciar transações distribuídas em microserviços?
1. O que é **Change Data Capture (CDC)**? Como ferramentas como o Debezium funcionam?
1. Quando você escolheria o Amazon Aurora em vez de um MySQL/PostgreSQL padrão na AWS?
1. O que é o Amazon DynamoDB? Quais são seus principais casos de uso e limitações?
1. O que é o Google Cloud Spanner e o que o torna único em termos de consistência global?
1. Explique o conceito de **NewSQL**.
1. Como você projetaria um sistema de cache (usando Redis, por exemplo) para aliviar a carga de um banco de dados relacional? Quais estratégias de cache (ex: cache-aside, read-through) você usaria?
1. O que é um **índice geo-hash** e como funciona?
1. Quais são os desafios de segurança específicos para bancos de dados NoSQL?
1. O que é **criptografia em repouso (at rest)** e **em trânsito (in transit)**?
1. Como você implementaria um sistema de **auditoria** em um banco de dados?
1. Qual a diferença entre um **Data Scientist**, um **Data Analyst** e um **Data Engineer** no que tange ao uso de bancos de dados?
1. O que é um **Object-Database Mapper (ODM)**, como o Mongoose para MongoDB?
1. Você precisa armazenar sessões de usuário para um site de alto tráfego. Qual tipo de banco de dados você escolheria e por quê?
1. Para um catálogo de produtos de um e-commerce com muitos atributos e filtros, qual banco de dados seria mais adequado? (Ex: SQL, MongoDB, Elasticsearch). Justifique.
1. Como você migraria, com o mínimo de downtime, um banco de dados de um datacenter on-premise para a nuvem?
1. Descreva um cenário onde você precisaria usar múltiplos tipos de bancos de dados (poliglota de persistência) em uma única aplicação.

**[Continuando a lista para 200]**

1. Qual o papel da compactação de dados em bancos de dados colunares?
1. Explique o que é "impedance mismatch" no contexto de ORMs.
1. Como funciona o "MVCC" (Multiversion Concurrency Control)?
1. O que é o "two-phase commit" (2PC) e por que ele é problemático em sistemas web distribuídos?
1. Qual a diferença entre uma "query ad-hoc" e uma "query parametrizada"?
1. Explique o conceito de "ACID 2.0" ou transações em larga escala.
1. O que é um "vector database" e por que ele é importante para aplicações de IA/ML?
1. Como a virtualização e os contêineres (Docker) mudaram a forma como gerenciamos bancos de dados?
1. O que é "Infrastructure as Code" (IaC) para bancos de dados?
1. Qual a função de uma ferramenta de migração de esquema como Flyway ou Liquibase?
1. Para um placar de líderes (leaderboard) de um jogo online, qual banco de dados você usaria (ex: Redis com Sorted Sets)? Por quê?
1. O que é "time-series data"? Cite exemplos de bancos de dados otimizados para isso.
1. Quais são os desafios em manter a consistência de caches?
1. O que é o "Thundering Herd Problem" e como ele pode afetar um banco de dados?
1. Como você monitoraria a saúde e a performance de um banco de dados em produção? Quais métricas são cruciais?
1. Explique o que é uma "query idempotente".
1. Como você lidaria com a evolução do esquema de um banco de dados de grafos?
1. Qual a diferença entre "fail-stop" e "Byzantine fault"?
1. Como a Lei de Amdahl se aplica à otimização de performance em bancos de dados?
1. O que é "Database as a Service" (DBaaS)?
1. Discuta os trade-offs entre normalização e performance.
1. Como você projetaria um sistema de "feed de notícias" similar ao do Facebook ou Twitter?
1. O que são os "GSI" (Global Secondary Indexes) e "LSI" (Local Secondary Indexes) no DynamoDB?
1. Descreva uma situação onde a desnormalização seria uma má ideia.
1. O que é "ACID" vs "BASE" em termos práticos para um desenvolvedor?
1. Qual o impacto da latência da rede na performance de um banco de dados distribuído?
1. Como você garante a qualidade dos dados (Data Quality) que entram no banco?
1. O que é "Data Governance"?
1. Como você faria um teste A/B em uma funcionalidade que depende fortemente de uma estrutura de banco de dados?
1. O que é um "anti-pattern" comum na modelagem de dados SQL? Dê um exemplo.
1. E um "anti-pattern" comum na modelagem de documentos NoSQL?
1. Como você lidaria com dados sensíveis (como CPFs ou dados de cartão de crédito) no banco de dados?
1. O que é "tokenização" de dados?
1. Explique o conceito de "Data Mesh".
1. Cenário: Uma query `DELETE` está demorando muito em uma tabela grande. Quais podem ser as causas e como você investigaria?
1. Cenário: A aplicação está lenta e o uso de CPU do banco de dados está em 100%. Qual seu plano de ação?
1. Cenário: Você precisa armazenar o histórico completo de todas as alterações em um registro de cliente. Como você modelaria isso em SQL? E em NoSQL?
1. Cenário: Sua empresa decide que precisa de análises mais rápidas. Você propõe um Data Warehouse. Como você o alimentaria a partir do banco de dados de produção?
1. Cenário: Um colega sugere usar GUIDs/UUIDs como chaves primárias em uma tabela relacional. Quais os prós e contras dessa abordagem em comparação com inteiros sequenciais?
1. Pergunta final: Qual foi o problema mais desafiador relacionado a banco de dados que você já resolveu e como você o abordou?
