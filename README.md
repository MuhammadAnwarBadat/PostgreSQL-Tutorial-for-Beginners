# PostgreSQL Tutorial for Beginners

Welcome to the PostgreSQL Tutorial for Beginners! This guide is designed to help anyone with zero knowledge about PostgreSQL get started with this powerful open-source relational database system. We'll cover everything from installation to basic commands, each accompanied by challenges to reinforce your learning.

## 1. Installation of PostgreSQL and pgAdmin4 GUI

Before diving into PostgreSQL, you'll need to set up your environment. This section guides you through installing PostgreSQL and obtaining a free open-source database for practice.

### About PostgreSQL and pgAdmin4 GUI

PostgreSQL is a highly scalable, SQL-compliant, and open-source object-relational database system. It is known for its robustness, strong community, and its ability to handle complex queries and transactions.

## 2. Installation of PostgreSQL and pgAdmin

**PostgreSQL**:
1. Visit the official PostgreSQL website (https://www.postgresql.org/download/) to download the PostgreSQL installer for your operating system.
2. Follow the installation wizard steps. It will prompt you to select components such as the server, pgAdmin, command line tools, etc. Ensure you select pgAdmin, as it's a popular graphical management tool for PostgreSQL.
3. Choose the directory for installation and the data directory where you want your database files to be stored.
4. Set a password for the PostgreSQL superuser (postgres) and note it down securely.
5. Select a port (the default is 5432) on which the PostgreSQL server should listen.
6. Complete the installation.

**pgAdmin4**:
pgAdmin is usually installed as part of the PostgreSQL installation process. If you need to install it separately, visit https://www.pgadmin.org/download/ and follow the instructions for your operating system.

## 3. Getting a Free Open-Source Database for Practice

To effectively practice the SQL commands and challenges outlined in this tutorial, you'll need access to a PostgreSQL database filled with sample data. One of the best ways to get started is by using the **DVD Rental database**, a popular sample database in the PostgreSQL community.

### DVD Rental Database

The DVD Rental database is a lightweight, fictional database that models a DVD rental store. It includes tables for films, customers, inventory, rentals, and more, making it ideal for practicing basic to intermediate SQL queries.

### How to Download and Restore the DVD Rental Database

1. **Download the Database**: 
   - Visit the PostgreSQL Sample Database section on the PostgreSQL Tutorial website (https://www.postgresqltutorial.com/postgresql-sample-database/) to download the DVD Rental database. The database is provided as a `.tar` file, which is a PostgreSQL database backup.

2. **Restore the Database Using pgAdmin**:
   - Open pgAdmin and connect to your PostgreSQL server.
   - Right-click on "Databases" and select "Create" > "Database". Name it `dvdrental` and click "Save".
   - Right-click on the newly created `dvdrental` database, navigate to "Restore", and choose the `.tar` file you downloaded.
   - Click "Restore" to populate the `dvdrental` database with sample data.

3. **Restore the Database Using the Command Line**:
   - Open your command-line tool and navigate to the directory containing the downloaded `.tar` file.
   - Use the following command to restore the database (replace `<username>` with your PostgreSQL username):
     ```
     pg_restore -U <username> -d dvdrental dvdrental.tar
     ```
   - You may be prompted for your PostgreSQL user password. After entering it, the restoration process will begin.

4. **Verifying the Restoration**:

- After restoring the database, you can verify it by connecting to the `dvdrental` database using pgAdmin or the psql command-line interface and executing a simple query, such as:
```sql
SELECT COUNT(*) FROM film;
```
This query counts the number of films in the `film` table, confirming that the sample data is ready for use.

5. **Using the DVD Rental Database for Challenges**:

- Now that you have the DVD Rental database set up, you can start working through the challenges provided in the tutorial. Each challenge is designed to apply the SQL commands you've learned in a practical context, enhancing your understanding and proficiency with PostgreSQL.

Remember, practice is key to mastering SQL, so don't hesitate to experiment with your own queries beyond the provided challenges to explore the full capabilities of PostgreSQL and solidify your learning.

## 4. Basic Commands and Challenges

### SELECT
**Explanation**: To retrieve the title and release year of all films, you would use `SELECT title, release_year FROM film;`.
**Challenge**: Retrieve all columns from the `film` table for films that were released in the year 2006.

### SELECT DISTINCT
**Explanation**: To get a list of unique film ratings, `SELECT DISTINCT rating FROM film;`.
**Challenge**: Find all unique languages in the `film` table by selecting distinct language IDs.

### COUNT
**Explanation**: To count the number of films available, `SELECT COUNT(*) FROM film;`.
**Challenge**: Count the number of actors in the `actor` table.

### SELECT WHERE
**Explanation**: To find films with a rental duration longer than 5 days, `SELECT * FROM film WHERE rental_duration > 5;`.
**Challenge**: Select all customers from the `customer` table who live in the city with city_id = 300.

### ORDER BY
**Explanation**: To order films by release year in descending order, `SELECT * FROM film ORDER BY release_year DESC;`.
**Challenge**: Order the actors by their last name in ascending order and retrieve their first and last names.

### LIMIT
**Explanation**: To get the top 5 longest films, `SELECT * FROM film ORDER BY length DESC LIMIT 5;`.
**Challenge**: Retrieve the first 5 stores from the `store` table by store ID in ascending order.

### BETWEEN
**Explanation**: To select films with a rental rate between $0.99 and $2.99, `SELECT * FROM film WHERE rental_rate BETWEEN 0.99 AND 2.99;`.
**Challenge**: Find all customers with customer IDs between 100 and 200.

### BOOLEAN STATEMENTS (AND, OR, NOT)
**Explanation**: To find films rated 'PG' or 'PG-13' that are not longer than 120 minutes, `SELECT * FROM film WHERE rating IN ('PG', 'PG-13') AND length <= 120;`.
**Challenge**: Select all films that have a replacement cost of more than $20.00 and were released after the year 2000.

### IN
**Explanation**: To select films that are in either 'Action', 'Drama', or 'Horror' categories (assuming you know the category IDs), `SELECT * FROM film WHERE category_id IN (1, 2, 7);`.
**Challenge**: Find all payments made with payment amounts of $5.99, $7.99, or $9.99.

### LIKE and ILIKE
**Explanation**: To find films whose titles start with 'Al', `SELECT * FROM film WHERE title LIKE 'Al%';`.
**Challenge**: Search for customers whose first name contains 'Anne'.

### AGGREGATION FUNCTIONS (SUM, AVG, MAX, MIN, COUNT)
**Explanation**: To calculate the average rental cost of all films, `SELECT AVG(rental_rate) FROM film;`.
**Challenge**: Find the maximum length of films in the database.

### GROUP BY
**Explanation**: To count the number of films in each rating category, `SELECT rating, COUNT(*) FROM film GROUP BY rating;`.
**Challenge**: Group customers by their store ID and count how many customers belong to each store.

### HAVING
**Explanation**: To list categories of films that have more than 50 films, `SELECT category_id FROM film_category GROUP BY category_id HAVING COUNT(*) > 50;`.
**Challenge**: Display the film categories that have an average rental rate of more than $2.00.

### AS (Alias)
**Explanation**: To list the total number of films as "TotalFilms", `SELECT COUNT(*) AS TotalFilms FROM film;`.
**Challenge**: Show the average rental duration of films, labeling the result as "AverageRentalDuration".

## 5. Resources:
1. https://www.w3schools.com/sql/default.asp
2. https://www.youtube.com/watch?v=SpfIwlAYaKk
3. https://www.youtube.com/playlist?list=PLS-kiDL9KrIh-E5eadtnp-8l55H7e2LN0
4. https://www.youtube.com/watch?v=4_Xz4appt-s
