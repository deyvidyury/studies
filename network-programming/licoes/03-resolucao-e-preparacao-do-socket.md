# Licao 03 - Resolucao e preparacao do socket

**Estado:** [ ]

**Projeto:** resolvedor de endpoints e preparador de endereco de escuta/conexao.

## Objetivo

Usar resolucao de nomes para preparar enderecos que podem ser IPv4 ou IPv6, sem codificar manualmente estruturas especificas de uma familia.

## Beej

- [5.1 getaddrinfo() - Prepare to launch!](https://beej.us/guide/bgnet/html/split/system-calls-or-bust.html#getaddrinfoprepare-to-launch)
- [5.2 socket() - Get the File Descriptor!](https://beej.us/guide/bgnet/html/split/system-calls-or-bust.html#socket)
- [5.3 bind() - What port am I on?](https://beej.us/guide/bgnet/html/split/system-calls-or-bust.html#bind)

## Direcoes

1. Crie um comando que recebe host e servico (nome ou numero de porta) e enumera os resultados de `getaddrinfo()`.
2. Suporte dois modos: preparar uma escuta local/passiva ou preparar uma conexao a um host.
3. Para cada resultado, tente criar o socket correspondente e apresente o resultado de forma diagnostica; libere a lista de resultados em todos os caminhos.
4. Use uma porta configuravel para o projeto. Mantenha os testes limitados ao proprio ambiente.

## Criterios de aceite

- A resolucao pode retornar mais de um endereco e a aplicacao percorre a lista.
- IPv4/IPv6 e modo passivo/ativo sao definidos por hints, nao por casts improvisados.
- Falhas de resolucao e de criacao de socket sao apresentadas como erros distintos.
- Recursos obtidos durante a resolucao sao liberados mesmo quando uma tentativa falha.

## Dica (somente se pedir ajuda)

Pense no resultado como uma lista de candidatos: a primeira familia/endereco pode nao ser utilizavel no ambiente.
