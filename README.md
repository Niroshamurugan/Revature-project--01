 # Movies Data Analysis
 
 ## Project Description                                                                                 
Use Sqoop to collect data and to store the data to HDFS. Process various insights while analyzing the data using Hive. The database consist of movies_dataset  table, I will import movies_dataset table, which contains about movies id, names, year, rating and duration. 

## Technologies Used
* HADOOP
* HDFS
* HIVE
* SQOOP
* Hortonworks Sandbox
* Ambari
   
 ## Description
* Use Sqoop to collect data and to store the data to HDFS. Process various insights while analyzing the data using Hive. The database consist of movies_dataset  table, I will import movies_dataset table, which contains about movies id, names, year, rating and duration. 
In this project 
    * I collected the movies dataset from Data.World 
    * Movie dataset contains 49590 rows and five columns.

## Code

### Making a directory in HDFS

hdfs dfs -mkdir '/moviedata/'

### Pushing data in HDFS

hdfs dfs -put '/home/cloudera/Downloads/moviesdataset.txt' '/moviedata/'

### Getting started with hive

hive

### Creating a DB

create database movie;

### Creating a table

create table moviedata (id int, name string, year int, rating float, duration int) > row format delimited > fields terminated by ',' > ;

### Loading data into the table

LOAD DATA INPATH '/moviedata/movies dataset for pig.txt' > INTO TABLE moviedata;

### Problem Statements

1.Find the number of movies released between 1950 and 1960.

hive>SELECT count(*) FROM moviedata > WHERE year BETWEEN 1950 AND 1960;

OUTPUT - 547

2.Find the number of movies having rating more than 4.

hive> SELECT count(*) FROM moviedata > WHERE rating > 4.0;

OUTPUT - 897

3.Find the movies whose rating are between 3 and 4.

hive> SELECT name FROM moviedata > where rating > 3.0 and rating < 4.0;

OUTPUT - # Long List of Movies

4.Find the number of movies with duration more than 2 hours (7200 second).

hive> SELECTcount (*) FROM moviedata > WHERE duration > 7200;

OUTPUT - 641

5.Find the list of years and number of movies released each year.

hive> SELECT year, count (*) FROM moviedata > GROUP BY (year);

OUTPUT - Year Number_of_movies xxxx xxxxxxxx xxxx xxxxxxxx xxxx xxxxxxxx xxxx xxxxxxxx xxxx xxxxxxxx xxxx xxxxxxxx xxxx xxxxxxxx xxxx xxxxxxxx xxxx xxxxxxxx

6.Find the total number of movies in the dataset.

hive> SELECT count (*) FROM moviedata;

OUTPUT - 49590

### SQOOP COMMANDS                                               

### Take data from MySQL DB to your HDFS using Sqoop
sqoop import --connect jdbc:mysql://127.0.0.1:3306/movie -username root -password hortonworks1 -table movies_dataset -m 1 --target-di
r /movies_dataset-table

### sqoop eval command
sqoop eval --connect jdbc:mysql://127.0.0.1:3306/movie --username root --password hortonworks1 --query "select * from movies_dataset 
limit 5;"              

### List the tables in the movie database
sqoop list-tables --connect jdbc:mysql://127.0.0.1:3306/movie --username root --password hortonworks1;

## Usage

This project is used to find the highest rate of movie name's,how many movies released in particular year and how many movies are released per year there are lots og use cases i mentioned some of them.


