# Capstone Api

A API possui 4 endpoints, register, login, products e cart

### Cadastro

POST /register <br/>

Para realizar o registro é necessário informar o email e a senha da seguinte maneira:<br/>
{<br/>
"email": "exemplo@email.com",<br/>
"password":"123456"<br/>
}<br/>

### Login

POST /login <br/>

A realizção do login deve ser feita de maneira análoga ao de registro, passando as mesmas informações:<br/>
{<br/>
"email": "exemplo@email.com",<br/>
"password":"123456"<br/>
}<br/>

### Produtos

-> Carregamento

GET /produtos <br/>

É necessário a autorização pelo token para visualização<br/>

### Cart

-> Carregamento

GET /cart <br/>

É necessário autorização para acessar esse recurso<br/>

-> Adicionar item ao carrinho

POST /cart <br/>

O cadastro do item ao carrinho requer autorização e deve ser feito passando as informações:<br/>
{<br/>
"title": "Hamburguer",<br/>
"id": 1,<br/>
"price": 19,90,<br/>
"url_image": "https://image.com.br"<br/>
}<br/>
