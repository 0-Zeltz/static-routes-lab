# 4. Floating Static Route

## Topologia

![Topologia Floating Static Route](./images%20/floating-route/topology.png)

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
| R1       | 192.168.10.0/24 | 10.20.0.2/30  |
| R1       | 192.168.10.0/24 | 10.10.0.2/30  |
| R2       | 192.168.0.0/24  | 10.40.0.2/30  |
| R2       | 192.168.0.0/24  | 10.30.0.2/30  |
| R3       | 192.168.0.0/24  | 10.20.0.1/30  |
| R3       | 192.168.10.0/24 | 10.30.0.1/30  |
| R4       | 192.168.10.0/24 | 10.40.0.1/30  |
| R4       | 192.168.0.0/24  | 10.10.0.1/30  |

## Como funciona

Esta topologia é muito semelhante à anterior, utilizada no laboratório de ECMP. A principal diferença está no uso da Distância Administrativa (AD).

Com essa medida adicional, é possível definir uma rota preferencial no R1 e no R2. A rota secundária entra em uso caso a rota principal fique indisponível, funcionando como rota de backup.

## Testes

[Validação LAN1 -> LAN2](./images%20/floating-route/lan1-validation.png)

[Validação LAN2 -> LAN1](./images%20/floating-route/lan2-validation.png)

### Rota principal

![Traceroute pela rota principal](images/floating-primary-route.png)

### Falha do Roteador 3

![Roteador 3 desligado](images/router3-down.png)

### Rota secundária

![Traceroute pela rota secundária](images/floating-backup-route.png)

Como mostrado na imagem acima, o tráfego da rede continua fluindo mesmo com a rota principal indisponível.
