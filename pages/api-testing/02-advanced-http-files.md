# Advanced .http Features
## Response testing

```{10-18}
### Login and get token
POST {{baseUrl}}/auth/login
Content-Type: application/json

{
  "email": "admin@example.com",
  "password": "admin123"
}

> {%
  client.test("Login successful", function() {
    client.assert(response.status === 200, "Response status should be 200");
    client.assert(response.body.token, "Token should be present");
  });
  
  client.global.set("authToken", response.body.token);
  client.global.set("userId", response.body.user.id);
%}
```

---

# Advanced .http Features
## Use of the token

```{1,2,7,8}
  client.global.set("authToken", response.body.token);
  client.global.set("userId", response.body.user.id);
[...]

### Get User information

GET {{baseUrl}}/users/{{userId}}
Authorization: Bearer {{authToken}}

> {%
  client.test("Get user profile", function() {
    client.assert(response.status === 200);
    client.assert(response.body.id == client.global.get("userId"));
  });
%}
```
