# Licao 02 - Enderecos e representacao

**Estado:** [ ]

**Projeto:** utilitario de diagnostico de enderecos.

## Objetivo

Representar e validar enderecos IPv4/IPv6 e explicar portas, sub-redes e ordem de bytes da rede.

## Beej

- [3.1 IP Addresses, versions 4 and 6](https://beej.us/guide/bgnet/html/split/ip-addresses-structs-and-data-munging.html#ip-addresses-versions-4-and-6)
- [3.2 Byte Order](https://beej.us/guide/bgnet/html/split/ip-addresses-structs-and-data-munging.html#byte-order)
- [3.3 structs](https://beej.us/guide/bgnet/html/split/ip-addresses-structs-and-data-munging.html#structs)
- [3.4 IP Addresses, Part Deux](https://beej.us/guide/bgnet/html/split/ip-addresses-structs-and-data-munging.html#ip-addresses-part-deux)
- [4 Jumping from IPv4 to IPv6](https://beej.us/guide/bgnet/html/split/jumping-from-ipv4-to-ipv6.html#jumping-from-ipv4-to-ipv6)

## Direcoes

1. Faca um utilitario de linha de comando que recebe um endereco numerico e informa se e IPv4 ou IPv6.
2. Converta entre texto e representacao binaria usando as APIs de conversao do sistema; mostre uma forma canonica de volta para texto.
3. Inclua uma porta como valor separado do endereco IP e documente os limites validos.
4. Mostre um exemplo que deixe visivel a diferenca entre ordem de bytes do host e ordem de bytes da rede, sem interpretar o endereco como string de numeros separados por pontos.

## Criterios de aceite

- Aceita enderecos validos IPv4 e IPv6 e rejeita texto invalido.
- Converte endereco numerico texto -> binario -> texto sem perda do endereco.
- Trata porta fora do intervalo como erro.
- Explica por que campos multibyte de protocolos de rede usam ordem de bytes definida pelo protocolo.

## Extensao opcional

Compare enderecos loopback, privados e globais; nao tente enviar trafego para terceiros.

## Dica (somente se pedir ajuda)

Separe a validacao/conversao do endereco da analise da porta; IPv6 torna perigoso inferir a porta apenas pelos dois-pontos.
