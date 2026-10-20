<h1 align="center">Book Store Management</h1>

<p align="center">
    <img width="100%" src="src/main/resources/static/images/bg.png">
</p>

Server-rendered web application for managing a book collection, built with **Spring Boot**, **Spring Data JPA**
and **Thymeleaf** on MySQL.

## Features

- Register, edit and delete books (name, author, page count, publisher)
- Browse all books, authors and publishers
- Personal "My Books" list: add a book from the catalogue, remove it again

## Architecture

```
controller  ──►  service  ──►  repository (Spring Data JPA)  ──►  MySQL
    │
    └── Thymeleaf templates (home, books, bookRegister, bookEdit, myBooks, authors, publishers)
```

| Route | Purpose |
|---|---|
| `/` | Home |
| `/book_register` · `/save` | Book form and save |
| `/books` | Catalogue |
| `/editBook/{id}` · `/deleteBook/{id}` | Edit or delete a book |
| `/my_books` · `/my_books/{id}` · `/deleteMyBook/{id}` | Personal list |
| `/authors` · `/publishers` | Author and publisher lists |

## Tech

Java 11 · Spring Boot · Spring Web · Spring Data JPA (Hibernate) · Thymeleaf · MySQL · Maven

## Run

Create a MySQL database named `book2`, then:

```bash
export DB_USERNAME=root
export DB_PASSWORD=<your-password>
./mvnw spring-boot:run
```

The app runs on `http://localhost:8080`; tables are created by Hibernate (`ddl-auto=update`).

*Archived learning project.*
