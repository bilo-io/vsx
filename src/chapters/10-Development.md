# 10. Development

> A guide to frontend development with Visual Studio Code.
>
> - Back to the [README](../../README.md)
> - Check out the [Guides](./guides/CryptoCharts.md)
> - Also check out [Appendices](./appendix/CodingStandards.md)

- [1. Environment](./1-Environment.md)
- [2. ES6, Typescript & NodeJS](./2-Javascript.md)
- [3. React](./3-React.md)
- [4. Redux](./4-Redux.md)
- [5. Styling](./5-Styling.md)
- [6. Storybook](./6-Storybook.md)
- [7. Testing](./7-Testing.md)
- [8. Git](./8-Git.md)
- [9. Webpack](./9-Webpack.md)
- `10. Development`

## Overview

This chapter outlines various aspects you should be aware of, regarding web development.

**Frontend**

Herewith we pretty much summarize the fundamentals of React frontend development, with modern technologies (again... at the time of writing).

**Backend**

The back-end is a whole other rabbit whole in itself, assuring for business logic and data persistance, and many other aspects. With this users can view the same information on different devices, using the same login, for example.

**Devops**

Another important aspect to the whole stack is the devops/cloud engineering, which helps keep your app/platform running and scaling based on the needs of its users.

### HTTP

One common way to communicate with decoupled parts of the stack is with HTTP (Hyper Text Transfer Protocol), which is the most common way web applications send data between the front and back end.

#### HTTP Requests

There are a few more requests, but these are the most common ones:

|Method|Description|Example|
|:-|:-|:-|
|`GET`|Retrieve data from the server|Url: `http://api.test/todos`|
|`POST`|Create a new resource|Url: `http://api/test/todos`, Body*|
|`PUT`|Update (completely override object with new one)|Url: `http://api/test/todos/1`, Body*|
|`PATCH`|Update (update arbitrary, specified fields of resource)|Url: `http://api/test/todos/1`, Body*|
|`DELETE`|Delete resource|Url: `http://api/test/todos/1`|

Example JSON `Body*`:

```json
{
    “title”: “NewTodoItem”,
    “text”: “NewTodoDescription”
}
```

#### HTTP Status Codes

- **2xx: Success**
  - `200: OK`  a successful request, e.g when fetching data with GET
  - `201: Created` when a new resource is created, e.g with a POST
  - `204: No Content` when there is not content, but the request completed successfully
- **3xx: No change**
  - `301: Moved Permanently` when the requested resource is invalid and that the request should be redirected to a new, “proper” URL.
- **4xx: User Error**
  - `400: Bad Request` when the user specified incorrect/missing info in a request
  - `401: Unauthorized` when the user must be authenticated to complete the request
  - `403: Forbidden` when the user lacks permissions for the particular action
  - `404: Not Found` when the requested resource does not exist

- **5xx: Server Error**
  - `500: Internal Server Error` when an exception is thrown on the server
  - `504: Gateway Timeout` when the request takes too long to complete

### DevTools

- Inspector
  - selectors
- Network tab
  - filtering
  - request / status
  - request body (payload)
  - response (preview)
- JS Console
  - JS Playground
