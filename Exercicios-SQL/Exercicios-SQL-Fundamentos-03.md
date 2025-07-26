# Fundamentos de banco de dados e modelagem de dados

---

## Fundamentos e 1ª Forma Normal (1FN)

### Exercícios de Identificação de Repetições e Atributos Multivalorados (20 Exercícios)

1.  **Vendas Online:** Você está modelando um sistema de vendas online. Um pedido pode conter vários itens, e cada item tem um nome, quantidade e preço. O que precisa ser desmembrado para atingir a 1FN?
2.  **Biblioteca:** Uma tabela de livros contém o título, autor(es) e editora. Alguns livros têm múltiplos autores. Como você reestruturaria isso para a 1FN?
3.  **Currículo:** Um currículo lista o nome da pessoa, habilidades (e.g., Python, SQL, Java) e anos de experiência em cada habilidade. Como garantir a 1FN?
4.  **Projeto de Software:** Uma equipe de projeto tem uma lista de membros, e cada membro pode ter vários números de telefone. Como você normalizaria isso para a 1FN?
5.  **Agenda de Contatos:** Uma agenda armazena nomes, endereços e vários endereços de e-mail para cada contato. Aplique a 1FN.
6.  **Cursos Universitários:** Uma tabela de cursos inclui o nome do curso, o professor e uma lista de alunos matriculados. O que precisa ser feito para a 1FN?
7.  **Empresa de Consultoria:** Uma tabela registra clientes, e cada cliente pode ter vários projetos em andamento. Como você a adequaria à 1FN?
8.  **Inventário de Produtos:** Uma loja registra seus produtos. Cada produto pode ter várias cores e tamanhos disponíveis. O que você faria para a 1FN?
9.  **Filmes:** Uma tabela de filmes lista o título, diretor e uma lista de atores principais. Como você normalizaria isso para a 1FN?
10. **Restaurante:** Um restaurante tem um menu com pratos. Cada prato pode ter vários ingredientes. Aplique a 1FN.
11. **Blog:** Um post de blog tem um título, conteúdo e várias tags associadas. Como você garantiria a 1FN?
12. **Música:** Uma música tem um título, artista e uma lista de gêneros. O que precisa ser feito para a 1FN?
13. **Relatório de Erros:** Um sistema de rastreamento de erros registra o ID do erro, descrição e uma lista de passos para reproduzi-lo. Como normalizar para 1FN?
14. **Veículos:** Um carro tem um modelo, ano e uma lista de recursos opcionais. Aplique a 1FN.
15. **Eventos:** Uma tabela de eventos inclui o nome do evento, data e uma lista de palestrantes. Como garantir a 1FN?
16. **Laboratório:** Uma amostra de laboratório pode ter vários resultados de testes associados. O que você faria para a 1FN?
17. **Software de Edição:** Um projeto em software de edição pode ter vários arquivos de mídia (imagens, vídeos, áudios). Como normalizar para 1FN?
18. **Escola de Idiomas:** Um aluno pode estar matriculado em vários cursos de idiomas. Como representar isso em 1FN?
19. **Equipamento Esportivo:** Uma bicicleta pode ter vários componentes (quadro, rodas, marchas). Como garantir a 1FN?
20. **Campanha de Marketing:** Uma campanha pode ter vários canais de distribuição (e.g., e-mail, redes sociais, TV). Como normalizar para 1FN?

---

## 2ª Forma Normal (2FN)

### Exercícios de Dependências Parciais (30 Exercícios)

1.  **Pedidos e Produtos:** Uma tabela de `Itens_Pedido` tem `(ID_Pedido, ID_Produto)` como chave primária composta. Os atributos `Nome_Produto` e `Preco_Unitario` dependem apenas de `ID_Produto`. Como você normalizaria para 2FN?
2.  **Alunos e Cursos:** Uma tabela de `Matriculas` tem `(ID_Aluno, ID_Curso)` como chave primária. `Nome_Aluno` depende apenas de `ID_Aluno`, e `Nome_Curso` e `Carga_Horaria` dependem apenas de `ID_Curso`. Aplique a 2FN.
3.  **Voo e Assentos:** Uma tabela `Reservas_Assento` tem `(ID_Voo, Numero_Assento)` como chave primária. `Origem_Voo`, `Destino_Voo` e `Hora_Voo` dependem apenas de `ID_Voo`. Como normalizar para 2FN?
4.  **Funcionários e Departamentos:** Uma tabela `Alocacao_Funcionarios` tem `(ID_Funcionario, ID_Projeto)` como chave primária. `Nome_Funcionario` e `Salario` dependem de `ID_Funcionario`. `Nome_Projeto` e `Prazo_Projeto` dependem de `ID_Projeto`. Aplique a 2FN.
5.  **Compras e Fornecedores:** Uma tabela `Itens_Compra` tem `(ID_Compra, ID_Item)` como chave primária. `Nome_Fornecedor` e `Endereco_Fornecedor` dependem de `ID_Compra`. Como normalizar para 2FN?
6.  **Livros e Cópias:** Uma tabela `Copias_Livro` tem `(ISBN, Numero_Copia)` como chave primária. `Titulo_Livro`, `Autor_Livro` e `Editora_Livro` dependem de `ISBN`. Como você normalizaria para 2FN?
7.  **Pacientes e Consultas:** Uma tabela `Historico_Consultas` tem `(ID_Paciente, Data_Consulta)` como chave primária. `Nome_Paciente` e `Data_Nascimento_Paciente` dependem de `ID_Paciente`. Como normalizar para 2FN?
8.  **Eventos e Participantes:** Uma tabela `Inscricoes_Evento` tem `(ID_Evento, ID_Participante)` como chave primária. `Nome_Evento` e `Local_Evento` dependem de `ID_Evento`. `Nome_Participante` e `Email_Participante` dependem de `ID_Participante`. Aplique a 2FN.
9.  **Carros e Peças:** Uma tabela `Instalacao_Pecas` tem `(ID_Carro, ID_Peca)` como chave primária. `Modelo_Carro` e `Ano_Carro` dependem de `ID_Carro`. `Nome_Peca` e `Preco_Peca` dependem de `ID_Peca`. Como normalizar para 2FN?
10. **Filmes e Gêneros:** Uma tabela `Filmes_Generos` tem `(ID_Filme, ID_Genero)` como chave primária. `Titulo_Filme` e `Ano_Lancamento` dependem de `ID_Filme`. `Nome_Genero` depende de `ID_Genero`. Aplique a 2FN.
11. **Músicas e Artistas:** Uma tabela `Musicas_Artista` tem `(ID_Musica, ID_Artista)` como chave primária. `Titulo_Musica` e `Duracao_Musica` dependem de `ID_Musica`. `Nome_Artista` e `Pais_Artista` dependem de `ID_Artista`. Como normalizar para 2FN?
12. **Produtos e Categorias:** Uma tabela `Produtos_Categoria` tem `(ID_Produto, ID_Categoria)` como chave primária. `Nome_Produto` e `Descricao_Produto` dependem de `ID_Produto`. `Nome_Categoria` depende de `ID_Categoria`. Aplique a 2FN.
13. **Hóspedes e Quartos:** Uma tabela `Ocupacao_Quartos` tem `(ID_Hospede, Numero_Quarto)` como chave primária. `Nome_Hospede` e `Telefone_Hospede` dependem de `ID_Hospede`. `Tipo_Quarto` e `Preco_Diaria` dependem de `Numero_Quarto`. Como normalizar para 2FN?
14. **Receitas e Ingredientes:** Uma tabela `Receitas_Ingredientes` tem `(ID_Receita, ID_Ingrediente)` como chave primária. `Nome_Receita` e `Tempo_Preparo` dependem de `ID_Receita`. `Nome_Ingrediente` e `Unidade_Medida` dependem de `ID_Ingrediente`. Aplique a 2FN.
15. **Atletas e Competições:** Uma tabela `Resultados_Competicao` tem `(ID_Atleta, ID_Competicao)` como chave primária. `Nome_Atleta` e `Nacionalidade_Atleta` dependem de `ID_Atleta`. `Nome_Competicao` e `Data_Competicao` dependem de `ID_Competicao`. Como normalizar para 2FN?
16. **Projetos e Tarefas:** Uma tabela `Tarefas_Projeto` tem `(ID_Projeto, ID_Tarefa)` como chave primária. `Nome_Projeto` e `Orcamento_Projeto` dependem de `ID_Projeto`. `Descricao_Tarefa` e `Status_Tarefa` dependem de `ID_Tarefa`. Aplique a 2FN.
17. **Cidades e Regiões:** Uma tabela `Cidades_Regiao` tem `(ID_Cidade, ID_Regiao)` como chave primária. `Nome_Cidade` e `Populacao_Cidade` dependem de `ID_Cidade`. `Nome_Regiao` e `Area_Regiao` dependem de `ID_Regiao`. Como normalizar para 2FN?
18. **Veículos e Proprietários:** Uma tabela `Registros_Veiculos` tem `(Placa_Veiculo, ID_Proprietario)` como chave primária. `Modelo_Veiculo` e `Ano_Veiculo` dependem de `Placa_Veiculo`. `Nome_Proprietario` e `Endereco_Proprietario` dependem de `ID_Proprietario`. Aplique a 2FN.
19. **Postagens e Comentários:** Uma tabela `Comentarios_Postagem` tem `(ID_Postagem, ID_Comentario)` como chave primária. `Titulo_Postagem` e `Data_Publicacao_Postagem` dependem de `ID_Postagem`. `Autor_Comentario` e `Texto_Comentario` dependem de `ID_Comentario`. Como normalizar para 2FN?
20. **Produtos e Lojas:** Uma tabela `Estoque_Loja` tem `(ID_Produto, ID_Loja)` como chave primária. `Nome_Produto` e `Preco_Produto` dependem de `ID_Produto`. `Nome_Loja` e `Endereco_Loja` dependem de `ID_Loja`. Aplique a 2FN.
21. **Pacotes e Conteúdos:** Uma tabela `Conteudo_Pacote` tem `(ID_Pacote, ID_Item)` como chave primária. `Nome_Pacote` e `Descricao_Pacote` dependem de `ID_Pacote`. `Nome_Item` e `Quantidade_Item` dependem de `ID_Item`. Como normalizar para 2FN?
22. **Medicamentos e Fabricantes:** Uma tabela `Medicamento_Fabricante` tem `(ID_Medicamento, ID_Fabricante)` como chave primária. `Nome_Medicamento` e `Dosagem_Medicamento` dependem de `ID_Medicamento`. `Nome_Fabricante` e `Pais_Fabricante` dependem de `ID_Fabricante`. Aplique a 2FN.
23. **Jornais e Notícias:** Uma tabela `Noticias_Jornal` tem `(ID_Noticia, ID_Jornal)` como chave primária. `Titulo_Noticia` e `Data_Publicacao_Noticia` dependem de `ID_Noticia`. `Nome_Jornal` e `Sede_Jornal` dependem de `ID_Jornal`. Como normalizar para 2FN?
24. **Universidades e Departamentos:** Uma tabela `Alocacao_Departamento` tem `(ID_Universidade, ID_Departamento)` como chave primária. `Nome_Universidade` e `Local_Universidade` dependem de `ID_Universidade`. `Nome_Departamento` e `Chefe_Departamento` dependem de `ID_Departamento`. Aplique a 2FN.
25. **Seguradoras e Apólices:** Uma tabela `Apolices_Cliente` tem `(ID_Apolice, ID_Cliente)` como chave primária. `Tipo_Apolice` e `Valor_Apolice` dependem de `ID_Apolice`. `Nome_Cliente` e `Data_Nascimento_Cliente` dependem de `ID_Cliente`. Como normalizar para 2FN?
26. **Equipes e Jogadores:** Uma tabela `Jogadores_Equipe` tem `(ID_Equipe, ID_Jogador)` como chave primária. `Nome_Equipe` e `Cidade_Equipe` dependem de `ID_Equipe`. `Nome_Jogador` e `Posicao_Jogador` dependem de `ID_Jogador`. Aplique a 2FN.
27. **Redes Sociais e Usuários:** Uma tabela `Seguidores_Usuario` tem `(ID_Seguidor, ID_Seguido)` como chave primária. `Nome_Seguidor` e `Email_Seguidor` dependem de `ID_Seguidor`. `Nome_Seguido` e `Perfil_Seguido` dependem de `ID_Seguido`. Como normalizar para 2FN?
28. **Hospitais e Médicos:** Uma tabela `Atendimentos_Medico` tem `(ID_Hospital, ID_Medico)` como chave primária. `Nome_Hospital` e `Endereco_Hospital` dependem de `ID_Hospital`. `Nome_Medico` e `Especialidade_Medico` dependem de `ID_Medico`. Aplique a 2FN.
29. **Países e Cidades:** Uma tabela `Cidades_Pais` tem `(ID_Pais, ID_Cidade)` como chave primária. `Nome_Pais` e `Continente_Pais` dependem de `ID_Pais`. `Nome_Cidade` e `Populacao_Cidade` dependem de `ID_Cidade`. Como normalizar para 2FN?
30. **Escritórios e Funcionários:** Uma tabela `Funcionarios_Escritorio` tem `(ID_Escritorio, ID_Funcionario)` como chave primária. `Nome_Escritorio` e `Endereco_Escritorio` dependem de `ID_Escritorio`. `Nome_Funcionario` e `Cargo_Funcionario` dependem de `ID_Funcionario`. Aplique a 2FN.

---

## 3ª Forma Normal (3FN)

### Exercícios de Dependências Transitivas (40 Exercícios)

1.  **Clientes e Cidades:** Uma tabela `Clientes` tem `ID_Cliente`, `Nome_Cliente`, `Endereco_Cliente`, `Cidade_Cliente`, `Estado_Cliente` e `CEP_Cidade`. `Estado_Cliente` e `CEP_Cidade` dependem de `Cidade_Cliente`, que por sua vez depende de `ID_Cliente`. Como você normalizaria para 3FN?
2.  **Pedidos e Produtos:** Uma tabela `Pedidos` tem `ID_Pedido`, `Data_Pedido`, `ID_Cliente`, `Nome_Cliente`, `ID_Produto`, `Nome_Produto`, `Preco_Unitario` e `Desconto_Aplicado`. `Nome_Produto` depende de `ID_Produto`. `Nome_Cliente` depende de `ID_Cliente`. Como você normalizaria para 3FN?
3.  **Livros e Editoras:** Uma tabela `Livros` tem `ISBN`, `Titulo`, `ID_Editora`, `Nome_Editora` e `Endereco_Editora`. `Nome_Editora` e `Endereco_Editora` dependem de `ID_Editora`, que depende de `ISBN`. Aplique a 3FN.
4.  **Cursos e Departamentos:** Uma tabela `Cursos` tem `ID_Curso`, `Nome_Curso`, `ID_Departamento`, `Nome_Departamento` e `Chefe_Departamento`. `Nome_Departamento` e `Chefe_Departamento` dependem de `ID_Departamento`, que depende de `ID_Curso`. Como normalizar para 3FN?
5.  **Funcionários e Cargos:** Uma tabela `Funcionarios` tem `ID_Funcionario`, `Nome_Funcionario`, `ID_Cargo`, `Nome_Cargo` e `Salario_Base_Cargo`. `Nome_Cargo` e `Salario_Base_Cargo` dependem de `ID_Cargo`, que depende de `ID_Funcionario`. Aplique a 3FN.
6.  **Concertos e Bandas:** Uma tabela `Concertos` tem `ID_Concerto`, `Data_Concerto`, `Local_Concerto`, `ID_Banda`, `Nome_Banda` e `Genero_Banda`. `Nome_Banda` e `Genero_Banda` dependem de `ID_Banda`, que depende de `ID_Concerto`. Como normalizar para 3FN?
7.  **Filmes e Diretores:** Uma tabela `Filmes` tem `ID_Filme`, `Titulo_Filme`, `Ano_Lancamento`, `ID_Diretor`, `Nome_Diretor` e `Nacionalidade_Diretor`. `Nome_Diretor` e `Nacionalidade_Diretor` dependem de `ID_Diretor`, que depende de `ID_Filme`. Aplique a 3FN.
8.  **Produtos e Fornecedores:** Uma tabela `Produtos` tem `ID_Produto`, `Nome_Produto`, `Preco_Produto`, `ID_Fornecedor`, `Nome_Fornecedor` e `Contato_Fornecedor`. `Nome_Fornecedor` e `Contato_Fornecedor` dependem de `ID_Fornecedor`, que depende de `ID_Produto`. Como normalizar para 3FN?
9.  **Pacientes e Médicos:** Uma tabela `Pacientes` tem `ID_Paciente`, `Nome_Paciente`, `Data_Nascimento`, `ID_Medico`, `Nome_Medico` e `Especialidade_Medico`. `Nome_Medico` e `Especialidade_Medico` dependem de `ID_Medico`, que depende de `ID_Paciente`. Aplique a 3FN.
10. **Disciplinas e Professores:** Uma tabela `Disciplinas` tem `ID_Disciplina`, `Nome_Disciplina`, `Creditos`, `ID_Professor`, `Nome_Professor` e `Departamento_Professor`. `Nome_Professor` e `Departamento_Professor` dependem de `ID_Professor`, que depende de `ID_Disciplina`. Como normalizar para 3FN?
11. **Alunos e Bolsas:** Uma tabela `Alunos` tem `ID_Aluno`, `Nome_Aluno`, `Curso`, `ID_Bolsa`, `Tipo_Bolsa` e `Valor_Bolsa`. `Tipo_Bolsa` e `Valor_Bolsa` dependem de `ID_Bolsa`, que depende de `ID_Aluno`. Aplique a 3FN.
12. **Carros e Fabricantes:** Uma tabela `Carros` tem `ID_Carro`, `Modelo_Carro`, `Ano_Fabricacao`, `ID_Fabricante`, `Nome_Fabricante` e `Pais_Sede_Fabricante`. `Nome_Fabricante` e `Pais_Sede_Fabricante` dependem de `ID_Fabricante`, que depende de `ID_Carro`. Como normalizar para 3FN?
13. **Vendas e Vendedores:** Uma tabela `Vendas` tem `ID_Venda`, `Data_Venda`, `ID_Cliente`, `ID_Vendedor`, `Nome_Vendedor` e `Comissao_Padrao_Vendedor`. `Nome_Vendedor` e `Comissao_Padrao_Vendedor` dependem de `ID_Vendedor`, que depende de `ID_Venda`. Aplique a 3FN.
14. **Filiais e Gerentes:** Uma tabela `Filiais` tem `ID_Filial`, `Nome_Filial`, `Endereco_Filial`, `ID_Gerente`, `Nome_Gerente` e `Contato_Gerente`. `Nome_Gerente` e `Contato_Gerente` dependem de `ID_Gerente`, que depende de `ID_Filial`. Como normalizar para 3FN?
15. **Hóspedes e Reservas:** Uma tabela `Reservas` tem `ID_Reserva`, `Data_Checkin`, `ID_Hospede`, `Nome_Hospede`, `Tipo_Quarto_Reservado` e `Preco_Tipo_Quarto`. `Tipo_Quarto_Reservado` e `Preco_Tipo_Quarto` dependem de `ID_Quarto_Reservado`, que por sua vez depende de `ID_Reserva`. Aplique a 3FN.
16. **Postagens e Autores:** Uma tabela `Postagens` tem `ID_Postagem`, `Titulo_Postagem`, `Conteudo_Postagem`, `ID_Autor`, `Nome_Autor` e `Bio_Autor`. `Nome_Autor` e `Bio_Autor` dependem de `ID_Autor`, que depende de `ID_Postagem`. Como normalizar para 3FN?
17. **Revistas e Editores:** Uma tabela `Revistas` tem `ID_Revista`, `Titulo_Revista`, `Periodicidade`, `ID_Editor`, `Nome_Editor` e `Endereco_Editor`. `Nome_Editor` e `Endereco_Editor` dependem de `ID_Editor`, que depende de `ID_Revista`. Aplique a 3FN.
18. **Peças de Carro e Fabricantes:** Uma tabela `Pecas_Carro` tem `ID_Peca`, `Nome_Peca`, `Material`, `ID_Fabricante_Peca`, `Nome_Fabricante_Peca` e `Local_Fabricacao_Peca`. `Nome_Fabricante_Peca` e `Local_Fabricacao_Peca` dependem de `ID_Fabricante_Peca`, que depende de `ID_Peca`. Como normalizar para 3FN?
19. **Equipamentos e Manutenção:** Uma tabela `Equipamentos` tem `ID_Equipamento`, `Nome_Equipamento`, `Numero_Serie`, `ID_Fabricante_Equipamento`, `Nome_Fabricante_Equipamento` e `Contato_Fabricante_Equipamento`. `Nome_Fabricante_Equipamento` e `Contato_Fabricante_Equipamento` dependem de `ID_Fabricante_Equipamento`, que depende de `ID_Equipamento`. Aplique a 3FN.
20. **Atletas e Clubes:** Uma tabela `Atletas` tem `ID_Atleta`, `Nome_Atleta`, `Esporte`, `ID_Clube`, `Nome_Clube` e `Cidade_Clube`. `Nome_Clube` e `Cidade_Clube` dependem de `ID_Clube`, que depende de `ID_Atleta`. Como normalizar para 3FN?
21. **Cursos e Salas:** Uma tabela `Cursos_Oferecidos` tem `ID_Curso_Oferecido`, `Nome_Curso`, `Horario_Curso`, `Numero_Sala`, `Capacidade_Sala` e `Andar_Sala`. `Capacidade_Sala` e `Andar_Sala` dependem de `Numero_Sala`, que depende de `ID_Curso_Oferecido`. Aplique a 3FN.
22. **Projetos e Clientes:** Uma tabela `Projetos` tem `ID_Projeto`, `Nome_Projeto`, `Prazo_Projeto`, `ID_Cliente`, `Nome_Cliente` e `Email_Cliente`. `Nome_Cliente` e `Email_Cliente` dependem de `ID_Cliente`, que depende de `ID_Projeto`. Como normalizar para 3FN?
23. **Receitas e Culinária:** Uma tabela `Receitas` tem `ID_Receita`, `Nome_Receita`, `Tempo_Preparo`, `Tipo_Culinaria`, `Descricao_Tipo_Culinaria`. `Descricao_Tipo_Culinaria` depende de `Tipo_Culinaria`, que depende de `ID_Receita`. Aplique a 3FN.
24. **Pedidos de Suprimentos e Departamentos:** Uma tabela `Pedidos_Suprimentos` tem `ID_Pedido_Suprimento`, `Data_Pedido`, `ID_Departamento`, `Nome_Departamento` e `Local_Departamento`. `Nome_Departamento` e `Local_Departamento` dependem de `ID_Departamento`, que depende de `ID_Pedido_Suprimento`. Como normalizar para 3FN?
25. **Aluguéis e Imóveis:** Uma tabela `Alugueis` tem `ID_Aluguel`, `Data_Inicio`, `Data_Fim`, `ID_Imovel`, `Endereco_Imovel` e `Tipo_Imovel`. `Endereco_Imovel` e `Tipo_Imovel` dependem de `ID_Imovel`, que depende de `ID_Aluguel`. Aplique a 3FN.
26. **Consultores e Habilidades:** Uma tabela `Consultores` tem `ID_Consultor`, `Nome_Consultor`, `ID_Habilidade_Primaria`, `Nome_Habilidade_Primaria` e `Descricao_Habilidade_Primaria`. `Nome_Habilidade_Primaria` e `Descricao_Habilidade_Primaria` dependem de `ID_Habilidade_Primaria`, que depende de `ID_Consultor`. Como normalizar para 3FN?
27. **Compras e Lojas:** Uma tabela `Compras` tem `ID_Compra`, `Data_Compra`, `ID_Loja`, `Nome_Loja` e `Endereco_Loja`. `Nome_Loja` e `Endereco_Loja` dependem de `ID_Loja`, que depende de `ID_Compra`. Aplique a 3FN.
28. **Exames e Laboratórios:** Uma tabela `Exames` tem `ID_Exame`, `Tipo_Exame`, `Resultado_Exame`, `ID_Laboratorio`, `Nome_Laboratorio` e `Telefone_Laboratorio`. `Nome_Laboratorio` e `Telefone_Laboratorio` dependem de `ID_Laboratorio`, que depende de `ID_Exame`. Como normalizar para 3FN?
29. **Revistas e Publicações:** Uma tabela `Publicacoes` tem `ID_Publicacao`, `Titulo_Artigo`, `Autor_Artigo`, `ID_Revista`, `Nome_Revista` e `ISSN_Revista`. `Nome_Revista` e `ISSN_Revista` dependem de `ID_Revista`, que depende de `ID_Publicacao`. Aplique a 3FN.
30. **Shows e Locais:** Uma tabela `Shows` tem `ID_Show`, `Data_Show`, `Hora_Show`, `ID_Local`, `Nome_Local` e `Capacidade_Local`. `Nome_Local` e `Capacidade_Local` dependem de `ID_Local`, que depende de `ID_Show`. Como normalizar para 3FN?
31. **Equipamentos Médicos e Modelos:** Uma tabela `Equipamentos_Medicos` tem `ID_Equipamento`, `Numero_Serie`, `Data_Instalacao`, `ID_Modelo`, `Nome_Modelo` e `Fabricante_Modelo`. `Nome_Modelo` e `Fabricante_Modelo` dependem de `ID_Modelo`, que depende de `ID_Equipamento`. Aplique a 3FN.
32. **Animais e Espécies:** Uma tabela `Animais` tem `ID_Animal`, `Nome_Animal`, `Data_Nascimento`, `ID_Especie`, `Nome_Especie` e `Classificacao_Especie`. `Nome_Especie` e `Classificacao_Especie` dependem de `ID_Especie`, que depende de `ID_Animal`. Como normalizar para 3FN?
33. **Palestras e Temas:** Uma tabela `Palestras` tem `ID_Palestra`, `Titulo_Palestra`, `Palestrante`, `ID_Tema`, `Nome_Tema` e `Descricao_Tema`. `Nome_Tema` e `Descricao_Tema` dependem de `ID_Tema`, que depende de `ID_Palestra`. Aplique a 3FN.
34. **Softwares e Desenvolvedores:** Uma tabela `Softwares` tem `ID_Software`, `Nome_Software`, `Versao`, `ID_Desenvolvedor`, `Nome_Desenvolvedor` e `Empresa_Desenvolvedor`. `Nome_Desenvolvedor` e `Empresa_Desenvolvedor` dependem de `ID_Desenvolvedor`, que depende de `ID_Software`. Como normalizar para 3FN?
35. **Agências e Clientes (Publicidade):** Uma tabela `Contratos_Publicidade` tem `ID_Contrato`, `Data_Inicio`, `ID_Agencia`, `Nome_Agencia`, `Endereco_Agencia` e `ID_Cliente`, `Nome_Cliente`, `Setor_Cliente`. `Nome_Agencia` e `Endereco_Agencia` dependem de `ID_Agencia`. `Nome_Cliente` e `Setor_Cliente` dependem de `ID_Cliente`. Como normalizar para 3FN (considerando múltiplas dependências transitivas)?
36. **Contratos e Tipos de Contrato:** Uma tabela `Contratos` tem `ID_Contrato`, `Data_Assinatura`, `Tipo_Contrato`, `Descricao_Tipo_Contrato`. `Descricao_Tipo_Contrato` depende de `Tipo_Contrato`, que depende de `ID_Contrato`. Aplique a 3FN.
37. **Veículos e Cores:** Uma tabela `Veiculos` tem `ID_Veiculo`, `Modelo`, `Ano`, `Cor_Predominante`, `Codigo_Cor_Predominante`. `Codigo_Cor_Predominante` depende de `Cor_Predominante`, que depende de `ID_Veiculo`. Como normalizar para 3FN?
38. **Empregos e Setores:** Uma tabela `Oportunidades_Emprego` tem `ID_Oportunidade`, `Titulo_Vaga`, `Salario_Oferecido`, `Setor_Emprego`, `Descricao_Setor_Emprego`. `Descricao_Setor_Emprego` depende de `Setor_Emprego`, que depende de `ID_Oportunidade`. Aplique a 3FN.
39. **Projetos e Fases:** Uma tabela `Projetos` tem `ID_Projeto`, `Nome_Projeto`, `Data_Inicio`, `Fase_Atual`, `Descricao_Fase_Atual`. `Descricao_Fase_Atual` depende de `Fase_Atual`, que depende de `ID_Projeto`. Como normalizar para 3FN?
40. **Cidades e Países:** Uma tabela `Cidades` tem `ID_Cidade`, `Nome_Cidade`, `Populacao`, `Nome_Pais`, `Continente_Pais`. `Nome_Pais` e `Continente_Pais` dependem de `ID_Pais`, que por sua vez depende de `ID_Cidade`. Como normalizar para 3FN?

---

## Forma Normal de Boyce-Codd (BCNF)

### Exercícios de Chaves Candidatas e Dependências Anômalas (30 Exercícios)

1.  **Estudantes e Cursos/Professores:** Uma tabela `Inscricoes` tem `(ID_Estudante, ID_Curso, ID_Professor)` como chave primária. Um professor pode lecionar vários cursos, e um curso pode ser lecionado por vários professores. No entanto, para um dado curso, apenas um professor é atribuído em uma inscrição específica. Ou seja, `ID_Curso` determina `ID_Professor`. Como você normalizaria para BCNF?
2.  **Projetos e Gerentes/Habilidades:** Uma tabela `Atribuicoes_Projeto` tem `(ID_Projeto, ID_Gerente, Habilidade_Gerente)` como chave primária. `Habilidade_Gerente` depende de `ID_Gerente`, mas `ID_Gerente` não é uma chave candidata. Como você normalizaria para BCNF?
3.  **Livros e Títulos/Autores:** Uma tabela `Livros_Autores` tem `(Titulo_Livro, Nome_Autor)` como chave primária. No entanto, se um autor escreve vários livros, e o título de um livro é único para aquele autor, mas não globalmente, e você tem `Nacionalidade_Autor` que depende de `Nome_Autor`. Como você normalizaria para BCNF?
4.  **Empregos e Habilidades/Salários:** Uma tabela `Cargos` tem `(Nome_Cargo, Habilidade_Requerida)` como chave primária. `Salario_Medio` depende de `Nome_Cargo`. No entanto, `Habilidade_Requerida` não é uma chave candidata. Como você normalizaria para BCNF?
5.  **Cursos e Salas/Períodos:** Uma tabela `Agendamentos_Cursos` tem `(ID_Curso, Numero_Sala, Periodo)` como chave primária. Mas `Numero_Sala` e `Periodo` juntos determinam o `Tipo_Equipamento_Sala`. Como você normalizaria para BCNF?
6.  **Voluntários e Projetos/Funções:** Uma tabela `Voluntarios_Projeto` tem `(ID_Voluntario, ID_Projeto, Funcao_Voluntario)` como chave primária. `Habilidade_Requerida_Funcao` depende de `Funcao_Voluntario`. Como você normalizaria para BCNF?
7.  **Pacientes e Doenças/Medicamentos:** Uma tabela `Historico_Medico` tem `(ID_Paciente, ID_Doenca, ID_Medicamento)` como chave primária. `Dosagem_Medicamento_Padrao` depende de `ID_Medicamento`. Como você normalizaria para BCNF?
8.  **Automóveis e Cores/Tipos de Motor:** Uma tabela `Automoveis` tem `(ID_Automovel, Cor, Tipo_Motor)` como chave primária. `Eficiencia_Combustivel_Tipo_Motor` depende de `Tipo_Motor`. Como você normalizaria para BCNF?
9.  **Filmes e Estúdios/Gêneros:** Uma tabela `Producoes_Filme` tem `(Titulo_Filme, Nome_Estudio, Genero_Principal)` como chave primária. `Receita_Media_Genero` depende de `Genero_Principal`. Como você normalizaria para BCNF?
10. **Ações e Bolsas/Países:** Uma tabela `Cotacoes_Acoes` tem `(Simbolo_Acao, Nome_Bolsa, Pais_Bolsa)` como chave primária. `Pais_Bolsa` depende de `Nome_Bolsa`. Como você normalizaria para BCNF?
11. **Pedidos e Produtos/Descontos:** Uma tabela `Itens_Pedido` tem `(ID_Pedido, ID_Produto)` como chave primária. `Percentual_Desconto_Produto` depende de `ID_Produto`. Se `ID_Produto` não é uma chave candidata (i.e., pode ter duplicatas em diferentes pedidos), como normalizar para BCNF?
12. **Funcionários e Projetos/Habilidades:** Uma tabela `Alocacao_Funcionarios` tem `(ID_Funcionario, ID_Projeto, Habilidade_Aplicada_No_Projeto)` como chave primária. `Descricao_Habilidade` depende de `Habilidade_Aplicada_No_Projeto`. Como você normalizaria para BCNF?
13. **Artigos e Revistas/ISSN:** Uma tabela `Publicacoes_Artigo` tem `(ID_Artigo, Titulo_Revista, ISSN_Revista)` como chave primária. `ISSN_Revista` depende de `Titulo_Revista`. Como você normalizaria para BCNF?
14. **Aviões e Modelos/Capacidades:** Uma tabela `Frota_Avioes` tem `(Numero_Registro_Aviao, Modelo_Aviao, Capacidade_Passageiros_Modelo)` como chave primária. `Capacidade_Passageiros_Modelo` depende de `Modelo_Aviao`. Como você normalizaria para BCNF?
15. **Países e Cidades/Populações:** Uma tabela `Populacao_Cidades` tem `(Nome_Pais, Nome_Cidade, Populacao_Cidade)` como chave primária. `Populacao_Cidade` depende de `Nome_Cidade`. Como você normalizaria para BCNF?
16. **Professores e Disciplinas/Departamentos:** Uma tabela `Lecionando_Disciplinas` tem `(ID_Professor, ID_Disciplina, Nome_Departamento_Disciplina)` como chave primária. `Nome_Departamento_Disciplina` depende de `ID_Disciplina`. Como você normalizaria para BCNF?
17. **Produtos e Marcas/Países de Origem:** Uma tabela `Produtos_Internacionais` tem `(ID_Produto, Nome_Marca, Pais_Origem_Marca)` como chave primária. `Pais_Origem_Marca` depende de `Nome_Marca`. Como você normalizaria para BCNF?
18. **Escolas e Alunos/Notas:** Uma tabela `Notas_Alunos` tem `(ID_Escola, ID_Aluno, ID_Materia, Nota_Final)` como chave primária. `Nome_Escola` depende de `ID_Escola`. `Nome_Aluno` depende de `ID_Aluno`. `Nome_Materia` depende de `ID_Materia`. No entanto, se `ID_Aluno` e `ID_Materia` não forem chaves candidatas independentes, mas `ID_Escola` junto com `ID_Aluno` determinarem `Nome_Aluno`, e `ID_Materia` for única para a escola. Como normalizar para BCNF? (Cenário mais complexo de múltiplas dependências).
19. **Equipes e Jogadores/Posições:** Uma tabela `Escalacao_Equipe` tem `(Nome_Equipe, Nome_Jogador, Posicao_Jogador_Padrao)` como chave primária. `Posicao_Jogador_Padrao` depende de `Nome_Jogador`. Como você normalizaria para BCNF?
20. **Livros e Gêneros/Descrições:** Uma tabela `Classificacao_Livros` tem `(ISBN, Genero_Livro, Descricao_Genero)` como chave primária. `Descricao_Genero` depende de `Genero_Livro`. Como você normalizaria para BCNF?
21. **Cursos e Professores/Semanas:** Uma tabela `Horario_Cursos` tem `(Nome_Curso, Nome_Professor, Dia_Semana, Hora_Inicio)` como chave primária. Se `Nome_Professor` para um dado `Nome_Curso` é único, mas `Nome_Professor` tem `Departamento_Professor` que depende dele. Como normalizar para BCNF?
22. **Artistas e Obras/Estilos:** Uma tabela `Obras_Artista` tem `(Nome_Artista, Titulo_Obra, Estilo_Obra_Principal)` como chave primária. `Descricao_Estilo_Obra` depende de `Estilo_Obra_Principal`. Como você normalizaria para BCNF?
23. **Cidades e Estados/Capitais:** Uma tabela `Geografia_Cidades` tem `(Nome_Cidade, Nome_Estado, Capital_Estado)` como chave primária. `Capital_Estado` depende de `Nome_Estado`. Como você normalizaria para BCNF?
24. **Produtos e Cores/Códigos:** Uma tabela `Variacoes_Produto` tem `(ID_Produto, Cor_Produto, Codigo_Cor_RGB)` como chave primária. `Codigo_Cor_RGB` depende de `Cor_Produto`. Como você normalizaria para BCNF?
25. **Segurados e Apólices/Agentes:** Uma tabela `Segurados_Apolices` tem `(ID_Segurado, ID_Apolice, Nome_Agente_Seguradora)` como chave primária. `Nome_Agente_Seguradora` depende de `ID_Agente_Seguradora` (que não está na chave primária). Como você normalizaria para BCNF? (Assumindo que `ID_Agente_Seguradora` pode ser determinado por `ID_Apolice`).
26. **Usuários e Perfis/Cargos:** Uma tabela `Usuarios_Sistema` tem `(ID_Usuario, Nome_Perfil, Permissao_Padrao_Perfil)` como chave primária. `Permissao_Padrao_Perfil` depende de `Nome_Perfil`. Como você normalizaria para BCNF?
27. **Empresas e Setores/Subsetores:** Uma tabela `Classificacao_Empresas` tem `(Nome_Empresa, Setor_Principal, Subsetor_Especifico)` como chave primária. `Descricao_Setor_Principal` depende de `Setor_Principal`. Como você normalizaria para BCNF?
28. **Hospitais e Departamentos/Chefes:** Uma tabela `Departamentos_Hospital` tem `(ID_Hospital, Nome_Departamento, Nome_Chefe_Departamento)` como chave primária. `Nome_Chefe_Departamento` depende de `Nome_Departamento`. Como você normalizaria para BCNF?
29. **Discos e Músicas/Gêneros:** Uma tabela `Conteudo_Disco` tem `(ID_Disco, Titulo_Musica, Genero_Musica_Principal)` como chave primária. `Descricao_Genero_Musica` depende de `Genero_Musica_Principal`. Como você normalizaria para BCNF?
30. **Livros e Editoras/Países:** Uma tabela `Livros_Publicados` tem `(ISBN, Nome_Editora, Pais_Sede_Editora)` como chave primária. `Pais_Sede_Editora` depende de `Nome_Editora`. Como você normalizaria para BCNF?

---

## Modelagem Completa e Cenários Complexos

### Exercícios de Aplicação de Múltiplas Normalizações e Decisões de Modelagem (80 Exercícios)

1.  **Sistema de Biblioteca (Completo):** Modele um sistema de biblioteca que gerencie livros, autores, leitores e empréstimos. Garanta que todas as tabelas estejam pelo menos na 3FN.
2.  **Sistema de Gerenciamento de Pedidos:** Modele um sistema de gerenciamento de pedidos para uma loja online, incluindo clientes, produtos, pedidos e itens de pedido. Normalize até a 3FN/BCNF.
3.  **Sistema de Gerenciamento de Funcionários:** Modele um sistema para gerenciar funcionários, departamentos, projetos e alocações de funcionários a projetos. Normalize até a 3FN.
4.  **Sistema de Controle Acadêmico:** Modele um sistema acadêmico para gerenciar alunos, cursos, professores e notas. Normalize até a 3FN/BCNF.
5.  **Sistema de Clínica Médica:** Modele um sistema para registrar pacientes, médicos, consultas e históricos de tratamento. Normalize até a 3FN.
6.  **Sistema de Reserva de Voos:** Modele um sistema de reservas de voos, incluindo voos, passageiros, assentos e companhias aéreas. Normalize até a 3FN/BCNF.
7.  **Sistema de Gerenciamento de Restaurantes:** Modele um sistema para gerenciar restaurantes, menus, pratos e ingredientes. Normalize até a 3FN.
8.  **Sistema de Blog:** Modele um sistema de blog com posts, autores, comentários e tags. Normalize até a 3FN.
9.  **Sistema de Gestão de Eventos:** Modele um sistema para gerenciar eventos, participantes, palestrantes e locais. Normalize até a 3FN.
10. **Sistema de Inventário de Loja:** Modele um sistema de inventário para uma loja, incluindo produtos, categorias, fornecedores e estoque. Normalize até a 3FN/BCNF.
11. **Sistema de Gerenciamento de Conteúdo de Vídeo:** Modele um sistema para gerenciar vídeos, diretores, atores e gêneros. Normalize até a 3FN.
12. **Sistema de Gerenciamento de Música:** Modele um sistema para gerenciar músicas, artistas, álbuns e gêneros. Normalize até a 3FN.
13. **Sistema de Gestão de Projetos de Software:** Modele um sistema para gerenciar projetos, equipes, tarefas e membros da equipe. Normalize até a 3FN.
14. **Sistema de CRM (Customer Relationship Management):** Modele um sistema CRM, incluindo clientes, contatos, interações e histórico de vendas. Normalize até a 3FN.
15. **Sistema de Gerenciamento de Veículos:** Modele um sistema para gerenciar veículos, proprietários, manutenções e registros. Normalize até a 3FN.
16. **Sistema de Gestão de Seguros:** Modele um sistema para gerenciar segurados, apólices, sinistros e agentes. Normalize até a 3FN.
17. **Sistema de Gerenciamento de Hospitalidade:** Modele um sistema para gerenciar hotéis, quartos, hóspedes e reservas. Normalize até a 3FN.
18. **Sistema de Gestão de Transportes:** Modele um sistema para gerenciar rotas, veículos, motoristas e entregas. Normalize até a 3FN.
19. **Sistema de Gestão de Fazendas:** Modele um sistema para gerenciar culturas, animais, funcionários e equipamentos agrícolas. Normalize até a 3FN.
20. **Sistema de Gestão de Galeria de Arte:** Modele um sistema para gerenciar artistas, obras de arte, exposições e colecionadores. Normalize até a 3FN.
21. **Sistema de Gerenciamento de Ginásio:** Modele um sistema para gerenciar membros, planos de adesão, aulas e instrutores. Normalize até a 3FN.
22. **Sistema de Gerenciamento de Imobiliárias:** Modele um sistema para gerenciar propriedades, agentes imobiliários, clientes e negociações. Normalize até a 3FN.
23. **Sistema de Gestão de Recursos Humanos:** Modele um sistema para gerenciar funcionários, cargos, folhas de pagamento e avaliações de desempenho. Normalize até a 3FN.
24. **Sistema de Gestão de Finanças Pessoais:** Modele um sistema para gerenciar contas bancárias, transações, categorias de despesas e orçamentos. Normalize até a 3FN.
25. **Sistema de Gerenciamento de Suprimentos:** Modele um sistema para gerenciar pedidos de suprimentos, fornecedores, itens e estoque. Normalize até a 3FN.
26. **Sistema de E-commerce B2B:** Modele um sistema de e-commerce focado em negócios para negócios, incluindo empresas, contatos, produtos e pedidos complexos. Normalize até a 3FN/BCNF.
27. **Sistema de Notícias Online:** Modele um sistema para gerenciar artigos de notícias, jornalistas, categorias e comentários. Normalize até a 3FN.
28. **Sistema de Gerenciamento de Esportes:** Modele um sistema para gerenciar equipes, jogadores, ligas e resultados de partidas. Normalize até a 3FN.
29. **Sistema de Gerenciamento de Redes Sociais:** Modele um sistema simplificado para gerenciar usuários, postagens, amigos e curtidas. Normalize até a 3FN.
30. **Sistema de Gerenciamento de Serviços de TI:** Modele um sistema para gerenciar solicitações de serviço, técnicos, clientes e status. Normalize até a 3FN.
31. **Sistema de Gerenciamento de Marketing Digital:** Modele um sistema para gerenciar campanhas de marketing, canais, orçamentos e resultados. Normalize até a 3FN.
32. **Sistema de Gerenciamento de Frota de Veículos:** Modele um sistema para gerenciar veículos, motoristas, rotas e manutenção programada. Normalize até a 3FN.
33. **Sistema de Gerenciamento de Contratos:** Modele um sistema para gerenciar contratos, partes envolvidas, datas de vencimento e termos. Normalize até a 3FN.
34. **Sistema de Gerenciamento de Doações:** Modele um sistema para gerenciar doadores, campanhas de doação, valores e histórico. Normalize até a 3FN.
35. **Sistema de Gerenciamento de Equipamentos de Laboratório:** Modele um sistema para gerenciar equipamentos, fabricantes, datas de calibração e usuários. Normalize até a 3FN.
36. **Sistema de Gerenciamento de Produção (Manufatura):** Modele um sistema para gerenciar ordens de produção, matérias-primas, produtos acabados e etapas de processo. Normalize até a 3FN.
37. **Sistema de Gerenciamento de Ativos Fixos:** Modele um sistema para gerenciar ativos da empresa (computadores, móveis), localização, responsável e depreciação. Normalize até a 3FN.
38. **Sistema de Gerenciamento de Eventos Corporativos:** Modele um sistema para gerenciar eventos internos, participantes, agendas e custos. Normalize até a 3FN.
39. **Sistema de Gerenciamento de Associações:** Modele um sistema para gerenciar membros, tipos de associação, pagamentos e benefícios. Normalize até a 3FN.
40. **Sistema de Gerenciamento de Licenças de Software:** Modele um sistema para gerenciar licenças, softwares, usuários e datas de expiração. Normalize até a 3FN.
41. **Sistema de Gestão de Projetos Freelancer:** Modele um sistema para freelancers gerenciarem clientes, projetos, tarefas e faturamento. Normalize até a 3FN.
42. **Sistema de Gerenciamento de Portfólio de Investimentos:** Modele um sistema para gerenciar ativos (ações, fundos), transações, valorizações e investidores. Normalize até a 3FN.
43. **Sistema de Gerenciamento de Patentes:** Modele um sistema para gerenciar patentes, inventores, datas de registro e status. Normalize até a 3FN.
44. **Sistema de Gerenciamento de Receitas de Culinária:** Modele um sistema para gerenciar receitas, ingredientes, categorias e avaliações. Normalize até a 3FN.
45. **Sistema de Gerenciamento de Aluguéis de Carros:** Modele um sistema para gerenciar carros, clientes, aluguéis e histórico. Normalize até a 3FN.
46. **Sistema de Gerenciamento de Animais de Estimação (Pet Shop):** Modele um sistema para gerenciar animais, donos, serviços e produtos. Normalize até a 3FN.
47. **Sistema de Gerenciamento de Ordem de Serviço:** Modele um sistema para gerenciar ordens de serviço, clientes, técnicos, peças e status. Normalize até a 3FN.
48. **Sistema de Gerenciamento de Leilões:** Modele um sistema para gerenciar itens, licitantes, lances e resultados. Normalize até a 3FN.
49. **Sistema de Gerenciamento de Conteúdo para Mídias Sociais:** Modele um sistema para gerenciar posts, agendamentos, plataformas e métricas. Normalize até a 3FN.
50. **Sistema de Gerenciamento de Clientes (Freelancer):** Modele um sistema para freelancers para gerenciar clientes, projetos, faturas e pagamentos. Normalize até a 3FN.
51. **Sistema de Gerenciamento de Vendas B2B:** Modele um sistema para vendas de empresa para empresa, com foco em contas, leads, oportunidades e pipeline de vendas. Normalize até a 3FN/BCNF.
52. **Sistema de Gerenciamento de Fórum Online:** Modele um sistema para gerenciar usuários, tópicos, postagens e subfóruns. Normalize até a 3FN.
53. **Sistema de Gerenciamento de Reservas de Espaços:** Modele um sistema para gerenciar salas de reunião, equipamentos, reservas e usuários. Normalize até a 3FN.
54. **Sistema de Gerenciamento de Qualidade (ISO):** Modele um sistema para gerenciar documentos de qualidade, não conformidades, auditorias e ações corretivas. Normalize até a 3FN.
55. **Sistema de Gerenciamento de Talentos (Recrutamento):** Modele um sistema para gerenciar candidatos, vagas, entrevistas e status de contratação. Normalize até a 3FN.
56. **Sistema de Gerenciamento de Programas de Fidelidade:** Modele um sistema para gerenciar clientes, pontos, recompensas e histórico de transações. Normalize até a 3FN.
57. **Sistema de Gerenciamento de Redes (TI):** Modele um sistema para gerenciar dispositivos de rede, IPs, portas e status. Normalize até a 3FN.
58. **Sistema de Gerenciamento de Coleção de Filmes Pessoais:** Modele um sistema para organizar filmes, atores, diretores, gêneros e mídias (DVD, Blu-ray). Normalize até a 3FN.
59. **Sistema de Gerenciamento de Pacotes e Entregas:** Modele um sistema para gerenciar pacotes, remetentes, destinatários, status de entrega e motoristas. Normalize até a 3FN.
60. **Sistema de Gerenciamento de Reservas de Restaurantes:** Modele um sistema para gerenciar mesas, clientes, horários de reserva e status. Normalize até a 3FN.
61. **Sistema de Gerenciamento de Conteúdo para E-learning:** Modele um sistema para gerenciar cursos, módulos, lições, alunos e progresso. Normalize até a 3FN.
62. **Sistema de Gerenciamento de Manutenção Predial:** Modele um sistema para gerenciar solicitações de manutenção, técnicos, equipamentos e status de reparo. Normalize até a 3FN.
63. **Sistema de Gerenciamento de Bibliotecas de Mídia (Imagens/Áudios):** Modele um sistema para gerenciar arquivos de mídia, categorias, tags e metadados. Normalize até a 3FN.
64. **Sistema de Gerenciamento de Pesquisas de Mercado:** Modele um sistema para gerenciar pesquisas, participantes, perguntas e respostas. Normalize até a 3FN.
65. **Sistema de Gerenciamento de Equipamento de Áudio/Vídeo para Eventos:** Modele um sistema para gerenciar equipamentos, disponibilidade, locações e clientes. Normalize até a 3FN.
66. **Sistema de Gerenciamento de Projetos de Construção:** Modele um sistema para gerenciar projetos, etapas, materiais, fornecedores e orçamentos. Normalize até a 3FN.
67. **Sistema de Gerenciamento de Campanhas de Crowdfunding:** Modele um sistema para gerenciar campanhas, doadores, recompensas e progresso. Normalize até a 3FN.
68. **Sistema de Gerenciamento de Relacionamento com Fornecedores:** Modele um sistema para gerenciar fornecedores, contratos, produtos fornecidos e avaliações. Normalize até a 3FN.
69. **Sistema de Gerenciamento de Publicações Científicas:** Modele um sistema para gerenciar artigos científicos, autores, periódicos, citações e revisões. Normalize até a 3FN.
70. **Sistema de Gerenciamento de Assinaturas (Revistas/Serviços):** Modele um sistema para gerenciar assinantes, tipos de assinatura, pagamentos e datas de renovação. Normalize até a 3FN.
71. **Sistema de Gerenciamento de Aulas Particulares:** Modele um sistema para gerenciar alunos, professores, aulas, horários e pagamentos. Normalize até a 3FN.
72. **Sistema de Gerenciamento de Prêmios e Reconhecimentos:** Modele um sistema para gerenciar prêmios, candidatos, vencedores e categorias. Normalize até a 3FN.
73. **Sistema de Gerenciamento de Patrimônio Cultural:** Modele um sistema para gerenciar obras de arte, locais históricos, restauradores e coleções. Normalize até a 3FN.
74. **Sistema de Gerenciamento de Reservas de Equipamentos (Empresa):** Modele um sistema para gerenciar equipamentos da empresa, usuários, datas de reserva e devolução. Normalize até a 3FN.
75. **Sistema de Gerenciamento de Voluntários:** Modele um sistema para gerenciar voluntários, habilidades, disponibilidade e projetos. Normalize até a 3FN.
76. **Sistema de Gerenciamento de Frotas de Taxis/Ubers:** Modele um sistema para gerenciar veículos, motoristas, passageiros, corridas e pagamentos. Normalize até a 3FN.
77. **Sistema de Gerenciamento de Campanhas Políticas:** Modele um sistema para gerenciar eleitores, voluntários, doações e eventos de campanha. Normalize até a 3FN.
78. **Sistema de Gerenciamento de Acompanhamento de Saúde (Fitness):** Modele um sistema para gerenciar usuários, treinos, dieta, métricas de saúde e progresso. Normalize até a 3FN.
79. **Sistema de Gerenciamento de Produção de Conteúdo (Redação):** Modele um sistema para gerenciar artigos, redatores, editores, status e prazos. Normalize até a 3FN.
80. **Sistema de Gerenciamento de Certificações (Profissional):** Modele um sistema para gerenciar profissionais, certificações, datas de validade e órgãos certificadores. Normalize até a 3FN.
