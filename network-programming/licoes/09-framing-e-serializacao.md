# Licao 09 - Framing e serializacao

**Estado:** [ ]

**Projeto:** protocolo de mensagens com tamanho explicito sobre TCP.

## Objetivo

Definir como reconstruir mensagens sobre um stream TCP, mesmo quando o cabecalho ou payload chega dividido entre varias leituras.

## Beej

- [3.2 Byte Order](https://beej.us/guide/bgnet/html/split/ip-addresses-structs-and-data-munging.html#byte-order)
- [7.5 Serialization - How to Pack Data](https://beej.us/guide/bgnet/html/split/slightly-advanced-techniques.html#serialization)
- [7.6 Son of Data Encapsulation](https://beej.us/guide/bgnet/html/split/slightly-advanced-techniques.html#sonofdataencap)

## Direcoes

1. Especifique um frame composto por um comprimento fixo de 32 bits em ordem de bytes da rede seguido pelos bytes do payload.
2. Defina um limite pequeno e documentado para payload e rejeite comprimentos acima dele antes de reservar memoria.
3. Implemente um parser incremental que aceite cabecalho e payload fragmentados ou varios frames agrupados em uma unica leitura.
4. Implemente o envio do frame usando a rotina de I/O robusto da licao anterior.
5. Escreva um cliente de teste que possa dividir o frame em varias escritas e outro caso que envie mais de um frame seguido.

## Criterios de aceite

- O receptor emite cada payload exatamente uma vez, independentemente da fragmentacao/agrupamento das leituras.
- Comprimento zero, limite maximo e comprimento acima do maximo tem comportamento documentado.
- Valores multibyte sao codificados/decodificados em ordem de rede.
- EOF no meio do cabecalho ou payload e detectado como frame truncado, nao como mensagem valida.

## Dica (somente se pedir ajuda)

O parser precisa guardar estado entre chamadas de leitura; a fronteira de uma chamada nao e a fronteira do frame.
