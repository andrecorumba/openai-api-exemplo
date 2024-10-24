# Exercício Prático - Curso de IA em Auditoria

Este repositório contém um exercício prático desenvolvido para o Curso de IA em Auditoria. O objetivo do exercício é demonstrar como enviar um prompt via API para o OpenAI e receber uma resposta gerada pelo modelo GPT-4. No exemplo fornecido, o modelo irá criar uma história infantil sobre uma capivara usando calça vermelha.

## Descrição

O exercício é feito utilizando o Google Colab com o arquivo `openai-api.ipynb`. O código realiza uma requisição para a API da OpenAI usando o modelo gpt-4o-mini, que responde com uma história inventada de acordo com o prompt enviado. Este é um exemplo simples de interação com a API para fins de auditoria e uso de IA em casos práticos.

## Pré-requisitos

Para rodar o exercício no Google Colab, será necessário:

1.	Uma conta no Google Colab
2.	Chave de API da OpenAI (para acessar os modelos de IA)
3.	Um arquivo .env com as credenciais necessárias

## Instalação

1.	Faça o upload do arquivo openai-api.ipynb para seu Google Colab.
2.	No Colab, certifique-se de instalar as bibliotecas necessárias, como openai e python-dotenv. Use o comando:

```
!pip install openai python-dotenv
```

3.	Carregue suas credenciais no formato .env no Google Colab com as seguintes variáveis:

```
OPENAI_API_KEY=your_openai_api_key
ORGANIZATION=your_organization_id
PROJECT=your_project_id
```


## Uso

1.	No Google Colab, execute as células do notebook openai-api.ipynb. Ele enviará o seguinte prompt para o modelo GPT-4: “Invente uma história de uma capivara que usava calça vermelha.”
2. A IA responderá com uma história criativa baseada no contexto fornecido.

## Exemplo de Código

Aqui está o trecho de código que será executado no notebook:

```
from openai import OpenAI
import os
from dotenv import load_dotenv, find_dotenv

# Carrega as variáveis de ambiente
load_dotenv(find_dotenv())

# Autenticação na plataforma
client = OpenAI(
    api_key=os.getenv("OPENAI_API_KEY"),
    organization=os.getenv("ORGANIZATION"),
    project=os.getenv("PROJECT"),
)

# Envia um prompt para o modelo GPT-4o-mini
completion = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=[
        {"role": "system", "content": "Você é um assistente que sabe inventar histórias infantis."},
        {"role": "user", "content": "Invente uma história de uma capivara que usava calça vermelha."}
    ],
    temperature=0.8,
)

# Exibe a resposta gerada
print(completion.choices[0].message)
```

## Conclusão

Mão à obra!
