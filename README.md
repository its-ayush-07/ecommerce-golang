## **Ecommerce With Golang Project**

```bash
# You can start the project with below commands
go run main.go
```

- **SIGNUP FUNCTION API CALL (POST REQUEST)**

http://localhost:8000/users/signup

```json
{
  "first_name": "Ayush",
  "last_name": "Dey",
  "email": "ayush@gmail.com",
  "password": "ayushdey",
  "phone": "+4534545435"
}
```

Response :"Successfully Signed Up!!"

- **LOGIN FUNCTION API CALL (POST REQUEST)**

  http://localhost:8000/users/login

```json
{
  "email": "ayush@gmail.com",
  "password": "ayushdey"
}
```

response will be like this

```json
{
    "_id": "65d1ea3ce3407766af949fac",
    "first_name": "Ayush",
    "last_name": "Dey",
    "password": "$2a$14$nnHc41ANTrZoJNmQ/S0G8.daUUtLrJYraWHzkilZxf8OLH9mzZSa6",
    "email": "ayush@gmail.com",
    "phone": "+4534545435",
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJFbWFpbCI6ImF5dXNoQGdtYWlsLmNvbSIsIkZpcnN0X05hbWUiOiJBeXVzaCIsIkxhc3RfTmFtZSI6IkRleSIsIlVpZCI6IjY1ZDFlYTNjZTM0MDc3NjZhZjk0OWZhYyIsImV4cCI6MTcwODM0MjIwNH0.IauQPOYNnAWCmuwhR5q6CtN7HRh3_-IK3mosAecCEMQ",
    "Refresh_Token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJFbWFpbCI6IiIsIkZpcnN0X05hbWUiOiIiLCJMYXN0X05hbWUiOiIiLCJVaWQiOiIiLCJleHAiOjE3MDg4NjA2MDR9.rE6ku-q2iX5B16DbHAUE58YS_xq_TmbcTh4m356Ll_Y",
    "created_at": "2024-02-18T11:30:04Z",
    "updtaed_at": "2024-02-18T11:30:04Z",
    "user_id": "65d1ea3ce3407766af949fac",
    "usercart": [],
    "address": [],
    "orders": []
}
```

- **Admin add Product Function (POST REQUEST)**

  http://localhost:8000/admin/addproduct

```json
{
  "product_name": "Alienware x15",
  "price": 2500,
  "rating": 10,
  "image": "alienware.jpg"
}
```

Response : "Successfully added our Product Admin!!"

- **View all the Products in db GET REQUEST**

  http://localhost:8000/users/productview

Response

```json
[
  {
    "Product_ID": "6153ff8edef2c3c0a02ae39a",
    "product_name": "alienwarex15",
    "price": 1500,
    "rating": 10,
    "image": "alienware.jpg"
  },
  {
    "Product_ID": "616152679f29be942bd9df8f",
    "product_name": "giner ale",
    "price": 900,
    "rating": 5,
    "image": "gin.jpg"
  },
  {
    "Product_ID": "616152ee9f29be942bd9df90",
    "product_name": "iphone 13",
    "price": 1700,
    "rating": 4,
    "image": "ipho.jpg"
  },
  {
    "Product_ID": "616152fa9f29be942bd9df91",
    "product_name": "whiskey",
    "price": 100,
    "rating": 7,
    "image": "whis.jpg"
  },
  {
    "Product_ID": "616153039f29be942bd9df92",
    "product_name": "acer predator",
    "price": 3000,
    "rating": 10,
    "image": "acer.jpg"
  }
]
```

- **Search Product by regex function (GET REQUEST)**

defines the word search sorting
http://localhost:8000/users/search?name=al

response:

```json
[
  {
    "Product_ID": "616152fa9f29be942bd9df91",
    "product_name": "Alienware x15",
    "price": 1500,
    "rating": 10,
    "image": "1.jpg"
  },
  {
    "Product_ID": "616153039f29be942bd9df92",
    "product_name": "ginger Ale",
    "price": 300,
    "rating": 10,
    "image": "1.jpg"
  }
]
```

- **Adding the Products to the Cart (GET REQUEST)**

  http://localhost:8000/addtocart?id=xxxproduct_idxxx&userID=xxxxxxuser_idxxxxxx

  Corresponding mongodb query

- **Removing Item From the Cart (GET REQUEST)**

  http://localhost:8000/addtocart?id=xxxxxxx&userID=xxxxxxxxxxxx

- **Listing the item in the users cart (GET REQUEST) and total price**

  http://localhost:8000/listcart?id=xxxxxxuser_idxxxxxxxxxx

- **Addding the Address (POST REQUEST)**

  http://localhost:8000/addadress?id=user_id**\*\***\***\*\***

  The Address array is limited to two values home and work address more than two address is not acceptable

```json
{
  "house_name": "white house",
  "street_name": "white street",
  "city_name": "washington",
  "pin_code": "332423432"
}
```

- **Editing the Home Address(PUT REQUEST)**

  http://localhost:8000/edithomeaddress?id=xxxxxxxxxxuser_idxxxxxxxxxxxxxxx

- **Editing the Work Address(PUT REQUEST)**

  http://localhost:8000/editworkaddress?id=xxxxxxxxxxuser_idxxxxxxxxxxxxxxx

- **Delete Addresses(GET REQUEST)**

  http://localhost:8000/deleteaddresses?id=xxxxxxxxxuser_idxxxxxxxxxxxxx

  delete both addresses

- **Cart Checkout Function and placing the order(GET REQUEST)**

  After placing the order the items have to be deleted from cart functonality added

  http://localhost:8000?id=xxuser_idxxx

- **Instantly Buying the Products(GET REQUEST)**
  http://localhost:8000?userid=xxuser_idxxx&pid=xxxxproduct_idxxxx
