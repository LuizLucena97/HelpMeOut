# HelpMeOut
API do projeto HelpMeOut

## Tarefas

- [ ] CRUD de categorias 
- [ ] CRUD de Movimentações
- [ ] CRUD de Usuário
- [ ] Dashboard

## Documentações da API

Endpoint
- [Listar todas as categorias]
(#listar-todas-as-cateogrias)
- [Apagar categoria](#apagar-categoria)
-[Atualizar Categoria]

### Listar todas as cateogrias

`GET` /categoria

Retorna um array com todas as categorias cadastradas.

#### Exemplo de resposta

```js
[
    {
        "id": 1,
        "nome": "Alimentacao",
        "icone": "fast-food"
    }
]
```

#### Código de Status

|código|Descrição|
|------|---------|
|200|Os dados das categorias foram retornados sucesso
|401| Acesso negado. Você deve se autenticar

### Cadastrar categorias

`POST`/categoria

Cria uma nova categoria com os dados enviados no corpoo da requisição

#### Corpo da requisição

|campo|tipo|obrigatório|descrição|
|-----|----|:-----------:|---------|
|nome|string|✅|um nome curto para a categoria.
|icone|string|❌|o nome do icone de acordo com a biblioteca material Icons

```js
    {
        "nome": "Alimentacao",
        "icone": "fast-food"
    }
```

#### Exemplo de resposta

```js

    {
        "id": 1,
        "nome": "Alimentacao",
        "icone": "fast-food"
    }

```

#### Código de Status

|código|Descrição|
|------|---------|
|201| Categoria cadastrada com sucesso
|400| Dados enviados são inválidos. Verifique o corpo da requisição.
|401| Acesso negado. Você deve se autenticar


### Detalhes da categoria

`GET` / categoria / `{id}`

#### Exemplo de resposta

```js
// requisição para/categoria/1
    {
        "nome": "Alimentacao",
        "icone": "fast-food"
    }
```

#### Código de Status

|código|Descrição|
|------|---------|
|200|Os dados das categorias foram retornados sucesso
|401| Acesso negado. Você deve se autenticar
|404| Não existe categoria com o id informado 

### Apagar Categoria

`DELETE` /categoria/ `{id}`

Apaga a categoria com o `ìd` especificado no paâmetro path

#### Código de Status

|código|Descrição|
|------|---------|
|204| Categoria foi apagada com sucesso
|401| Acesso negado. Você deve se autenticar
|404| Não existe categoria com o id informado 


### Atualizar categoria

`PUT` /categoria/`{id}`

Altera os dados da catregoria especificada no `id`, utilizando as informações enviadas no corpo da requisição.

#### Corpo da requisição

|campo|tipo|obrigatório|descrição|
|-----|----|:-----------:|---------|
|nome|string|✅|um nome curto para a categoria.
|icone|string|✅|o nome do icone de acordo com a biblioteca material Icons

```js
    {
        "nome": "Alimentacao",
        "icone": "fast-food"
    }
```

#### Exemplo de resposta

```js

    {
        "id": 1,
        "nome": "Alimentacao",
        "icone": "fast-food"
    }

```

#### Código de Status

|código|Descrição|
|------|---------|
|204| Categoria alterada com sucesso
|401| Acesso negado. Você deve se autenticar
|404| Não existe categoria com o id informado 