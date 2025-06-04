---
layout: center
class: text-center
---

# API Testing
## Let's Remove external tooling from API testing 

<br>

<v-click>
Now that we've automated our setup, let's make API testing just as efficient!
</v-click>

<!--
Story:
I started now in multiple companies and had a lot of experience of changing employees,  but sharing API test files is always a bad experience.

Problem:
- Sharing usually cost money, for example Seats in Postman
- Sharing across teams is always a hassle and every team member has its own approach
- Automation is not seamless
-->

---

# Introduction to .http Files

<div grid="~ cols-2 gap-2">
<div>

## What are .http Files?
- Plain text files with HTTP requests
- IDE-integrated testing
- Version control friendly
- No external dependencies
- Great for documentation

</div>
  <div>

  ## Benefits
  - **Fast execution**
  - **Self-documenting**
  - **Shareable with team**
  - **Environment-specific**
  - **Easy debugging**

  </div>
</div>

---

# Intro into .http files
## Basic structure of a .http file
<br>

```http
[auth.http]
### Get all users

GET {{baseUrl}}/users

Authorization: Bearer {{authToken}}
Accept: application/json
```


<v-click>

**Key Elements:**
- `###` separates requests
- `{{variable}}` for dynamic values
- Standard HTTP headers and methods

</v-click>

---

# Intro into .http files
## Environment configurations

<br>

```json
[http-client.env.json]
{
  "dev": {
    "baseUrl": "https://api-dev.example.com/v1",
    "authToken": "dev_token_here",
    "userId": "123"
  },
  "staging": {
    "baseUrl": "https://api-staging.example.com/v1", 
    "authToken": "staging_token_here",
    "userId": "456"
  },
  "production": {
    "baseUrl": "https://api.example.com/v1",
    "authToken": "prod_token_here",
    "userId": "789"
  }
}
```


---

# Intro into .http files
## Local env file
<br>
```json
[http-client.private.env.json (gitignored)]
{
  "prod": {
    "apiKey": "secret_dev_key",
    "authToken": "actual_dev_token"
  }
}
```
