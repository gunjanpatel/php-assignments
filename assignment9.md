SPECIFICATIONS
==============

/////////////////////////////////////////////////////////////////////////////////////////////

PageNbr : CNT01

Screen Name : Country

File Name : 	../admin/cnt02.php

Group : Application

This screen is used to manage Country related information.

Table Used : country

Structure of the Table:
=======================

Table : country

 Fields			Type		Short Description	Default	Value	Extra Info
------------------------------------------------------------------------------------------
1) recid		bigint(20)	Primary Key		Not Specified	NOT NULL

2) code			char(2)		Stores two character		NULL		None
					ISO codes for countries.

3) name			varchar(100)	Stores Country Name.		NULL		None

4) ldesc		text		Stores long description		NULL		None
					for any particular 
					country.

5) displayname1		varchar(100)	Stores display name		NULL		None
					for document-1.

6) document1		varchar(255)	Stores document-1		NULL		None
					relative path.	

7) displayname2		varchar(100)	Stores display name		NULL		None
					for document-2.

8) document2		varchar(255)	Stores document-2		NULL		None
					relative path.	

9) flagimage		varchar(255)	Stores relative path of 	NULL		None
					country	flag image.

10) active		char(1)		Stores 'Y' for active		'Y'		None
					record and 'N' for 
					inactive record.

11) endeffdt		date		Stores current			NULL		None
					date when any 
					particular "country" 
					record is deleted.

Main Display
------------

    -   Radio Button Set :- 
	1) Label Name : "Display" 
	2) Consists of 'All', 'Active' or 'Inactive' radio buttons. Default selection : 'All'.

    -   Display all the country records fetched from the "country" table, as per radio button 
	selection which could be either all, active or inactive "country" records.
		
    -   Add Button: Allows Admin person to add a Country Record. (See Below - Add Screen)

    -	Heading : "Country"
   
    -   Fields

	-   Del			-	Delete Record (See Below - Delete Section)

	-   Mod			-	Edit Screen (See Below - Edit Screen)
	
	-   Code		-	country.code

	-   Name		-	country.name

	-   Flag		-	country.flagimage

	-   Change Status	-	Display text "Inactivate" or "Activate" in the form of a link as the case may be, i.e., for active country record display "Inactivate" link and for inactive country record display "Activate" link. When clicked toggles the country record status. Display relevant notification message, as per the operation performed,	
					viz.,
					1) Record activated successfully. 
					2) Record inactivated successfully. 
					3) Record NOT activated successfully. 
					4) Record NOT inactivated successfully.

Add Screen
----------
    -	Heading : "Country - Add"

    -   Fields
	
	-  *Code		-	country.code (Text Box)

	-  *Name		-	country.name (Text Box)

	-  Long Description	-	country.ldesc (Display FCK editor)

	-  Document1 Name	-	country.displayname1 (Text Box)
			File	-	country.document1 (File Selection Box)

	-  Document2	Name	-	country.displayname2 (Text Box)
			File	-	country.document2 (File Selection Box)

	-  Flag Image		-	country.flagimage (File Selection Box)


    -	When user clicks on "Add" button, attempt to insert a corresponding record in the "country" table with
 'country.active = Y' only when following requirements are satisfied:

    1) Allow only "*.pdf" or "*.txt" for upload in case of Document1 and Document2.

    2) Allow only "*.jpg", "*.gif", "*.pjpeg", "*.png" image files for upload in case of Flag Image. 
For both these cases provide both Client Side as well as Server Side Validations.

    3) Use following notification messages:
	
	i) Client Side alert messages :
		For Image : "Please select JPG, GIF or PNG image types only for Flag Image"
		For Documents : "Please select PDF or DOC files only for Document". Concat with document number.

	ii) Server Side messages:
		For Image and Documents : "Please select binary files having '<strong>.jpg</strong>, '<strong>.gif</strong>' or '<strong>.png</strong>' extensions for <strong>Images</strong> and files having '<strong>.pdf</strong>' or '<strong>.doc</strong>' extensions for <strong>Documents</strong>."

		For Image : "Please select binary files having '<strong>.jpg</strong>, '<strong>.gif</strong>' or '<strong>.png</strong>' extension for <strong>Images</strong>."

		For Documents : "Please select files having '<strong>.pdf</strong>' or '<strong>.doc</strong>' extension for <strong>Documents</strong>.";

    4) Store all uploaded documents and image file in your "../sysimages/" folder. Resize all image files using resize parameters and class file.

    - Display relevant notification message, as per the operation performed, viz.,
	i) Record added successfully. 
	ii) Record NOT added successfully.
    


Edit Screen
-----------
     -	Heading : "Country - Edit"

     - Same as "Add Screen" except the screen will display default values for the selected "country" record.

     - Here, if particular document exists (i.e, Document1 or Document2), then instead of displaying File Selection Box, display original file name along with "Delete Document" link. When user clicks on this link delete the relevant document from the database and "../sysimages/" folder and redirect user to "Edit" case where we will be displaying File Selection Box for the relevant document.

     - In case of Flag Image, if Flag Image exists then display that image with "Delete Image" link. When user clicks on this link delete the relevant image from the database and "../sysimages/" folder and redirect user to "Edit" case where we will be displaying File Selection Box for Flag Image field.

     - Same requirements will be applicable to "Edit" case as where applicable to "Add" case.

     - When user clicks on "Update" button, update the corresponding record in "country" table and display relevant notification message like "Record updated successfully." or "Record NOT updated successfully.".
   


Delete Section
--------------	
	
     -	Allows deletion of a "country" record. Set 'country.endeffdt = NOW()' for the selected record.


//////////////////

ENHANCEMENTS

//////////////////

1) Show Navigational Links on the Main Display of the screen.

2) Do not allow duplicate values for "country.code" field, i.e, "country.code" should be Unique. If user tries to add a record having duplicate "country.code" value then display this notification message to user "Country code <strong>'code added by user'</strong> already exists. Please enter another code." and redirect him to either "ToAddRecord/Edit" case.