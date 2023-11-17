Group: 1
Name: 
XX (00000000)

#Application link: https://projectsample381.render.com/

********************************************
# Login
Through the login interface, each user can access the Shop Information Management System by entering their username and password.

Each user has a userID and password;
[
	{userid: user1, password: 1user},
	{userid: user2, password: 2user},
	{suerid: user3, password: 3user}
]

When the user has successfully login, the userid will be automatically store in the session.

********************************************
# Logout
In the home page, each user can log out from his/her account by simply pressing on logout button.

********************************************
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

Shop Name and Shop ID are mandatory, and other attributes are optional.

Create operation is a post request, and all information is in the body of the request.

********************************************
# CRUD service
- Read
- There are two options to read and find shop information: list all information or search by shop ID.

1) List all information
	list.ejs will show all the shops IDs;
	clicking on a shop ID will show the details of that specific shop;

2) Searching by shop ID
	input the ID of the shop you want to find (12121212);
	the ID is in the body of the post request, and in list.ejs, the shop ID will be shown as a link, blue in colour;
	clicking on the shop ID will show the details of that shop;

********************************************
# CRUD service
- Update
- The user can change the shop information through the details interface.
- Among the attributes shown above, the Shop ID cannot be changed. Since the Shop ID is fixed, the Shop ID is the search criteria for updating information.

- A shop document may contain the following attributes with an example: 
	1) Shop Name (Lucky store)
	2) Sub district (Tsim Sha Tsui)
	3) building name(ChungKing Mansion)
	4) Shop contact no. (23232233), telephone number must be 8 digits
	5) Cheap Items Category (Soft drinks)
	6) Description (... more information about items)

	In the above example, we have updated the sub district, building name, and the shop contact number.

********************************************
# CRUD service
- Delete
- The user can delete the shop information through the details interface.

********************************************
# Restful
In this project, there are three HTTP request types: post, get and delete.
- Post 
	Post request is given for inserting shopID .
	Path URL: /api/item/shopID/:shopID
	Test: curl -X POST -H "Content-Type: application/json" --data '{"name": "ABC Shop", "shopID":"12121212"}'localhost:8099/api/item/shopID/12121212/name/ABC Shop

- Get
	Get request is given for finding the information.
	Path URL: /api/item/shopID/:shopID
	Test: curl -X GET http://localhost:8099/api/item/shopID/13131313

- Delete
	Delete request is given for deletion the shop information.
	Path URL: /api/item/shopID/:shopID
	Test: curl -X DELETE localhost:8099/api/item/shopID/13131313

Login will be done first among all RESTful CRUD services.

curl -X POST -H "Content-Type: application/json" --data '{"name": "ABC Shop", "shopID":"12121212"}' http://localhost:8099/api/item/shopID/12121212

curl -X GET http://localhost:8099/api/item/shopID/13131313

curl -X DELETE http://localhost:8099/api/item/shopID/13131313
