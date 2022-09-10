# Como Consultar um Registro ![imagem-versao](https://img.shields.io/badge/GET-2094f3?style=flat-square)


=== "main.py"

    ``` py
    import requests

    cpf = "123.123.123-12"
    url = f'https://registros-funcionarios-api.luishperna.com.br/funcionarios/consultas/{cpf}'

    resposta = requests.get(url)
    dados = resposta.json()

    print(dados)
    ```

=== "saída"

    ``` 
    {'codigo': '2201', 'nome': 'Peter Jason Quill', 'data_nascimento': '1980-12-20', 'cpf': '123.123.123-12', 'email': 'perterquill@gmail.com', 'cargo': 'Desenvolvedor Web', 'data_inicio': '2022-09-07', 'data_cancelamento': 'None', 'comportamento': 'Proativo'}
    ```

=== "erro"

    ``` 
    {'Status': 'Erro ao consultar', 'Tipo de erro': 'CPF incorreto ou não cadastrado'}
    ```