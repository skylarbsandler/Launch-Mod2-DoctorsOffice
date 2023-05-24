# Mod2 Week3 Assessment

## Setup
1. Fork this repository.
1. Clone your repo to your local machine.
1. Open your cloned repository in Visual Studio.
1. Answer the following questions
1. Commit and push your answers

## Questions (10 Points Possible)

<img width="282" alt="erd_for_assessment" src="https://github.com/modelmapper/modelmapper/assets/11747682/60bebb3c-9faa-4f3e-ae0a-7df7dde06784">

[Citation for ERD](https://circle.visual-paradigm.com/hospital/)
1. Use the Doctors Office ERD above to answer the following questions:
    1. How many patients can each doctor have?
    1. How many doctors can each patient have?
    1. How would you describe the relationship between patients and tests? Be sure to use either one-to-one, one-to-many, or many-to-many in your answer.
    1. What are the foreign keys in this diagram?
    1. What is the primary key for the Tests table.
    1. What query would return the number of doctors who have a specialization in "pediatrics"?

<br>

2. What does a join table do? Why would we need one?
3. What is a question that the following query helps answer?
```SQL
SELECT hometown, COUNT(name) FROM artists
GROUP BY hometown;
```

4. I'm trying to write a query to find the average age of all patients, but it's not working. How would you modify this query to get it to work as expected?
```SQL
SELECT age FROM AVERAGE(patients);
```
5. How would you describe the difference between a `LEFT JOIN` and an `INNER JOIN`
  
## Submission

Submit the Assessment Submission form linked in your cohort slack channel!

## Rubric

This assessment has a total of 16 Points. Earning 11 or more points is a pass and will indicate that you are progressing well with the material.

As a reminder, this assessment is for students and instructors to determine if there are any areas that need additional reinforcement!
