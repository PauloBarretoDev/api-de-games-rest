# API de Games
Esta API é utilizada para estudos.
## Endpoints
### GET /games
Esse endpoint é responsável por retornar a listagem de todos os games cadastrados no banco de dados
#### Parametros
Nenhum
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber a listagem de todos os games.
Exemplo de resposta:

```
[
    {
        "id": 23,
        "title": "Red Dead Redemption 2",
        "year": 2018,
        "price": 60
    },
    {
        "id": 65,
        "title": "The witcher 3",
        "year": 2015,
        "price": 40
    },
    {
        "id": 2,
        "title": "Minecraft",
        "year": 2012,
        "price": 20
    }
]
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autentificação da requisição. Motivos: Token inválido, Token expirado.

Exemplo de resposta: 
```
{
    "err": "Token inválido!"
}
```

## Endpoints
### POST /auth
Esse endpoint é responsável por fazer o processo de login.
#### Parametros
email: E-mail do usuário cadastrado no sistema.

password: Senha do usuário cadastrado no sistema, com aquele determinado e-mail.

Exemplo:
```
{
    "email": "paulo@gmail.com",
    "password": "123456"
}
```

#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber o token JWT para conseguir acessar endpoints protegidos na API.

Exemplo de resposta:

```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJwYXVsb0BnbWFpbC5jb20iLCJpYXQiOjE2NTg5NTA1OTAsImV4cCI6MTY1OTEyMzM5MH0.elukytbBqCVBR1-Ef8FeBDrL3viu5jEJbamWDxKJibk"
}
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autentificação da requisição. Motivos: Senha ou e-mail incorretos.

Exemplo de resposta: 
```
{err: "Credenciais inválidas!"}
```
