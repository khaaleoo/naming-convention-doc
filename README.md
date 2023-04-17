## Naming Convention

This document describes the naming convention for all projects. Including:
- [Naming Convention](#naming-convention)
  - [I. Redis Key](#i-redis-key)
  - [II. RESTful API Url Naming](#ii-restful-api-url-naming)
  - [III. API Payload](#iii-api-payload)
  - [IV. API Response Message](#iv-api-response-message)

### I. Redis Key
- We use colon sign `:` is a convention when naming keys
- For multi-word keys, we use hyphen sign `-` as a separator<br>
- For example:
    ```
    user:1
    user:1:role
    ```
- Namespace:<br/>
    + Redis server stores keys to all applications. So we need to namespace keys to avoid conflict.
    + For example, we have 2 applications: `app1` and `app2`. We namespace keys as follow:
    ```
    app1:user:1
    app1:user:1:role

    app2:user:1
    app2:user:1:role
    ```

### II. RESTful API Url Naming
- We use hyphen sign `-` as a separator for multi-word URL.<br/>
- All lower case.<br/>
- No extension. Such as `.html`, `.php`, `.jsp`.<br/>
- Status code in body message is same as HTTP status code.<br/>
- Naming convention:<br/>
    + Not good:
    ```
    GET /user/getUserById
    POST /user/createUser
    PUT /user/updateUser
    DELETE /user/deleteUser
    ```
    + Good:
    ```
    GET /user/:id
    POST /user
    PUT /user/:id
    DELETE /user/:id
    ```


### III. API Payload
- We use snake_case for all keys in API response<br/>
- For instance:
    ```
    {
        "user_id": 1,
        "user_name": "John"
    }
    ```

- Instead of:
    ```
    {
        "userId": 1,
        "userName": "John"
    }
    ```

### IV. API Response Message
- With success response, the response should be in the following format:
    ```
    {
        "code": 200,
        "status": "success",
        "data": {
            "user_id": 1,
            "user_name": "John"
        }
    }
    ```
    The `data` key is optional. It depends on the API.
- With error response, the response should be in the following format:
    ```
    {
        "code": 400,
        "status": "error",
        "message": "Bad request"
    }
    ```
    The `message` key is optional. It depends on the API.