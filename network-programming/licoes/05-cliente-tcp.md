# Licao 05 - Cliente TCP

**Estado:** [ ]

**Projeto:** cliente de linha de comando para o servidor de eco.

## Objetivo

Completar o primeiro ciclo cliente-servidor TCP e observar o estabelecimento e o encerramento da conexao.

## Beej

- [5.4 connect()](https://beej.us/guide/bgnet/html/split/system-calls-or-bust.html#connect)
- [5.7 send() and recv()](https://beej.us/guide/bgnet/html/split/system-calls-or-bust.html#sendrecv)
- [6.2 A Simple Stream Client](https://beej.us/guide/bgnet/html/split/client-server-background.html#a-simple-stream-client)

## Direcoes

1. Receba host e porta pela linha de comando e resolva os candidatos para conexao.
2. Tente conectar aos candidatos ate obter uma conexao ou esgotar as opcoes.
3. Envie dados digitados pelo usuario e apresente os bytes recebidos do eco; mantenha o teste simples e documente que TCP nao preserva fronteiras de escrita.
4. Permita encerrar pelo EOF da entrada ou por um comando local, fechando a conexao de forma previsivel.

## Criterios de aceite

- O cliente conecta ao servidor local e troca dados em ambas as direcoes.
- Host inexistente, porta invalida e servidor indisponivel produzem erros compreensiveis.
- O cliente fecha o socket em saida normal e apos falha.
- Um teste com dois clientes sequenciais confirma o limite conhecido do servidor desta etapa.

## Dica (somente se pedir ajuda)

O cliente e o servidor fazem operacoes complementares: o cliente nao escolhe a porta local de escuta do servidor.
