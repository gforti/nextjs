# Sample App

Using `json-server` we will simulate a local rest API with JWT authentication using `json-server-auth`.

## Running the backend

```sh
$ cd ./server
$ npm install
$ npm start
```

The server will run on port 3004. 
- http://localhost:3004/dessert
- http://localhost:3004/users

For Auth based use http://localhost:3004/660/dessert

The Auth header must be sent.  For more information https://github.com/jeremyben/json-server-auth#readme


Sample code on using Auth headers.

```js
const headersList = {
 "Authorization": "Bearer [token]"
}

fetch("http://localhost:3004/660/dessert", { 
  method: "GET",
  headers: headersList
})
.then(response => response.text())
.then(data => {
  console.log(data)
})
```

### Storing the token
In production it is best practice to store the token using cookies.
session storage and local storage can be a viable solution but many
of the API's used in JavaScript rely on cookies to send credentials.

An Example of this is SSE(Server Sent Events)


### References

- API Data:  https://random-data-api.com/documentation
- Alternative API for users: https://avatars.dicebear.com/
