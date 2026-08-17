# 3. Static ECMP

## Topologia

![Topologia Static ECMP](./images%20/static-ECMP%20/EMCP-top.png)

## Endereçamento

### Redes

| Rede   | Endereço        |
| ------ | --------------- |
| LAN 01 | 192.168.0.0/24  |
| LAN 02 | 192.168.10.0/24 |

### Roteadores

| Roteador | Interface | Endereço        |
| -------- | --------- | --------------- |
| R1       | G0/0/0    | 192.168.0.1/24  |
| R1       | G0/0/1    | 10.10.0.1/30    |
| R1       | G0/0/2    | 10.20.0.1/30    |
| R2       | G0/0/0    | 192.168.10.1/24 |
| R2       | G0/0/1    | 10.40.0.1/30    |
| R2       | G0/0/2    | 10.30.0.1/30    |
| R3       | G0/0/0    | 10.20.0.2/30    |
| R3       | G0/0/1    | 10.30.0.2/30    |
| R4       | G0/0/0    | 10.10.0.2/30    |
| R4       | G0/0/1    | 10.40.0.2/30    |

## Rotas

| Roteador | Destino         | Próximo salto |
| -------- | --------------- | ------------- |
| R1       | 192.168.10.0/24 | 10.20.0.2     |
| R1       | 192.168.10.0/24 | 10.10.0.2     |
| R2       | 192.168.0.0/24  | 10.40.0.2     |
| R2       | 192.168.0.0/24  | 10.30.0.2     |
| R3       | 192.168.0.0/24  | 10.20.0.1     |
| R3       | 192.168.10.0/24 | 10.30.0.1     |
| R4       | 192.168.10.0/24 | 10.40.0.1     |
| R4       | 192.168.0.0/24  | 10.10.0.1     |

## Como funciona

### Static ECMP — Equal-Cost Multi-Path

Neste laboratório, R1 e R2 possuem duas rotas estáticas para a mesma rede de destino, utilizando next-hops diferentes com o mesmo custo.

Dessa forma, os dois caminhos podem ser instalados na tabela de roteamento e utilizados para distribuir o tráfego. Em equipamentos Cisco, essa distribuição é realizada pelo CEF.

### Vantagens

* **Distribuição de tráfego:** permite utilizar múltiplos caminhos disponíveis até o mesmo destino.
* **Redundância de caminho:** caso um caminho deixe de ser válido, o caminho restante pode continuar sendo utilizado.
* **Simplicidade:** em redes pequenas, pode ser implementado apenas com rotas estáticas.

### Limitação

* **Configuração manual:** alterações na topologia exigem manutenção das rotas pelo administrador.

## Testes

![Teste de traceroute](./images%20/static-ECMP%20/validation.png)

## Observação

Caso você opte por abrir o arquivo `.pkt` e fazer os testes por conta própria, é importante ressaltar que podem ocorrer perdas nas primeiras requisições ICMP enquanto os dispositivos populam suas tabelas ARP.

Após a resolução dos endereços de camada 2, os pings seguintes funcionam normalmente.

Aplicações baseadas em TCP, como HTTP e HTTPS, podem não apresentar uma falha perceptível durante esse processo, pois o TCP realiza retransmissões em caso de perda.

