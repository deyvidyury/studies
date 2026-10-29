# Licao 08 - I/O robusto e encerramento

**Estado:** [ ]

**Projeto:** endurecer a troca TCP contra escritas parciais, interrupcoes e encerramento do peer.

## Objetivo

Tratar corretamente que uma chamada de escrita pode transferir menos bytes do que solicitado e que leitura/escrita podem ser interrompidas ou falhar.

## Beej

- [5.9 close() and shutdown()](https://beej.us/guide/bgnet/html/split/system-calls-or-bust.html#close-and-shutdownget-outta-my-face)
- [7.4 Handling Partial send()s](https://beej.us/guide/bgnet/html/split/slightly-advanced-techniques.html#sendall)
- [8 Common Questions](https://beej.us/guide/bgnet/html/split/common-questions.html#common-questions)

## Direcoes

1. Crie uma rotina de envio que acompanha quantos bytes foram aceitos e continua ate concluir, encontrar EOF/erro ou ser interrompida.
2. Trate `EINTR` sem descartar bytes ja enviados e diferencie fechamento normal do peer de erro.
3. Compare `shutdown()` e `close()` no ciclo de vida: defina quando encerrar uma direcao de comunicacao e quando liberar o descritor.
4. Aplique a rotina ao eco e depois ao servidor com multiplos clientes. Se usar sockets nao bloqueantes, enfileire bytes pendentes e monitore prontidao de escrita com `poll()`.

## Criterios de aceite

- O codigo nao presume que uma chamada `send()` transmite todo o buffer.
- EOF, interrupcao e erro de socket seguem caminhos distintos e liberam recursos corretamente.
- Um cliente que encerra a escrita nao causa leitura infinita nem queda inesperada do servidor.
- O servidor conserva dados pendentes quando uma escrita nao bloqueante nao termina.

## Dica (somente se pedir ajuda)

Pense no envio como um cursor sobre o buffer: avance somente pela quantidade confirmada pela chamada.
