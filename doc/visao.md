# Documento de visão
# Banco Imobiário
## 0 - Observações
Observações:
- Este é apenas um rascunho e não reflete a versão final dos requisitos levantados.
- Houve também certa confusão ao distinguir requisitos não funcionais, funcionais e regras de negócio.
- Para melhor compreensão,eventuais erros de pt-br **devem ser totalmente ignorados**.
- Trabalhos em grupo me fazem entender o pq do Batman preferir trabalhar sozinho.

## 1. Introdução
### 1.1 Resumo
Por ser uma adaptação do jogo para fins de estudo, algumas características e/ou funções serão abstraídas e outras simplificadas.

Objetivo do jogo: Tornar-se o mais rico jogador, através de compra, aluguel ou venda de propriedades. O jogo termina quando ficar somente um jogador (os outros foram à falência). Somam-se os valores possuídos através das notas, terrenos, propriedades, casas e hotéis. Se algum jogador possuir terreno ou propriedades hipotecadas, ele deverá computar metade do valor pago.

### 1.2 Escopo
Principais responsabilidades e não responsabilidades do sistema.

##### Responsabilidades:
- Permitir a escolha entre 2 a 6 jogadores.
- Permitir a inserção de nicknames por jogador.
- Gerar nickname para um jogador afim de representa-lo dentro do jogo.
- Sortear valores simulando o lançamento de dados.
- Guardar posições dos jogadores.
- Agir como banqueiro.
- Permitir visualizar o tabuleiro por meio de uma aplicação desktop.
- Representar o tabueiro, os jogadores, propriedades por meio de uma aplicação desktop.
- Permitir a escolha de tempo limite ou número de rodadas limites para fim de jogo, ganhando o jogador mais rico.
- Após sorteio, mostrar o avanço do jogador pelo tabuleiro sem que ela saiba o número sorteado até que esteja no fim da jogada.
##### Não-Responsabilidades:
- Garantir a conclusão do jogo.
- Salvar informações após o jogo ser encerrado.
- O não aparecimento de bugs, é sério.
- Ser visualmente bonito.

## 2. Requisitos

### 2.1 Requisitos Funcionais

| Cod. | Nome | Descrição | Categoria |
| -------- | -------- | -------- | -------- |
| F01| Iniciar Jogo| Uma nova partida é iniciada.| Evidente| 
| F02| Definir Participantes | Ao iniciar o jogo, pode-se escolher a quantidade de jogadores respeitando o limite de 2 a 6.| Evidente| 
| F03|  Escolher Nickname | O ator Jogador pode escolher um nickname para representa-ló. |Evidente|
| F04|  Gerar Nickname | O ator Jorgador pode escolher um nickname surido pelo ator Sistema usando uma base de dados com xingamentos, nomes de cantores k-pop e políticos brasileiros |Desejável|
| F05|  Configurar Término | Ao iniciar o jogo pode-se escolher entre terminar após um período de tempo e/ou após um número determinado de jogadas. Ganhando assim o jogador mais rico. Por padrão, o ator Sistema usa o método normal do jogo que ganha o último que restar sem declarar falência.|Desejável| 
| F06|  Sortear Dados | O ator Jogador, em sua vez de jogar, se utiliza do botão "Lançar Dados ao Diabo" para que os números sejam sorteados. |Evidente|
| F07|  Comprar Propriedade | Após o sorteio dos dados, caso caia em uma propriedade, o ator Jogador tem a opção de comprar ela por um valor pré-determinado ao banco.|Evidente| 
| F08|  Vender Propriedade | Além da venda por parte do banco, o ator Jogador também pode negociar com outros jogadores a respeito de suas propriedades. |Evidente|
| F09|  Receber Honorários |  Cada vez que o ator Jogador alcançar o Start Point ou por ele passar, receberá do banqueiro $200 como honorários.  |Evidente|
| F10|  Pagar Imposto | Se o ator Jogador alcançar um terreno ou empresa que já tenha sido adquirido, pagará aluguel ou taxa correspondente, ao respectivo proprietário, conforme os dados constantes do título. O dono do terreno ou propriedade, deverá cobrar antes que o jogador seguinte lance os dados, caso contrário não terá mais direito. |Evidente|
| F11|  Ser Preso |  O ator Jogador é preso se cair no campo "VÁ PARA A PRISÃO" ou se tirar 3 duplas seguidas com os dados. |Evidente|
|F12|Ser Solto| Da prisão o jogador poderá sair se conseguir numa das suas 3 próximas jogadas tirar uma dupla. Se não conseguir na 4$ jogada pagará $50 ao banqueiro e andará o número de pontos conseguidos nos dados. Também poderá sair da prisão se possuir o cartão “SAÍDA LIVRE DA PRISÃO”. |Evidente|
| F13| Construir | Logo que o ator Jogador possua todo um grupo de propriedades da mesma cor, ele poderá construir casas pagando ao Banqueiro os preços indicados nos títulos. Em cada terreno pode-se construir 4 casas e tendo construído 4 casas, no mesmo terreno, pode-se construir nele um hotel. O ator Jogador não pode colocar 3 casas em uma propriedade e nenhuma noutra, do mesmo grupo de cor. Ele deve colocar uma em cada propriedade do mesmo grupo de cor, antes de colocar a segunda e assim sucessivamente até a compra do hotel. |Evidente|
| F14| Negociar Propriedade|  É permitido aos jogadores vender ou trocar terrenos ou empresa entre si, quando acharem conveniente por preços a combinar. No caso de terrenos que possuam casas ou hotel, o dono deverá vendê-las ao Banco pela metade do preço, para depois vender o terreno. Se algum jogador comprar uma propriedade ou terreno hipotecado, ao resgatar o titulo de posse, ele deverá pagar além do valor da hipoteca mais 20% do valor da mesma a “título de juros.|Evidente| 
| F15| Hipotecar| Terrenos sem construção (caso haja casas ou hotel é necessário antes vendê-las ao Banco pela metade do preço) e empresas podem ser hipotecadas pelos valores determinados nos títulos por qualquer período de tempo. |Evidente|
| F16|  Exibir Placar | Ao final do jogo é exibida uma tabela com os jogadores empilhados, sendo o do topo o vencedor e o da base o primeiro a perder.|Desejável| 
|F17|Falir | Se mesmo após vender suas casas e hotéis, hipotecar ou vender suas propriedades o jogador não conseguir pagar suas dívidas ele irá à falência, e se retirará do jogo. O dinheiro conseguido será entregue ao jogador credor. Caso haja propriedades hipotecadas o Banco deverá resgatá-las e o dinheiro conseguido irá para o credor. As propriedades devem ser colocadas em leilão. OBS.: Durante um jogo nenhum jogador poderá dar ou emprestar dinheiro a outro.|Evidente|
| F18|  Quit | O jogo pode ser encerrado a qualquer momento, mas sem salvar qualquer informação. |Evidente|
|F19|Transações| Os pagamentos devem ser efetuados sempre em dinheiro. Se o jogador não tiver dinheiro para pagar ao Banco ou a um jogador, ele deve obedecer esta ordem de negociações:– Vendas de casas e hotéis pela metade do preço pago.– Hipotecar ou vender suas propriedades. No caso de vendas ele poderá colocar em leilão as propriedades visando um lucro maior. Caso ninguém queira comprá-la o Banco pagará seu valor nominal. |Evidente|

### 2.2 Requisitos não funcionais

| Cod. | Nome               | Descrição                                                                                        | Categoria   |
| ---- | --------           | --------                                                                                         | --------    |
| NF01 | PyGame| Trequinho para desenvolvimento de jogos usando a linguagem de programação python.                                         | Desejável |
| NF02 | Python             | Linguagem de programação. | Desejável |
|NF03 | Terror Psicológico | De forma prévia, deve ser feita uma base de frases para nutrir nervosismo nos jogadores prestes a falir. |Desejável|

### 2.3. Atores

| Ator | Descrição |
| -------- | -------- |
| Sistema | Ator que representa o sistema do jogo em si.|  
| Banqueiro | Ator responsável por adminstrar as negociações do jogo, nesse caso atribuído ao ator Sistema. |  
| Jogador | Ator com as funções de negociar de forma geral propriedades, escolher nickname, ganhar, perder.|  
