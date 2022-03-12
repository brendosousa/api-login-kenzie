<h1 align="center">
  Devs Network - API
</h1>

<h2 align="center">Uma API para os devs da Kenzie Academy Brasil registrarem suas redes sociais e profissionais</h2>

## **Endpoints**

A API tem um total de 4 endpoints, sendo para cadastro, login, cadastro de redes e listagem de tecnologias de um usuário. A base da API é https://api-login-kenzie.herokuapp.com/

<h2 align ='center'> Cadastro de usuário </h2>

O usuário pode fazer um cadastro utilizando o seguinte endpoint:

`POST /register - FORMATO DA REQUISIÇÃO`

```json
{
  "email": "brendo@email.com",
  "password": "123456",
  "name": "Brendo Sousa"
}
```

Caso tudo ocorra bem, a resposta será a seguite:

`POST /users - FORMATO DA RESPOSTA - STATUS 201`

```json
{
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImJyZW5kb0BlbWFpbC5jb20iLCJpYXQiOjE2NDcwNDg3ODQsImV4cCI6MTY0NzA1MjM4NCwic3ViIjoiMSJ9.4PNVP1i5QnxZbx926OQXKpXxEh2REzrALHEDXdVmL48",
  "user": {
    "email": "brendo@email.com",
    "name": "Brendo Sousa",
    "id": 1
  }
}
```

<h2 align ='center'> Login </h2>

O usuário pode fazer login utilizando o seguinte endpoint

`POST /login - FORMATO DA REQUISIÇÃO`

```json
{
  "email": "brendo@email.com",
  "password": "123456"
}
```

Caso tudo dê certo, a resposta será:

`POST /login - FORMATO DA RESPOSTA - STATUS 201`

```json
{
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImJyZW5kb0BlbWFpbC5jb20iLCJpYXQiOjE2NDcwNTA3MTYsImV4cCI6MTY0NzA1NDMxNiwic3ViIjoiMSJ9.xRKf-SHt2n-_odp83k6Vu6okUo0ocuaUlpW4sS7a71U",
  "user": {
    "email": "brendo@email.com",
    "name": "Brendo Sousa",
    "id": 1
  }
}
```

<h2 align ='center'> Cadastrar redes sociais </h2>

O usuário pode cadastrar uma rede social do seguinte modo, após estar logado:

`POST /networks - FORMATO DA REQUISIÇÃO`

```json
{
  "network": "LinkedIn",
  "link": "https://www.linkedin.com/in/brendo-sousa/",
  "userId": 1
}
```

Caso tudo ocorra bem, a resposta será a seguite:

`POST /networks - FORMATO DA RESPOSTA - STATUS 201`

```json
{
  "network": "LinkedIn",
  "link": "https://www.linkedin.com/in/brendo-sousa/",
  "userId": 1,
  "id": 1
}
```

<h2 align ='center'> Listar redes de um usuário </h2>

Qualquer usuário, mesmo sem estar logado, pode ver as redes sociais de um usuário cadastrado da seguinte forma, utilizando query params:

`GET /networks?userId=1 - FORMATO DA RESPOSTA - STATUS 200`

```json
[
  {
    "network": "LinkedIn",
    "link": "https://www.linkedin.com/in/brendo-sousa/",
    "userId": 1,
    "id": 1
  }
]
```
