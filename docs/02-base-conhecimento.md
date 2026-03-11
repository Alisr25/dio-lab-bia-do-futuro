# Base de Conhecimento

## Dados Utilizados

Descreva se usou os arquivos da pasta `data`, por exemplo:

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `transacoes_usuario.csv` | CSV | Histórico de gastos do usuário utilizado para análise de padrões de consumo |
| `categorias_financeiras.json` | JSON | Define as categorias utilizadas pelo agente para classificar despesas |
| `perfil_usuario.json` | JSON | Contém informações do usuário para personalizar as respostas do agente |
| `dicas_financeiras.json` | JSON | Conjunto de dicas financeiras que podem ser utilizadas pelo agente nas recomendações |



---

## Adaptações nos Dados

> Você modificou ou expandiu os dados mockados? Descreva aqui.

Os dados mockados foram adaptados para representar um cenário simples de controle financeiro pessoal. Foram criados registros fictícios de transações financeiras contendo data, categoria, descrição e valor gasto.
Além disso, foram definidas categorias de despesas e incluídas dicas financeiras básicas para que o agente possa fornecer sugestões de organização financeira.
Esses dados foram estruturados em arquivos CSV e JSON, facilitando o carregamento e a utilização pelo agente durante as interações.

---

## Estratégia de Integração

### Como os dados são carregados?
> Descreva como seu agente acessa a base de conhecimento.

Os arquivos JSON e CSV são carregados no início da execução do sistema utilizando Python. Esses dados são armazenados em estruturas de dados na memória e utilizados como base de conhecimento para fornecer contexto ao modelo de linguagem durante a geração das respostas.

### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?

As informações mais relevantes, como o perfil do usuário e o histórico recente de transações, são incluídas no contexto do prompt enviado ao modelo de linguagem.
Dessa forma, o agente consegue gerar respostas mais personalizadas e baseadas nos dados financeiros fornecidos. As categorias financeiras também são utilizadas para auxiliar na classificação automática dos gastos informados pelo usuário.

---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

```
Dados do Cliente:
- Nome: Alice Silva
- Perfil financeiro: Estudante
- Renda mensal: R$ 2.000
- Objetivo: Controlar gastos mensais

Últimas transações:
- 02/03: Supermercado - R$ 180
- 03/03: Transporte (Uber) - R$ 45
- 05/03: Streaming - R$ 39
- 06/03: Restaurante - R$ 70
- 07/03: Farmácia - R$ 55

Resumo de categorias:
- Alimentação: R$ 250
- Transporte: R$ 45
- Assinaturas: R$ 39
- Saúde: R$ 55
```
