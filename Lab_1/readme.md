# Prática 1 -> Redes de Computadores

| Autor                          | NUSP      |
| ------------------------------ | --------- |
| Aruan Bretas de Oliveira Filho | 12609731  |
| Leonardo                       | XXXXXXXX  |
| Andre                          | XXXXXXXX  |
| Fellipe Tripovichy             | XXXXXXXX  |

## 1. Transferência de arquivo usando TCP

1. **Qual o endereço IP e número de porta TCP usado pelo computador cliente (origem) para transferir o arquivo para gaia.cs.umass.edu?**

**Resposta:** Endereço IP da fonte: 172.20.22.235
Porta: 57939

2. **Qual o endereço IP de gaia.cs.umass.edu? Qual a porta TCP destino utilizada para a transferência de arquivo?**

**Resposta:** Endereço IP de gaia.cs.umass.edu: 128.119.245.12
Porta: 80

## 2. Analisando o TCP

1. **Identifique o segmento TCP SYN usado para iniciar a conexão TCP entre o computador cliente e gaia.cs.umass.edu. Sobre este segmento, responda:**

    a) Qual o número de seqüência do segmento?

**Resposta:** Numero de Sequência relativo: 0


    b) O que identifica este segmento como um segmento SYN?

**Resposta:** Sua flag que é 0x002 (SYN)

2. **Identifique o segmento TCP SYN+ACK enviado por gaia.cs.umass.edu para o computador cliente em resposta ao segmento SYN. Sobre este segmento, responda:**

    a) Qual o número de seqüência do segmento?

**Resposta:** Número de Sequência: 0

    b) Qual o valor do campo ACKnowledgement no segmento SYN+ACK? Como este valor foi determinado por gaia.cs.umass.edu?

**Resposta:** O valor ACKnowledgement é 1. Como ele recebe o primeiro pacote para estabelecer a conexão, sendo esse o SYN, vindo zero no número de sequência, apenas há um incremento de 1, para que saiba que foi recebido pacote numero 0, e que poss enviar o próximo

    c) O que identifica um segmento como um segmento SYN+ACK?

**Resposta:** Sua flag 0x012 (SYN, ACK)

3. **Identifique o segmento TCP que contém o comando HTTP POST. Qual o número de seqüência do segmento?**

**Resposta:** Seu número de sequência é 152954

4. **Considere o segmento TCP que contém o comando HTTP POST como o primeiro segmento de dados da conexão TCP. Observe os seis primeiros segmentos da conexão TCP (incluindo o que contém o comando HTTP POST).**

    (a) Quais os números de seqüência dos segmentos?

**Resposta:** 
1. 152954
2. 1
3. 152954
4. 776
5. 152954
6. 1


    (b) Identifique o tempo (horário) que cada um dos seis segmentos foi enviado.

**Resposta:**
1. 56.6403
2. 56.8114
3. 56.8609
4. 61.8157
5. 61.8161
6. 63.5465

    (c) Quando o ACK para cada segmento foi recebido?

**Resposta:** 
1. 1
2. 152954
3. 776
4. 152954
5. 777
6. 1

    (d) Dada a diferença de quando cada segmento TCP foi enviado, e quando o
    respectivo ACK foi recebido, qual o valor de RTT para cada um dos seis
    segmentos?

**Resposta:**
1. 0,1711
2. 0,0495
3. 4,9552
4. 0,0004
5. 1,7304

    (e) Qual o valor de EstimatedRTT (de acordo com o livro-texto) depois do
    recebimento de cada ACK? Assuma que o valor de EstimatedRTT é igual ao valor
    medido do RTT para o primeiro segmento.


**Resposta:**

5. **Qual o comprimento de cada um dos seis primeiros segmentos de dados?**

**Resposta:** 
1. 539
2. 829
3. 54
4. 56
5. 54
6. 54

6. **Qual a quantia mínima de espaço no buffer anunciado para o receptor no trace todo? A falta de espaço no buffer do receptor bloqueia o transmissor alguma vez?**

**Resposta:** Para a Janela do POST, obtive isso de janela

Calculated window size = 513 * 256 = 131328 bytes. Onde 513 era a propria janela e 256 o fator de escala

7. **Existem segmentos retransmitidos no arquivo de trace? O que você procurou no arquivo de trace para responder a esta pergunta?**

**Resposta:** até apareceu segmentos retransmitidos, as nenhum com tinha ligação com o IP (128.119.245.12), então não. Apliquei o filtro tcp.analysis.retransmission para procurar por retransmissões TCP, e verifiquei os pacotes rotulados com [TCP Retransmission], além de inspecionar os números de sequência dos pacotes para ver se foram repetidos em diferentes momentos.

8. 

9. 