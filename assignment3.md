Write an appropriate PHP script for following requirements:

	A) Files Used : shoppingcart.php and shoppingcart.class.php

		- Create a Shopping Cart application which allows user to 
		  view, add and remove the products from the Shopping Cart. 
		
		  There will be two sections for display, viz. "Add to Shopping Cart" section and
                  "Your Shopping Cart contains:" section.

	All the products are displayed in the following manner:
		
		i) All the products which are not added to the Shopping Cart should be displayed under 
		   "Add to Shopping Cart" section with "Add to Cart" link. When user clicks on the "Add to Cart" 
		   link, add that product in his/her Shopping Cart. The product added to the 
		   Shopping Cart should not be displayed under "Add to Shopping Cart" section.

		ii) If a Product is already added to the Shopping Cart, no need to display it under 
			"Add To Cart" section, but display under "Your Shopping Cart contains:" section with link 
			"Remove". When user clicks on the "Remove" link the product should be 
			removed from the cart and should be displayed under "Add To Cart" section.
		
		iii) If no product has been added to the Shopping Cart, display text "Your Shopping Cart is 
			Empty." below "Your Shopping Cart contains:" section.

		HINT : This application makes use of Class and its Object along with the Session Variable. 
		       All the relevant operations like adding a product, removing it, etc. 
   		       are done by calling the class methods.





	B) File Used : dbconn.php

		- Write a PHP script which establishes a MySQL connection. Note that, 
                  it is not recommended to store connection parameters like database host name, 
                  database user name, database password, etc. in the same file.


	


	C) Files Used : dbconn.php and queryoutput.php

		- Create a PHP script "queryoutput.php" which makes use of "dbconn.php" for  
		  establishing MySQL connection and which displays output of all MySQL queries 
		  of MySQL Assignments - 2 and 6 which you have solved. 
		  
		  Following requirements should be met:
			
			i)   Display output in proper tabular format.
			ii)  Print a brief description above each tabular display of output,
                             depicting what the query is fetching or displaying.
			iii) In each tabular display of output print a header row, showing proper title 
			     for each column.



	D) Filed Used : config/config.php
		- Create file using file operations.
		- Use all necessary parameters to establish MY SQL connection for database.
		- Read file and establish connection and display message "Connection established successfully...!"

		NOTE : Use config.php file for further database connectivity.



	E) MySQL : 1) Create a table called "users" with following fields:
			recid, username, password

		   2) Insert three appropriate records in this table. Make sure you use MySQL
                      encryption/decryption function for 'password' field.

	   PHP : Files Used - login.php and login.class.php
		
		- Create a LOGIN based application consisting of two pages and use SESSION variable.
			- "login.php" will display "User Name" and "Password" field along with "Submit" and "Reset" buttons.

			- When user clicks on the "Submit" button, validate the user by checking whether 
                         the entered username and password are valid or not.

			- If user is found to be valid user, store the corresponding 'recid' value of the "users"
                         table in a SESSION variable; otherwise give appropriate error message.