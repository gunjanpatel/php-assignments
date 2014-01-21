Write an appropriate PHP script for following requirements:

	A) MySQL : Create a table called "employee" with following fields:
		   (recid, name, city, phone, joindate, salary, endeffdt)

	   PHP : Files Used - empadd.php and empadd.class.php
		
		- Display a user entry form with following fields along with a "Submit" and "Reset" buttons:
			-> Name
			-> City
			-> Phone
			-> Join Date (YYYY-MM-DD format) (Database format) 
			-> Salary

		- 'Name' and 'Join Date' field should be mandatory. 
                  Provide appropriate java script date validation for 'Join Date' field and numeric check 
                 for 'Salary' field.

		- When user clicks on "Submit" button, insert an appropriate record in "employee" table.





	B) Files Used : empdisp.php and empdisp.class.php

		- Display following information fetched from the "employee" table (only active record's 
		  needs to be fetched, i.e., those records for which employee.endeffdt = NULL or 0 or 
                  greater than the current date) in a tabular format :
			Table Heading : Employee Detail
			Column Heading : Name	City	Phone	Joining Date	Salary

		- Specify "Add" link above and below "Employee Detail" block.

		- When user clicks on the "Add" link, open "empadd.php" file in a new window which will 
                 allow user to add employee detail. 
                 When user clicks on "Submit" button close "empadd.php" page 
                 and reload "empdisp.php" page in order to display latest employee information.




	C) Files Used : empmoddel.php and empmoddel.class.php

		- Allow user to either 'Modify' or 'Delete' any existing record of "employee" table.
		
		- Show "Modify" and "Delete" links along with each employee record.

		- When user clicks on "Modify" link, show modify screen depicting following fields:
			-> Name
			-> City
			-> Phone
			-> Join Date (DDMMYYYY format) 
			-> Salary

		- "Modify" screen is similar to "Add" screen, except the column values will be displayed as 
		   default values in the user entry form. Display "Update" button, 
                   which when clicked updates the related record of the "employee" table. Provide relevant
                   Java script validations as given in "empadd.php".

		- Delete Link:
			- Delete the related record after seeking proper 
                         confirmation from the user. Confirmation message should be "Are you sure?" 
                         with "Yes" and "No" buttons. If user clicks on "Yes" button delete the corresponding record 
                  (Note that the record is not actually deleted from the database, we just 
                   set the 'endeffdt' field of the record to current date, so that it becomes non-operative); 
                  	otherwise do nothing.