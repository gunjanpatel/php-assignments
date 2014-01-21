SPECIFICATIONS
==============

/////////////////////////////////////////////////////////////////////////////////////////////

PageNbr :   PTY01

Screen Name : Property Type

File Name : ../admin/pty01.php

Group : Application

This screen is used to manage top Property Types.

Table Used : propertytype, propertysubtype

Structure of the Table:
=======================

Table : propertytype

 Fields			Type			Short Description		Default	Value	Extra Info
------------------------------------------------------------------------------------------
1) recid		bigint(20)		Primary Key			Not Specified	NOT NULL
			unsigned

2) proptype		varchar(255)		Stores Property Type		Not Specified	NOT NULL
						Name.	 

3) endeffdt		date			Stores current			NULL		None
						date when any 
						particular record 
						is deleted.



Table : propertysubtype

 Fields			Type			Short Description		Default	Value	Extra Info
------------------------------------------------------------------------------------------
1) recid		bigint(20)		Primary Key			Not Specified	NOT NULL
			unsigned

2) propertytypeid	bigint(20)		Stores 'recid' of		Not Specified	NOT NULL
						unsigned"propertytype" 
						table.	
	
3) subtype		varchar(255)		Stores Property Sub		Not Specified	NOT NULL
						Type Name.

4) endeffdt		date			Stores current			NULL		None
						date when any 
						particular record 
						is deleted.



Main Display
------------

    -   This will display all the active top property types fetched from "propertytype" table. 	
       (propertytype.endeffdt = NULL or 0 or greater than the current date)


    -	Heading : "Property Type"
   
    -   Display Fields
	
    -   Add Link: Allows Admin person to add a Top Property Type. (See Below - Add Screen)

	-   Del			-   Delete Record (See Below - Delete Section)

	-   Mod			-   Edit Screen (See Below - Edit Screen)
	
	-   Property Type	-   propertytype.type


Add Screen
----------
    -	Heading : "Property Type - Add"

    -   Fields

	-  *Property Type	-	propertytype.type (Text Box)

    -	When user clicks on "Add" button, insert a corresponding record in "propertytype" table. 
	Redirect user to the Main Display screen with appropriate notification message.
    


Edit Screen
-----------
     -	Heading : "Property Type - Edit"

     - Same as "Add Screen" except the screen will display default values for the selected 'propertytype' record.

     - When user clicks on "Update" button, update the corresponding record in "propertytype" table.
	 Redirect user to the Main Display screen with appropriate notification message.
   


Delete Section
--------------	
	
     - Allows deletion of a Property Type only if no sub property type exists for that record.
       
       If atleast one active property sub type record exists for a top property type,
	 display following notification message "There exists Property Sub Type record(s) which uses
   	this Property Type record. You cannot delete this record." and redirect user to 'Main Display'
 	page. 
       
       Otherwise, set 'propertytype.endeffdt = NOW()' for the selected record.


//////////////////

ENHANCEMENTS

//////////////////

- Show Navigational Links on the Main Display of the screen.