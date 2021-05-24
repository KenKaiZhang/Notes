# Creating a Table

```SQL:
mysql> CREATE TABLE table_name (
	-> col1 SMALLINT(5) NOT NULL DEFAULT 0,
	-> col2 CHAR(128) DEFAULT NULL,
	-> ...
	-> PRIMARY KEY (col1)
	-> );

```
Each argument is a new column in the table generated

Basic syntax of making column: ***name type*** **NOT NULL | NULL** **DEFAULT** ***value***

Some usable **type**

- **INT [(width)] [UNSIGNED] [ZEROFILL]** 

	- stores values in range -2,147,483,648 -> 2,147,483,648
	- **UNSIGNED** makes range 0 -> 4,294,967,295
	- ***width*** and **ZEROFILL** is for left-padding values

	```
	// with ZEROFILL
	+-----------+
	| my_number |
	+-----------+
	|      0003 |
	|      0033 |
	|      0333 |
	|      3333 |
	|     33333 |
	|    333333 |
	+-----------+
	// without
	+-----------+
	| my_number |
	+-----------+
	|         3 |
	|        33 |
	|       333 |
	|      3333 |
	|     33333 |
	|    333333 |
	+-----------+
	```
	
- **DECIMAL[width[,decimals]] [UNSIGNED] [ZEROFILL]**

	- ***width*** corresponds to how many digits and **decimal** how many digits in the width are decimals
	-  ***decimals** should be 2 less than the value of width

- **DATE**

	- stores and display in format YYYY-MM-DD (many more other formats but just use -)


**NOT NULL** states that a row / entry is not valid without input for that col: `INSERT INTO col1 SET col1 = 5`

**NULL** allows row to exist without the value given: `INSERT INTO col2`

**DEFAULT** is the value used if a value is not given

**PRIMARY KEY** sets a col to be a PK

---

**IF NOT EXISTS** allows avoidance of error message is created table shares name of one in existence

