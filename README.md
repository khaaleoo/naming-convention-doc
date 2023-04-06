## Naming Convention

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

### II. API Response
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