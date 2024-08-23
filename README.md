# afonsinhoponderadaDanielZ

# Decisões de Negócio e Modelo DMN

## Regras de Decisão do Negócio

1. **Regra de Verificação de Disponibilidade**: Antes de validar uma requisição de compra, é necessário verificar a disponibilidade do item no estoque. Se disponível, o processo de compra é cancelado e o item é reservado para entrega. Caso contrário, inicia-se a aquisição junto aos fornecedores.

2. **Regra de Aprovação do Orçamento**: Compras que ultrapassem o orçamento designado para o departamento exigem uma avaliação financeira minuciosa e a aprovação do setor financeiro antes de continuar.

3. **Regra de Cotação Mínima de Fornecedores**: Para compras de valor elevado, é obrigatório obter propostas de no mínimo três fornecedores distintos para assegurar a competitividade e transparência do processo de aquisição.

4. **Regra de Prioridade de Compras**: Requisições de compra relacionadas a operações urgentes ou críticas têm prioridade sobre outras menos urgentes, respeitando os prazos pré-definidos para cada tipo de material.

5. **Regra de Conformidade de Qualidade**: Todos os itens adquiridos precisam cumprir com os padrões de qualidade estabelecidos e ser validados pelo departamento de qualidade antes de serem aceitos e efetuados os pagamentos.

## Modelo de Decisão DMN

### Decisões Principais

#### Verificação de Disponibilidade

| **Input**                   | **Output**                                    | **Decision**                                                 |
|-----------------------------|-----------------------------------------------|--------------------------------------------------------------|
| ID do item e a quantidade   | Se temos o item em estoque e quantos estão disponíveis | Se a quantidade em estoque é suficiente, o item está disponível |

#### Aprovação do Orçamento

| **Input**                           | **Output**                                              | **Decision**                                                    |
|-------------------------------------|---------------------------------------------------------|-----------------------------------------------------------------|
| Custo total da compra e o orçamento do departamento | Se o orçamento permite a compra ou necessita análise financeira detalhada | Se o custo exceder o orçamento, requer aprovação extra do financeiro |

### Informações Necessárias

- **Estoque de Itens**: Uma lista atualizada do que há no estoque.
- **Orçamento do Departamento**: Quanto dinheiro está disponível para gastar.

### Regras de Negócio Envolvidas

- Regra de Verificação de Disponibilidade
- Regra de Aprovação do Orçamento

### Conexões entre Informações

- A decisão sobre a disponibilidade do item usa diretamente os dados do estoque.
- A aprovação do orçamento depende tanto do resultado da verificação de disponibilidade quanto do limite de orçamento.

### Como as Decisões se Conectam

1. Primeiro, checamos se o item que queremos comprar está disponível.
2. Se tivermos o item, verificamos se o custo total está dentro do nosso orçamento.
3. Se o custo for maior, precisamos de uma análise mais aprofundada do financeiro.
