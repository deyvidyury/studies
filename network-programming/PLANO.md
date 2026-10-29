# Trilha: Network Programming

## O que vamos construir

Um chat TCP multiusuario em C, evoluido em incrementos pequenos: primeiro os fundamentos e a resolucao de enderecos, depois servidor e cliente de eco, suporte a UDP, atendimento de varios clientes, envio robusto, enquadramento de mensagens e, por fim, conversa com apelidos e encerramento controlado. O estudante escreve e executa cada etapa; este plano nao contem implementacoes prontas.

## Referencia principal

[Beej's Guide to Network Programming](https://beej.us/guide/bgnet/html/split/). As referencias abaixo apontam para os capitulos e secoes numerados no guia. Leia a secao indicada para responder a tarefa, sem precisar percorrer o livro inteiro antes de codificar.

## Perfil e ritmo

- Publico: desenvolvedor experiente; conceitos gerais de engenharia de software sao considerados conhecidos.
- Linguagem e plataforma: C em Linux/POSIX. Winsock e Windows nativo ficam fora desta primeira trilha.
- Ritmo sugerido: uma entrega pequena por licao; conclua os criterios antes de avancar.
- Bibliotecas: biblioteca C padrao e APIs POSIX de sockets; sem framework de rede.
- Testes: use dois terminais no mesmo host e loopback nas primeiras etapas. Nao exponha servicos a internet.

## Ambiente e bloqueios conhecidos

A instancia informada pelo estudante e `i-019fea1edf183b895`. A consulta de inventario EC2 nao foi concluida; portanto, regiao, estado, tipo, imagem, distribuicao, GCC e acesso por terminal ainda nao estao confirmados. O WinLibs compila, mas a execucao de binarios locais foi bloqueada por politica de grupo. O CloudShell tambem apresentou falha de acesso.

A Licao 01 deve estabelecer, com um teste simples, um ambiente Linux autorizado no qual o estudante consiga abrir um terminal, compilar e executar um programa. EC2 so sera adotada se o acesso remoto permitido estiver funcional. Se nao estiver, pause a trilha pratica em C e escolha com o estudante um ambiente autorizado; nao contorne controles da organizacao.

## Sequencia

| Licao | Incremento no projeto                                                              | Referencia Beej                |
| ----- | ---------------------------------------------------------------------------------- | ------------------------------ |
| 01    | Validar ambiente Linux/C e mapear socket, cliente e servidor                       | 1.2, 1.5 (comparacao), 2.1-2.2 |
| 02    | Utilitario de inspecao de enderecos IPv4/IPv6 e representacao de rede              | 3.1-3.4, 4                     |
| 03    | Resolver host/servico e preparar endereco de escuta                                | 5.1-5.3                        |
| 04    | Primeiro servidor TCP de eco, um cliente por vez                                   | 5.2-5.6, 6.1                   |
| 05    | Cliente TCP e troca de mensagens de eco                                            | 5.4, 5.7, 6.2                  |
| 06    | Versao UDP de eco, com datagramas                                                  | 5.8, 6.3                       |
| 07    | Servidor TCP com varios clientes usando `poll()`                                   | 7.1-7.3                        |
| 08    | Envio parcial, erros, EOF e encerramento de sockets                                | 5.9, 7.4, 8                    |
| 09    | Framing e serializacao de mensagens para o chat                                    | 3.2, 7.5-7.6                   |
| 10    | Chat multiusuario integrado, distribuicao TCP aos clientes e encerramento gracioso | 7.6, 8                         |

## Como considerar a trilha concluida

O chat aceita varios clientes simultaneos, identifica remetente, encaminha mensagens sem misturar fronteiras de mensagens TCP, lida com desconexoes e encerra recursos de forma previsivel. Os testes usam clientes locais e incluem casos de entrada incompleta, conexao encerrada e mais de um cliente ativo. O estudante explica as decisoes de enderecamento, framing e ciclo de vida do socket.

Broadcast UDP da secao 7.7 e uma extensao opcional independente; nao e necessario para distribuir mensagens do chat, que faz fan-out na camada da aplicacao sobre conexoes TCP.

## Arquivos

- [Progresso](PROGRESSO.md)
- [Licoes](licoes/)
- Os fontes produzidos pelo estudante ficam em `projeto/` quando a primeira licao pratica criar essa estrutura.
