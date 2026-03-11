# Código da Aplicação

Esta pasta contém o código do agente financeiro responsável por analisar gastos do usuário, organizar as informações por categoria e oferecer sugestões simples de controle financeiro.
O agente utiliza um modelo de linguagem para interpretar as perguntas do usuário e gerar respostas baseadas nos dados disponíveis na base de conhecimento (perfil do usuário, histórico de transações e dicas financeiras).

## Estrutura Sugerida

```
src/
├── app.py              # Aplicação principal (Streamlit/Gradio)
├── agente.py           # Lógica do agente
├── config.py           # Configurações (API keys, etc.)
└── requirements.txt    # Dependências
```

## Exemplo de requirements.txt

```
streamlit
openai
python-dotenv
```

## Como Rodar

```bash
# Instalar dependências
pip install -r requirements.txt

# Rodar a aplicação
streamlit run app.py
```
