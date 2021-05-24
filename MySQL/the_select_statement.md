# The SELECT Statement

`SELECT column_to_retrieve FROM table;` : get the information of a query

- can run `SELECT * FROM table;` to get information of all the columns of a table

## The SELECT Clause

`SELECT * ...` : grabs EVERYTHING from a table

- bad if table has millions or billions of data

`SELECT column, column1, etc ...`: grabs only the listed columns from the table

- you can also perform aritmetic to the output: `SELECT column_of_int + 10` will return column with the data added by 10
	- arithmetic is based on order of operation

`SELECT column AS alias ...`: displays the column as `alias`

- use quotes if alias has space

`SELECT DISTINCT column ...`: show columns without repeating any identical ones




## Clauses To Place After `FROM`

ORDER MATTERS

`WHERE condition`: retrieve column that match the condition

- `... WHERE customer_id=1` will retrive information of data where the column `customer_id` has a value of 1

`ORDER BY column_to_base_order_by`: sorts data based on a particular column

- `... ORDER BY first_name` will show the data in an order based on the first name

## The `WHERE` Clause

can also use arithmetics
####Operations:
- `>`
- `=>`
- `<`
- `<=`
- `=`
- `!= or <>`
- `OR`
- `AND`

EX:

```
SELECT * 
FROM customers 
WHERE birth_date > '1990-01-01' OR points > 1000
```
- grab the data for those in the table customer that have the column value `birth_date` greater than `1990-01-01` or have column vlaue `points` greater than 1000
- by making it`WHERE NOT`, you can show any data that don't pass the requirements

### The `IN` Operator

a shorter and cleaner way to write `_ OR _ OR _ OR...`

- `...WHERE column = 1 OR column = 2 OR ...` is the same as writing `...WHERE column IN (1, 2, ...)`
	- can also use `NOT IN` to do opposite of `IN`

	
### The `BETWEEN` Operator

used to find rows with column data between two points

- `...WHERE column BETWEEN 'x' AND 'y'`

### The `LIKE` Operator

get rows with column data that match a specific string pattern

`%` is any number of characters while `_` specifies one character each	

-	`...WHERE column LIKE '%character%'`
	- any data that includes the `character` will count 
	- `%a%` will include data like `bacon`, `addict`, `boa`

- `WHERE column LIKE '_character'`
	- must have n `_` letters followed by a `character`
	- `_ _ _y` will include data like `baby`, `tiny`

### THE `REGEXP` Operator

powerful tool to find data with certain characteristics

`...WHERE column REGEXP 'char'`: any data with 'char' in it counts

`...WHERE column REGEXP '^char'`: data must start with char

`...WHERE column REGEXP 'char$'`: data must end with char 

`...WHERE column RECEXP 'char0|char1|char2'`: pipe to search more than one pattern:

`...WHERE column REGEXP '[a-c]d'`: data containingeither `ad`, `bd`, or `cd`







