# Verificando Status da API ![imagem-versao](https://img.shields.io/badge/GET-2094f3?style=flat-square)

Para verificar o status da API, no código ou no navegador, deve ser informado a `URL` correspondente a requisição GET - Status da API.

---

## URL

[https://registros-funcionarios-api.luishperna.com.br/status](https://registros-funcionarios-api.luishperna.com.br/status)

---

## Requisição

Para realizar esta requisição basta utilizar a URL.

```
# Link para verificação do status da API
https://registros-funcionarios-api.luishperna.com.br/status`
```

!!! note

    A verificação pode ser feita tanto por códigos, quanto diretamente pelo navegador. 

---

## Resposta da Requisição

Ao realizar a requisição, por parte da API, é esperado apenas o retorno de status de **sucesso**, caso contrário, significa que a API não está sendo executada.

### Status de Sucesso ✔️

Essa resposta informa se a API está rodando.

``` JSON
{
  "Status": "API rodando"
}
```

---

## Exemplo de Consumo em Python

!!! example "Verificando o status da API em Python"

    === "main.py"

        ``` py
        # Importando a biblioteca requests para trabalhar com solicitações HTTP
        import requests

        # Link público da API para requisições do tipo GET - Status da API
        url = f'https://registros-funcionarios-api.luishperna.com.br/status'

        # Resposta da requisição feita a partir do link juntamento com o CPF
        resposta = requests.get(url)

        # Obtendo o JSON da resposta da API
        dados = resposta.json()

        # Mostrando a resposta no terminal
        print(dados)
        ```

    === "Resposta de Sucesso"

        ``` JSON
        {'Status': 'API rodando'}
        ```

---