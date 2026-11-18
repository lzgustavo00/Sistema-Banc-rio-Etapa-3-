Banco Digital – Sistema de Gestão de Contas Bancárias

Projeto desenvolvido em C++ para implementar um sistema de cadastro e movimentação de contas bancárias, permitindo registrar clientes, consultar contas, realizar operações financeiras e acompanhar o histórico de movimentações.

Nesta terceira etapa, o sistema foi aprimorado com a utilização de arquivos de texto, possibilitando armazenar permanentemente os dados das contas e das movimentações, mesmo após o encerramento do programa.

Objetivo

O projeto foi desenvolvido para realizar as seguintes atividades:

1. Cadastrar e organizar diferentes contas bancárias.
2. Realizar operações de depósito, saque e transferência entre contas.
3. Registrar e consultar o histórico de movimentações.
4. Armazenar os dados em arquivos para preservar as informações entre diferentes execuções do programa.
5. Recuperar automaticamente as contas e movimentações ao iniciar o sistema.

Funcionalidades

1. Cadastrar contas bancárias

O programa permite abrir novas contas e armazenar informações dos clientes, como:

* Número da conta, gerado automaticamente a partir de 1001;
* Nome do titular;
* CPF;
* Modalidade da conta (Corrente ou Poupança);
* Saldo inicial;
* Situação da conta.

O sistema permite cadastrar até 100 contas.

Após o cadastro, as informações são automaticamente gravadas no arquivo contas.txt.

2. Listar e pesquisar contas

O programa permite visualizar todas as contas cadastradas ou pesquisar uma conta pelo número.

Na consulta são apresentadas informações como:

* Número da conta;
* Nome do titular;
* CPF;
* Modalidade da conta;
* Saldo disponível;
* Situação da conta.

Os dados são recuperados automaticamente do arquivo quando o programa é iniciado.

3. Realizar depósitos e saques

O sistema permite adicionar ou retirar valores das contas cadastradas.

Para realizar essas operações, são verificadas as seguintes condições:

* A conta informada precisa existir e estar ativa;
* O valor da operação deve ser maior que zero;
* Para saques, é necessário possuir saldo suficiente;
* Deve existir espaço disponível no histórico de movimentações.

Os depósitos são registrados com o código D, enquanto os saques utilizam o código S.

Após cada operação, o saldo da conta e o histórico de movimentações são atualizados nos respectivos arquivos.

4. Realizar transferências

O programa permite transferir valores entre duas contas diferentes.

Antes de concluir a operação, o sistema verifica:

* Se as duas contas foram encontradas;
* Se ambas estão ativas;
* Se a conta de origem é diferente da conta de destino;
* Se o valor informado é positivo;
* Se existe saldo suficiente na conta de origem;
* Se há espaço para registrar as duas movimentações.

Cada transferência gera dois registros no histórico:

* S: saída do valor na conta de origem;
* D: entrada do valor na conta de destino.

Os saldos das duas contas e os respectivos registros são atualizados nos arquivos, garantindo a persistência da transferência.

5. Consultar extrato

O sistema permite consultar as movimentações de uma conta específica, apresentando:

* Créditos e depósitos recebidos;
* Débitos e saques realizados;
* Total de créditos;
* Total de débitos;
* Saldo disponível.

O extrato percorre o histórico de movimentações e apresenta somente os lançamentos pertencentes à conta consultada.

As movimentações realizadas anteriormente também são recuperadas do arquivo, permitindo consultar o histórico completo após reiniciar o programa.

6. Armazenamento permanente dos dados

Nesta etapa, o sistema passou a utilizar arquivos de texto para armazenar as informações das contas e das movimentações.

São utilizados dois arquivos:

contas.txt

Armazena os dados de todas as contas cadastradas, incluindo:

* Número da conta;
* Nome do cliente;
* CPF;
* Tipo da conta;
* Saldo;
* Situação da conta.

Exemplo de registro:

1001;Ana Silva;12345678900;1;700.00;1
1002;Bruno Souza;98765432100;2;800.00;1

movimentacoes.txt

Armazena o histórico de todas as movimentações realizadas, incluindo:

* Número da conta;
* Tipo da movimentação;
* Valor da movimentação.

Exemplo de registro:

1001;D;500.00
1001;S;300.00
1002;D;300.00

Os campos dos arquivos são separados por ponto e vírgula (;).

7. Carregamento e salvamento automático

Ao iniciar o programa, o sistema verifica a existência dos arquivos e recupera os dados armazenados, carregando as informações nos arrays utilizados pelo sistema.

Para isso, foram implementadas funções específicas:

* carregarContas(): realiza a leitura e recuperação das contas cadastradas;
* salvarContas(): grava os dados atualizados das contas no arquivo;
* carregarMovimentacoes(): recupera o histórico de movimentações;
* salvarMovimentacoes(): grava o histórico atualizado no arquivo.

O salvamento ocorre automaticamente após o cadastro de uma conta, depósito, saque ou transferência.

Dessa forma, as informações permanecem armazenadas mesmo depois que o programa é encerrado, podendo ser recuperadas na próxima execução.

Tecnologias utilizadas

* C++;
* Arrays (vetores paralelos);
* Funções;
* Estruturas condicionais (if, else e switch);
* Estruturas de repetição (for e do while);
* Manipulação de arquivos com a biblioteca fstream;
* ofstream para gravação de dados;
* ifstream para leitura de dados;
* is_open() para verificar a abertura dos arquivos;
* getline() para leitura de linhas;
* close() para fechamento dos arquivos;
* stringstream para separação e interpretação dos dados.

Instalação

Primeiro, clone o repositório:

git clone https://github.com/USUARIO/REPOSITORIO.git

Entre na pasta do projeto:

cd REPOSITORIO

Compilação e execução

Com o compilador G++ instalado, compile o programa:

Windows

g++ -std=c++17 -Wall -Wextra -pedantic BancoDigital.cpp -o BancoDigital.exe

Execute o programa:

BancoDigital.exe

Linux

g++ -std=c++17 -Wall -Wextra -pedantic BancoDigital.cpp -o BancoDigital
./BancoDigital

Estrutura do projeto

* BancoDigital.cpp – código-fonte do sistema bancário;
* README.md – documentação do projeto e instruções de instalação e execução;
* contas.txt – arquivo responsável pelo armazenamento permanente dos dados das contas;
* movimentacoes.txt – arquivo responsável pelo armazenamento permanente do histórico de movimentações.

Os arquivos .txt são criados automaticamente pelo programa quando ocorre o primeiro salvamento. Eles devem permanecer na pasta de execução para que os dados possam ser recuperados corretamente.

Considerações finais

O projeto foi desenvolvido como parte da Etapa 3 do trabalho da disciplina INF101 – Programação de Computadores I.

Nesta etapa, o sistema bancário foi aprimorado com a implementação da manipulação de arquivos em C++, permitindo armazenar e recuperar permanentemente os dados das contas e o histórico de movimentações.

A implementação mantém as funcionalidades desenvolvidas nas etapas anteriores e acrescenta a persistência das informações, garantindo que os dados cadastrados e as operações realizadas não sejam perdidos após o encerramento do programa.
