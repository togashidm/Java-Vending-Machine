Cheap Software Solutions (CSS.inc)

1) Summary:
	The application simulates a vending machine (VM). Only regitered users can use the VM by
	login operation. It reads external files that allows VM to identify its users and products.


2) Installation:
	To run jar file from prompt command:
	a) Ensure you have "VendingMachineDT.jar" in suitable folder/directory
	b) Certifify about the enviromental variables - you can run "java.exe" from anywhere
	c) Certify that you have the most recent JDK version (at least jdk-13.0.1)
	d) Be sure the external files "Clients.dat", "Admin.dat" and "Product.dat" are in the same folder where 
	   you install "VendingMachineDT.jar".
	e) Find the path for the JDKFX library, in my case is D:\javafx-sdk-14\lib\
	f) IN THE Command propmt (CMD): run
	java --module-path D:\javafx-sdk-14\lib\ --add-modules javafx.controls,javafx.fxml -jar VendingMachineDT.jar

	To run from Eclipse
	a) Certify that you have the most recent JDK version (at least jdk-13.0.1) in Eclipse
	b) File->Import->General->Projects from Folder or Archive-> Archive -> then browser "VendingMachineFx_03May.zip"
	c) uncheck VendingMachineFx_03May.zip, then Finish
	d) Project VendingMachineFx folder will appear on Packge Explorer. Mark fold by clicking on it
	e) File->Properties->Libraries(Tab on right side). Select JavaFX14 and remove. Then Select Modulepath, and Add Library.
	f) Select User Library -> next -> User Libraries -> New -> input JavaFX14 -> ok -> Select JavaFX and Add External Jars..
	g) Browser the location where javafx-sdk-14\lib\ folder is located in your computer.
	h) Select all *.jar files (total of 8 javafx files) -> Open -> Apply and Close. JavaFX14 should be checked in -> Finish 
	i) Click on VendingMachineFx folder -> src -> application -> Main.java (double click) -> Run
	j) Error message will be displayed. On top Menu, Run -> Run Configurations -> Arguments (tab on right side)
	i) In the 'VM arguments' text area field,  add:
		--module-path "D:\javafx-sdk-14\lib" --add-modules javafx.controls,javafx.fxml
	j) Run, and you should have the application running.
 

3) Functionalities:
	Login
	* It allows only registered users. Username is case sensitive.Password 6 digit numbers.

	Client
	* It displays client's name and current balance
	* It displays product list with description, location and price
	* It displays coin values to be inserted in VM
	* It controls the operation by verifying clients' balances against th proposed purchase item
		+ only allows purchase if there is enought credit
		+ return change if amount inserted is higher than the item price
		+ updates client balance to the external file
		+ updates product quantity to the external file
		+ removes product from the list if there are zero units left.
		+ resets the operation at any stage
	Administrator
	* It display's the administrator's name
	* It display's the product list with description, location and price
	* It allows a new product to be added if it is not already present and in an unoccupied location
	* It allows existing products to be reloaded in new quantities
	* It allows a shutdown and record all the information to the respective files (Product.dat and Admin.dat)
	* It records the total money left in VM before shutdown operation.
	* It allows the VM to be restarted


4) Operation procedure:
	* Client / purchase Item
	1) Click on the desired item in the List
	2) Click on 'Select' button in the control board
	3) Insert the correct amount of coins
	4) Click on 'Buy'
	5) If another item is requested, the process is repeated. 
	6) Logout

	* Administrator / Add new product
	1) Input the respective values in the text field, for 
	   Product description, location, price and quantity.
	2) Click on "Add"

	* Administrator / Load product
	1) Click on product item in the list
	2) Click on 'Select' button in the control board
	3) Change the quantity value in the Quantity text field
	4) Click on 'Re-load'

	* Administrator / Shutdown / Turn on
	1) Click on 'shutdow'n button - note none of the other buttons are active except for the 'Turn on'button.
	* Administrator / Turn on
	1) Click on 'Turn on' button - note this button is only active when machine is in shutdown mode.
