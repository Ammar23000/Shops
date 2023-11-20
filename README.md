Group: 83
Name: AMMAR Muhammad
Student ID (1257719)

#Application link: https://projectsample381.render.com/

*******************************************************
# The Purpose of this application 
To help people to save information about the shops which sell items that are cheaper than the other shops, as not everyone can bear to buy expensive products. They can always get access to the information they have created.

*******************************************************

# Login
Each user can access to the Cheap Shop Information Management System by entering their userid and password at login interface. After inputting the userid and password, user has to click the login button to get into the application.

As each user has a userID and a password to login to his account and get access to the application, the info of 3 userid and password is below;
[
	{userid: userA, password: am123},
	{userid: userB, password: am123},
	{userid: userC, password: am123},
	{suerid: userD, password: am123}
]

When the user has successfully login into the appplication, the userid will automatically be stored in the session.

*******************************************************

# Logout
In the home page, each user can log out from his/her account by simply pressing on logout button. When he will press the logout button, the first page of login will appear, user can login again if he/she wants to.

*******************************************************
# CRUD service
- Create
- A shop document may contain the following attributes with an example: 
	1) Shop Name (Lucky Store)
	2) Shop ID (12121212), shop ID must be 8 digits
	3) Sub district (Diamond Hill)
	4) building name (Li Sing building)
	5) Shop Contact No. (22332233), telephone number must be 8 digits
	6) Cheap Items Category (soft drinks)
	7) Description (... more informaton about items)

Shop Name and Shop ID are must to create a Shop information, but the other attributes are optional, if user want to choose he can input information or just leave it empty.
Create operation is a post request, and all information is in the body of the request.

*******************************************************
# CRUD service
- Read
- There are two options to read and find shop information: list all information or search by shop ID.

1) Searching by shop ID
	input the ID of the shop you want to find (12121212);
	the ID is in the body of the post request, and in list.ejs, the shop ID will be shown as a link, blue in colour;
	clicking on the shop ID will show the details of that shop;

2) List all information
	list.ejs will show all the shops IDs;
	clicking on a shop ID will show the details of that specific shop;



*******************************************************
# CRUD service
- Update
- The user can change the shop information through the details interface.
- Among the attributes shown above, the Shop ID cannot be changed. Since the Shop ID is fixed, the Shop ID is the search criteria for updating information.

- A shop document may contain the following attributes with an example for each attribute: 
	1) Shop Name (Lucky store)
	2) Sub district (Tsim Sha Tsui)
	3) building name(ChungKing Mansion)
	4) Shop contact no. (23232233), telephone number must be 8 digits
	5) Cheap Items Category (Soft drinks)
	6) Description (... more information about items)

	In the above example, we have updated the sub district, building name, and the shop contact number.

*******************************************************
# CRUD service
- Delete
- The user can delete the shop information through the details interface.

*******************************************************
# Restful
In this project, there are three HTTP request types: post, get and delete.
- Post 
	Post request is given for inserting shopID .
	Path URL: /api/item/shopID/:shopID
	Test: curl -X POST -H "Content-Type: application/json" --data '{"name": "ABC Shop", "shopID":"12121212"}'localhost:8099/api/item/shopID/12121212/name/ABC Shop

- Get
	Get request is given for finding the information.
	Path URL: /api/item/shopID/:shopID
	Test: curl -X GET http://localhost:8099/api/item/shopID/12121212

- Delete
	Delete request is given for deletion the shop information.
	Path URL: /api/item/shopID/:shopID
	Test: curl -X DELETE localhost:8099/api/item/shopID/12121212

*******************************************************

# Note
Login will be done first among all RESTful CRUD services. Then the user can Create, Update or Remove the shop he wants to, at the end logout should be done.

