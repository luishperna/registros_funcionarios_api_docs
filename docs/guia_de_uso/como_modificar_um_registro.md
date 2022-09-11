# Como Consultar um Registro ![imagem-versao](https://img.shields.io/badge/PATCH-3eb096?style=flat-square)

Para modificar uma informação de um registro na API, no código, deve ser informado a `URL` correspondente a requisição PATCH e o corpo da requisição em `JSON`.

---

## URL

[https://registros-funcionarios-api.luishperna.com.br/funcionarios/modificacoes](https://registros-funcionarios-api.luishperna.com.br/funcionarios/modificacoes)

---

## Corpo da Requisição

O corpo da requisição deve ser no formato `JSON` contendo as seguintes **chaves**:

1. codigo ➔ Código de cadastro do funcionário(a).
2. atributo ➔ Atributo no qual dejesa modificar.
3. novo_valor ➔ Novo valor para o qual deseja ser modificado.

!!! note "Observação"

    A modificação só pode ser realizada nos atributos: **cargo**, **data_inicio**, **data_cancelamento** e **comportamento**.

Os **valores** correspondentes as chaves devem obedecer aos tipos de dados mostrado abaixo:

``` JSON
{
  "codigo": int,
  "atributo": "string",
  "novo_valor": "string"
}
```

---

## Respostas da Requisição

Ao realizar a requisição pode-se retornar uma das duas respostas: status de **sucesso** ou status de **erro**.

### Status de Sucesso ✔️

Essa resposta informa a modificação realizada no registro do funcionário(a).

``` JSON
{
  "Status": "2201 - Modificação realizado com sucesso!",
  "Atualização": "Atributo data_inicio setado para 2022-09-11"
}
```

### Status de Erro ❌

Essa resposta informa o tipo de erro detectado ao tentar realizar a requisição.

``` JSON
# Erro ao tentar modificar um atributo não permitido
{
  "Status": "Erro ao modificar",
  "Tipo de erro": "O atributo codigo não pode ser modificado"
}

# Erro ao informar um atributo ou valor incorretamente
{
  "Status": "Erro ao modificar",
  "Tipo de erro": "1054 (42S22): Unknown column 'dat_inicio' in 'field list'",
  "Causas": "Dados faltantes ou incorretos"
}
```

---

## Exemplo de Consumo em Python

!!! example "Modificando um registro em Python"

    === "main.py"

        ``` py
        # Importando a biblioteca requests para trabalhar com solicitações HTTP
        import requests

        # Link público da API para requisições do tipo PATCH - Modificar um registro
        url = 'https://registros-funcionarios-api.luishperna.com.br/funcionarios/modificacoes'

        # Modificações no formato JSON a ser enviado na requisição PATCH - Modificar um registro
        modificacoes = '''{
            "codigo": "2201",
            "atributo": "data_inicio",
            "novo_valor": "2022-09-11"
            }'''

        # Resposta da requisição feita a partir do link e JSON passados como parâmetros
        resposta = requests.patch(url, data=modificacoes)

        # Obtendo o JSON da resposta da API
        dados = resposta.json()

        # Mostrando a resposta no terminal
        print(dados)
        ```

    === "Resposta de Sucesso"

        ```
        {'Status': '2201 - Modificação realizado com sucesso!', 'Atualização': 'Atributo data_inicio setado para 2022-09-11'}
        ```

    === "Resposta de Erro"

        ```
        # Erro ao tentar modificar um atributo não permitido
        {'Status': 'Erro ao modificar', 'Tipo de erro': 'O atributo codigo não pode ser modificado'}

        # Erro ao informar um atributo ou valor incorretamente
        {'Status': 'Erro ao modificar', 'Tipo de erro': "1054 (42S22): Unknown column 'dat_inicio' in 'field list'", 'Causas': 'Dados faltantes ou incorretos'}
        ```
        
---