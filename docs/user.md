## User API Spec

## Register User API

Endpoint :  POST /api/users/

Request Body : 
```json
{
    "username" : "beby",
    "password" : "rahasia",
    "name" : "beby kurniawan"
}
```

Response Body Success : 
```json 
{
"data" : {
    "username" : "Beby",
    "name" : "Beby Kurniawan"
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
Endpoint :  POST /api/users/login

Request Body : 
```json 
{
"username" : "beby",
"password" : "rahasia"
}
```
Request Body Success : 
```json 
{
"data" : {
    "token" : "unique-token"
    }
}
```
Request Body Error : 
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
"name" : "Beby", // optional
"password" : "new password" // optional
}
```

Request Body Success : 
```json 
{
"data" : {
    "username" : "beby",
    "name" : "Beby Kurniawan Lagi"
}
}
```

Request Body Error : 
```json
{
"errors" : "Name length max 100"
}
```

## Get User API

Endpoint : GET /api/users/current

Headers : 
- Authorization : token

Response Body Success:
```json
{
"data" : {
    "username" : "beby",
    "name" : "Beby Kurniawan"
}
}
```

Response Body Error :
```json 
{
"errors" : "Unauthorized"
}
```

## Logout User API

Endpoint : DELETE /api/users/logout

Headers : 
- Authorization : token


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