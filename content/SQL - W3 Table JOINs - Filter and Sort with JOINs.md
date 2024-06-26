# Filter and Sort with JOINs

<iframe src="https://egator.hosted.panopto.com/Panopto/Pages/Embed.aspx?id=68a81ea3-08b4-42c1-8467-b0fb000ebe38&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all" height="405" width="720" style="border: 1px solid #464646;" allowfullscreen allow="autoplay" aria-label="Panopto Embedded Video Player"></iframe>

## Using WHERE and ORDER BY with JOINs

We can still utilize the clauses from previous lessons to filter and sort on joined data. 

For this example, we'll use the `Authors` and `Books` tables with a one-to-many relationship. Each author can write multiple books, but each book has only one author.
### Authors Table:
|AuthorID|AuthorName|
|---|---|
|1|J.K. Rowling|
|2|George Orwell|
|3|Leo Tolstoy|
### Books Table:
| BookID | Title | AuthorID |
| ---- | ---- | ---- |
| 101 | Harry Potter | 1 |
| 102 | 1984 | 2 |
| 103 | Animal Farm | 2 |
| 104 | War and Peace | 3 |
| 105 | Anna Karenina | 3 |
### SQL JOIN with Filter and Sort

Create a query that joins these tables and:
1. Filters to show only books written by a specific author (e.g., George Orwell).
2. Sorts the results by the book's title.

```sql
SELECT Books.Title, Authors.AuthorName FROM Books
JOIN Authors ON Books.AuthorID = Authors.AuthorID
WHERE Authors.AuthorName = 'George Orwell'
ORDER BY Books.Title;
```
##### Expected Output:
|Title|AuthorName|
|---|---|
|Anna Karenina|Leo Tolstoy|
|War and Peace|Leo Tolstoy|
### Explanation:

1. **SELECT Clause**: Retrieves the book titles and their corresponding author names.
2. **JOIN Operation**: Joins the `Books` and `Authors` tables using the `AuthorID` as the common field.
3. **WHERE Clause**: Filters the results to include only those books written by 'Leo Tolstoy'.
4. **ORDER BY Clause**: Sorts the resulting list of books by their titles in ascending order.

`JOIN` must come before our `WHERE` and `ORDER BY` clauses because we need to have access to both the `AuthorName` and `Title` in order to filter and sort them.

# Practice Questions

3. Write a query to list all products supplied by 'Enchanted Wares Ltd.' including the supplier name along with the product names and prices. Sort the results by product name (Z to A).

4. Write a query to list all suppliers and their products, sorted by the supplier's name and product price.

# Lessons
- [[SQL - W3 Table JOINs - Introduction]]
- [[SQL - W3 Table JOINs - DROP Tables]]
- [[SQL - W3 Magic Store Database Overview]]
- [[SQL - W3 Table JOINs - One-to-Many Relationships]]
- [[SQL - W3 Table JOINs - JOIN Tables with One-to-Many Relationships]]
- SQL - W3 Table JOINs - Filter and Sort with JOINs
- Next: [[SQL - W3 One-to-Many JOINs - Practice Assignment]]