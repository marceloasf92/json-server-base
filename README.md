### Níveis de segurança

**600** O usuário deve possuir o recurso para gravar ou ler o recurso.
**644** O usuário deve possuir o recurso para gravar o recurso. Todos podem ler o recurso.
**660** O usuário deve estar logado para gravar ou ler o recurso.

### Cadastro

POST /register

{
"email": "marcelo@mail.com",
"password": "1234"
}

### Login

POST /login

**EXEMPLO**

{
"email": "marcelo@mail.com",
"password": "1234"
}

### Verificar usuário

GET /users/:id - Sem corpo na requisição
Token: accessToken -> Informado no momento do cadastro ou login
Nível de segurança: 600

### Inserir Profile

POST /profile
Token: accessToken -> Informado no momento do cadastro ou login
Nível de segurança: 644

**EXEMPLO**
{
"Name": "Marcelo2",
"Age": 29,
"Etc": "blablabla",
"userId": 1 **Inserir o id do usuário para fazer o cadastro do profile**
}

### Ler Profile

GET /profile - Sem corpo na requisição e sem token
Nível de segurança: 644

### Inserir Bank Account

POST /bankAccount
Token: accessToken -> Informado no momento do cadastro ou login
Nível de segurança: 600

**EXEMPLO**
{
"userId": 1, **Inserir o id do usuário para fazer o cadastro do profile**
"account": 123456,
"id": 1
}

### Ler Bank Account

GET /bankAccount - Sem corpo na requisição
Token: accessToken -> Informado no momento do cadastro ou login
Nível de segurança: 600

### Inserir Comentário

POST /comments
Token: accessToken -> Informado no momento do cadastro ou login
Nível de Segurança: 660

**EXEMPLO**
{
"userId": 1, **Inserir o id do usuário para fazer o cadastro do profile**
"comment": "Parabéns pela promoção!"
}

### Ler Comentário

GET /comments - Sem corpo na requisição
Token: accessToken -> Informado no momento do cadastro ou login
Nível de Segurança: 660
