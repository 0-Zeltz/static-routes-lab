# 2. Rotas estáticas

## Topologia

![Topologia de rotas estáticas](./images%20/static-routes/topology.png)

## Endereçamento

### Redes

| Rede   | Endereço        |
| ------ | --------------- |
| LAN 01 | 192.168.0.0/24  |
| LAN 02 | 192.168.10.0/24 |

### Roteadores

| Roteador | Interface | Endereço        |
| -------- | --------- | --------------- |
| R0       | G0/0/0    | 192.168.0.1/24  |
| R0       | G0/0/1    | 10.0.0.1/30     |
| R1       | G0/0/0    | 192.168.10.1/24 |
| R1       | G0/0/1    | 10.0.0.2/30     |

## Como funciona

Cada LAN está conectada ao seu próprio roteador, enquanto os dois roteadores estão interligados por uma rede de trânsito separada.

Cada roteador conhece apenas as redes diretamente conectadas a ele. Por isso, são configuradas rotas estáticas para alcançar a LAN remota através do outro roteador.

## Testes

### Ping e Traceroute

![Teste de ping e traceroute](./images%20/static-routes/validation.png)
