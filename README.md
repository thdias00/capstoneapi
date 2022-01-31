# Capstone - API
Este é o back-end da aplicação cujo objetivo é encontrar receitas que aproveitem ao máximo os ingredientes disponíveis em casa. 
Além disso, o usuário pode ver publicações no feed tal como cadastrá-las, editá-las e deletá-las.

## Endpoints 

A URL base desta API encontra-se em: https://capstone-json.herokuapp.com/

### Criação de usuário

`POST /users - FORMATO DA REQUISIÇÃO`

```JSON
{
	"email": "jondoe@mail.com",
	"password": "987654321",
	"username": "johnjohn",
	"profile": "https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fcdn.onlinewebfonts.com%2Fsvg%2Fimg_132120.png&f=1&nofb=1"
}
```
Esperamos a seguinte resposta positiva:

`POST /users - FORMATO DA RESPOSTA - STATUS 201`

```JSON
{
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImpvbmRvZUBtYWlsLmNvbSIsImlhdCI6MTY0MzY2NTI4NSwiZXhwIjoxNjQzNjY4ODg1LCJzdWIiOiIxMCJ9.tae-IFm75M8AYzlBSwjwnqvDbwrcykdo7jHrZoQPe_0",
  "user": {
    "email": "jondoe@mail.com",
    "username": "johnjohn",
    "profile": "https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fcdn.onlinewebfonts.com%2Fsvg%2Fimg_132120.png&f=1&nofb=1",
    "id": 10
  }
}
```
### Edição de usuário - Uso para escolher ícone de perfil

`PATCH /users/:id - FORMATO DA REQUISIÇÃO`

```json
{
	"profile": "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fstatic.vecteezy.com%2Fsystem%2Fresources%2Fpreviews%2F000%2F571%2F419%2Foriginal%2Fvector-network-icon.jpg&f=1&nofb=1"
}
```

Esperamos a seguinte resposta:

`PATCH /users/:id - FORMATO DA RESPOSTA - STATUS 200`

```json
{
  "email": "jondoe@mail.com",
  "password": "$2a$10$kqXOyfz5MGUIhCuOovkbWODmDGtn2/6eGvaTigUBRf0QRK56RWy3i",
  "username": "johnjohn",
  "profile": "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fstatic.vecteezy.com%2Fsystem%2Fresources%2Fpreviews%2F000%2F571%2F419%2Foriginal%2Fvector-network-icon.jpg&f=1&nofb=1",
  "id": 10
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
## Publicações do Feed

O usuário precisa estar logado para ter acesso, cadastrar, editar e deletar.

### Visualização de publicações

`GET /publications - FORMATO DA REQUISIÇÃO`

Nós receberemos a seguinte resposta:

`GET /publications - 200 OK`

```json

[
  {
    "userId": 3,
    "icon": "",
    "username": "",
    "photo": "",
    "category": "",
    "description": "",
    "id": 1
  },
  {
    "userId": 3,
    "icon": "",
    "username": "",
    "photo": "",
    "category": "Lorem",
    "description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
    "id": 2
  },
  {
    "userId": 3,
    "icon": "",
    "username": "",
    "photo": "",
    "category": "Lorem",
    "description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
    "id": 3
  },
  {
    "userId": 5,
    "icon": "",
    "username": "",
    "photo": "",
    "category": "Lorem",
    "description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
    "id": 4
  }
]

```

### Cadastro de publicação

`POST /publications - FORMATO DA REQUISIÇÃO`

```json
{
    "userId": 5,
    "icon": "",
    "username": "",
    "photo": "",
    "category": "Lorem",
    "description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna."
}
```

Esperamos a seguinte resposta caso dê tudo certo:

`POST/ publications - FORMATO DA RESPOSTA - 201 created`

```json
{
  "userId": 5,
  "icon": "",
  "username": "",
  "photo": "",
  "category": "Lorem",
  "description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
  "id": 4
}
```

### Edição de publicação

`PATCH /publications/:id - FORMATO DA REQUISIÇÃO`

```json
{
	 "userId": 5,
   "icon": "",
   "username": "",
   "photo": "",
   "category": "Lorem ipsum",
   "description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
	"id": "4"
}
```

Esperamos a seguinte resposta: 

`PATCH /publications/:id - FORMATO DA RESPOSTA - 200 OK`

```json
{
  "userId": 5,
  "icon": "",
  "username": "",
  "photo": "",
  "category": "Lorem ipsum",
  "description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
  "id": 4
}
```

### Deleção de publicação

`DELETE /publications/:id - FORMATO DA REQUISIÇÃO`

```json
{
	 "userId": 5,
   "icon": "",
   "username": "",
   "photo": "",
   "category": "Lorem ipsum",
   "description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
	"id": "4"
}
```
Após a deleção esperamos a seguinte resposta: 

`DELETE /publications/:id - FORMATO DA RESPOSTA - 200 OK`

```json
{}
```
