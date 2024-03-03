# User API Spec

## Register User API

Endpoint : POST /api/users

Request Body :
```json
{
    "username" : "aryaprdni",
    "password" : "rahasia",
    "name" : "Arya Perdana Irawan"
}
```

Response Body Success :
```json 
{
    "data" : {
        "username" : "aryaprdni",
        "name" : "Arya Perdana Irawan"
    },
}
```

Response Body Error :
```json
{
    "errors" : "Username already registered"
}
```

## Login User API

Endpoint : POST /api/users/login

Request Body :

```json
{
    "username" : "aryaprdni",
    "password" : "rahasia",
}
```

Response Body Success :

```json
{
    "data" : {
        "token" : "unique-token"
    }
}
```

Response Body Errors :

```json
{
    "errors" : "Username or password wrong"
}
```

## Update User API

Endpoint : PATCH /api/users/current

Headers :
- Authorization : token

Request Body :

```json
{
    "name" : "Arya Perdana Irawan lagi", // optional
    "password" : "new password" // optional
}
```

Response Body Success :

```json
{
    "data" : {
        "username": "arya",
        "name" : "Arya Perdana Irawan"
    }
}
```

Response Body Error :

```json
{
    "errors" : "Name length max 100"
}
```

## Get User API

Endpoint : GET /API/users/current

Headers :
- Authorization : token

Response Body Success :

```json
{
    "data" : {
        "username" : "arya",
        "name" : "Arya Perdana Irawan"
    }
}
```

Response Body Error :

```json

{
    "erros" : "Unauthorized"
}

```

## Logout User API

Headers :
- Authorization : token

Endpoint : DELETE /api/users/logout

Response Body Success :

```json
{
    "data" : "OK"
}
```

Response Body Error :

```json
{
    "errors" : "Unauthorized"
}
```