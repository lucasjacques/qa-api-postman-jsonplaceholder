# Lucas Jacques' API Testing with Postman

This project contains API automated tests using Postman to validate
endpoints of the JSONPlaceholder fake REST API.

---

## 📌 Automated Scenarios

-   ✅ Retrieve posts (GET)
-   ✅ Retrieve single post by ID
-   ✅ Validate invalid requests (404 scenarios)
-   ✅ Response structure and data validation

---

## ⚙️ Prerequisites

-   Postman
-   Optional: Newman (for CLI execution)

---

## 📄 Test Documentation

Detailed descriptions of each API request, including purpose, scenarios, and validations, can be found in:

- `documentation-en.md` (English)
- `documentation-pt-BR.md` (Brazilian Portuguese)


---

## 🚀 Setup

1.  Clone this repository
2.  Import the Postman collection into Postman

---

## ▶️ Running the tests

### Postman (GUI)

-   Open Postman
-   Import the collection
-   Run requests individually or via **Collection Runner**

---

### Newman (CLI)

``` bash
npm install -g newman
```

Run the collection:

``` bash
newman run postman_collection.json
```

---

## 📁 Project structure

``` bash
  README.md
  LICENSE
  documentation-en.md
  documentation-pt-BR.md
  postman/
    collection.json
```

---

## 🧠 Technical approach

-   Use of **collection variables** for reusability (`baseUrl`,
    `postId`)
-   Validation of status codes and response bodies
-   Separation of success and failure scenarios
-   Clear and descriptive test names

---

## ⚠️ API notes

The JSONPlaceholder API is a **fake API**, meaning:

-   Some operations (POST, PUT, DELETE) do not persist data
-   Responses are mocked for testing purposes

Tests are designed considering these limitations.

---

## 📦 Installation Summary

``` bash
# Install Newman (optional)
npm install -g newman

# Run collection
newman run <collection-file>.json
```

---

## 💡 Notes

-   Tests are designed to be simple, readable, and maintainable
-   Focus on demonstrating API testing fundamentals and QA best
    practices
-   Suitable for showcasing API testing skills in a QA portfolio
