# Reactive Programming

# O que é?

Programação reativa é um paradigma de programação que é baseado em eventos assíncronos, onde a aplicação reage automaticamente aos eventos gerados e realiza as ações desejadas para o tipo do evento. Uma sequência de eventos é chamado de fluxo de dados, também conhecido como streams, que é gerado por um “produtor” que tem a fonte dos dados.

Os produtores são responsáveis por criar a sequência de eventos de acordo com que acontecem e para que a reação aconteça é criado observadores/assinantes para os eventos, então, quando é produzido um novo evento, os observadores daquele evento são notificados e iniciam a execução da lógica que é de sua responsabilidade. 

## Exemplo

João e Pedro vão assistir a um jogo de futebol. João ficará responsável por contar quantos gols tiveram na partida, independente do time e Pedro ficará responsável por contar a quantidade de cartões amarelos. 

Os 2 começam a observar/assistir o jogo e ficam atentos a cada evento que cabe a eles contar. Quando é marcado um gol o narrador/TV notifica (produz) o evento “gol” e então João reage ao evento incrementando a contagem de gols. Quando é aplicado um cartão amarelo a algum jogador o narrador/TV notifica (produz) o evento “cartão amarelo” e então Pedro reage ao evento incrementando a contagem de cartões amarelos.