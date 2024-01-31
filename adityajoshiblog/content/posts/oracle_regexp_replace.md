---
title: "Oracle REGEXP_REPLACE"
date: 2024-01-23T09:21:08+05:30
tags: ["Oracle Database"]
draft: false
---

This post is to remind myself power of Oracle REGEXP_REPLACE. At time I forget how this in-build function can be used instead of writing a code! 

### Few examples:

1. Below will replace remove digits.

    ```SQL
    WITH strings AS (   
            SELECT 'abc123' s FROM dual union all   
            SELECT '123abc' s FROM dual union all   
            SELECT 'a1b2c3' s FROM dual   
    )   
    SELECT s "STRING", regexp_replace(s, '[0-9]', '') "MODIFIED_STRING"  
    FROM strings
    ```
    Output:

    |STRING|MODIFIED_STRING|
    |------|---------------|
    |abc123|abc|
    |123abc|abc|
    |a1b2c3|abc|

2. Convert multiple spaces to single space.

    ```SQL
        WITH strings AS (   
            SELECT 'Hello  World' s FROM dual union all   
            SELECT 'Hello        World' s FROM dual union all   
            SELECT 'Hello,   World  !' s FROM dual   
        )   
        SELECT s "STRING", regexp_replace(s, ' {2,}', ' ') "MODIFIED_STRING"  
        FROM   strings
    ```
    Output:

    |STRING|MODIFIED_STRING|
    |------|---------------|
    |Hello  World|Hello World|
    |Hello        World|abHello World|
    |Hello,   World  !|Hello, World!|

3. Convert camel case string to lowercase with underscores between words. Very handy if you ever want to create table from a POJO!

    ```SQL
        WITH strings as (   
            SELECT 'AddressLine1' s FROM dual union all   
            SELECT 'ZipCode' s FROM dual union all   
            SELECT  'Country' s FROM dual   
        )
        SELECT s "STRING",  
            lower(regexp_replace(s, '([A-Z0-9])', '_\1', 2)) "MODIFIED_STRING"  
        FROM strings
    ```
    Output:

    |STRING|MODIFIED_STRING|
    |------|---------------|
    |AddressLine1|address_line_1|
    |ZipCode|zip_code|
    |Country|country|

4. If you are sure that input string is date only then you convert yyyy-mm-dd date formats to dd.mm.yyyy like this. 

    ```SQL
        WITH date_strings AS (   
            SELECT  '2015-01-01' d from dual union all   
            SELECT '2000-12-31' d from dual union all   
            SELECT '900-01-01' d from dual   
        )   
            SELECT d "STRING",   
                regexp_replace(d, '([[:digit:]]+)-([[:digit:]]{2})-([[:digit:]]{2})', '\3.\2.\1') "MODIFIED_STRING"  
            FROM date_strings
    ```
    Output:

    |STRING|MODIFIED_STRING|
    |------|---------------|
    |2015-01-01|01.01.2015|
    |2000-12-31|31.12.2000|
    |900-01-01|01.01.900|

These snippets are from [Reference](https://docs.oracle.com/en/database/oracle/oracle-database/18/sqlrf/REGEXP_REPLACE.html#GUID-EA0A33C-441A-4692-A959-273B5A224490)


