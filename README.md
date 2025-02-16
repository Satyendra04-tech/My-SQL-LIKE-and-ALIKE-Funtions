# Hello all, I am sharing how to use LIMIT, BETWEEN and IN functions in SQL  

## We have already been able to perform direct comparisons against string such as `WHERE first_name = 'John'`.  
## But what if we want to match against a general pattern in a string such as All Emails ending in '@gmail.com' or all names that begin with an 'A'.  
## The LIKE operator allows us to perform pattern matching against a string data with the use of wild card characters.  
                 Percent (%) = matches any sequence of characters.
                 Underscore (_) = matches any single character. 

All names that **begin** with 'A' = `WHERE name LIKE 'A%'`  
All names that **ends** with 'a' = `WHERE name LIKE '%a'`  

## LIKE is <mark>case sensitive</mark>, we can use ALIKE which is <mark>case-insensitive</mark>.  
## Using a unserscore(_) allows us to replace just a single character.  

For example - Get all the mission Impossible films = `WHERE title LIKE 'Mission Impossible_'`.  

## We can use multiple unserscores. Imagine we have version string codes in the format 'Version#A4' , 'Version#B7' so we can match like `WHERE value LIKE 'Version#__'`  

## We can also combine pattern matching operators to create more complex pattern.  
        `WHERE name LIKE '_her%'` : Here _ can be filled by any 1 value and after 'her' any sequence or any number of characters can come. 



