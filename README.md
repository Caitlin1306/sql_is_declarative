# sql_is_declarative
Task to help decide if SQL is imperative or declarative

Please see below SQL codeblock that i have got from the BigQuery public data set:

```
SELECT
  SUM(number) AS num_people
FROM
  `bigquery-public-data.usa_names.usa_1910_current`;
```

To help me decide that SQL was declarative, I practiced codeing using the below information.

- Extend the query above to sum numbers of people for each name

- Only group and sum female names

- Sort the results with the most common names first

- Only show names that were used by over one million people

- Only get the top 5 most common American female names

Please see below code that I produced;

```
SELECT
  name,
  SUM(number) AS num_people
FROM
  `bigquery-public-data.usa_names.usa_1910_2013`
WHERE
  gender = 'F'
GROUP BY
  name
HAVING
  num_people > 1000000
ORDER BY
  num_people DESC
LIMIT
  5;
  ```
  
 From analysing the above code and what information it produces. I have decided that SQL is declarative because I have specifyed the result that I want the code to produce eg gender must be female, instead of how to get it which would be imperative.
