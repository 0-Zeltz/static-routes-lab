# Static Routing Lab 🛜

Este lab foi criado no **Cisco Packet Tracer** para estudar diferentes formas de trabalhar com rotas estáticas e entender melhor como o tráfego se comporta entre diferentes redes.

A ideia aqui não é montar uma infraestrutura gigantesca. São topologias relativamente simples, cada uma focada em demonstrar um comportamento específico.

## 🔧 O que tem aqui?

O lab foi dividido em quatro cenários:

### 01 — Connected Routing
Duas redes diretamente conectadas ao mesmo roteador.

### 02 — Static Routing
Duas LANs com seus próprios roteadores e uma rede dedicada conectando os dois.

### 03 — Floating Static Route
Duas rotas para o mesmo destino utilizando **Administrative Distance (AD)** para definir uma rota principal e outra como backup.

### 04 — Static ECMP
Múltiplas rotas estáticas de mesmo custo para o mesmo destino, permitindo que mais de um caminho seja utilizado.

## 🎯 Objetivo

Entender na prática:

- Como um roteador constrói e utiliza sua routing table;
- Como configurar rotas estáticas;
- O papel do next-hop e das redes diretamente conectadas;
- Como a Administrative Distance influencia a escolha de uma rota;
- Como uma Floating Static Route pode ser utilizada como redundância;
- Como o ECMP trabalha com múltiplos caminhos para o mesmo destino.

## 🧪 Ambiente

- Cisco Packet Tracer
- Roteadores Cisco
- Switches L2
- Endpoints para testes de conectividade

Cada cenário possui sua própria topologia, configuração e testes para demonstrar o comportamento das rotas.
