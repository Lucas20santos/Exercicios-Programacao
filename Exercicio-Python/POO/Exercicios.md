# Exercicicios de POO direcionado para linguagem pyhthon

## 100 Exercícios de POO em Python: Do Básico ao SOLID

### Parte 1: Fundamentos de POO (30 Exercícios)

#### Nível Básico: Classes, Objetos, Atributos e Métodos

#### Nível Intermediário: Herança, Encapsulamento, Polimorfismo

1. **Classe Abstrata (ABC):**
    * Crie uma classe base abstrata `Animal` com um método abstrato `emitir_som()`.
    * Crie classes concretas `Cachorro` e `Gato` que herdam de `Animal` e implementam `emitir_som()`.
1. **Herança e Composição:**
    * Considere um `Motor` como uma classe separada.
    * A classe `Carro` agora **tem um** `Motor` (composição), em vez de herdar dele.

1. **Polimorfismo com Composição:**
    * Crie diferentes tipos de `Motor` (ex: `MotorCombustao`, `MotorEletrico`) que herdem de uma classe base `Motor`.
    * A classe `Carro` agora pode aceitar qualquer tipo de `Motor` e chamar um método como `motor.ligar()` polimorficamente.

1. **Sobrecarga de Operadores (`__add__`, etc. - Básico):**
    * Na classe `Retangulo`, defina o método `__add__` para que a soma de dois retângulos retorne um novo retângulo com a soma das áreas (ou outra lógica simples).

1. **Métodos Mágicos (`__str__`, `__repr__`):**
    * Para as classes `Pessoa` e `Carro`, implemente os métodos `__str__` e `__repr__` para fornecer representações de string úteis.

1. **Comparação de Objetos (`__eq__`):**
    * Na classe `Carro`, implemente `__eq__` para que dois carros sejam considerados iguais se tiverem a mesma marca e modelo.

1. **Exceções Personalizadas:**
    * Na classe `ContaBancaria`, crie uma exceção personalizada `SaldoInsuficienteError` e lance-a quando o saque não for possível.

1. **Classe `Produto`:**
    * Crie uma classe `Produto` com `nome`, `preco` e `quantidade_estoque`.
    * Adicione métodos para `vender(qtd)` e `repor(qtd)`.
    * Implemente `@property` para `preco` (não pode ser negativo) e `quantidade_estoque` (não pode ser negativo).

1. **Classe `Pedido` (Composição):**
    * Crie uma classe `Pedido` que **contém** uma lista de `Produto`s e suas quantidades.
    * Adicione um método `adicionar_item(produto, quantidade)` e `calcular_total()`.

1. **Mixins (Conceito):**
    * Crie um mixin `Logavel` com um método `logar_evento(mensagem)`.
    * Aplique este mixin a classes como `ContaBancaria` para adicionar funcionalidade de log.

1. **Classe `Data`:**
    * Crie uma classe `Data` com `dia`, `mes`, `ano`.
    * Implemente `__str__` para formatar como "DD/MM/AAAA".
    * Valide a data no construtor (ex: mês entre 1 e 12).

1. **Context Manager (`__enter__`, `__exit__`):**
    * Crie uma classe `GerenciadorArquivo` que abra um arquivo no `__enter__` e o feche no `__exit__`.
    * Use com a instrução `with`.

1. **Classe `Robo`:**
    * Crie uma classe `Robo` com `nome` e `bateria` (0-100%).
    * Métodos: `mover()`, `carregar()`.
    * Adicione um `__str__` para mostrar o status do robô.
    * Implemente `@property` e `@bateria.setter` para validar a porcentagem da bateria.

---

### Parte 2: Design Patterns e Princípios SOLID (70 Exercícios)

---

#### Princípio da Responsabilidade Única (SRP) - 10 Exercícios

* **Conceito:** Uma classe deve ter apenas uma razão para mudar.

1. **Refatorar `ContaBancaria` (SRP):**
    * Separe a lógica de validação de saldo (ex: em uma classe `ValidadorConta`).
    * Separe a lógica de log (ex: em uma classe `Logger`).

2. **`ProcessadorDePedidos` (SRP):**
    * Crie uma classe `Pedido`.
    * Crie uma classe `ProcessadorDePedidos` que tem a responsabilidade única de processar (alterar status, enviar notificação).
    * Separe a `GeradorDeRelatoriosDePedidos`.

3. **`AutenticadorDeUsuario` (SRP):**
    * Crie uma classe `Usuario` com dados.
    * Crie uma classe `AutenticadorDeUsuario` que tem a única responsabilidade de verificar credenciais.
    * Separe a `PersistenciaDeUsuario`.

4. **`GeradorDeRelatorios` (SRP):**
    * Uma classe `DadosVendas` que apenas armazena dados.
    * Uma classe `GeradorDeRelatoriosCSV` que gera o relatório em CSV.
    * Uma classe `GeradorDeRelatoriosPDF` que gera o relatório em PDF.

5. **`Notificador` (SRP):**
    * Crie uma classe `NotificadorEmail` e uma `NotificadorSMS`.
    * Cada uma tem uma única responsabilidade de enviar um tipo de notificação.

6. **`ConversorDeMoeda` (SRP):**
    * Uma classe `Valor` que armazena um número e uma moeda.
    * Uma classe `ConversorDeMoeda` que tem a única responsabilidade de converter entre moedas.

7. **`ValidadorDeCPF` (SRP):**
    * Crie uma classe `Cliente` com dados.
    * Crie uma classe `ValidadorDeCPF` que tem a única responsabilidade de validar um CPF.

8. **`ManipuladorDeArquivos` (SRP):**
    * Uma classe `LeitorDeArquivo` (lê conteúdo).
    * Uma classe `EscritorDeArquivo` (escreve conteúdo).

9. **`CalculadoraDeImpostos` (SRP):**
    * Uma classe `Produto` com preço.
    * Uma classe `CalculadoraDeImpostos` que tem a única responsabilidade de calcular impostos sobre um produto.

10. **`ImpressorDeDados` (SRP):**
    * Uma classe `DadosCliente` que armazena informações.
    * Uma classe `ImpressorDeDados` que formata e imprime os dados.

---

#### Princípio Aberto/Fechado (OCP) - 10 Exercícios

* **Conceito:** Entidades de software (classes, módulos, funções, etc.) devem ser abertas para extensão, mas fechadas para modificação.

1. **Sistema de Descontos (OCP):**
    * Crie uma classe `CalculadorDesconto`.
    * Inicialmente, implemente um desconto fixo.
    * **Estenda** o sistema para adicionar novos tipos de desconto (ex: `DescontoVIP`, `DescontoPorQuantidade`) **sem modificar** `CalculadorDesconto`. Use herança ou estratégias.

2. **Formatador de Relatórios (OCP):**
    * Classe base `FormatadorRelatorio`.
    * Estenda para `FormatadorHTML`, `FormatadorCSV`, `FormatadorPDF` sem modificar a classe base `FormatadorRelatorio`.

3. **Formas Geométricas (OCP):**
    * Classe base `Forma` com método `calcular_area()`.
    * Estenda para `Circulo`, `Quadrado`, `Triangulo`. Adicione uma nova forma sem modificar a classe base ou as existentes.

4. **Processador de Pagamentos (OCP):**
    * Classe base `ProcessadorPagamento`.
    * Estenda para `ProcessadorCartaoCredito`, `ProcessadorPayPal`, `ProcessadorBoleto`. Adicione um novo tipo de pagamento sem modificar os existentes.

5. **Notificador de Eventos (OCP):**
    * Classe base `Notificador`.
    * Estenda para `EmailNotificador`, `SMSNotificador`, `PushNotificador`. Adicione um novo canal de notificação sem alterar o código existente.

6. **Filtro de Produtos (OCP):**
    * Classe `Produto` com atributos.
    * Classe `FiltroProdutos` que filtra por um critério.
    * **Estenda** o `FiltroProdutos` para permitir filtragem por múltiplos critérios (ex: por cor, por tamanho) **sem modificar** a classe principal do filtro.

7. **Validador de Entrada (OCP):**
    * Classe base `Validador`.
    * Estenda para `ValidadorEmail`, `ValidadorSenhaForte`. Adicione um novo validador (ex: `ValidadorCPF`) sem modificar o validador base ou os existentes.

8. **Sistema de Envio (OCP):**
    * Classe base `Transportadora`.
    * Estenda para `Correios`, `FedEx`, `DHL`. Adicione uma nova transportadora sem modificar o código existente.

9. **Processador de Ordens (OCP):**
    * Classe `Ordem`.
    * Classe base `ProcessadorOrdem`.
    * Estenda para `ProcessadorOrdemNormal`, `ProcessadorOrdemExpressa`. Adicione um novo tipo de processamento de ordem.

10. **Estratégia de Log (OCP):**
    * Classe `Logger` com uma estratégia de log.
    * Crie classes de estratégia `LogConsole`, `LogArquivo`, `LogDatabase`. Mude a estratégia sem modificar o `Logger`.

---

#### Princípio da Substituição de Liskov (LSP) - 10 Exercícios

* **Conceito:** Se S é um subtipo de T, então os objetos do tipo T em um programa podem ser substituídos por objetos do tipo S sem alterar as propriedades desejáveis do programa.

1. **Veículos (LSP):**
    * Classe base `Veiculo` com método `ligar_motor()` e `acelerar()`.
    * Crie `Carro` e `Bicicleta` (ou `CarroEletrico`).
    * **Desafio:** `Bicicleta` não tem motor para ligar. Como você modelaria para respeitar LSP? (Dica: talvez `Veiculo` não deva ter `ligar_motor()` ou tenha uma implementação padrão que faça sentido para todos).

2. **Pássaros (LSP):**
    * Classe base `Pássaro` com método `voar()`.
    * Crie `Pardal` e `Pinguim`.
    * **Desafio:** Pinguins não voam. Como modelar para LSP? (Dica: `voar()` não deve estar na classe base se nem todo pássaro voa).

3. **Formas Geométricas para Desenho (LSP):**
    * Classe base `FormaGeometrica` com método `desenhar()`.
    * Crie `Retangulo` e `Quadrado`.
    * **Desafio:** Se `Quadrado` herda de `Retangulo`, alterar a largura de um quadrado também altera a altura. Isso viola LSP se o cliente espera que `Retangulo` permita largura e altura independentes. (Dica: Composição ou um `Quadrado` não deve herdar de `Retangulo` diretamente).

4. **Contas Bancárias (LSP):**
    * Classe base `Conta` com `sacar(valor)`.
    * Crie `ContaCorrente` e `ContaPoupanca`. Ambas devem permitir saque de forma consistente.
    * **Desafio:** Se você tiver `ContaInvestimento` que não permite saque, como modelar? (Dica: Refatorar a hierarquia ou o método `sacar()` para retornar um status/erro).

5. **Armas (LSP):**
    * Classe base `Arma` com `atirar()`.
    * Crie `Pistola` e `Faca`.
    * **Desafio:** Uma faca não "atira". Como modelar?

6. **Coleções (LSP):**
    * Classe base `Colecao` com `adicionar(item)` e `remover(item)`.
    * Crie `Lista` e `Conjunto`.
    * **Desafio:** Garantir que o comportamento de adicionar/remover seja consistente, mesmo que `Conjunto` não permita duplicatas.

7. **Leitores de Dados (LSP):**
    * Classe base `LeitorDeDados` com `ler()`.
    * Crie `LeitorCSV`, `LeitorJSON`.
    * Garanta que `ler()` retorne dados de forma consistente (ex: lista de dicionários).

8. **Processadores de Texto (LSP):**
    * Classe base `ProcessadorTexto` com `processar(texto)`.
    * Crie `ProcessadorMaiusculas`, `ProcessadorLimparEspacos`.
    * Ambos devem aceitar e retornar strings processadas.

9. **Notificadores (LSP):**
    * Classe base `Notificador` com `enviar_mensagem(destinatario, mensagem)`.
    * Crie `NotificadorEmail` e `NotificadorSMS`.
    * Garanta que a interface `enviar_mensagem` funcione para ambos os tipos, mesmo que a implementação interna seja diferente.

10. **Dispositivos de Impressão (LSP):**
    * Classe base `Impressora` com `imprimir_documento(doc)`.
    * Crie `ImpressoraLaser` e `ImpressoraJatoTinta`.
    * Ambas devem ser substituíveis onde um `Impressora` é esperado.

---

#### Princípio da Segregação de Interfaces (ISP) - 10 Exercícios

* **Conceito:** Clientes não devem ser forçados a depender de interfaces que não utilizam.

1. **Trabalhadores (ISP):**
    * Em vez de uma interface única `Trabalhador` com `trabalhar()`, `comer()`, `dormir()`, `gerenciar()`.
    * Crie interfaces menores: `Trabalhavel`, `Comivel`, `Dormivel`, `Gerenciavel`.
    * Crie classes como `Programador`, `GerenteDeProjeto`, `Estagiário` implementando apenas as interfaces que precisam.

2. **Máquinas Multifuncionais (ISP):**
    * Em vez de uma interface `MaquinaMultifuncional` com `imprimir()`, `escanear()`, `fax()`.
    * Crie interfaces `Impressora`, `Scanner`, `FaxMachine`.
    * Crie classes que implementam apenas as capacidades que possuem.

3. **Sistema de Pagamento (ISP):**
    * Em vez de uma interface `ProcessadorPagamento` com `processar_cartao()`, `processar_boleto()`, `processar_pix()`.
    * Crie interfaces como `PagamentoCartao`, `PagamentoBoleto`, `PagamentoPix`.
    * Implemente em classes concretas conforme a necessidade.

4. **Leitor de Mídia (ISP):**
    * Em vez de uma interface `LeitorMidia` com `tocar_audio()`, `tocar_video()`, `mostrar_imagem()`.
    * Crie interfaces `AudioPlayer`, `VideoPlayer`, `ImageDisplayer`.
    * Crie classes que implementam apenas o que precisam.

5. **Veículos (ISP):**
    * Em vez de uma interface `Veiculo` com `voar()`, `nadar()`, `andar()`.
    * Crie interfaces `Voavel`, `Nadavel`, `Andavel`.
    * Crie classes como `Avião`, `Submarino`, `Carro` implementando as interfaces apropriadas.

6. **Persistência de Dados (ISP):**
    * Em vez de uma interface `RepositorioGenerico` com `salvar()`, `buscar()`, `deletar()`, `validar()`, `auditar()`.
    * Crie interfaces menores como `RepositorioCrud`, `Validavel`, `Auditor`.

7. **Serviços de Mensagens (ISP):**
    * Em vez de uma interface `ServicoMensagem` com `enviar_sms()`, `enviar_email()`, `enviar_notificacao_push()`.
    * Crie interfaces específicas como `ServicoSMS`, `ServicoEmail`, `ServicoPush`.

8. **Controle de Acesso (ISP):**
    * Em vez de uma interface `GerenciadorPermissoes` com `pode_editar_documento()`, `pode_ver_relatorio_financeiro()`, `pode_deletar_usuario()`.
    * Crie interfaces granulares como `EditorDocumento`, `VisualizadorFinanceiro`, `AdministradorUsuario`.

9. **Impressoras (ISP):**
    * Em vez de uma interface `ImpressoraCompleta` com `imprimirColorido()`, `imprimirPretoBranco()`, `escanearDocumento()`, `fazerCopia()`.
    * Crie interfaces mais focadas para cada funcionalidade.

10. **Sensores (ISP):**
    * Em vez de uma interface `Sensor` com `lerTemperatura()`, `lerUmidade()`, `lerPressao()`.
    * Crie interfaces `SensorTemperatura`, `SensorUmidade`, `SensorPressao`.

---

#### Princípio da Inversão de Dependência (DIP) - 10 Exercícios

* **Conceito:**
    1. Módulos de alto nível não devem depender de módulos de baixo nível. Ambos devem depender de abstrações.
    2. Abstrações não devem depender de detalhes. Detalhes devem depender de abstrações.

1. **Notificador Flexível (DIP):**
    * Crie uma abstração (`interface`/ABC) `INotificador`.
    * Crie classes de baixo nível `EmailNotificador` e `SMSNotificador` que implementem `INotificador`.
    * Crie uma classe de alto nível `ServicoDePedidos` que **dependa de `INotificador`**, e não de `EmailNotificador` ou `SMSNotificador` diretamente.

2. **Banco de Dados Flexível (DIP):**
    * Crie uma abstração `IRepositorioUsuario`.
    * Crie implementações `MongoDBRepositorioUsuario` e `SQLRepositorioUsuario`.
    * Uma classe de alto nível `ServicoDeUsuario` deve depender de `IRepositorioUsuario`.

3. **Leitor de Configuração (DIP):**
    * Crie uma abstração `ILeitorConfiguracao`.
    * Crie implementações `JsonConfigReader`, `XmlConfigReader`.
    * Uma classe de alto nível `Aplicacao` deve depender de `ILeitorConfiguracao`.

4. **Processador de Imagem (DIP):**
    * Crie uma abstração `IProcessadorImagem`.
    * Crie implementações `ProcessadorPNG`, `ProcessadorJPEG`.
    * Uma classe de alto nível `EditorDeFotos` deve depender de `IProcessadorImagem`.

5. **Autenticação Flexível (DIP):**
    * Crie uma abstração `IProvedorAutenticacao`.
    * Crie implementações `ProvedorAutenticacaoDatabase`, `ProvedorAutenticacaoOAuth`.
    * Uma classe de alto nível `SistemaLogin` deve depender de `IProvedorAutenticacao`.

6. **Gerador de Relatórios (DIP):**
    * Crie uma abstração `IGeradorRelatorio`.
    * Crie implementações `GeradorRelatorioCSV`, `GeradorRelatorioPDF`.
    * Uma classe de alto nível `ModuloAnalitico` deve depender de `IGeradorRelatorio`.

7. **Serviço de Pagamento (DIP):**
    * Crie uma abstração `IProcessadorPagamento`.
    * Crie implementações `GatewayCartaoCredito`, `GatewayPayPal`.
    * Uma classe de alto nível `CarrinhoDeCompras` deve depender de `IProcessadorPagamento`.

8. **Gerenciador de Eventos (DIP):**
    * Crie uma abstração `IObservadorEvento`.
    * Crie implementações `EmailObservador`, `LogObservador`.
    * Uma classe de alto nível `GerenciadorDeEventos` (o "Subject") deve notificar `IObservadorEvento`.

9. **Leitor de Mensagens (DIP):**
    * Crie uma abstração `ILeitorMensagem`.
    * Crie implementações `LeitorMensagemFila`, `LeitorMensagemHTTP`.
    * Uma classe de alto nível `ConsumidorDeMensagens` deve depender de `ILeitorMensagem`.

10. **Dispositivo de Saída (DIP):**
    * Crie uma abstração `IDispositivoSaida`.
    * Crie implementações `Impressora`, `Monitor`.
    * Uma classe de alto nível `RenderizadorDeDocumento` deve depender de `IDispositivoSaida`.

---

#### Padrões de Projeto (Design Patterns) - 20 Exercícios

* **Aplicar diferentes Design Patterns em cenários específicos.**

1. **Singleton Pattern:**
    * Implemente um `Logger` usando o padrão Singleton para garantir que haja apenas uma instância do logger no sistema.

2. **Factory Method Pattern:**
    * Crie uma `FabricaDeVeiculos` com um método de fábrica que cria diferentes tipos de veículos (`Carro`, `Moto`, `Caminhao`) com base em um parâmetro.

3. **Abstract Factory Pattern:**
    * Estenda o exercício anterior. Crie `FabricaVeiculosEletricos` e `FabricaVeiculosCombustao`, cada uma criando um conjunto de produtos relacionados (ex: `CarroEletrico`, `MotoEletrica`).

4. **Builder Pattern:**
    * Crie um construtor (`Builder`) para um objeto `RelatorioComplexo` que tem muitos atributos opcionais e encadeáveis.

5. **Prototype Pattern:**
    * Crie uma classe `Configuracao` e use o padrão Prototype para criar cópias de configurações existentes, modificando apenas o necessário.

6. **Adapter Pattern:**
    * Imagine que você tem uma API legada para `ProcessadorPagamentoAntigo`.
    * Crie um `ProcessadorPagamentoNovo` que usa o `ProcessadorPagamentoAntigo` através de um adaptador para se encaixar em uma nova interface `IProcessadorPagamento`.

7. **Bridge Pattern:**
    * Crie uma abstração de `DispositivoRemoto` (interface) e uma implementação (`TVRemota`, `RadioRemoto`).
    * Crie uma abstração de `ControleRemoto` e suas implementações (`ControleBasico`, `ControleAvancado`). Use Bridge para conectar os controles aos dispositivos.

8. **Composite Pattern:**
    * Crie um sistema de arquivos (`Arquivo` e `Pasta`) onde tanto arquivos quanto pastas podem ser tratados de forma uniforme (ex: `obter_tamanho()`).

9. **Decorator Pattern:**
    * Crie uma classe `Cafe` básica.
    * Use decoradores para adicionar funcionalidades a um café (ex: `ComLeite`, `ComAcucar`, `ComChantilly`) sem modificar a classe `Cafe`.

10. **Facade Pattern:**
    * Crie um sistema complexo de compra online (com subsistemas de `Estoque`, `Pagamento`, `Envio`).
    * Implemente uma `FacadeDeCompra` que simplifica a interface para o cliente.

11. **Flyweight Pattern (Desafio):**
    * Crie um editor de texto onde caracteres idênticos (com a mesma fonte, cor, tamanho) compartilham um objeto `CaracterFlyweight` para economizar memória.

12. **Proxy Pattern:**
    * Crie um `ServicoDeRede` (simule um serviço que faz requisições lentas).
    * Implemente um `ProxyDeServicoDeRede` que adicione cache para o `ServicoDeRede`.

13. **Chain of Responsibility Pattern:**
    * Implemente um sistema de aprovação de despesas onde as solicitações passam por uma cadeia de aprovadores (ex: `Gerente`, `Diretor`, `CEO`), e cada um aprova se a despesa estiver dentro de seu limite.

14. **Command Pattern:**
    * Crie um "controle remoto" que pode executar diferentes comandos (ex: `LigarTVCommand`, `AumentarVolumeCommand`). Permita "desfazer" operações.

15. **Interpreter Pattern (Desafio):**
    * Implemente um interpretador simples para expressões matemáticas básicas (ex: "2 + 3 *5").

16. **Iterator Pattern:**
    * Crie uma coleção personalizada (ex: `MinhaListaOrdenada`) e implemente um iterador para ela, permitindo percorrê-la usando um `for` loop.

17. **Mediator Pattern:**
    * Crie um sistema de chat onde diferentes `UsuarioChat`s se comunicam através de um `MediadorChat`, sem se conhecerem diretamente.

18. **Memento Pattern:**
    * Crie uma classe `EditorTexto` que permita salvar e restaurar o estado atual do texto.

19. **Observer Pattern:**
    * Implemente um sistema de newsletter onde `Assinante`s são notificados quando um novo `Artigo` é publicado por um `Jornalista` (o Subject).

20. **State Pattern:**
    * Crie uma classe `MaquinaDeVendas` com diferentes estados (ex: `SemMoeda`, `TemMoeda`, `ProdutoVendido`). O comportamento da máquina muda dependendo do estado.

---

Este conjunto de exercícios deve proporcionar uma jornada completa pelo universo da POO em Python, desde os fundamentos até a aplicação de princípios de design robustos. Comece pelos mais simples e avance gradualmente. Se tiver dúvidas ou quiser que eu avalie suas soluções, é só chamar!
