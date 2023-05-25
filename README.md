# Mod2 Week3 Assessment

## Setup
1. Fork this repository.
1. You can either work on your clone in GitHub, or open your clone in visual studio.

## Questions (10 Points Possible)

<img alt="erd_for_assessment" src="https://github.com/modelmapper/modelmapper/assets/11747682/60bebb3c-9faa-4f3e-ae0a-7df7dde06784">

[Citation for ERD](https://circle.visual-paradigm.com/hospital/)
1. Use the Doctors Office ERD above to answer the following questions:
    1. How many patients can each doctor have?
        Patients and doctors have a one to many relationship, meaning that each doctor can have many patients.
    1. How many doctors can each patient have?
        Each patient can have one doctor.
    1. How would you describe the relationship between patients and tests? Be sure to use either one-to-one, one-to-many, or many-to-many in your answer.
        This would be considered a one-to-many relationship because each test belongs to one patient and one patient can have many tests.
    1. What are the foreign keys in this diagram?
        The foreign keys in this diagram at the doctor_id and the patient_id.
    1. What is the primary key for the Tests table.
        The primary keys are id (doctor table), id (patient table), and id (tests table).
    1. What query would return the number of doctors who have a specialization in "pediatrics"?
        SELECT * FROM doctors WHERE specialization = 'pediatrics';

<br>

2. What does a join table do? Why would we need one?
    A join table combines information from multiple tables and returns a table that includes information from both tables. 
    Join tables allow us to run queries based on information from more than one table.
3. What is a question that the following query helps answer?
```SQL
SELECT hometown, COUNT(name) FROM artists
GROUP BY hometown;
```
    This query will tell us how many artists from the artists table are from each hometown. The return will display the tally of artists from each respective hometown.
4. I'm trying to write a query to find the average age of all patients, but it's not working. How would you modify this query to get it to work as expected?
```SQL
SELECT AVG(age) FROM patients;
```
5. How would you describe the difference between a `LEFT JOIN` and an `INNER JOIN`
INNER JOIN only returns records that match the ON condition, therefore it only returns records from table A that have a corresponding record in table B.
LEFT JOIN will return all records from table A regardless of if they have corresponding rows in table B. The Left table is the first table references in the query.
 
## Exercise (10 Points Possible)

Follow these steps to setup the assessment:
1. Create a new database named `flight_db` using pgAdmin.
2. Copy [this script](https://launch.turing.edu/module2/assessments/flight_db.txt) and paste it into the query tool to insert records into your database.
3. Run the following `SELECT` queries individually to get an understanding of the data:
> `SELECT * FROM airlines;`
> `SELECT * FROM flights;`

** If you need help setting up the database, reach out to an instructor! **

Please provide the QUERY (not the answer) that returns each of the following:
1. The flight numbers for all delayed flights (i.e. not on time).
    SELECT flight_number
    FROM flights
    WHERE on_time = false;

2. The count of delayed flights.
    SELECT COUNT(id)
    FROM flights
    WHERE on_time = false;

3. The sum of prices for all flights arriving to Raleigh-Durham (`RDU`).
    SELECT SUM(price)
    FROM flights
    WHERE arrive_city = 'RDU';

4. The average price for all flights in the database.
   SELECT ROUND(AVG(price),2) AS "Average Price"
    FROM flights;

5. The average price for all flights arriving to Raleigh-Durham.
    SELECT ROUND(AVG(price),2) AS "Average Price"
    FROM flights
    WHERE arrive_city = 'RDU';

6. The departure city and number of flights departing from each city.
    SELECT depart_city, flight_number
    FROM flights
    GROUP BY depart_city, flight_number
    ORDER BY depart_city;

7. The count of airlines in the database.
    SELECT COUNT(id)
    FROM airlines;

8. The count of flights in the database.
    SELECT COUNT(id)
    FROM flights;

9. The flight number, departure city, arrival city, price, and airline name of each flight. Do not return the airline ID number.
    SELECT flights.flight_number, flights.depart_city, flights.arrive_city, flights.price, airlines.airline_name
    FROM flights JOIN airlines
    ON flights.airline_id = airlines.id;
    
10. The airline name, flight number, and price of each flight on the Delta airline. (Assume that you do not know the ID number of the Delta airline. In a larger database, you would be expected to memorize ID numbers).
    SELECT flights.flight_number, flights.price, airlines.airline_name
    FROM flights JOIN airlines
    ON flights.airline_id = airlines.id
    WHERE airline_name = 'Delta';

## Submission

Submit the Assessment Submission form linked in your cohort slack channel!

## Rubric

This assessment has a total of 20 Points. Earning 14 or more points is a pass and will indicate that you are progressing well with the material.

As a reminder, this assessment is for students and instructors to determine if there are any areas that need additional reinforcement!
