# Considerações Iniciais

## Atraso ao Consumir a API

Ao consumir a RegistrosFuncionariosAPI poderá haver um certo atraso (delay) de execução acarretado por fatores das hospedagens, tanto do banco de dados, quanto da API em si.

Observação: A primeira executação pode apresentar um aumento nesse atraso pelo fato de estar iniciando a sua execução no servidor hospedado.

---

## Consumindo API no Navegador

Vale ressaltar que os navegadores só aceitam requisições HTTP que utilizam do método `GET`, sendo assim algumas rotas (_URL_) desta API não poderão ser executadas diretamento pelo navegador.

Observação: Os métodos de cada rota estão informados neste **Guia de Uso** e na rota [Home da API](https://registros-funcionarios-api.herokuapp.com).

---

## Indicação ao Inserir Dados Falsos

Para melhor experiência indico o uso de dados falsos que seguem os mesmos padrões/formatos e números de caracteres dos dados verídicos, como mostrado abaixo:

Campos de Preenchimento   | Dados falsos fora dos padrões ❌ | Dados falsos seguindo os padrões ✔️
---------                 | :------:                         | :------:
Código de identificação   | 22sdwA01                         | 2201
Nome                      | senhor das Estrelas              | Peter Jason Quill
Data de nascimento        | 0093-13-31                       | 1980-12-20
CPF                       | 1.23.12-312312                   | 123.123.123-12
Email                     | perteroloko.omelhor              | perterquill@gmail.com
Cargo                     | só nos compiuter                 | Desenvolvedor Web 
Data de início ou entrada | 3000-09-07                       | 2022-09-07
Data de cancelamento      | trabalhando ainda                | NULL
Comportamento             | O melhor do mundo                | Proativo
---