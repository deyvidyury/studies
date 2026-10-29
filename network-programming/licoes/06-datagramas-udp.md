# Licao 06 - Datagramas UDP

**Estado:** [ ]

**Projeto:** utilitarios UDP de envio e recepcao de eco.

## Objetivo

Comparar uma troca sem conexao TCP com UDP e preservar os limites de cada datagrama recebido.

## Beej

- [5.8 sendto() and recvfrom()](https://beej.us/guide/bgnet/html/split/system-calls-or-bust.html#sendtorecv)
- [6.3 Datagram Sockets](https://beej.us/guide/bgnet/html/split/client-server-background.html#datagram)

## Direcoes

1. Crie um listener que associa um socket UDP a uma porta local e recebe um datagrama por vez.
2. Registre o endpoint remetente e devolva o datagrama ao endereco de origem.
3. Crie um sender que envia datagramas e mostra as respostas recebidas, com timeout local para que a ausencia de resposta nao bloqueie indefinidamente.
4. Compare a experiencia com TCP: UDP nao cria uma sessao confiavel e nao promete entrega, ordem ou ausencia de duplicatas.

## Criterios de aceite

- Dois processos locais trocam datagramas e o listener responde ao remetente correto.
- Cada datagrama e tratado como unidade, respeitando o tamanho maximo do buffer escolhido.
- A ausencia de resposta termina por timeout ou interrupcao tratada, nao por espera infinita.
- O estudante descreve o que a aplicacao teria de acrescentar se precisasse de confirmacao/retentativa.

## Dica (somente se pedir ajuda)

Em UDP, o endereco do remetente chega junto com o datagrama; nao ha um socket conectado por cliente no modelo basico.
