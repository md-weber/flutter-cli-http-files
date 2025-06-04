---
theme: default
class: text-center
lineNumbers: true
drawings:
  persist: false
transition: fade
title: Elevate Your Flutter Project
mdc: true
---

# Elevate Your Flutter Project
## Custom CLIs and API Testing with .http Files

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Let's dive in! <carbon:arrow-right class="inline"/>
  </span>
</div>

---

# <tabler-user-circle /> About Me
<div grid="~ cols-2">
  <ul>
    <li>Mobile Engineer @ **sevdesk GmbH**</li>
    <li>Creator of **Flutter Explained** on YouTube</li>
    <li>Full Stack Dev with 10+ years experience</li>
    <li>Proud father of two</li>
    <li>Gamer — Still playing WC3 <tabler-swords /></li>
  </ul>
  <div>
    <img class="rounded-xl" src="../../assets/img/about-me.jpg" width=250 />
  </div>
</div>

---
src: ./pages/cli/what-we-cover-today.md
---

---
src: ./pages/cli/why-custom-clis-matter.md
---

--- 
src: ./pages/cli/getting-started-with-dart-clis.md
---

---
src: ./pages/cli/pubspec-yaml.md
---

---
src: ./pages/cli/activate-and-executable.md
---

---
src: ./pages/api-testing/01-intro-to-http-files.md
---

---
src: ./pages/api-testing/02-advanced-http-files.md
---

--- 
src: ./pages/api-testing/03-benefits-http-files.md
---


# Testing API Responses

```http
### Create product with validation
POST {{baseUrl}}/products
Content-Type: application/json
Authorization: Bearer {{authToken}}

{
  "name": "Flutter Development Book",
  "price": 29.99,
  "category": "books",
  "inStock": true
}

> {%
  client.test("Product creation", function() {
    // Status code validation
    client.assert(response.status === 201, "Should return 201 Created");
    
    // Response structure validation
    const product = response.body;
    client.assert(product.id, "Product should have an ID");
    client.assert(product.name === "Flutter Development Book");
    client.assert(product.price === 29.99);
    client.assert(product.createdAt, "Should have creation timestamp");
    
    // Store for subsequent requests
    client.global.set("productId", product.id);
  });
%}

###

### Verify product was created
GET {{baseUrl}}/products/{{productId}}
Authorization: Bearer {{authToken}}

> {%
  client.test("Product retrieval", function() {
    client.assert(response.status === 200);
    client.assert(response.body.name === "Flutter Development Book");
  });
%}
```

---

# Organizing API Tests by Feature

## File Structure
```
api_tests/
├── auth/
│   ├── login.http
│   ├── register.http
│   └── password-reset.http
├── users/
│   ├── crud-operations.http
│   ├── profile-management.http
│   └── permissions.http
├── products/
│   ├── catalog.http
│   ├── inventory.http
│   └── pricing.http
└── shared/
    ├── http-client.env.json
    └── http-client.private.env.json
```

<v-click>

<div class="mt-4 p-4 bg-blue-500 rounded-lg">
<strong>💡 Organization Tip:</strong> Group related endpoints together and use descriptive filenames
</div>

</v-click>


---

# Demo Time! <tabler-rocket />
## Let's See It in Action

<br>

1. Create a .http file
2. Test it against some value
3. Reuse values from a prev. call

---

# Getting Started Checklist (1/2)

- [ ] **Set up Dart CLI project structure**
  - Create `bin/` directory with CLI scripts
  - Configure `pubspec.yaml` with executables
  - Install necessary dependencies

<v-click>

- [ ] **Create your first automation CLI**
  - Start with project setup automation
  - Add environment configuration
  - Include error handling and logging
</v-click>

---

# Getting Started Checklist (2/2)
- [ ] **Organize .http files**
  - Create `api_tests/` directory structure
  - Set up environment configurations
  - Write your first API test

<v-click>

- [ ] **Integrate with your workflow**
  - Add CLI commands to team documentation
  - Set up pre-commit/pre-push hooks
  - Configure CI/CD integration

</v-click>

---
layout: center
class: text-center
---

# Thank You! <tabler-confetti/>

## Ready to elevate your Flutter development?

<div class="pt-12">
  <div class="mb-4">
    <strong>Questions? Let's discuss!</strong>
  </div>
  
  <div class="flex items-center justify-center space-x-4">
    <div><tabler-mail /> max.weber@flutter-explained.dev</div>
    <div><tabler-brand-bluesky /> @flutter-explained.dev</div>
  </div>
</div>

<div class="pt-8">
  <span class="text-sm opacity-75">
    Slides available at: <a href="https://github.com/md-weber/flutter-cli-http-slides">github.com/md-weber/flutter-cli-http-slides</a>
  </span>
</div>

