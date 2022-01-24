# Capstone - API
Este é o back-end da aplicação cujo objetivo é encontrar e cadastrar receitas que aproveitem ao máximo os ingredientes disponíveis em casa. 

## Endpoints 

A URL base desta API encontra-se em: https://capstone-json.herokuapp.com/

### Criação de usuário

`POST /users - FORMATO DA REQUISIÇÃO`

```JSON
{
	"email": "jondoe@mail.com",
	"password": "987654321"
}
```
Esperamos a seguinte resposta positiva:

`POST /users - FORMATO DA RESPOSTA - STATUS 201`

```JSON
{
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImpvbmRvZUBtYWlsLmNvbSIsImlhdCI6MTY0MzA1NDc0OSwiZXhwIjoxNjQzMDU4MzQ5LCJzdWIiOiIzIn0.00NSDg5P0D7ZhDxVFL4gLn5dXcvCJlUhNFXhNXXESws",
  "user": {
    "email": "jondoe@mail.com",
    "id": 3
  }
}
```
### Login

`POST /login - FORMATO DA REQUISIÇÃO`

```JSON
{
	"email": "jondoe@mail.com",
	"password": "987654321"
}
```
Esperamos a seguinte resposta caso esteja correto:

`POST /login - FORMATO DA RESPOSTA - 200 OK`

```JSON
{
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImpvbmRvZUBtYWlsLmNvbSIsImlhdCI6MTY0MzA1NDk2OCwiZXhwIjoxNjQzMDU4NTY4LCJzdWIiOiIzIn0.neNCWA9WR9CZO6E2Y0IzEUQaECfFqaYz03MQHCXKOy8",
  "user": {
    "email": "jondoe@mail.com",
    "id": 3
  }
}
```
## Criação de receitas

O usuário precisa estar logado para ter acesso, cadastrar, editar e deletar.

`GET /publications - FORMATO DA REQUISIÇÃO`

`POST /publications - FORMATO DA REQUISIÇÃO`

`PATCH /publications/id - FORMATO DA REQUISIÇÃO`

`DELETE /publications/id - FORMATO DA REQUISIÇÃO`
