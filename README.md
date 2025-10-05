# 🧾 Inventory Management System

This repository contains the code for a simple Inventory Management System built with **Spring Boot** and **MongoDB**.  
It provides endpoints to create, read, update, and delete product records, manage stock dynamically, and monitor low-stock products.

---

## Features

- Add new products (POST)
- View all products (GET)
- View a single product by ID (GET)
- Update product details (PUT)
- Delete a product (DELETE)
- Increase or decrease stock (POST)
- Fetch low-stock products (GET)

---

## Technologies Used

- **Backend Framework:** Spring Boot 3  
- **Database:** MongoDB  
- **Build Tool:** Maven  
- **Language:** Java 17  
- **API Testing:** Postman  
- **Version Control:** Git & GitHub  

---

## Prerequisites

Before setting up the project, ensure you have the following installed on your system:

1. [Java 17](https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html)  
2. [Maven](https://maven.apache.org/download.cgi)  
3. [MongoDB](https://www.mongodb.com/try/download/community)  
4. Git  

---

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/Rakesh-honawad/inventory-management-system.git
cd inventory-management-system
```
### 2. Open the Project

Open the project in IntelliJ IDEA or VS Code (with Java extensions).
Wait for Maven to download all dependencies automatically.

### 3. Start MongoDB

Make sure MongoDB is running locally:

mongosh


Verify the available databases:
```bash
show dbs
```
### 4. Configure the Application

In src/main/resources/application.properties:
```bash
spring.application.name=inventory-management
spring.data.mongodb.uri=mongodb://localhost:27017/inventorydb
```
### 5. Run the Application

Start the application using:
```bash
mvn spring-boot:run
```

Or run InventoryManagementApplication from your IDE.
Once started, visit: http://localhost:8080

### 6. Test the Endpoints

You can test the API endpoints using tools like Postman
 or curl.

Sample Endpoints

**Create a Product**
```bash
POST http://localhost:8080/api/products
Body (JSON):
{
  "name": "Wireless Mouse",
  "description": "Logitech M170",
  "stockQuantity": 25,
  "lowStockThreshold": 10
}
```

**Get All Products**
```bash
GET http://localhost:8080/api/products
```

**Get a Product by ID**
```bash
GET http://localhost:8080/api/products/{id}
```

**Update a Product**
```bash
PUT http://localhost:8080/api/products/{id}
Body (JSON):
{
  "name": "Updated Mouse",
  "description": "Updated Description",
  "stockQuantity": 30,
  "lowStockThreshold": 5
}
```

**Delete a Product**
```bash
DELETE http://localhost:8080/api/products/{id}
```

**Increase Stock**
```bash
POST http://localhost:8080/api/products/{id}/increase?amount=10
```

 **Decrease Stock**
```bash
POST http://localhost:8080/api/products/{id}/decrease?amount=5
```

**Fetch Low-Stock Products**
```bash
GET http://localhost:8080/api/products/low-stock
```
### 7. Verify Data in MongoDB

After inserting data through Postman, check the database:
```bash
use inventorydb
show collections
db.products.find().pretty()
```

### 8. Push to GitHub

After making changes:
```bash
git add .
git commit -m "Your commit message"
git push origin main
```

### Folder Structure
```plaintext
inventory-management/
├── src/
│   ├── main/
│   │   ├── java/com/example/inventory_management/
│   │   │   ├── controller/     # REST Controllers
│   │   │   ├── model/          # Product entity
│   │   │   ├── repository/     # MongoDB repositories
│   │   │   ├── service/        # Business logic
│   │   │   └── InventoryManagementApplication.java
│   │   └── resources/
│   │       └── application.properties
├── pom.xml                     # Maven build file
└── README.md                   # Project documentation

```
