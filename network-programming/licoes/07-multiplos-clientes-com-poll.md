# Licao 07 - Multiplos clientes com poll

**Estado:** [ ]

**Projeto:** servidor TCP de eco capaz de acompanhar varias conexoes simultaneas.

## Objetivo

Substituir o atendimento sequencial por um loop de eventos com `poll()` e entender a prontidao de leitura/escrita.

## Beej

- [7.1 Blocking](https://beej.us/guide/bgnet/html/split/slightly-advanced-techniques.html#blocking)
- [7.2 poll()](https://beej.us/guide/bgnet/html/split/slightly-advanced-techniques.html#poll)
- [7.3 select()](https://beej.us/guide/bgnet/html/split/slightly-advanced-techniques.html#select)

## Direcoes

1. Mantenha o socket de escuta e os sockets aceitos em uma colecao de descritores acompanhada por `poll()`.
2. Quando a escuta ficar pronta, aceite novos clientes; quando um cliente ficar pronto, leia apenas dele e atualize seu estado.
3. Remova clientes desconectados ou com erro sem invalidar os demais registros do loop.
4. Teste pelo menos tres clientes abertos ao mesmo tempo e confirme que um cliente ocioso nao impede os outros de trocar dados.

## Criterios de aceite

- O servidor mantem pelo menos tres clientes ativos sem criar uma thread por cliente.
- A desconexao de um cliente nao derruba o processo nem os outros clientes.
- O conjunto observado por `poll()` e atualizado quando clientes entram e saem.
- O codigo distingue prontidao, EOF e erro; nao assume que todo evento significa dados validos.

## Limite intencional

Esta etapa pode usar mensagens curtas em loopback. Ainda nao e um servidor resiliente a clientes que leem lentamente; backpressure e escritas parciais sao tratados na proxima etapa.

## Dica (somente se pedir ajuda)

Associe cada posicao da colecao de `pollfd` ao estado do cliente correspondente; quando remover uma entrada, mantenha essa associacao consistente.
