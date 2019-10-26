UCXX - Nome do Caso de Uso

Descrição:
Caso um jogador (ator primário) caia em uma propriedade que seja de outro, o mesmo terá que pagar uma taxa correspondente ao valor do aluguel da propriedade para o proprietário dela.

Ator Primário: 
Jogador da vez.

Ator Secundário:
Dono da propriedade.

Pré-condições:

O jogador caiu numa propriedade que já tenha sido adquirida.
A propriedade não está hipotecada.

Pós-Condições:

Foi subtraído da conta do jogador o valor do aluguel.
Foi somado o valor do aluguel para o proprietário.

Fluxo de Básico:

1. Durante a rodada o jogador cai na propriedade de um jogador;
2. O sistema subtrai da conta do jogador o valor do aluguel;
3. O sistema soma o valor do aluguel ao dono da propriedade;
4. O sistema notifica a alteração dos valores das contas;
5. O case de uso é encerrado.

Fluxos Alternativo: 

2A) O jogador não tem dinheiro suficiente para pagar o aluguel

1. O sistema notifica que o ator primário não tem dinheiro suficiente para pagar o aluguel;
2. O sistema seleciona propriedades do ator primário. A soma dos valores das propriedades deve ser maior ou igual ao valor do aluguel;
3. O sistema vende essa propriedade;
4. Uma notificação mostrando os valores da conta é mostrada;


