# Como Cadastrar um Registro ![imagem-versao](https://img.shields.io/badge/POST-43bf86?style=flat-square)

Para cadastrar um registro na API, no código, deve ser informado a `URL` correspondente a requisição POST e o corpo da requisição em `JSON`.

---

## URL

[https://registros-funcionarios-api.luishperna.com.br/funcionarios/cadastros](https://registros-funcionarios-api.luishperna.com.br/funcionarios/cadastros)

---

## Corpo da Requisição

O corpo da requisição deve ser no formato `JSON` contendo as seguintes **chaves**:

- nome, data_nascimento, cpf, email, codigo, cargo, data_inicio, data_cancelamento e comportamento.

Os **valores** correspondentes as chaves devem obedecer aos tipos de dados mostrado abaixo:

``` JSON
{
  "nome": "string",
  "data_nascimento": "string",
  "cpf": "string",
  "email": "string",
  "codigo": int,
  "cargo": "string",
  "data_inicio": "string",
  "data_cancelamento": "string",
  "comportamento": "string"
}
```

---

## Respostas da Requisição

Ao realizar a requisição pode-se retornar uma das duas respostas: status de **sucesso** ou status de **erro**.

### Status de Sucesso ✔️

Essa resposta informa o funcionário(a) cadastrado(a) e seu código.

``` JSON
{
  "Status": "Cadastrado realizado com sucesso!",
  "Funcionário(a)": "Peter Jason Quill",
  "Código": "2201"
}
```

### Status de Erro ❌

Essa resposta informa o tipo de erro detectado ao tentar realizar a requisição.

``` JSON
{
  "Status": "Erro ao cadastrar",
  "Tipo de erro": "1062 (23000): Duplicate entry '2201' for key 'dados_pessoais.codigo'",
  "Causas": "Dados duplicados, faltantes ou incorretos"
}
```

---

## Exemplo de Consumo em Python

!!! example "Cadastrando um registro em Python"

    === "main.py"

        ``` py
        # Importando a biblioteca requests para trabalhar com solicitações HTTP
        import requests

        # Link público da API para requisições do tipo POST - Cadastrar um registro
        url = 'https://registros-funcionarios-api.luishperna.com.br/funcionarios/cadastros'

        # Informações no formato JSON a ser enviado na requisição POST - Cadastrar um registro
        informacoes = '''{
            "nome": "Peter Jason Quill",
            "data_nascimento": "1980-12-20",
            "cpf": "123.123.123-12",
            "email": "perterquill@gmail.com",
            "codigo": 2201,
            "cargo": "Desenvolvedor Web",
            "data_inicio": "2022-09-07",
            "data_cancelamento": "NULL",
            "comportamento": "Proativo"
            }'''

        # Resposta da requisição feita a partir do link e JSON passados como parâmetros
        resposta = requests.post(url, data=informacoes)

        # Obtendo o JSON da resposta da API
        dados = resposta.json()

        # Mostrando a resposta no terminal
        print(dados)
        ```

    === "Resposta de Sucesso"

        ```
        {'Status': 'Cadastrado realizado com sucesso!', 'Funcionário(a)': 'Peter Jason Quill', 'Código': '2201'}
        ```

    === "Resposta de Erro"

        ```
        {'Status': 'Erro ao cadastrar', 'Tipo de erro': "1062 (23000): Duplicate entry '2201' for key 'dados_pessoais.codigo'", 'Causas': 'Dados duplicados, faltantes ou incorretos'}
        ```
        
---