# Como Consultar um Registro ![imagem-versao](https://img.shields.io/badge/GET-2094f3?style=flat-square)

Para consultar um registro na API, no código ou navegador, deve ser informado a `URL` correspondente a requisição GET - Consultar um registro, seguido do CPF do funcionário(a).

---

## URL

[https://registros-funcionarios-api.luishperna.com.br/funcionarios/consultas/{cpf}](https://registros-funcionarios-api.luishperna.com.br/funcionarios/consultas/{cpf})

---

## Requisição

Para realizar esta requisição basta alterar o `{cpf}` por um número de CPF já cadastrado.

```
# Link base
https://registros-funcionarios-api.luishperna.com.br/funcionarios/consultas/{cpf}`

# Consultando funcionário com o número de CPF 123.123.123-12
https://registros-funcionarios-api.luishperna.com.br/funcionarios/consultas/123.123.123-12
```

!!! note "Observação"

    A consulta pode ser feita tanto por códigos, quanto diretamente pelo navegador. 

---

## Respostas da Requisição

Ao realizar a requisição pode-se retornar uma das duas respostas: status de **sucesso** ou status de **erro**.

### Status de Sucesso ✔️

Essa resposta informa os dados do funcionário(a) cadastrado(a).

``` JSON
{
  "codigo": "2201",
  "nome": "Peter Jason Quill",
  "data_nascimento": "1980-12-20",
  "cpf": "123.123.123-12",
  "email": "perterquill@gmail.com",
  "cargo": "Desenvolvedor Web",
  "data_inicio": "2022-09-07",
  "data_cancelamento": "None",
  "comportamento": "Proativo"
}
```

### Status de Erro ❌

Essa resposta informa o tipo de erro detectado ao tentar realizar a requisição.

``` JSON
{
  "Status": "Erro ao consultar",
  "Tipo de erro": "CPF incorreto ou não cadastrado"
}
```

---

## Exemplo de Consumo em Python

!!! example "Consultando um registro em Python"

    === "main.py"

        ``` py
        # Importando a biblioteca requests para trabalhar com solicitações HTTP
        import requests

        # Informação do número do CPF
        cpf = "123.123.123-12"

        # Link público da API para requisições do tipo GET - Consultar um registro
        url = f'https://registros-funcionarios-api.luishperna.com.br/funcionarios/consultas/{cpf}'

        # Resposta da requisição feita a partir do link juntamento com o CPF
        resposta = requests.get(url)

        # Obtendo o JSON da resposta da API
        dados = resposta.json()

        # Mostrando a resposta no terminal
        print(dados)
        ```

    === "Resposta de Sucesso"

        ``` JSON
        {'codigo': '2201', 'nome': 'Peter Jason Quill', 'data_nascimento': '1980-12-20', 'cpf': '123.123.123-12', 'email': 'perterquill@gmail.com', 'cargo': 'Desenvolvedor Web', 'data_inicio': '2022-09-07', 'data_cancelamento': 'None', 'comportamento': 'Proativo'}
        ```

    === "Resposta de Erro"

        ``` JSON
        {'Status': 'Erro ao consultar', 'Tipo de erro': 'CPF incorreto ou não cadastrado'}
        ```

---