# LibraryWithExternalData 📚

End-to-End **API Automation Testing** project for a **Library Management System** using **Postman**, **Newman**, and **external test data**.

This collection validates the complete CRUD flow for books with strong assertions, variable handling, and data-driven testing.

---

## 🔧 Tech Stack

      - **Postman** – API request & test scripting
      - **Newman** – CLI execution
      - **JavaScript** – Assertions & logic
      - **CSV (External Data)** – Data-driven testing
      - **Git & GitHub** – Version control
      - **Jenkins (Optional)** – CI integration

---

## 📁 Project Structure

      LibraryWithExternalData/
      │
      ├── LibraryWithExternalData.postman_collection.json
      ├── book_api.csv # External test data
      ├── README.md



---

## 🔄 API Test Flow

1. **AddBook**
   - Creates a new book using external CSV data
   - Stores `book_id` as a collection variable
   - Validates response schema, data types, and performance

2. **GetBookByID**
   - Fetches book details using `book_id`
   - Validates ID match, fields, data types, and `checkedOut` state

3. **UpdateBookById**
   - Updates the `checkedOut` status of the book
   - Ensures book ID remains unchanged
   - Handles empty or non-JSON responses gracefully

4. **DeleteBookById**
   - Deletes the created book
   - Supports `200`, `204`, and `404` responses
   - Validates proper error handling if book is already deleted

---

## 🧪 Key Features

      - ✔ Data-driven testing using **iteration data (CSV)**
      - ✔ Collection-level variable management
      - ✔ Robust assertions with conditional handling
      - ✔ Response time validation
      - ✔ API key authentication
      - ✔ Newman & CI-friendly design

---

## ▶️ How to Run Tests (CLI)

### Prerequisites
    - Node.js installed
    - Newman installed
    
    ```bash
    npm install -g newman


## **Run with External Data**
newman run LibraryWithExternalData.postman_collection.json \
      -d book_api.csv \
      -r cli,htmlextra

## **Authentication**

    Uses API Key authentication
    
    API key is managed via collection variables

## 📊 **Reports**

 ## HTML report can be generated using:

newman run LibraryWithExternalData.postman_collection.json \
      -d book_api.csv \
      -r cli,htmlextra


**Notes**

    All variables are maintained at collection level
    
    Designed to run smoothly via Newman / Jenkins
    
    Supports multiple iterations with external test data
    
    Defensive scripting used to avoid false failures
