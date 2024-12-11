# Book Haven - Library Management Project

## Overview
Welcome to **Book Haven**, a beginner-friendly Django project designed to help you learn how to manage a simple library system. In this project, you will create models for books and authors, implement functions to manipulate them, and write tests to ensure everything works correctly.

---

## Project Structure

### Models

#### **Book**
- **Fields**:
  - `title`: The title of the book.
  - `genre`: The genre of the book.
  - `pages`: The number of pages in the book.
  - `author`: A `ForeignKey` to the `Author` model.

#### **Author**
- **Fields**:
  - `name`: The full name of the author.
  - `birth_year`: The year the author was born.
  - `published_books`: The number of books the author has published.

---

## Functions

### **create_author(name, birth_year)**
- **Description**: Creates and returns a new `Author` instance.
- **Parameters**:
  - `name` (str): The name of the author.
  - `birth_year` (int): The year the author was born.
- **Returns**: `Author` instance.

### **create_book(title, genre, pages, author)**
- **Description**: Creates and returns a new `Book` instance.
- **Parameters**:
  - `title` (str): The title of the book.
  - `genre` (str): The genre of the book.
  - `pages` (int): The number of pages in the book.
  - `author` (Author): The `Author` instance associated with the book.
- **Returns**: `Book` instance.

### **list_books_by_author(author)**
- **Description**: Returns all books written by the specified author.
- **Parameters**:
  - `author` (Author): The `Author` instance whose books are to be retrieved.
- **Returns**: QuerySet of `Book` instances.

### **longest_book()**
- **Description**: Returns the `Book` instance with the most pages.
- **Returns**: `Book` instance.

---

## Testing

Write comprehensive tests for the following:

1. **`create_author`**:
   - Verify the `Author` instance is created correctly.
   - Handle edge cases like missing or invalid input.

2. **`create_book`**:
   - Ensure a `Book` instance is created with the correct attributes.
   - Verify the `ForeignKey` relationship to the `Author` model.

3. **`list_books_by_author`**:
   - Confirm that all books by the specified author are returned.
   - Test behavior for authors with no books.

4. **`longest_book`**:
   - Verify the function correctly identifies the book with the most pages.
   - Handle edge cases such as no books in the database.

---

## Additional Tips

- Use Django’s `TestCase` to write your tests.
- Test edge cases thoroughly, such as missing or invalid input.
- Ensure the database relationships are working as expected.



