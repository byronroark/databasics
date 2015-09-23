## Databasics

Fork this repository into your own github profile.

Before closing the homework assignment issue:

- Update this README as follows:
  - [X] For each question (just after or below the question itself) include the SQL you wrote to generate the answer
  - [X] For each question (just after or below the question itself) include the *answer* to the question asked.

- Also:
  - [ ] Commit the updated `store.sqlite3` database file
  - [ ] Include a link to your forked repo in the comments when closing the issue.


NOTE: To run sqlite with this database: `sqlite3 store.sqlite3`

NOTE: You may want to keep a backup of the `store.sqlite3` file in case you damage the file. *OR* you can use the command `git checkout store.sqlite3` to undo any changes to the database file since the fork or your last commit.

## Explorer Mode

- [X] How many users are there?  
  `SELECT count(*) FROM "users";`  
  *ANSWER = 50*
- [X] What are the 5 most expensive items?  
  `SELECT * FROM "items" ORDER BY "price" DESC LIMIT 5;`  
  *ANSWER = Small Cotton Gloves, Small Wooden Comput, Awesome Granite Pan, Sleek Wooden Hat, Ergonomic Steel Car*
- [X] What's the cheapest book? (Does that change for "category is exactly 'book'" versus "category contains 'book'"?)  
  `SELECT * FROM "items" WHERE category LIKE "%books%" ORDER BY "price" LIMIT 1;`  
  *ANSWER = Ergonomic Granite Chair*
- [X] Who lives at "6439 Zetta Hills, Willmouth, WY"? Do they have another address?  
  `SELECT "first_name", "last_name", "street", "city", "state", "zip" FROM "users" AS u JOIN "addresses" AS a on u.id = a.user_id WHERE "street"="6439 Zetta Hills";`  
  *ANSWER = Corrine Little*
- [X] Correct Virginie Mitchell's address to "New York, NY, 10108".  
  `UPDATE addresses SET city="New York", zip="10108" WHERE user_id=(SELECT id FROM users WHERE first_name = "Virginie");`  
  *ANSWER = Virginie Mitchell 12263 Jake Crossing New York 10108
Virginie Mitchell 83221 Mafalda Canyo New York 10108*
- [X] How much would it cost to buy one of each tool?  
  `SELECT SUM(price) FROM items WHERE category LIKE "Tools%"`  
  *ANSWER = 24605*
- [X] How many total items did we sell?  
  `SELECT SUM(quantity) FROM orders;`  
  *ANSWER = 2125*
- [X] How much was spent on books?  
  `SELECT category, sum(price) FROM items JOIN orders ON items.id = orders.item_id WHERE category="Books";`  
  *ANSWER = 420566*
- [X] Simulate buying an item by inserting a User for yourself and an Order for that User.  
  `INSERT INTO users (first_name, last_name, email) VALUES ("Byron", "Roark", "byronroark@gmail.com");`  
  `INSERT INTO orders (item_id, quantity, user_id, created_at) VALUES ("78", "2", "51", datetime());`  
  
## Adventure Mode

- [ ] What item was ordered most often? Grossed the most money?
- [ ] What user spent the most?
- [ ] What were the top 3 highest grossing categories?
