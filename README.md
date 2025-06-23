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


