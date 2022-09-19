# JSONServer + JWT Auth

Una falsa REST API usando json-server con JWT autenticación.

End-points implementados: test_users_login, users

## Instalación

```bash
$ npm install
$ npm run start-auth
```

## Cómo ir a test_users_login/

Usted puede logearse enviando una solicitud POST:

```
POST http://localhost:8000/test_users_login

con los siguientes datos en el body

```
{
  "username": "admin",
  "password":"admin"
}

Usted deberá recibir un token de acceso con el siguiente formato

{
   "access_token": "<ACCESS_TOKEN>"
}
```

## Cómo ir a users/

Usted puede ir a users usando el header Authorization: Bearer <ACCESS_TOKEN> para enviar una solicitud GET, POST o DELETE

```
conseguir lista de usuarios:

GET http://localhost:8000/users

enviar el parámetro _page en la url si desea paginar la información (cada página contiene 10 items por defecto), no enviarlo recibirá toda la información completa, por ejemplo:

GET http://localhost:8000/users?_page=1

enviar en Headers:
Authorization: Bearer <ACCESS_TOKEN>

```
crear un usario nuevo:

POST http://localhost:8000/users

enviar en Headers:
Authorization: Bearer <ACCESS_TOKEN>

enviar en el Body por ejemplo:
{
	"first_name": "Carlos",
	"last_name": "Carlos",
	"company": 1,
	"email": "carlos@example.com"
}

```
eliminar un usuario existente:

DELETE http://localhost:8000/users/:id

enviar en Headers:
Authorization: Bearer <ACCESS_TOKEN>

enviar el id del usuario en la url, por ejemplo:
http://localhost:8000/users/1
```