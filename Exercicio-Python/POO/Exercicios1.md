---

Excelente! Dar o próximo passo para **Design Patterns**, **SOLID** e conceitos de POO mais avançados é o que realmente diferencia um desenvolvedor Júnior de um Pleno/Sênior. Não se trata apenas de saber a sintaxe, mas de **estruturar seu código para ser flexível, manutenível e escalável**.

Os exercícios abaixo são projetados para forçar você a pensar sobre essas questões, modelando soluções que podem crescer e se adaptar. Para cada um, detalho os conceitos-chave de POO e os Design Patterns/Princípios SOLID aplicáveis.

---

## 1. Sistema de Processamento de Pagamentos (Com Extensibilidade)

Este projeto vai além de um simples carrinho de compras, focando em como lidar com diferentes tipos de pagamentos e a adição de novos métodos no futuro.

* **Classes Iniciais:**
    * `Pedido`: Contém itens, valor total.
    * `Pagamento`: Classe base abstrata. Métodos abstratos como `processar_pagamento(valor)`.
    * `CartaoCredito` (herda de `Pagamento`): Implementa processamento para cartão de crédito.
    * `Boleto` (herda de `Pagamento`): Implementa processamento para boleto.
    * `PayPal` (herda de `Pagamento`): Implementa processamento para PayPal.
* **Conceitos POO Avançados/Design Patterns/SOLID:**
    * **Princípio Aberto/Fechado (OCP - SOLID):** Você pode adicionar novos métodos de pagamento (ex: `Pix`, `Criptomoeda`) sem precisar modificar a classe `Pedido` ou o sistema de processamento principal.
    * **Polimorfismo:** Diferentes objetos `Pagamento` respondem ao mesmo método `processar_pagamento()` de maneiras distintas.
    * **Classes Abstratas (ABC):** `Pagamento` seria uma `ABC` para definir a interface comum.
    * **Strategy Pattern:** O `Pedido` ou um `ProcessadorDePagamentos` central "usa" uma estratégia de pagamento (o objeto `Pagamento` concreto) para realizar a operação. A lógica de processamento é encapsulada na estratégia.
    * **Single Responsibility Principle (SRP - SOLID):** A classe `Pedido` se preocupa com o pedido, não com os detalhes de como cada pagamento é processado. Cada classe de pagamento se preocupa apenas com seu próprio tipo de pagamento.
* **Desafio Adicional:** Adicione um sistema de `Notificacao` (email, SMS) após o pagamento. Isso pode levar a um **Observer Pattern**.

---

## 2. Framework de Geração de Relatórios Flexível

Crie um sistema que pode gerar relatórios em diferentes formatos (PDF, CSV, HTML) e de diferentes fontes de dados.

* **Classes Iniciais:**
    * `Relatorio` (Classe Base Abstrata): Define interface para `gerar_cabecalho()`, `gerar_corpo(dados)`, `gerar_rodape()`.
    * `RelatorioPDF` (herda de `Relatorio`): Implementa para PDF.
    * `RelatorioCSV` (herda de `Relatorio`): Implementa para CSV.
    * `FonteDeDados` (Classe Base Abstrata): Define interface para `carregar_dados()`.
    * `FonteDadosBanco` (herda de `FonteDeDados`): Carrega dados de um banco de dados.
    * `FonteDadosCSV` (herda de `FonteDeDados`): Carrega dados de um arquivo CSV.
    * `GeradorRelatorios`: Orquestra a geração, recebendo um objeto `Relatorio` e um objeto `FonteDeDados`.
* **Conceitos POO Avançados/Design Patterns/SOLID:**
    * **Factory Method Pattern:** Um método de classe `RelatorioFactory.criar_relatorio(tipo)` para criar instâncias de `RelatorioPDF`, `RelatorioCSV`, etc., sem expor a lógica de criação.
    * **Strategy Pattern:** O `GeradorRelatorios` usa uma estratégia de "formato" (o objeto `Relatorio` concreto) e uma estratégia de "fonte" (o objeto `FonteDeDados` concreto).
    * **Princípio Aberto/Fechado (OCP - SOLID):** Fácil adicionar novos formatos de relatório ou novas fontes de dados sem modificar o `GeradorRelatorios`.
    * **Single Responsibility Principle (SRP - SOLID):** Cada classe tem uma responsabilidade bem definida (gerar parte de um formato, carregar dados de uma fonte, orquestrar).
    * **Dependency Inversion Principle (DIP - SOLID):** O `GeradorRelatorios` depende de abstrações (`Relatorio`, `FonteDeDados`), não de implementações concretas.
* **Desafio Adicional:** Adicione filtros aos dados do relatório (ex: filtrar por data). Isso pode levar ao **Decorator Pattern** para adicionar funcionalidades de filtro de forma dinâmica.

---

## 3. Sistema de Gestão de Usuários Autenticação (Com Plugins)

Desenvolva um sistema de autenticação que possa ser estendido para suportar diferentes provedores (usuário/senha, OAuth, LDAP).

* **Classes Iniciais:**
    * `Autenticador` (Classe Base Abstrata): Define método abstrato `autenticar(credenciais)`.
    * `AutenticadorPadrao` (herda de `Autenticador`): Lógica de autenticação com usuário e senha internos.
    * `AutenticadorOAuth` (herda de `Autenticador`): Simula autenticação OAuth.
    * `Usuario`: Atributos (`username`, `email`, `perfil`).
    * `SistemaAutenticacao`: Atributos (`autenticadores_registrados: dict`). Métodos (`registrar_autenticador()`, `login(tipo_autenticador, credenciais)`).
* **Conceitos POO Avançados/Design Patterns/SOLID:**
    * **Strategy Pattern:** O `SistemaAutenticacao` usa uma estratégia de autenticação (o `Autenticador` concreto).
    * **Princípio Aberto/Fechado (OCP - SOLID):** Adicionar novos métodos de autenticação não requer mudar o `SistemaAutenticacao`.
    * **Liskov Substitution Principle (LSP - SOLID):** Qualquer subclasse de `Autenticador` pode ser usada no lugar de `Autenticador` sem quebrar o sistema.
    * **Dependency Inversion Principle (DIP - SOLID):** `SistemaAutenticacao` depende da abstração `Autenticador`.
    * **Factory Method (Opcional):** Um método para criar instâncias de autenticadores.
* **Desafio Adicional:** Implemente um sistema de "roles" ou "permissões" (`RoleBasedAccessControl - RBAC`) para usuários, onde diferentes perfis de usuário têm acesso a diferentes funcionalidades. Isso pode ser feito com o **Chain of Responsibility** para verificar permissões.

---

## 4. Simulador de Eventos Orientado a Eventos

Crie um sistema onde diferentes "observadores" reagem a eventos gerados por "sujeitos".

* **Classes Iniciais:**
    * `Evento`: Classe base para diferentes tipos de eventos (ex: `EventoAlerta`, `EventoInfo`).
    * `Subject` (ou `EmissorDeEventos` - Classe Base Abstrata): Define métodos para `adicionar_observador()`, `remover_observador()`, `notificar_observadores(evento)`.
    * `Observer` (ou `ReceptorDeEventos` - Classe Base Abstrata): Define método abstrato `atualizar(evento)`.
    * `SensorTemperatura` (herda de `Subject`): Gera `EventoAlertaTemperatura` quando a temperatura excede um limite.
    * `Logger` (herda de `Observer`): Registra todos os eventos.
    * `AlertaSMS` (herda de `Observer`): Envia SMS para `EventoAlerta`.
* **Conceitos POO Avançados/Design Patterns/SOLID:**
    * **Observer Pattern:** Core do projeto. `Subjects` notificam `Observers` sobre mudanças.
    * **Polimorfismo:** Diferentes tipos de `Eventos` e diferentes `Observers` que reagem de formas variadas.
    * **Single Responsibility Principle (SRP - SOLID):** O sensor apenas detecta e emite; o logger apenas loga; o alerta apenas alerta.
    * **Princípio Aberto/Fechado (OCP - SOLID):** Fácil adicionar novos tipos de sensores (sujeitos) ou novos tipos de reações (observadores) sem modificar o núcleo.
* **Desafio Adicional:** Adicione um **Command Pattern** para que as ações (`Logger.log_action`, `AlertaSMS.send_sms`) possam ser encapsuladas como objetos, permitindo desfazer/refazer ou enfileirar ações.

---

## 5. Sistema de Log com Múltiplos Destinos

Construa um sistema de logging que pode enviar logs para o console, arquivo, banco de dados, etc., e pode ter diferentes níveis de severidade.

* **Classes Iniciais:**
    * `Logger`: Classe principal para o usuário.
    * `Handler` (Classe Base Abstrata): Define interface `emitir(mensagem, nivel)`.
    * `ConsoleHandler` (herda de `Handler`): Emite para o console.
    * `FileHandler` (herda de `Handler`): Emite para um arquivo.
    * `DatabaseHandler` (herda de `Handler`): Emite para um banco de dados.
    * `Formatter` (Classe Base Abstrata): Define interface para `formatar(mensagem, nivel)`.
    * `SimpleFormatter` (herda de `Formatter`): Formato simples de string.
    * `JSONFormatter` (herda de `Formatter`): Formato JSON.
* **Conceitos POO Avançados/Design Patterns/SOLID:**
    * **Chain of Responsibility Pattern:** Múltiplos `Handlers` podem ser encadeados. Por exemplo, um log de erro pode ir para o console e para um arquivo.
    * **Strategy Pattern:** O `Logger` usa um `Formatter` como estratégia para formatar a mensagem.
    * **Princípio Aberto/Fechado (OCP - SOLID):** Novos handlers ou formatters podem ser adicionados sem alterar o `Logger`.
    * **Dependency Inversion Principle (DIP - SOLID):** `Logger` depende de `Handler` e `Formatter` (abstrações).
    * **Builder Pattern (Opcional):** Para construir configurações complexas de `Logger` com vários handlers e formatters.
* **Desafio Adicional:** Implemente um sistema de cache para logs, onde os logs são armazenados temporariamente antes de serem escritos em um handler de forma assíncrona. Isso pode envolver o **Producer-Consumer Pattern**.

---

## 6. Editor de Documentos (Com Desfazer/Refazer)

Simula um editor de texto simples com funcionalidade de desfazer/refazer operações.

* **Classes Iniciais:**
    * `Documento`: Atributos (`conteudo: str`). Métodos (`adicionar_texto()`, `apagar_texto()`).
    * `Comando` (Interface/Classe Abstrata): Define métodos `executar()` e `desfazer()`.
    * `ComandoAdicionarTexto` (implementa `Comando`): Adiciona texto ao documento.
    * `ComandoApagarTexto` (implementa `Comando`): Apaga texto do documento.
    * `GerenciadorHistorico`: Atributos (`historico: list[Comando]`, `undo_stack: list[Comando]`, `redo_stack: list[Comando]`). Métodos (`executar_comando(comando)`, `desfazer()`, `refazer()`).
* **Conceitos POO Avançados/Design Patterns/SOLID:**
    * **Command Pattern:** Cada operação (adicionar, apagar) é encapsulada em um objeto `Comando`.
    * **Memento Pattern (Opcional/Alternativa):** Em vez de comandos, você pode usar o Memento para salvar/restaurar o estado do `Documento`. O `GerenciadorHistorico` seria o `Caretaker`.
    * **Encapsulamento:** `Documento` não precisa saber como os comandos são executados ou desfeitos.
    * **Princípio Aberto/Fechado (OCP - SOLID):** Fácil adicionar novos tipos de comandos (ex: `ComandoFormatarTexto`) sem modificar o `GerenciadorHistorico`.
* **Desafio Adicional:** Adicione um sistema de "salvamento" onde o estado do documento pode ser salvo e carregado de um arquivo. Isso se relaciona bem com o Memento.

---

## 7. Sistema de Reservas Flexível

Permite reservas de diferentes tipos de recursos (salas de reunião, carros, equipamentos) com validações e disponibilidade.

* **Classes Iniciais:**
    * `Recurso` (Classe Base Abstrata): Atributos (`id`, `nome`). Métodos abstratos como `verificar_disponibilidade(data_hora_inicio, data_hora_fim)`.
    * `SalaReuniao` (herda de `Recurso`): Adiciona `capacidade`, `equipamentos`.
    * `Carro` (herda de `Recurso`): Adiciona `placa`, `modelo`.
    * `Equipamento` (herda de `Recurso`): Adiciona `serial`.
    * `Reserva`: Atributos (`id_reserva`, `recurso: Recurso`, `usuario`, `data_hora_inicio`, `data_hora_fim`). Métodos (`validar_conflito()`).
    * `GerenciadorReservas`: Atributos (`recursos: list[Recurso]`, `reservas: list[Reserva]`). Métodos (`fazer_reserva()`, `cancelar_reserva()`, `listar_reservas_por_recurso()`).
* **Conceitos POO Avançados/Design Patterns/SOLID:**
    * **Template Method Pattern:** A lógica geral de `verificar_disponibilidade` poderia ser um Template Method, onde subclasses implementam detalhes específicos (ex: verificar capacidade da sala, se carro está em manutenção).
    * **Polimorfismo:** Diferentes `Recursos` podem ser tratados de forma uniforme pelo `GerenciadorReservas`.
    * **Liskov Substitution Principle (LSP - SOLID):** Subclasses de `Recurso` podem ser usadas no lugar da classe base.
    * **Single Responsibility Principle (SRP - SOLID):** `Reserva` se preocupa com os dados da reserva, `Recurso` com suas próprias regras de disponibilidade.
    * **Observer Pattern (Opcional):** Notificar usuários sobre status da reserva ou conflitos.
* **Desafio Adicional:** Implementar um sistema de notificação por email para confirmações e lembretes de reserva.

---

## 8. Sistema de Gerenciamento de Projetos (Tarefas e Status)

Um sistema para gerenciar projetos, tarefas, membros da equipe e seus status.

* **Classes Iniciais:**
    * `Tarefa`: Atributos (`nome`, `descricao`, `status: str`, `atribuida_a: MembroEquipe`, `prazo`). Métodos (`atualizar_status()`).
    * `MembroEquipe`: Atributos (`nome`, `id_membro`, `cargo`).
    * `Projeto`: Atributos (`nome_projeto`, `descricao`, `tarefas: list[Tarefa]`, `membros: list[MembroEquipe]`). Métodos (`adicionar_tarefa()`, `adicionar_membro()`, `gerar_relatorio_status()`).
    * `EstadoTarefa` (Classe Abstrata): Define interface para `manipular_estado(contexto_tarefa)`.
    * `EstadoPendente` (implementa `EstadoTarefa`): Transições para `EmAndamento`, `Concluida`, `Cancelada`.
    * `EstadoEmAndamento`, `EstadoConcluida`, `EstadoCancelada`.
* **Conceitos POO Avançados/Design Patterns/SOLID:**
    * **State Pattern:** O comportamento da `Tarefa` muda dependendo do seu `status` (estado). Cada `EstadoTarefa` encapsula a lógica de transição e o que pode ser feito naquele estado.
    * **Composite Pattern (Opcional):** Se tarefas pudessem ter subtarefas, o Composite Pattern seria ideal para tratar tarefas individuais e grupos de tarefas uniformemente.
    * **Encapsulamento:** Esconder a complexidade das transições de estado.
    * **Single Responsibility Principle (SRP - SOLID):** O `Projeto` gerencia tarefas e membros; a `Tarefa` gerencia seu próprio estado; cada `Estado` gerencia sua lógica de transição.
* **Desafio Adicional:** Adicione um sistema de "histórico de tarefas" que registra todas as mudanças de status e quem as fez.

---

## 9. Sistema de Votação/Enquetes (Com Votação Anônima)

Crie um sistema onde usuários podem criar enquetes e votar, com a opção de votação anônima.

* **Classes Iniciais:**
    * `OpcaoVoto`: Atributos (`texto`, `contagem_votos`).
    * `Enquete`: Atributos (`titulo`, `opcoes: list[OpcaoVoto]`, `is_anonima: bool`, `votantes: set`). Métodos (`adicionar_opcao()`, `registrar_voto(opcao_selecionada, usuario_id=None)`).
    * `UsuarioVotante`: Atributos (`id_usuario`, `nome`).
    * `SistemaEnquetes`: Atributos (`enquetes: list[Enquete]`). Métodos (`criar_enquete()`, `votar_em_enquete()`).
* **Conceitos POO Avançados/Design Patterns/SOLID:**
    * **Template Method Pattern:** O `registrar_voto` pode ser um template. A parte de "registrar o ID do votante" seria um passo que subclasses de `Enquete` (ou o próprio método, com um if) podem decidir implementar ou não, dependendo se é anônima.
    * **Strategy Pattern (Opcional):** Estratégia de validação de voto (ex: `ValidacaoVotoUnico`, `ValidacaoMultiplosVotos`).
    * **Encapsulamento:** `contagem_votos`, `votantes` (para garantir unicidade).
    * **Validação:** Votar apenas uma vez em enquetes não anônimas, votar em opções válidas.
* **Desafio Adicional:** Implementar um "relatório de resultados" para cada enquete, que pode ser gerado em diferentes formatos (usando conceitos do Projeto 2).

---

## 10. Agente de Automação (Com Componentes Plugáveis)

Desenvolva um agente que pode executar diferentes "ações" e "gatilhos", que podem ser configurados e adicionados dinamicamente.

* **Classes Iniciais:**
    * `Acao` (Classe Base Abstrata): Define método abstrato `executar()`.
    * `AcaoEnviarEmail` (herda de `Acao`): Envia um email.
    * `AcaoSalvarArquivo` (herda de `Acao`): Salva algo em um arquivo.
    * `Gatilho` (Classe Base Abstrata): Define método abstrato `monitorar()` e `disparar_acao(acao)`.
    * `GatilhoTempo` (herda de `Gatilho`): Dispara após um intervalo de tempo.
    * `GatilhoEventoSistema` (herda de `Gatilho`): Dispara em um evento do sistema (simulado).
    * `AgenteAutomacao`: Atributos (`gatilhos_registrados: list`, `acoes_disponiveis: dict`). Métodos (`registrar_gatilho()`, `registrar_acao()`, `rodar_agente()`).
* **Conceitos POO Avançados/Design Patterns/SOLID:**
    * **Strategy Pattern:** O `AgenteAutomacao` usa diferentes `Gatilhos` e `Acoes` como estratégias.
    * **Princípio Aberto/Fechado (OCP - SOLID):** Novos gatilhos e ações podem ser adicionados sem modificar o `AgenteAutomacao`.
    * **Command Pattern (Opcional):** `Acao` pode ser vista como um objeto Comando.
    * **Observer Pattern (Opcional):** Gatilhos podem notificar ações quando disparados.
    * **Dependency Inversion Principle (DIP - SOLID):** O agente depende de abstrações de Gatilho e Ação.
* **Desafio Adicional:** Implementar um "configurador" que permite ao usuário definir novas regras (`Gatilho` -> `Acao`) em tempo de execução, talvez lendo de um arquivo de configuração (JSON/YAML).

---

Lembre-se: A chave para esses projetos é **não focar apenas na funcionalidade final**, mas sim em **como você estrutura o código** para que ele seja **extensível, manutenível e siga os princípios de design**. Explique suas escolhas de design nas descrições do seu portfólio!

Qual desses projetos te parece mais interessante para começar?