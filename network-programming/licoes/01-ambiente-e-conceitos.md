# Licao 01 - Ambiente e conceitos

**Estado:** [ ]

**Projeto:** preparar uma bancada Linux/C verificavel, sem iniciar a implementacao do chat.

## Objetivo

Confirmar que existe um ambiente autorizado onde seja possivel editar, compilar e executar C, e explicar o papel de socket, cliente, servidor, stream TCP e datagrama UDP.

## Beej

- [1.2 Platform and Compiler](https://beej.us/guide/bgnet/html/split/intro.html#platform-and-compiler)
- [2.1 Two Types of Internet Sockets](https://beej.us/guide/bgnet/html/split/what-is-a-socket.html#two-types-of-internet-sockets)
- [2.2 Low-level Nonsense and Network Theory](https://beej.us/guide/bgnet/html/split/what-is-a-socket.html#lowlevel)

## Direcoes

1. Verifique com o responsavel pelo ambiente se a instancia EC2 `i-019fea1edf183b895` esta disponivel para desenvolvimento e se o acesso por terminal e permitido. Nao a inicie nem altere regras de rede sem autorizacao explicita.
2. Se houver acesso, identifique distribuicao Linux, arquitetura, compilador C, `make` e mecanismo de acesso persistente. Se nao houver, registre o bloqueio e escolha um ambiente Linux autorizado antes de seguir.
3. Crie uma area de trabalho versionavel para a trilha e compile/executa nela um programa C minimo, sem incluir sockets ainda.
4. Desenhe o fluxo de uma conexao TCP e compare-o com a troca de datagramas UDP.

## Criterios de aceite

- Consegue abrir um terminal Linux autorizado no ambiente escolhido.
- Consegue compilar e executar um programa C local nesse ambiente.
- Registra compilador/versao, distribuicao, arquitetura e comando de build usado.
- Explica em poucas frases a diferenca entre TCP stream e UDP datagrama e identifica cliente e servidor no futuro chat.

## Evidencia

Traga o resultado dos comandos de ambiente/build e um diagrama simples do fluxo cliente-servidor. Nao inclua credenciais, tokens ou dados sensiveis.

## Dica (somente se pedir ajuda)

Confirme primeiro se o bloqueio ocorre ao conectar ao ambiente, ao compilar ou ao executar; sao problemas diferentes e pedem verificacoes diferentes.
