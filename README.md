# Hello all, I am sharing how to use LIKE and ALIKE functions in SQL  

## We have already been able to perform direct comparisons against string such as `WHERE first_name = 'John'`.  
## But what if we want to match against a general pattern in a string such as All Emails ending in '@gmail.com' or all names that begin with an 'A'.  
## The LIKE operator allows us to perform pattern matching against a string data with the use of wild card characters.  
                 Percent (%) = matches any sequence of characters.
                 Underscore (_) = matches any single character. 

All names that **begin** with 'A' = `WHERE name LIKE 'A%'`  
All names that **ends** with 'a' = `WHERE name LIKE '%a'`  

## LIKE is <mark>case sensitive</mark>, we can use ILIKE which is <mark>case-insensitive</mark>.  
## Using an underscore(_) allows us to replace just a single character.  

For example - Get all the mission Impossible films = `WHERE title LIKE 'Mission Impossible_'`.  

## We can use multiple underscores. Imagine we have version string codes in the format 'Version#A4' , 'Version#B7' so we can match like `WHERE value LIKE 'Version#__'`  

## We can also combine pattern matching operators to create more complex pattern.  
        `WHERE name LIKE '_her%'` : Here _ can be filled by any 1 value and after 'her' any sequence or any number of characters can come.  

### Examples  

#### Suppose we have a table T1 which has columns named customer_id, first_name and last_name.  

1. Get all the customers whose name starts with 'J'.  
```
SELECT * FROM T1
WHERE first_name LIKE 'J%';
```

2. How many customers are there whose name starts with 'J'.  
```
SELECT COUNT(*) FROM T1
WHERE first_name LIKE 'J%';
```  

3. How many customers are there whose first name starts with 'J' and last name starts with 'S'.  
```
SELECT COUNT(*) FROM T1
WHERE first_name LIKE 'J%' AND last_name LIKE 'S%';
```  

4. How many customers are there whose first name starts with 'J' and last name starts with 'S'.  
```
SELECT COUNT(*) FROM T1
WHERE first_name ILIKE 'j%' AND last_name ILIKE 's%';
``` 
Note = ILIKE function is case insensitive and will return the same output as 3rd question.  

5. Get the customers who have 'er' anywhere in their first name.  
```
SELECT * FROM T1
WHERE first_name LIKE '%er%';
```

6. Get the customers who have 1 aplhabet before 'her' and can have any number of characters after 'her' in their first name.
```
SELECT * FROM T1
WHERE first_name LIKE '_her%';
```

```
SELECT * FROM T1
WHERE first_name NOT LIKE '_her%';
```
This code will work exactly opposite of the 6th question's code.  


7. Get customers whose first name starts with 'A' and then sort the data in ascending last name.  
```
SELECT COUNT(*) FROM T1
WHERE first_name LIKE 'A%'
ORDER BY last_name;
```  

8. Get the customers whose first name starts with 'A' and last name dosen't start with'B' and then sort the data in ascending last name.  
```
SELECT COUNT(*) FROM T1
WHERE first_name LIKE 'A%' AND last_name NOT LIKE 'B%'
ORDER BY last_name;
```  

## That's it for the ORDER BY functions, see you in the next chapter !!