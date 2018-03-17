# Laravel RESTful Application

A Restful API Application built on Laravel Framework. The resource of RESTful API is **Products**, which will response JSON structure data based on endpoints.

Laravel is accessible, yet powerful, providing tools needed for large, robust applications.

## Technologies used:
 * Language: **PHP**
 * PHP version: **7.2.2**
 * Framework: **Laravel**
 * Local Development Environment: **XAMPP**
 * Package Manager: **Composer**
 * Database: **MySQL**
 * Service API: **REST**

## Getting Started
These instructions will get you a copy of the project up and running on you local machine for development and testing purposes.

## Local Installation
### Prerequisites
 #### Required
  * Development and Server Solution Software: **XAMPP** or **WAMP** etc
  * Database: **MySQL**
  * Package Manager: **Composer**
  * Source Control: **Git**

## Installing and Running Application
Please follow carefully step by step instructions below in order to get the app up and running locally.

1. Open Terminal
2. Get a clone of this project in local machine:
    ```
     git clone https://github.com/fisnikcanaj1/laravel-proj.git
     cd laravel-proj
    ```
3. Install dependencies:
    ```
    composer install
    ```
3. Create database in MySQL with name **products**.
4. Create a clone of **.env.example** file with name **.env**:
    ```
    cp .env.example .env
    ```
5. Open **.env** file and configure your MySQL information:
    ```
        DB_CONNECTION=mysql
        DB_HOST=127.0.0.1
        DB_PORT=3306
        DB_DATABASE=products
        DB_USERNAME=<yourusername>
        DB_PASSWORD=<yourpassword>
    ```
    **Note: Make sure the MySQL server is running, database is created, and config of DB in .env is done.**
4. Migrate database to MySQL:
    ```
     php artisan migrate
    ```
5. To generate application key run the command below:
   ```
    php artisan key:generate
   ```
6. Run the application:
    ```
     php artisan serve
    ```
 ## API Documentation
 **Base URL: http://localhost:8000**

  **Note: In order to test API RESTful Endpoints you need to use an HTTP Client Tool, Postman is recommended**

### Show Products
Returns JSON list of products

* **URL**

    /api/products/

* **Method:**

    `Get`

 * **Success Response:**

      **Content:**

      ```json
      [{
         "id": 3,
         "name": "Samsung Galaxy S8",
         "descrpition": "Both chips are manufactured by Samsung with a 10 nm process.",
         "price": 725,
         "quantity": 100,
         "created_at": "2018-03-17 07:14:17",
         "updated_at": "2018-03-17 13:26:50"
       }, {...}]
       ```

### Show Product
   Returns JSON of a specific Product data based on its id
* **URL**

    /api/products/:id

*  **URL Params**

    **Required:**

     `id=[integer]`

* **Method:**

     `GET`

* **Success Response:**

     **Content:**

     ```json
     {
        "id": 2,
        "name": "iPhone 8",
        "descrpition": "Apple iPhone 8 Plus smartphone. Announced Sep 2017.",
        "price": 939,
        "quantity": 100,
        "created_at": "2018-03-17 09:52:04",
        "updated_at": "2018-03-17 13:35:03"
     }
     ```

### Create Product

Create new Product from JSON structure with values sent in body of request

* **URL**

    /api/products/

* **Method:**

    `POST`

* **Body Data (application/json)**

    ```json
        {
            "name": "iPhone charger",
            "descrpition": "Apple 12W USB Power Adapter.",
            "price": 2,
            "quantity": 100
        }
    ```
* **Success Response:**

    **Content:**

        ```json
        {
            "name": "iPhone charger",
            "descrpition": "Apple 12W USB Power Adapter.",
            "price": 2,
            "quantity": 100,
            "updated_at": "2018-03-17 13:40:52",
            "created_at": "2018-03-17 13:40:52",
            "id": 1
        }
        ```

### Update Product

Updates existing Product from JSON structure with values sent in body of request

* **URL**

    /api/products/:id

* **Method:**

    `PUT`

* **Body Data (application/json)**

    ```json
        {
            "name": "iPhone charger updated ",
            "descrpition": "Apple 12W USB Power Adapter updated.",
            "price": 700,
            "quantity": 3
        }
    ```
* **Success Response:**

    **Content:**

        ```json
        {
            "name": "iPhone charger updated",
            "descrpition": "Apple 12W USB Power Adapter updated.",
            "price": 700,
            "quantity": 3,
            "updated_at": "2018-03-17 13:50:52",
            "created_at": "2018-03-17 13:40:52",
            "id": 1
        }
        ```

### Delete Product
Deletes Product by its ID and returns a message if deleted successfully

* **URL**

   /api/products/:id

* **Method:**

   `DELETE`

* **URL Params**

    **Required:**

    `id=[integer]`

* **Success Response:**

    **Content:**

     ```json
        {
            "response": "Product successfully deleted",
            "success": true
        }
      ```
## Author
  * **Fisnik Canaj**
