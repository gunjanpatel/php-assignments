SPECIFICATIONS
==============

/////////////////////////////////////////////////////////////////////////////////////////////

PageNbr :   PST01

Screen Name : Property Sub Type

File Name : ../admin/pst01.php

Group : Application

This screen is used to manage Sub Property Types.

Table Used : propertytype, propertysubtype

Structure of the Table:
=======================

Table : propertytype

 Fields			Type			Short Description		Default	Value	Extra Info
------------------------------------------------------------------------------------------
1) recid		bigint(20)		Primary Key			Not Specified	NOT NULL
			unsigned

2) type			varchar(255)		Stores Property Type		Not Specified	NOT NULL
						Name.	 

3) endeffdt		date			Stores current			NULL		None
						date when any 
						particular record 
						is deleted.

Table : propertysubtype

 Fields			Type			Short Description	Default	Value	Extra Info
------------------------------------------------------------------------------------------
1) recid		bigint(20)		Primary Key		Not Specified	NOT NULL
			unsigned

2) propertytypeid	bigint(20)		Stores 'recid' of	0		None
			unsigned		"propertytype" table.	
	
3) subtype		varchar(255)		Stores Property Sub	Not Specified	NOT NULL
						Type Name.

4) endeffdt		date			Stores current		NULL		None
						date when any 
						particular record 
						is deleted.



Main Display
------------

    -   This will display all the active sub property types fetched from "propertysubtype" table. (propertysubtype.endeffdt = NULL or 0 or greater than the current date)

    -   Drop Down : Select Property Type
        (Displays all active Top Property Type fetched from "propertytype" table. Default 'All' will be selected. Based on the item value selected from the drop down Property Sub Type records will be fetched)


    -	Heading : "Property Sub Type"
   
    -   Fields
	
    -   Add Button: Allows Admin person to add a Sub Property Type. (See Below - Add Screen)

    -   Del			-   Delete Record (See Below - Delete Section)

	-   Mod			-   Edit Screen (See Below - Edit Screen)

	-   Type		-   propertytype.type (Display only when no Property Type is selected from the Property Type Drop Down)
	
	-   Sub Type		-   propertysubtype.subtype 
				   (if a particular Property Type is selected display those 'propertysubtype.subtype' for which 'propertysubtype.propertytypeid = selected Property Type id')
				    
	

Add Screen
----------
    -	Heading : "Property Sub Type - Add"

    -   Fields
	
	-  *Property Type	-	Drop down from 'propertytype' table. If a particular Property Type is already selected from Main Display, then by default that Property Type will be selected. (propertysubtype.propertytypeid)

	-  *Property Sub Type	-	propertysubtype.subtype (Text Box)

    -	When user clicks on "Add" button, insert a corresponding record in "propertysubtype" table. Redirect user to the Main Display screen with appropriate notification message.
    


Edit Screen
-----------
     -	Heading : "Property Sub Type - Edit"

     - Same as "Add Screen" except the screen will display default values for the selected 'propertysubtype' record. 

     - When user clicks on "Update" button, update the corresponding record in "propertysubtype" table. Redirect user to the Main Display screen with appropriate notification message.
   


Delete Section
--------------	
	
     - Allows deletion of a Property Sub Type record.
       
       Set 'propertysubtype.endeffdt = NOW()' for the selected record.


//////////////////

ENHANCEMENTS

//////////////////

- Show Navigational Links on the Main Display of the screen.