# Licao 04 - Servidor TCP de eco

**Estado:** [ ]

**Projeto:** servidor TCP sequencial que devolve os bytes recebidos.

## Objetivo

Implementar o ciclo de vida basico do lado servidor: socket, bind, listen, accept, leitura/escrita e fechamento.

## Beej

- [5.2 socket()](https://beej.us/guide/bgnet/html/split/system-calls-or-bust.html#socket)
- [5.3 bind()](https://beej.us/guide/bgnet/html/split/system-calls-or-bust.html#bind)
- [5.5 listen()](https://beej.us/guide/bgnet/html/split/system-calls-or-bust.html#listen)
- [5.6 accept()](https://beej.us/guide/bgnet/html/split/system-calls-or-bust.html#acceptthank-you-for-calling-port-3490.)
- [6.1 A Simple Stream Server](https://beej.us/guide/bgnet/html/split/client-server-background.html#a-simple-stream-server)

## Direcoes

1. Crie um servidor que faz bind somente ao loopback durante o desenvolvimento e usa uma porta configuravel.
2. Aceite uma conexao por vez. Para cada cliente, leia bytes em blocos e devolva os bytes lidos.
3. Trate o retorno de fim de stream como desconexao normal e feche o socket do cliente antes de aceitar o proximo.
4. Registre erros de sistema com contexto suficiente para distinguir falha de bind, listen, accept, leitura e escrita.

## Criterios de aceite

- O servidor inicia, escuta na porta configurada e aceita um cliente local.
- O cliente recebe os mesmos bytes que enviou em uma sessao curta.
- Ao desconectar o cliente, o servidor fecha a conexao e continua aceitando outro.
- O programa libera os sockets mesmo ao encerrar por erro.

## Limite intencional

TCP e fluxo de bytes; cada leitura nao corresponde necessariamente a uma mensagem enviada. O eco desta etapa opera sobre blocos recebidos. Framing e envio parcial robusto entram depois.

## Dica (somente se pedir ajuda)

Separe o socket de escuta, que aceita novas conexoes, do socket retornado para conversar com um cliente.
