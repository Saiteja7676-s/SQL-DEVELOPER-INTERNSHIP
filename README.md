# SQL-DEVELOPER-INTERNSHIP
CREATE TABLE Authors (
    author_id INTEGER PRIMARY KEY,
    name TEXT NOT NULL,
    nationality TEXT,
    birth_year INTEGER
);
CREATE TABLE Books (
    book_id INTEGER PRIMARY KEY,
    title TEXT NOT NULL,
    genre TEXT,
    published_year INTEGER,
    isbn TEXT UNIQUE,
    copies_available INTEGER DEFAULT 0
);
CREATE TABLE Book_Author (
    book_id INTEGER,
    author_id INTEGER,
    PRIMARY KEY (book_id, author_id),
    FOREIGN KEY (book_id) REFERENCES Books(book_id),
    FOREIGN KEY (author_id) REFERENCES Authors(author_id)
);
CREATE TABLE Members (
    member_id INTEGER PRIMARY KEY,
    full_name TEXT NOT NULL,
    email TEXT UNIQUE,
    phone TEXT,
    membership_date DATE DEFAULT CURRENT_DATE
);
CREATE TABLE Staff (
    staff_id INTEGER PRIMARY KEY,
    name TEXT,
    role TEXT,
    hire_date DATE
);
CREATE TABLE Borrow_Transactions (
    transaction_id INTEGER PRIMARY KEY,
    book_id INTEGER,
    member_id INTEGER,
    staff_id INTEGER,
    borrow_date DATE DEFAULT CURRENT_DATE,
    return_date DATE,
    FOREIGN KEY (book_id) REFERENCES Books(book_id),
    FOREIGN KEY (member_id) REFERENCES Members(member_id),
    FOREIGN KEY (staff_id) REFERENCES Staff(staff_id)
);


1. What is normalization?
It is the process of organizing data to reduce duplication and improve consistency.

2. Explain primary vs foreign key.
A primary key uniquely identifies a row, while a foreign key links one table to another.

3. What are constraints?
Rules applied to table columns to control what data can be stored.

4. What is a surrogate key?
An auto-generated unique ID used as a primary key.

5. How do you avoid data redundancy?
By using normalization, separate tables, and foreign keys.

6. What is ER diagram?
A visual diagram that shows tables, their fields, and how they are connected.

7. What are the types of relationships in DBMS?
One-to-One, One-to-Many, and Many-to-Many.

8. Explain the purpose of AUTO_INCREMENT.
It automatically gives a unique number to each new row in a table.

9. What is the default storage engine in MySQL?
InnoDB, which supports transactions and foreign keys.

10. What is a composite key?
A primary key made using two or more columns together.





