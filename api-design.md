# Employee

## Entity design

<img src = "database_diagram.png" alt ="employee-entity-design" style="width:300px">

## API Methods

1. GET /api/v1/employees?starts-with={letter}
    - request-param : starts-with [required : true]
    - response-status : 200
    - response : employee details as JSON
    ```json
    {
        "id" : 1,
        "name"  : "Peter Parker",
        "designation" : "Manager",
        "accountName" : "Smart ops",
        "manager" : ""
    }
    ```
2. GET /api/v1/streams 
    - request-param-required : false
    - response-status : 200
    - response : streams details as JSON
    ```json
    {
        "streams" : ["stream1","stream2","stream3"]
    }
    ```
3. PUT /api/v1/employees?employee-id={employee_id}&manager-id={manager_id}&account-name={account_name}&designation={designation}
    - request-param : employee-id [required : true]
    - request-param : manager-id [required : false]
    - request-param : account-name [required : false]
    - request-param : designation [required : false]
    - response-status : 200
    - response : 
    ```json
    {
        "message" : "Peter Parker's Manager has been changed from May to Tony"
    }
    ```


# Inventory Management System

## Entity

<img src = "database_diagram_MySql.png" alt ="employee-entity-design" style="width:600px">

## API Methods

1. POST 
2. POST
3. GET
4. GET
5. GET
6. GET
7. PUT
8. PUT
9. DELETE
10. DELETE 
11. POST

