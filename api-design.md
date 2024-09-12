# Employee

## Entity design

<img src = "database_diagram.png" alt ="employee-entity-design" style="width:300px">

## API Methods
1. POST /api/v1/employee
   - request-body : 
   ```json
    {
        "id" : 1,
        "name"  : "Peter Parker",
        "designation" : "Manager",
        "accountName" : "Smart ops",
        "manager" : ""
    }
    ```
    - response-status : 200
    - response-body :
    ```json
    {
        "message" : "Successfully created"
    }
    ```

2. GET /api/v1/employees?starts-with={letter}
    - request-param : starts-with [required : true]
    - response-status : 200
    - response-body : employee details as JSON
    ```json
    {
        "id" : 1,
        "name"  : "Peter Parker",
        "designation" : "Manager",
        "accountName" : "Smart ops",
        "manager" : ""
    }
    ```
3. GET /api/v1/streams 
    - request-param-required : false
    - response-status : 200
    - response-body : streams details as JSON
    ```json
    {
        "streams" : ["stream1","stream2","stream3"]
    }
    ```
4. PUT /api/v1/employees?employee-id={employee_id}&manager-id={manager_id}&account-name={account_name}&designation={designation}
    - request-param : employee-id [required : true]
    - request-param : manager-id [required : false]
    - request-param : account-name [required : false]
    - request-param : designation [required : false]
    - response-status : 200
    - response-body : 
    ```json
    {
        "message" : "Peter Parker's Manager has been changed from May to Tony"
    }
    ```


# Inventory Management System

## Entity

<img src = "database_diagram_MySql.png" alt ="employee-entity-design" style="width:600px">

## API Methods

1. POST /api/v1/product
   - request-body:
   ```json
    {
        "productId": "123",
        "productName": "Name",
        "categoryId": "789",
        "price": 500,
        "quantity": 10
    }
   ```
   - response-status : 201
   - response-body:
   ```json
   {
       "message":"Product is successfully created"
   }
   ```
2. POST /api/v1/category
   - request-body:
   ```json
   {
       "categoryId":"789",
       "name":"Name",
   }
   ```
   - response-status : 201
   - response-body:
   ```json
   {
       "message":"Category is successfully created"
   }
   ```
3. GET api/v1/products?product-id={productId}&category_id={categoryId}
   - request-param : product-id [required = false]
   - request-param : category-id [required = false]
   - response-status:200
   - response-body:
   ```json
    { 
        "products":
        [ 
        {
        "productId":"123",
        "productName":"Name",
        "categoryId":"789",
        "price":500,
        "quantity":10
        }
        ]
    }
   ```

4. GET /api/v1/category?category-id={categoryId}
   - request-param : category-id [required = true]
   - response-status:200
   - response-body:
   ```json
    {  
       "details":
       {
       "categoryId":"123",
       "categoryName":"Name",
       }
    }
   ```
5. PUT /api/v1/product
   - request-body :
   ```json
   {
       "productId":"123",
       "productName":"Name",
       "categoryId":"789",
       "price":500,
       "quantity":10
   }
   ```
   - response-status:200
   - response-body:
   ```json
   {
       "message":"Successfully updated product"
   }
   ```
6. PUT /api/v1/category
   - request-body :
   ```json
   {
       "categoryId":"123",
       "Name":"Name"
   }
   ```
   - response-status:200
   - response-body:
   ```json
   {
       "message":"Successfully updated category"
   }
   ```
7.  DELETE /api/v1/product?product-id={productId}
   - request-param:product-id [required = true]
   - response-status:200
   - response-body:
   ```json
   {
       "message":"Successfully deleted product"
   }
   ```
8.  DELETE /api/v1/category?category-id={categoryId}
   - request-param:category-id [required = true]
   - response-status:200
   - response-body:
   ```json
   {
       "message": "Successfully deleted category"
   }
   ```
9.  PUT /api/v1/orders?product-id={productId}&quantity={quantity}
    - request-param:productId
    - request-param:quantity
    - response-status:200
    - response-body:
    ```json
    {
        "message": "Successfully sold"
    }
    ```
10. PUT /api/v1/stock?product-id={productId}&quantity={quantity}
    - request-param:product-id [required = true]
    - request-param:quantity [required = true]
    - response-status:200
    - response-body:
    ```json
    {
        "message": "Successfully restocked"
    }
    ```
