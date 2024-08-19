# Contact API Spec

## Create Contact API

Endpoint : POST /api/contacts

Headers :

- Authorization : token

Request Body :

```json
{
  "firstName": "Beby",
  "lastName": "Kurniawan",
  "email": "bebykurniawan2006@gmail.com",
  "phone": "1232144"
}
```

Request Body Success :

```json
{
  "data": {
    "id": 1,
    "firstName": "Beby",
    "lastName": "Kurniawan",
    "email": "bebykurniawan2006@gmail.com",
    "phone": "1232144"
  }
}
```

Request Body Error :

```json
{
  "errors": "Email is not valid format"
}
```

## Update Contact API

Endpoint : PUT /api/contacts:id

Headers :

- Authorization : token

Request Body :

```json
{
  "firstName": "Beby",
  "lastName": "Kurniawan",
  "email": "bebykurniawan2006@gmail.com",
  "phone": "1232144"
}
```

Request Body Success :

```json
{
  "data": {
    "firstName": "Beby",
    "lastName": "Kurniawan",
    "email": "bebykurniawan2006@gmail.com",
    "phone": "1232144"
  }
}
```

Request Body Error :

```json
{
  "errors": "Email is not valid format"
}
```

## Get Contact API

Endpoint : Get /api/contacts:id

Headers :

- Authorization : token

Request Body Success :

```json
{
  "data": {
    "id": 1,
    "firstName": "Beby",
    "lastName": "Kurniawan",
    "email": "bebykurniawan2006@gmail.com",
    "phone": "1232144"
  }
}
```

Request Body Error :

```json
{
  "errors": "Contact is not found"
}
```

## Search Contact API

Endpoint : GET /api/contacts

Headers :

- Authorization : token

Query Params :

- name : Search by firstName or lastName, using like, optional
- email : Search by email using like, optional
- phone : Search by phone using like, optional
- page : number of page, default 1
- size : size per page, default 10

Request Body Success:

```json
{
  "data": [
    {
      "id": 1,
      "firstName": "Beby",
      "lastName": "Kurniawan",
      "email": "bebykurniawan2006@gmail.com",
      "phone": "1232144"
    },
    {
      "id": 2,
      "firstName": "Beby",
      "lastName": "Kurniawan",
      "email": "bebykurniawan2006@gmail.com",
      "phone": "1232144"
    }
  ],
  "paging" : {
    "page" : 1,
    "total_page" : 3,
    "total_item" : 30 
  }
}
```

## Remove Contact API

Endpoint : DELETE /api/contacts

Headers :

- Authorization : token

Request Body Success :

```json
{
  "data": "OK"
}
```

Request Body Error :

```json
{
  "errors": "Contact is not found"
}
```
