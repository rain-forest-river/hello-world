# Logs Analysis Project

You've been hired onto a team working on a newspaper site. The user-facing newspaper site frontend itself, and the database behind it, are already built and running. You've been asked to build an internal reporting tool that will use information from the database to discover what kind of articles the site's readers like.

The database contains newspaper articles, as well as the web server log for the site. The log has a database row for each time a reader loaded a web page. Using that information, your code will answer questions about the site's user activity.

The program you write in this project will run from the command line. It won't take any input from the user. Instead, it will connect to that database, use SQL queries to analyze the log data, and print out the answers to some questions.

To start on this project, you'll need database software (provided by a Linux virtual machine) and the data to analyze.

## The virtual machine
This project makes use of the same Linux-based virtual machine (VM) as the preceding lessons.

you need to bring the virtual machine back online with vagrant up. Then log into it with vagrant ssh.

## Download the data
Download a file named newsdata.sql from the project link. Unzip this file after downloading it.

Put this file into the vagrant directory, which is shared with your virtual machine.

To build the reporting tool, you'll need to load the site's data into your local database.

To load the data, cd into the vagrant directory and use the command psql -d news -f newsdata.sql.
Here's what this command does:

psql — the PostgreSQL command line program
-d news — connect to the database named news which has been set up for you
-f newsdata.sql — run the SQL statements in the file newsdata.sql
Running this command will connect to your installed database server and execute the SQL commands in the downloaded file, creating tables and populating them with data.

## Explore the data
Once you have the data loaded into your database, connect to your database using psql -d news and explore the tables using the \dt and \d table commands and select statements.

\dt — display tables — lists the tables that are available in the database.
\d table — (replace table with the name of a table) — shows the database schema for that particular table.
Get a sense for what sort of information is in each column of these tables.

The database includes three tables:

The authors table includes information about the authors of articles.
The articles table includes the articles themselves.
The log table includes one entry for each time a user has accessed the site.

#### Your task is to create a reporting tool that prints out reports (in plain text) based on the data in the database. This reporting tool is a Python program using the psycopg2 module to connect to the database.

## So what are we reporting, anyway?
Here are the questions the reporting tool should answer. The example answers given aren't the right ones, though!

#### 1. What are the most popular three articles of all time? 
Which articles have been accessed the most? Present this information as a sorted list with the most popular article at the top.

Example:

"Princess Shellfish Marries Prince Handsome" — 1201 views
"Baltimore Ravens Defeat Rhode Island Shoggoths" — 915 views
"Political Scandal Ends In Political Scandal" — 553 views

#### 2. Who are the most popular article authors of all time? 
That is, when you sum up all of the articles each author has written, which authors get the most page views? Present this as a sorted list with the most popular author at the top.

Example:

Ursula La Multa — 2304 views
Rudolf von Treppenwitz — 1985 views
Markoff Chaney — 1723 views
Anonymous Contributor — 1023 views

#### 3. On which days did more than 1% of requests lead to errors? 
The log table includes a column status that indicates the HTTP status code that the news site sent to the user's browser. (Refer to this lesson for more information about the idea of HTTP status codes.)

Example:

July 29, 2016 — 2.5% errors


The submission of the project should include:
* The program's source code ie. logAnalysis.py
Usually this will be one source code file.
* An example of your program's output ie. query 1/2/3.txt
This will be a plain text file that is a copy of what your program printed out.
* A README.md file.
Which is this file.


## Instruction to run the program
Bring the virtual machine back online with vagrant up. Then log into it with vagrant ssh.
Browse to the folder that keeps the logAnalysis.py by using 'cd <foldername>'
Type python logAnalysis.py and hit Enter to run the python program.
Queries' results will be exported into 3 text files named query1, query2, & query3 
which represent answers for each respective queries, saved in the same folder that keeps the logAnalysis.py

  







