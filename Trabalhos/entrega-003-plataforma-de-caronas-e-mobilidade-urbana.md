
# ENTREGA 003 – MISSÃO: A FORJA DO COMPORTAMENTO DO SISTEMA  
## Plataforma de Caronas e Mobilidade Urbana
### Aluno(a): Emilly Pessutti
---

## 1. Descrição do Sistema

A Plataforma de Caronas e Mobilidade Urbana é um sistema digital que conecta passageiros e motoristas para realização de corridas em tempo real, permitindo solicitação, aceite, acompanhamento, pagamento e avaliação da viagem. O sistema busca reduzir dificuldades de deslocamento urbano, otimizar custos e melhorar a mobilidade nas cidades.

---

## 2. Atores do Sistema

- **Passageiro:** Usuário que solicita corridas  
- **Motorista:** Usuário que aceita e realiza corridas  
- **Administrador:** Responsável pelo gerenciamento do sistema  
- **Sistema de Pagamento:** Gerar cálculo de valores com base em distância percorrida, horários e dias da semana.
- **Serviço de Mapas:** Fornece rotas, cálculo de distâncias, tempo estimado e localização em tempo real.


---

## 3. Lista de Casos de Uso

- **UC01** – Cadastrar conta  
- **UC02** – Autenticar-se  
- **UC03** – Solicitar corrida  
- **UC04** – Calcular valor estimado  
- **UC05** – Aceitar corrida  
- **UC06** – Iniciar corrida  
- **UC07** – Finalizar corrida  
- **UC08** – Processar pagamento  
- **UC09** – Cancelar corrida  
- **UC10** – Avaliar corrida  
- **UC11** – Cadastrar veículo  
- **UC12** – Gerenciar usuários  

---

## 4. Casos de Uso Detalhados

### UC03 – Solicitar Corrida
**Ator:** Passageiro  
**Descrição:** Permite ao passageiro solicitar uma corrida informando origem e destino.  
**Pré-condições:** Usuário autenticado.  
**Pós-condições:** Corrida criada no sistema.  
**Fluxo principal:** Usuário informa origem, sistema calcula valor, busca motoristas e cria corrida.

### UC05 – Aceitar Corrida
**Ator:** Motorista  
**Descrição:** Permite ao motorista aceitar uma corrida disponível.  
**Pré-condições:** Motorista disponível.  
**Pós-condições:** Corrida associada ao motorista.

### UC07 – Finalizar Corrida
**Ator:** Motorista  
**Descrição:** Finaliza a corrida e inicia pagamento.  
**Pré-condições:** Corrida em andamento.  
**Pós-condições:** Corrida finalizada.

---

## 5. Regras de Negócio

- **RN01** – Apenas passageiros autenticados podem solicitar corridas  
- **RN02** - Apenas motoristas autenticados podem aceitar corridas
- **RN03** – Uma corrida só pode ser aceita por um motorista  
- **RN04** – Pagamento ocorre após finalização  
- **RN05** – Motorista deve estar disponível  
- **RN06** – Avaliação apenas após corrida finalizada  

---

## 6. Entidades

- **Usuário** – representa passageiros e administradores do sistema
- **Motorista** – usuário habilitado a realizar corridas
- **Veículo** – veículo vinculado a um motorista
- **Corrida** – solicitação de transporte entre passageiro e motorista
- **Pagamento** – registro financeiro da corrida
- **Avaliação** – feedback entre passageiro e motorista
- **Localização** – pontos de rastreamento da corrida em tempo real

---

## 7. Conexão com o Sistema Projetado

**UC03 – SOLICITAR CORRIDA**

- **Tela**: Solicitação de corrida
- **Endpoint**: POST /corridas
- **Entidade**: Corrida

**UC05 – ACEITAR CORRIDA**

- **Tela**: Corridas disponíveis / Painel do motorista
- **Endpoint**: POST /corridas/{id}/aceitar
- **Entidade**: Corrida

**UC08 – PROCESSAR PAGAMENTO**

- **Tela**: Pagamento da corrida
- **Endpoint**: POST /corridas/{id}/pagamento
- **Entidade**: Pagamento

---

## 8. Reflexão Arquitetural

O sistema está alinhado com os casos de uso definidos. Como evolução futura, podem ser implementadas corridas compartilhadas e melhorias no algoritmo de matching.
