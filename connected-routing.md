# 1. Roteamento conectado

## Topologia

![Topologia de roteamento conectado](./images%20/connected-routing/1-router-topology.png)

## Endereçamento

### Redes

| Rede   | Endereço        |
| ------ | --------------- |
| LAN 01 | 192.168.0.0/24  |
| LAN 02 | 192.168.10.0/24 |

### R0

| Interface | Endereço        |
| --------- | --------------- |
| G0/0/0    | 192.168.0.1/24  |
| G0/0/1    | 192.168.10.1/24 |

## Como funciona

As duas redes estão diretamente conectadas ao roteador e são adicionadas automaticamente à sua tabela de roteamento. Não é necessário configurar rotas estáticas.

## Testes

### Ping

![Teste de ping](./images%20/connected-routing/validation.png)
