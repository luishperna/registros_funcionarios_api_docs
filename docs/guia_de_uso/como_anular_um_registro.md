# Como Anular um Registro ![imagem-versao](https://img.shields.io/badge/DELETE-f93e3e?style=flat-square)

Para anular um registro na API, no código, deve ser informado a `URL` correspondente a requisição DELETE seguido do CPF do funcionário(a).

---

## URL

[https://registros-funcionarios-api.luishperna.com.br/funcionarios/anulacoes/{cpf}](https://registros-funcionarios-api.luishperna.com.br/funcionarios/anulacoes/{cpf})

---

## Requisição

Para realizar está requisição basta alterar o `{cpf}` por um número de CPF já cadastrado.

```
# Link base
https://registros-funcionarios-api.luishperna.com.br/funcionarios/anulacoes/{cpf}`

# Anulando funcionário correspondente ao número de CPF 123.123.123-12
https://registros-funcionarios-api.luishperna.com.br/funcionarios/anulacoes/123.123.123-12
```

---

## Respostas da Requisição

Ao realizar a requisição é esperado apenas um retorno de status de **sucesso**.

### Status de Sucesso ✔️

Essa resposta informa o cpf do(a) funcionário(a) que foi deletado.

``` JSON
{
  "Status": "Anulação realizada com sucesso!",
  "Anulação": "Deletado registro com cpf 123.123.123-12"
}
```

!!! note "Observação"

    A resposta será a mesma caso o CPF não esteja registrado. 

---

## Exemplo de Consumo em Python

!!! example "Anulando um registro em Python"

    === "main.py"

        ``` py
        # Importando a biblioteca requests para trabalhar com solicitações HTTP
        import requests

        # Informação do número do CPF
        cpf = "123.123.123-12"

        # Link público da API para requisições do tipo DELETE - Anular um registro
        url = f'https://registros-funcionarios-api.luishperna.com.br/funcionarios/anulacoes/{cpf}'

        # Resposta da requisição feita a partir do link juntamento com o CPF
        resposta = requests.delete(url)

        # Obtendo o JSON da resposta da API
        dados = resposta.json()

        # Mostrando a resposta no terminal
        print(dados)
        ```

    === "Resposta de Sucesso"

        ``` JSON
        {'Status': 'Anulação realizada com sucesso!', 'Anulação': 'Deletado registro com cpf 123.123.123-12'}
        ```

---