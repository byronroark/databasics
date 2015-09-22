## Databasics

Fork this repository into your own github profile.

Before closing the homework assignment issue:

- Update this README as follows:
  - [ ] For each question (just after or below the question itself) include the SQL you wrote to generate the answer
  - [ ] For each question (just after or below the question itself) include the *answer* to the question asked.

- Also:
  - [ ] Commit the updated `store.sqlite3` database file
  - [ ] Include a link to your forked repo in the comments when closing the issue.


NOTE: To run sqlite with this database: `sqlite3 store.sqlite3`

NOTE: You may want to keep a backup of the `store.sqlite3` file in case you damage the file. *OR* you can use the command `git checkout store.sqlite3` to undo any changes to the database file since the fork or your last commit.

## Explorer Mode

- [X] How many users are there?  
  `select count(*) from "users";`
- [X] What are the 5 most expensive items?  
  `select * from "items" order by "price" desc limit 5;`
- [X] What's the cheapest book? (Does that change for "category is exactly 'book'" versus "category contains 'book'"?)  
  `select * from "items" where category like "%books%" order by "price" limit 1;`
- [X] Who lives at "6439 Zetta Hills, Willmouth, WY"? Do they have another address?  
  `select "first_name", "last_name", "street", "city", "state", "zip" from "users" as u join "addresses" as a on u.id = a.user_id;`
- [ ] Correct Virginie Mitchell's address to "New York, NY, 10108".
- [ ] How much would it cost to buy one of each tool?
- [ ] How many total items did we sell?
- [ ] How much was spent on books?
- [ ] Simulate buying an item by inserting a User for yourself and an Order for that User.

## Adventure Mode

- [ ] What item was ordered most often? Grossed the most money?
- [ ] What user spent the most?
- [ ] What were the top 3 highest grossing categories?
