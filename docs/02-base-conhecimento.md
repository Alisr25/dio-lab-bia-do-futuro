# Base de Conhecimento

## Dados Utilizados

Descreva se usou os arquivos da pasta `data`, por exemplo:

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `historico_atendimento.csv` | CSV | Contextualizar interações anteriores |
| `perfil_investidor.json` | JSON | Personalizar recomendações |
| `produtos_financeiros.json` | JSON | Sugerir produtos adequados ao perfil |
| `transacoes.csv` | CSV | Analisar padrão de gastos do cliente |

> [!TIP]
> **Quer um dataset mais robusto?** Você pode utilizar datasets públicos do [Hugging Face](https://huggingface.co/datasets) relacionados a finanças, desde que sejam adequados ao contexto do desafio.

---

## Adaptações nos Dados

> Você modificou ou expandiu os dados mockados? Descreva aqui.

Os dados mockados foram adaptados para representar um cenário simples de controle financeiro pessoal. Foram criados registros fictícios de transações financeiras, contendo data, categoria e valor gasto. Além disso, foram incluídas categorias de despesas e algumas dicas financeiras básicas para que o agente possa sugerir melhorias no controle de gastos.

Esses dados foram organizados em arquivos CSV e JSON para facilitar o carregamento e a utilização pelo agente durante as interações.

---

## Estratégia de Integração

### Como os dados são carregados?
> Descreva como seu agente acessa a base de conhecimento.

Os arquivos JSON e CSV são carregados no início da execução do sistema utilizando Python. Esses dados são armazenados em variáveis e utilizados como base de conhecimento para fornecer contexto ao modelo de linguagem durante a geração das respostas.

### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?

As informações mais relevantes, como perfil do usuário e histórico recente de transações, são incluídas no contexto do prompt enviado ao modelo de linguagem. Dessa forma, o agente consegue gerar respostas mais personalizadas e baseadas nos dados financeiros fornecidos.

Além disso, as categorias de gastos são utilizadas para classificar automaticamente as despesas informadas pelo usuário.

---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

```
Dados do Cliente:
- Nome: Alicia Ribeiro
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
