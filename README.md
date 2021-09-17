 # Movies Data Analysis
 
 ## Project Description  
 
Use Sqoop to collect data and to store the data to HDFS. Process various insights while analyzing the data using Hive. The database consist of movies_dataset  table, I will import movies_dataset table, which contains about movies id, names, year, rating and duration. 

## Technologies Used

* HDP 2.6.5
* Hive 2.1.0
* Hadoop 2.7.3
* Sqoop 1.4.6
* MySQL 10.5
* Git/GitHub
   
## Features

List of features ready and TODOs for future development

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

## Getting Started

> All the operations below are for Windows OS.
   
* Make sure that the virtualization is enabled for your system from the BIOS.
* Install VMware Workshation Player.
* Download and insatll Hortonworks HDP 2.6.5.
* Get everything up and runninng.
* Connect to the system either through the webshell/OpenSSH/PuTTY.
* Upload all the required files into the local system or clone this repo using the following command:-
```
git clone https://github.com/meenal-shree/Analysis-of-crime-against-women-in-India-using-HIVE-and-HADOOP
```
> For linux, install all the dependencies and then run the project from the command-line.

## Usage

All the queries used in thge project can be fount [here](./Queries/commands.doc)

To run the hive queries, use the Hive shell

Use the Sqoop commands to load the data into MySQL
`sqoop export --connect jdbc:mysql://localhost:3306/<DB Name> -username <user> -password <pass> -table <table_name> -m 1 --export-dir /path/to/dir --input-fields-terminated-by ',';`

To run the MySQL queries, use the MySQL shell 
`mysql -u<username> -p<password>`

# License

 This project uses the [MIT](./LICENSE) license.


