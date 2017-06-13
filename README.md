# Udacity-fsnd-log-analysis
Udacity Full Stack NanoDegree Log Analysis Project

### Project Overview
>In this project, you'll work with data that could have come from a real-world web application, with fields representing information that a web server would record, such as HTTP status codes and URL paths. The web server and the reporting tool both connect to the same database, allowing information to flow from the web server into the report.
  
#### Setting up the database and Creating Views:

  1. Load the data in local database using the command:
  
  ```
    psql -d news -f newsdata.sql
  ```
  2. Use `psql -d news` to connect to database.
  
  3. Create view numviews_view using:
  ```
create view numviews_view as (select title, author, count(*) as num from articles,log where log.path=CONCAT('/article/',articles.slug) group by articles.title,articles.author order by num desc);
  ```
#### Running the queries:
  1. From the vagrant directory inside the virtual machine,run logs.py using:
  ```
    $ python logs.py
  ```
