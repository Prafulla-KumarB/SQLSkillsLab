Welcome to SQLSkillsLab, my personal repository for learning and mastering SQL. Here, I'm documenting my journey as I dive into the world of data analysis, SQL, and database management. I've embarked on this learning path with a specific goal in mind: to enhance my skills and knowledge in data analysis, ultimately aiming to secure a job in this exciting field.

## Why Data Analysis?

Data analysis has always fascinated me. In today's data-driven world, the ability to extract valuable insights from datasets is not just a valuable skill but a necessity. I've recognized the immense potential of data analysis to drive informed decision-making, solve complex problems, and unlock opportunities across various industries.

## Learning Resources

My SQLSkillsLab repository is a collection of materials, exercises, and projects I've undertaken on my journey. These resources include:

- **Coursera Courses:** I've enrolled in data analysis courses on Coursera, which have provided structured learning and hands-on experience.

- **SQL Bolt Exercises:** I've honed my SQL skills through interactive exercises on SQL Bolt, mastering the art of querying and manipulating data.

- **Additional Learning Materials:** I've supplemented my learning with books, articles, and tutorials from experts in the field.

## What You'll Find Here

In this repository, you'll discover:

- **SQL Queries:** A library of SQL queries I've written and optimized, ranging from basic to advanced topics.

- **Data Analysis Projects:** Real-world projects where I've applied my SQL knowledge to analyze datasets and draw meaningful conclusions.

- **Documentation:** Detailed explanations, code samples, and tips related to SQL and data analysis concepts.

Feel free to explore, learn, and collaborate! Your feedback and contributions are highly encouraged.

Let's embark on this data analysis journey together. I hope my experiences and learnings inspire you in your pursuit of data-driven excellence.

Happy coding!

**Schema (PostgreSQL v13)**

    CREATE SCHEMA dannys_diner;
    SET search_path = dannys_diner;
    
    CREATE TABLE sales (
      "customer_id" VARCHAR(1),
      "order_date" DATE,
      "product_id" INTEGER
    );
    
    INSERT INTO sales
      ("customer_id", "order_date", "product_id")
    VALUES
      ('A', '2021-01-01', '1'),
      ('A', '2021-01-01', '2'),
      ('A', '2021-01-07', '2'),
      ('A', '2021-01-10', '3'),
      ('A', '2021-01-11', '3'),
      ('A', '2021-01-11', '3'),
      ('B', '2021-01-01', '2'),
      ('B', '2021-01-02', '2'),
      ('B', '2021-01-04', '1'),
      ('B', '2021-01-11', '1'),
      ('B', '2021-01-16', '3'),
      ('B', '2021-02-01', '3'),
      ('C', '2021-01-01', '3'),
      ('C', '2021-01-01', '3'),
      ('C', '2021-01-07', '3');
     
    
    CREATE TABLE menu (
      "product_id" INTEGER,
      "product_name" VARCHAR(5),
      "price" INTEGER
    );
    
    INSERT INTO menu
      ("product_id", "product_name", "price")
    VALUES
      ('1', 'sushi', '10'),
      ('2', 'curry', '15'),
      ('3', 'ramen', '12');
      
    
    CREATE TABLE members (
      "customer_id" VARCHAR(1),
      "join_date" DATE
    );
    
    INSERT INTO members
      ("customer_id", "join_date")
    VALUES
      ('A', '2021-01-07'),
      ('B', '2021-01-09');

---

**Query #1**

    SELECT
      	product_id,
        product_name,
        price
    FROM dannys_diner.menu
    ORDER BY price DESC
    LIMIT 5;

| product_id | product_name | price |
| ---------- | ------------ | ----- |
| 2          | curry        | 15    |
| 3          | ramen        | 12    |
| 1          | sushi        | 10    |

---

[View on DB Fiddle](https://www.db-fiddle.com/f/2rM8RAnq7h5LLDTzZiRWcd/138)
