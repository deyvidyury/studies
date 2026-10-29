# Licao 10 - Chat integrado

**Estado:** [ ]

**Projeto:** concluir o chat multiusuario TCP com protocolo e desligamento controlado.

## Objetivo

Integrar sockets, `poll()`, framing, envio robusto, estado por cliente e fan-out de mensagens na camada da aplicacao.

## Beej

- [7.6 Son of Data Encapsulation](https://beej.us/guide/bgnet/html/split/slightly-advanced-techniques.html#sonofdataencap)
- [8 Common Questions](https://beej.us/guide/bgnet/html/split/common-questions.html#common-questions)

## Direcoes

1. Integre listener TCP, loop de `poll()`, parser de frames e fila de saida sem bloquear todos os clientes por causa de um peer lento.
2. Defina mensagens de aplicacao: entrada com apelido, mensagem de chat e saida. Limite tamanho e caracteres permitidos; nao aceite comandos ambiguos.
3. Ao receber uma mensagem valida, distribua-a aos demais clientes conectados pela camada da aplicacao. Isto e fan-out sobre TCP, nao broadcast UDP.
4. Limite o numero de clientes e trate apelido duplicado, cliente que envia frame invalido, desconexao abrupta e fila de saida cheia.
5. Implemente encerramento gracioso do servidor: pare de aceitar, notifique ou encerre clientes conforme o protocolo e libere todos os descritores.

## Criterios de aceite

- Tres ou mais clientes locais podem entrar, conversar e sair sem reiniciar o servidor.
- Cada cliente recebe mensagens completas, identificadas por remetente, e nao recebe a propria mensagem se essa for a regra escolhida.
- Frame malformado, payload acima do limite e apelido invalido nao derrubam o servidor.
- Cliente lento nao bloqueia indefinidamente o processamento de outros clientes; bytes pendentes sao limitados ou conexao e encerrada segundo regra documentada.
- Encerramento normal e desconexao inesperada liberam estado e sockets.
- O estudante explica o formato do protocolo, o ciclo de vida dos sockets e as limitacoes escolhidas.

## Extensoes opcionais

- Adicionar heartbeat/timeout de inatividade ou reconexao do cliente.
- Depois de concluir o chat, implementar um exercicio UDP separado sobre broadcast da secao 7.7. Nao misture broadcast UDP com o fan-out TCP do chat.

## Dica (somente se pedir ajuda)

Desenhe o estado por cliente e as filas de entrada/saida antes de integrar tudo; isso revela quais eventos de `poll()` cada cliente precisa monitorar.
