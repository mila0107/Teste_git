# [Nome Empresa: Clinica de Saúde]
A Clínica de sáude trata de pacientes adulto, fazendo um diagnóstico de diversas doenças que não sejam cirúrgicas, obstétricas e ginecológicas.

## Modelo negócio
A Clínica de Saúde está organizada em duas áreas:
	
	- Consultas
	- Exames

### Subsistema Consultas
Trata-se de uma sala onde o médico examina o paciente, escuta seus sintomas, pede e analisa exames complementares e dá o diagnóstico. Os clientes que queiram utilizar os serviços, têm que marcar consulta.

### Subsistema Exames
Realiza os exames solicitados pelo médico e dá o resultado.

### Secretária
Responsável por marcar consultas e realizar as solicitações de cancelamentos.





### Encomenda
[Ideia do funcionamento da empresa numa determinada área]
O processo pelo qual se satisfaz uma encomenda é semelhante, quer seja efetuada pela Internet ou pela loja.

Os produtos disponíveis são computadores, componentes e periféricos, assim como, smartphones e smartwatches.

Uma encomenda pode conter diferentes produtos em diferentes quantidades. Quando uma encomenda é efetuada e processo é o seguinte:

 1. Na altura em que o cliente faz a encomenda, o sistema coloca-a na lista de encomendas a satisfazer. O seu estado é "Recebida".
 2. Assim que o armazém começa a preencher a encomenda, o seu estado passa a ser "Em processamento".
 3. No momento em que o armazém finaliza a encomenda, esta está pronta para ser entregue. A mesma é enviada por transportadora e o seu estado passa a ser "Enviada".
 4. Quando e encomenda é entregue, é registado no sistema e é encerrado o processo relativo a esta encomenda, estado "Entregue".

## Modelo de Domínio

![Modelo Negócio](imagens/modeloNegocio.png "Modelo de Negócio")

Tendo como base o modelo de negocio da multiCore, foi desenvolvido um sistema de informação composto pelo subsistema Loja e subsistema Internet.
Esta arquitetura foi desenhada com o objetivo de ter uma base informática partilhada entre os subsistemas que permita otimizar o uso de recursos e um acesso à informação disponível mais célere. 
Isto permite uma maior eficácia no atendimento dos clientes e na expedição de encomendas.

### Subsistema Loja
A encomenda na Loja abrange todos os pedidos feitos pelo cliente. Este só tem que se dirigir a um funcionário e fazer o seu pedido. O funcionário verifica se o produto está disponível para venda e caso esteja, satisfaz o pedido. Caso contrário faz uma reserva produto para o cliente. 

### Subsistema Internet
No caso de encomendas pela Internet, o utilizador tem que fazer um pré-registo, no qual indica o nome utilizador, password, nome, morada, telefone e numero de contribuinte. Este registo é validado através de um email que contem um link de confirmação. Após efetuar a confirmação, o utilizador fica registado no sistema e já pode efetuar encomendas. O cliente tem que se autenticar, através do nome de utilizador e password, cada vez que fizer encomendas.


## Modelos da Casos de Uso

### Atores
**Colaborador Secretária**: Funcionário da Clinica de Saúde responsável pelo atendimento ao publico.

**Colaborador Doutor**: Médico examina o paciente, escuta seus sintomas, pede e analisa exames complementares e dá o diagnóstico.

**Paciente**:Pessoa que solicita as consultas.

**Cibernauta**: Todo aquele que, através da Internet, consulta as páginas da multiCore.

**Administrador de Sistemas**: Responsável por toda a gestão do sistema informático.

Além destes atores humanos existem, também, outro tipo de atores que são os subsistemas Loja e Internet.


### Casos de Uso

*Caso de Uso: **Efetuar pré-registo***: 
 
 1. O cibernauta utiliza o sistema de informação da página da Internet da multiCore para efetuar o pré-registo, e solicita a sua validação.
 2. O cibernauta tem que indicar o nome de utilizador, password, nome, morada, telefone e numero de contribuinte.
_Pós-condição:_ É gerado um email com um link para validação da conta.


*Caso de Uso: **Consultar Produtos***:
   
1. O cibernauta, o cliente e o colaborador loja utilizam o sistema de informação para consultar os produtos.
2. O catálogo é apresentado com a seguinte forma: referência, seguida da categoria, do produto e do preço.  


*Caso de Uso: **Atualizar Dados Cliente***:

1. O cliente utiliza o sistema de informação da página da Internet da multiCore para alterar os seus dados.
2. **_Includes_** _Fazer Autenticação_.


*Caso de Uso: **Consultar Encomendas***:

1. O cliente utiliza o sistema de informação da multiCore para consultar o estado da encomenda.
2. **_Includes_** _Fazer Autenticação_.


*Caso de Uso: **Efetuar Encomendas Internet***: 

1. O cliente utiliza o sistema de informação da página da Internet da multiCore para efetuar uma encomenda.
2. **_Includes_** _Fazer Autenticação_.
3. O cliente escolhe os produtos que pretende.
4. Para cada produto escolhido o sistema verifica o seu custo e adiciona-o ao total da encomenda.
5. O pedido é registado no sistema de informação.
6. O colaborador logística recebe o pedido através do sistema de informação processa a encomenda.


*Caso de Uso: **Validar Registo***:

1. O administrador de sistema verifica através do sistema de informação o pré-registo do cibernauta
2. Envia um email com o link de validação da conta.


*Caso de Uso: **Efetuar Encomendas***:

1. O cliente dirige-se ao balcão da loja multiCore para efetuar uma encomenda.
2. O colaborador loja regista e encomenda do cliente no sistema de informação.
3. O cliente escolhe os produtos que deseja.


*Caso de Uso: **Expedição de Encomendas***:

1. O funcionário logística recebe o pedido de encomenda através do sistema de informação.
2. Caso o produto esteja em stock, o funcionário logística processa a encomenda.
3. Caso haja rutura de stock o funcionário logística informa o administrador de sistemas.
4. Por fim, o funcionário logística expede a encomenda.


*Caso de Uso: **Receber Pagamento***:

1. O colaborador loja quando completa a encomenda, recebe o pagamento da mesma.
2. Quando o cliente finaliza a encomenda utilizando o sistema de informação da página da Internet da multiCore, é gerado referencias para pagamento.
3. O cliente faz o pagamento através de uma das modalidades disponíveis: à cobrança, referências multibanco, transferência bancária ou paypal.
4. **_Includes_** _Emitir Fatura_

### Diagramas de Casos de Uso
Diagrama de caso de uso subsistema Loja.

![Subsistema Loja](imagens/subsistemaLoja.png "Casos de Uso Sub Sistema Loja")

Diagrama de caso de uso subsistema Internet.

![Subsistema Internet](imagens/subsistemaInternet.png "Casos de Uso Sub Sistema Internet")

### Diagrama de atividades
[Colocar o diagrama de atividades com o funcionamento geral dos casos de Uso]

### Diagrama de sequência
Diagrama Sequência - Fazer Encomenda Internet

![Diagrama Sequência - Fazer Encomenda Internet](imagens/diagramaSequenciaFazerEncomendaInternet.png "Diagrama Sequência - Fazer Encomenda Internet")

## Modelo de Desenho

### Diagrama de Classes
![Diagrama Classes](imagens/diagramaClasses.png "Diagrama Classes")

### Descrição das Classes

**Cliente**:

Representa um cliente da multiCore que fez o Pré-Registo através da Internet para poder efetuar encomendas através do site. O cliente é caracterizado por único código, nome, morada e numero de contribuinte. Possui um username e um password únicas para efetuar encomenda através da Internet.

**Loja**:

Representa uma loja multiCore. A loja é caracterizada por único código, nome e localização e é constituída por uma área de atendimento ao publico assim como um armazém.

**Funcionário**:

Representa os funcionários que trabalham na multiCore. Estes são caracterizados por numero de identificação, nome e categoria profissional.

**Encomenda**:

Representa uma encomenda efetuada pela Internet ou na loja da multiCore. A encomenda é caracterizada por um numero de encomenda e pelo estado em que se encontra (recebida, expedida ou entregue). A cada encomenda corresponde pelo menos uma fatura.

**detalheEncomenda**:

Representa o código de um produto de uma determinada encomenda. Cada detalheEncomenda é caracterizado por uma quantidade e preço unitário.

**Preço**:

Representa a tabela de preços que um determinado Produto pode assumir. O Preço é caracterizado por tipo, normal ou promoção e valor.

**Fatura**:

Representa uma fatura referente a uma determinada encomenda. É caracterizada por um numero de fatura, data e total.

**itemFatura**:

Representa a referência a um produto de uma determinada fatura, que por sua vez corresponde a um item de
uma determinada encomenda.

**Produto**:

Representa a classe de produtos disponíveis ao clientes da multiCore. Um produto é caracterizado por uma referencia, categoria e descrição.

**Kit**:

É um tipo de produto que é composto por outros produtos. É caracterizado pelo tipo de produto que o compõe assim como o seu tipo.

**Computadores**:

É um tipo de produto e representa a classe dos computadores comercializados na multiCore.

**Armazenamento**:

É um tipo de produto e representa a classe do armazenamento comercializado na multiCore.

**Periféricos**:

É um tipo de produto e representa a classe dos periféricos comercializados na multiCore.

**Imagem**:

É um tipo de produto e representa a classe da imagem comercializados na multiCore.

**Componentes**:

É um tipo de produto e representa a classe dos componentes comercializados na multiCore.

**Mobilidade**

É um tipo de produto e representa a classe da mobilidade comercializados na multiCore.
