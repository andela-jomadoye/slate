---
title: API Reference

language_tabs:
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome!! This is a Document Management System, with user and documents roles and privileges. Each document has access levels, the document defines which users can access it. 
Also, each document specifies the date it was published, when it was last updated, and the author who published it.

# Tech Stack

* [React] - A javascript library for building user interfaces
* [Redux] - A predictable state container for JavaScript apps.
* [Enzyme] - A JavaScript Testing utility for React
* [node.js] - evented I/O for the backend
* [Express] - fast node.js network app framework
* [Webpack] - the streaming build system
* [Sequelize] - Sequelize is a promise-based ORM for Node.js and io.js.
* [JWT] - To authenticate routes
* [Postgresql and Sequelize ORM]
* [Material-css] - Material design components for react
* [React-materialize] - Material design components for react
* [Babel] - A javascript compiler
* [eslint] - Lints JavaScript
* [Mocha] - JavaScript testing library
* [webpack] - Bundler with plugin system and integrated development server

# Limitations
The limitations to the Document Management System API are as follows:

* Users can only create plain textual documents and retrieve same when needed. 
* Users cannot share documents with people, but can make document `public` to make it available to other users.
* Users login and obtain a token which is verified on every request, but users cannot logout (nullify the token), however tokens become invalid when it expires (after 1 day).

# Contributing
1. Fork this repository to your GitHub account
2. Clone the forked repository and cd into it
3. Create a .env file in the root of the project using the sample .env.sample in the root directory

5. Install all dependencies by running this command below in your terminal/shell
    ````
    npm install
    ````
6. Run the command below in your terminal/shell (initializes and seeds the database tables)
    ```` 
    npm db:migrate
    npm db:seed
    ````
7. To run the development server enter the command below in your terminal/shell
    ````
    npm run start
    ````
8. Run the tests via `npm test` to get familliar with the features of the code base
8. Create your feature branch
9. Commit your changes
10. Push to the remote branch
11. Open a Pull Request

# Endpoints

## Get all roles

> Response

```json
{
  "success": true,
  "message": "This are the roles",
  "roles": [
    {
      "id": 1,
      "title": "Administrator",
      "createdAt": "2017-05-24T01:37:54.742Z",
      "updatedAt": "2017-05-24T01:37:54.742Z"
    },
    {
      "id": 2,
      "title": "Tester",
      "createdAt": "2017-05-24T01:37:54.742Z",
      "updatedAt": "2017-05-24T01:37:54.742Z"
    },
    {
      "id": 3,
      "title": "Basic",
      "createdAt": "2017-05-24T01:37:54.742Z",
      "updatedAt": "2017-05-24T01:37:54.742Z"
    }
  ]
}
```

### Request
- Endpoint: GET: `api/roles`
- Body `(application/json)`

### Response
- Status: `200: OK`
- Body `(application/json)`



> Admin access is required to consume this API.


## Create a role

> Response

```json
{
  "message": "Role created successfully",
  "role": {
    "id": 4,
    "title": "jedidiah is a boss",
    "updatedAt": "2017-05-30T14:02:37.299Z",
    "createdAt": "2017-05-30T14:02:37.299Z"
  }
}
```

### Request
- Endpoint: POST: `api/roles`
- Body `(application/json)`

### Response
- Status: `201: Created`
- Body `(application/json)`



> Admin access is required to consume this API.


## Delete a role

> Response

```json
{
  "message": "Role deleted succesfully",
  "role": {
    "id": 4,
    "title": "jedidiah is a boss",
    "createdAt": "2017-05-30T14:02:37.299Z",
    "updatedAt": "2017-05-30T14:02:37.299Z"
  }
}
```

### Request
- Endpoint: DELETE: `api/roles`
- Body `(application/json)`

### Response
- Status: `200: OK`
- Body `(application/json)`



> Admin access is required to consume this API.

## Get all users

> Response

```json
[
  {
    "id": 3,
    "fullname": "dede",
    "username": "dede",
    "email": "Lyric86@yahoo.com",
    "roleId": 1,
    "password": "$2a$08$nlXfmAjSxaJj/fK7VHWvk.WzbVBokhCI5W1XulIxlf/jcWaSwBWHm",
    "createdAt": "2017-05-26T16:41:07.724Z",
    "updatedAt": "2017-05-26T16:41:07.732Z"
  },
  {
    "id": 20,
    "fullname": "NightWatch User",
    "username": "NightWatchUser",
    "email": "NightWatchUser@night.com",
    "roleId": 1,
    "password": "$2a$08$XbtFkkgN3FNnzmoZUi7v0.KNjh5bKjLoNgxCvU4BQF/2gRrFLChzu",
    "createdAt": "2017-05-26T16:41:07.724Z",
    "updatedAt": "2017-05-26T16:41:35.807Z"
  },
  {
    "id": 4,
    "fullname": "Omadoye Jedidiah",
    "username": "SlimJed1",
    "email": "jedd@email.com",
    "roleId": 3,
    "password": "$2a$08$9ddxfFTraUVlyTNYtAS5p.TOe7zcoaFOkHpfSwpkGo5utr1.hMCwG",
    "createdAt": "2017-05-27T11:28:54.221Z",
    "updatedAt": "2017-05-27T11:28:54.221Z"
  },
  {
    "id": 5,
    "fullname": "q",
    "username": "q",
    "email": "qq1be@email.com",
    "roleId": 3,
    "password": "$2a$08$aqrxrBo317gF6Y/wGeOfSOpKBiMEkI/E7o8Ir/qHkNGM.NwPEUzji",
    "createdAt": "2017-05-28T15:45:42.218Z",
    "updatedAt": "2017-05-28T15:45:42.218Z"
  },
  {
    "id": 6,
    "fullname": "w",
    "username": "w",
    "email": "w@ww.com",
    "roleId": 3,
    "password": "$2a$08$ikcs8grjG5GBeMdxlunzNuV7Ec2FMexEVRUGuEjCTS5aPTIr07B3q",
    "createdAt": "2017-05-28T15:45:58.112Z",
    "updatedAt": "2017-05-28T15:45:58.112Z"
  }
]
```

### Request
- Endpoint: GET: `api/users`
- Body `(application/json)`

### Response
- Status: `200: OK`
- Body `(application/json)`



> Admin access is required to consume this API.

## Get a user by Id

> Response

```json
{
  "username": "dede",
  "email": "Lyric86@yahoo.com",
  "fullname": "dede",
  "id": 3,
  "roleId": 1,
  "documents": []
}
```

### Request
- Endpoint: GET: `api/users/:userId`
- Body `(application/json)`

### Response
- Status: `200: OK`
- Body `(application/json)`



> Owner or Admin access is required to consume this API.

## Delete a user by Id

> Response

```json
{
  "message": "User deleted successfully."
}
```

### Request
- Endpoint: DELETE: `api/users/:userId`
- Body `(application/json)`

### Response
- Status: `200: OK`
- Body `(application/json)`



> Owner or Admin access is required to consume this API.

## Update a user by Id

> Response

```json
{
  "message": "User updated successfully.",
  "user": {
    "id": 3,
    "fullname": "Omadoye Jedidiah",
    "username": "dede",
    "email": "Lyric86@yahoo.com",
    "roleId": 1,
    "password": "$2a$08$LOovNmHFZdlDOgASnlQ94.cAZkPwJT333yr5zKTRyki7i5bqixyMi",
    "createdAt": "2017-05-26T16:41:07.724Z",
    "updatedAt": "2017-05-30T14:29:32.320Z",
    "documents": []
  }
}
```

### Request
- Endpoint: PUT: `api/users/:userId`
- Body `(application/json)`

### Response
- Status: `200: OK`
- Body `(application/json)`



> Owner or Admin access is required to consume this API.

## Get all Documents

> Response

```json
{
  "message": "Document is shown below",
  "document": [
    {
      "id": 2,
      "title": "Fake title document",
      "body": "Ea dolor commodi adipisci rerum perferendis. Est cum repellendus animi soluta. Possimus et sint dolores non omnis. Voluptate ipsum eum sit ut et voluptatibus dolore ea voluptatum.",
      "access": "public",
      "ownerRoleId": 2,
      "createdAt": "2017-05-26T16:41:07.867Z",
      "updatedAt": "2017-05-26T16:41:07.867Z",
      "userId": 1,
      "User": {
        "fullname": "Omadoye Jedidiah"
      }
    },
    {
      "id": 3,
      "title": "test document 2",
      "body": "Necessitatibus et eligendi nostrum. Debitis dolores suscipit sit. Recusandae ipsam in et illo.",
      "access": "public",
      "ownerRoleId": 2,
      "createdAt": "2017-05-26T16:41:07.867Z",
      "updatedAt": "2017-05-26T16:41:07.867Z",
      "userId": 1,
      "User": {
        "fullname": "Omadoye Jedidiah"
      }
    },
    {
      "id": 4,
      "title": "test document 3",
      "body": "Non at et et veniam est laboriosam debitis molestias. Quas repellat animi nobis sapiente dolores. Molestias aut quaerat ducimus saepe ut recusandae porro nisi. Non explicabo excepturi quia. Eum in repellendus eligendi dolores nostrum laboriosam. Necessitatibus earum similique qui soluta recusandae dolor dolore.",
      "access": "public",
      "ownerRoleId": 2,
      "createdAt": "2017-05-26T16:41:07.867Z",
      "updatedAt": "2017-05-26T16:41:07.867Z",
      "userId": 1,
      "User": {
        "fullname": "Omadoye Jedidiah"
      }
    },
    {
      "id": 5,
      "title": "test document 4",
      "body": "Cum consectetur omnis illum facilis atque et explicabo deleniti. Dolorem quo ab repudiandae qui est. Repellendus error sit ut. Quia sit sed suscipit iusto.",
      "access": "public",
      "ownerRoleId": 2,
      "createdAt": "2017-05-26T16:41:07.867Z",
      "updatedAt": "2017-05-26T16:41:07.867Z",
      "userId": 1,
      "User": {
        "fullname": "Omadoye Jedidiah"
      }
    },
    {
      "id": 6,
      "title": "test document 5",
      "body": "Aspernatur commodi odio quibusdam expedita harum enim quaerat modi. Sint nihil possimus sit atque quibusdam. Deleniti repellendus illum repellendus ut et quos est autem. Accusantium qui maxime ipsam labore voluptatem id ea. Cumque pariatur voluptatem illum et porro quas et minus molestiae. In fuga quasi.",
      "access": "public",
      "ownerRoleId": 2,
      "createdAt": "2017-05-26T16:41:07.867Z",
      "updatedAt": "2017-05-26T16:41:07.867Z",
      "userId": 1,
      "User": {
        "fullname": "Omadoye Jedidiah"
      }
    }
  ]
}
```

### Request
- Endpoint: GET: `api/documents`
- Body `(application/json)`

### Response
- Status: `200: OK`
- Body `(application/json)`



> Admin access is required to consume this API.

## Get a Document by Id

> Response

```json
{
  "message": "This is your document.",
  "document": {
    "id": 3,
    "title": "test document 2",
    "body": "Necessitatibus et eligendi nostrum. Debitis dolores suscipit sit. Recusandae ipsam in et illo.",
    "access": "public",
    "ownerRoleId": 2,
    "createdAt": "2017-05-26T16:41:07.867Z",
    "updatedAt": "2017-05-26T16:41:07.867Z",
    "userId": 1
  }
}
```

### Request
- Endpoint: GET: `api/documents/:documentId`
- Body `(application/json)`

### Response
- Status: `200: OK`
- Body `(application/json)`



> Owner or Admin access is required to consume this API.

## Delete a Document by Id

> Response

```json
{
  "message": "Document deleted successfully."
}
```

### Request
- Endpoint: DELETE: `api/documents/:documentId`
- Body `(application/json)`

### Response
- Status: `200: OK`
- Body `(application/json)`



> Owner or Admin access is required to consume this API.

## Update a Document by Id

> Response

```json
{
  "message": "Document successfuly updated",
  "document": {
    "id": 5,
    "title": "test document 4",
    "body": "Cum consectetur omnis illum facilis atque et explicabo deleniti. Dolorem quo ab repudiandae qui est. Repellendus error sit ut. Quia sit sed suscipit iusto.",
    "access": "public",
    "ownerRoleId": 2,
    "createdAt": "2017-05-26T16:41:07.867Z",
    "updatedAt": "2017-05-26T16:41:07.867Z",
    "userId": 1
  }
}
```

### Request
- Endpoint: PUT: `api/documents/:documentId`
- Body `(application/json)`

### Response
- Status: `200: OK`
- Body `(application/json)`



> Owner or Admin access is required to consume this API.

## Search a Document by title

> Response

```json
{
  "message": "This is your document.",
  "document": [
    {
      "id": 14,
      "title": "test document 13",
      "body": "Est mollitia aliquam repellendus incidunt reprehenderit odit. Veritatis aliquid nemo et rerum rerum. Nostrum alias fugiat debitis in temporibus blanditiis voluptates velit et. Eum consectetur nesciunt consectetur dolores velit earum amet. Expedita reiciendis laudantium delectus sed rem magni provident corrupti. Et illum iure velit dicta dignissimos qui eaque.",
      "access": "public",
      "ownerRoleId": 2,
      "createdAt": "2017-05-26T16:41:07.867Z",
      "updatedAt": "2017-05-26T16:41:07.867Z",
      "userId": 1,
      "User": {
        "fullname": "Omadoye Jedidiah"
      }
    }
  ]
}
```

### Request
- Endpoint: PUT: `api/search/documents/?q={doctitle}`
- Body `(application/json)`

### Response
- Status: `200: OK`
- Body `(application/json)`



> Owner or Admin access is required to consume this API.

## Search a User by Username

> Response

```json
{
  "message": "This is your user.",
  "user": [
    {
      "id": 4,
      "fullname": "Omadoye Jedidiah",
      "username": "SlimJed1",
      "email": "jedd@email.com",
      "roleId": 3,
      "password": "$2a$08$9ddxfFTraUVlyTNYtAS5p.TOe7zcoaFOkHpfSwpkGo5utr1.hMCwG",
      "createdAt": "2017-05-27T11:28:54.221Z",
      "updatedAt": "2017-05-27T11:28:54.221Z",
      "documents": []
    },
    {
      "id": 7,
      "fullname": "Omadoye Jedidiah",
      "username": "SlimJed11",
      "email": "jedd1@email.com",
      "roleId": 1,
      "password": "$2a$08$2XUYM2X9ESdwdSip6mgbC.aNUflqXfA/tywRfNNQZcxd5UKJIO8Dm",
      "createdAt": "2017-05-30T14:02:10.970Z",
      "updatedAt": "2017-05-30T14:02:10.970Z",
      "documents": []
    }
  ]
}
```

### Request
- Endpoint: PUT: `api/documents/:username`
- Body `(application/json)`

### Response
- Status: `200: OK`
- Body `(application/json)`



> Owner or Admin access is required to consume this API.
