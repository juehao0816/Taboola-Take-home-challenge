**Write a Java program that take a string input and convert it to an integer without using the build-in parse function.
Example: input value “123”, convert it to an integer type with value 123**

```JAVA
public Integer convertString(String input) {
		if (input == null || input.length() == 0) {
			return null;
		}
		Integer res = 0;
		for (int i = 0; i < input.length(); i++) {
			res = 10 * res + (input.charAt(i) - '0');
		}
		return res;
	}
// Time Complexity: O(n) since for loop will take O(n) time.
// Space Complexity: O(1)
```

\
**Write a Java program that take a input and detect whether there’s integer in there.
Example: input value “45222” return true, input value “This Is A Test4me” return true, input value “IAMGOOD” return false**



```JAVA
public boolean findInteger(String input) {
		for (int i = 0; i < input.length(); i++) {
			if (input.charAt(i) >= '0' && input.charAt(i) <= '9') {
				return true;
			}
		}
		return false;
	}
// Time Complexity: The worst case is O(n) since we have to loop through the input.
//Space Complexity: O(1)
```
\
**Please design two new tables to store information about: a. products
b. product price history
The product tables should include the name and category of the product.
The product price history table should refer to the product table and should include the price information of products and the start date and/or end date for the product. The current price of a product will have no end date.
Please list the table creation scripts for these two tables and a sample query to join two tables together.**

```SQL
CREATE TABLE Product (
    product_id int not null,
    product_name varchar(100) not null,
    product_category varchar(50) not null,
    
    primary key (product_id))

CREATE TABLE Product_pirce_history (
	product_id int not null,
	price decimal(10, 2) not null,
	start_date timestamp not null,
    end_date timestamp
    
    foreign key (product_id) references Product(product_id))

SELECT * 
FROM Product P1 
JOIN Product_price_history P2
ON P1.product_id = P2.product_id
```
