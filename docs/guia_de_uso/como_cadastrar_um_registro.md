# Como Cadastrar um Registro ![imagem-versao](https://img.shields.io/badge/POST-43bf86?style=flat-square)

=== "main.py"

    ``` py
    import requests

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

    url = 'https://registros-funcionarios-api.luishperna.com.br/funcionarios/cadastros'

    resposta = requests.post(url, data=informacoes)

    dados = resposta.json()

    print(dados)
    ```

=== "saída"

    ```
    {'Status': 'Cadastrado realizado com sucesso!', 'Funcionário(a)': 'Peter Jason Quill', 'Código': '2201'}
    ```

=== "erro"

    ```
    {'Status': 'Erro ao cadastrar', 'Tipo de erro': "1062 (23000): Duplicate entry '2201' for key 'dados_pessoais.codigo'", 'Causas': 'Dados duplicados, faltantes ou incorretos'}

    ```
    