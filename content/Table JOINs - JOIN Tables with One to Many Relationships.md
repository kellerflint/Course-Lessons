
# Table JOINs - JOIN Tables with One to Many Relationships

Video Embedding

## Understanding JOINs in One to Many Relationships

Given our bookstore database example from the previous lesson:
### Authors Table:
| AuthorID | AuthorName |
| ---- | ---- |
| 1 | J.K. Rowling |
| 2 | George Orwell |
| 3 | Leo Tolstoy |
### Books Table:
|BookID|Title|AuthorID|
|---|---|---|
|101|Harry Potter|1|
|102|1984|2|
|103|Animal Farm|2|
|104|War and Peace|3|
|105|Anna Karenina|3|

To retrieve data that spans across these two tables, we use the SQL JOIN operation. Let's see how we can use the JOIN command to fetch the list of books along with their authors' names.

```sql
SELECT Books.Title, Authors.AuthorName FROM Books
JOIN Authors ON Books.AuthorID = Authors.AuthorID; 
```
##### Expected Output:
| Title | AuthorName |
| ---- | ---- |
| Harry Potter | J.K. Rowling |
| 1984 | George Orwell |
| Animal Farm | George Orwell |
| War and Peace | Leo Tolstoy |
| Anna Karenina | Leo Tolstoy |
This query effectively combines data from the `Books` and `Authors` tables by linking books to their respective authors by the AuthorID. The `JOIN` operation, facilitated by the `ON` clause, ensures that each book is matched with its author. The selected columns `Books.Title` and `Authors.AuthorName` are displayed in the resulting output.

To understand exactly how the SQL JOIN command works in our Authors and Books example, let's break down the query piece by piece.
#### 1. `SELECT Books.Title, Authors.AuthorName`
- **Purpose**: This part of the query specifies what data we want to retrieve. Here, we are asking for the `Title` from the `Books` table and the `AuthorName` from the `Authors` table.
- **Action**: It tells the database to look at these two columns and prepare to output data from them.
#### 2. `FROM Books`
- **Purpose**: This clause specifies the primary table from which to retrieve data, which in this case is the `Books` table.
- **Action**: It sets the context for the SQL query, indicating that the data will be selected from the `Books` table.
#### 3. `JOIN Authors`
- **Purpose**: Indicates that we want to combine rows from the `Books` table with rows from the `Authors` table.
- **Action**: It initiates the action to merge data from the two tables based on a related column.
#### 4. `ON Books.AuthorID = Authors.AuthorID`
- **Purpose**: This is the condition on which the JOIN will be performed. To function, the JOIN needs to know what column it can use to match records between the two tables. `ON` is used to map this relationship. In this case, we are joining the tables based on the `AuthorID` column, which is common to both tables.
- **Action**: It matches each row in the `Books` table with the corresponding row in the `Authors` table where the `AuthorID` is the same.



Back: [[Table JOINs - One to Many Relationships]] | Next: [[Table JOINs - Many to Many Relationships]]