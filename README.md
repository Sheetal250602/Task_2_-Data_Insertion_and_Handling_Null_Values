# Task_2_-Data_Insertion_and_Handling_Null_Values
# Using 'Library' database and two tables 'Author' and 'Books' by using MySQL Workbench.

CREATE DATABASE LibraryDB;
USE LibraryDB;

CREATE TABLE Author(
Author_id INT PRIMARY KEY,
first_name VARCHAR(50),
last_name VARCHAR(50)
);

CREATE TABLE Books(
Book_id INT PRIMARY KEY,
Title VARCHAR(100),
published_year DATE,
Author_id INT NOT NULL, -- NOT NULL constraints ensures that a column cannot contain NULL values
FOREIGN KEY(Author_id) REFERENCES Author(Author_id)
);

# Data Insertion:

INSERT INTO Author Values
(101, 'William', 'Shakespeare'),
(102, 'Rabindranath', 'Tagore'),
(103, 'Hariwanshrai', 'Bachchan');

INSERT INTO Books Values
(1, 'Romeo And Juliet', '1597-01-01', 101),
(2, 'Gitanjali', '1910-01-01', 102),
(3, 'Madhushala', '1935-01-01', 103);

SELECT * FROM Author;

# <img width="310" height="154" alt="image" src="https://github.com/user-attachments/assets/6adaf701-2009-467f-9038-c8964b17c1fd" />

SELECT * FROM Books;

# <img width="416" height="132" alt="image" src="https://github.com/user-attachments/assets/a4a783aa-1577-4f76-b909-724a2a3c3015" />

# UPDATING DATA into 'Books' Table with WHERE clause:
-- Updating Title from "MADHUSHALA" to "AGNEEPATH"--

UPDATE Books
SET Title = 'Agneepath'
WHERE Book_id = 3;

SELECT * FROM Books;

# <img width="415" height="138" alt="image" src="https://github.com/user-attachments/assets/ca9a1209-1bc1-41d9-84fc-766e3a012670" />

# UPDATING DATA into 'Author' Table:
-- Updating Author's last_name From "SHAKESPEARE" to "BLAKE"--

UPDATE Author
SET last_name = 'Blake'
WHERE Author_id = 101;

# Adding column DOB:
ALTER TABLE Author
ADD COLUMN DOB DATE;

SELECT * FROM Author;

# <img width="348" height="139" alt="image" src="https://github.com/user-attachments/assets/8e97d2aa-c086-46a0-9048-9740e8ae1fb6" />

# Handling NULL Values by Using "IS NOT NULL" and "IS NULL":
SELECT * FROM Author 
WHERE DOB IS NOT NULL;

# <img width="332" height="77" alt="image" src="https://github.com/user-attachments/assets/6cabaff0-a217-4b59-aca2-20fe20317b1f" />

SELECT * FROM Author 
WHERE DOB IS NULL;

# <img width="363" height="147" alt="image" src="https://github.com/user-attachments/assets/3a538222-820e-436f-94eb-9dec4dd2fdda" />

# DELETING Data from Author Table with WHERE clause:

DELETE FROM Books 
WHERE Book_id = 1;

SELECT * FROM Books;

# <img width="380" height="111" alt="image" src="https://github.com/user-attachments/assets/3a64e458-26e9-4c54-b75e-ca3320ff7823" />
