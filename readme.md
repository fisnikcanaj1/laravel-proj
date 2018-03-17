

# Laravel RESTful Application

A Restful API Application built on Laravel Framework. When running this application a command line runner will be excetuted in order to populate the in-memory SQL database with entries from a JSON file. The resource of RESTful API is **Products**, which will response JSON structure data based on endpoints.


Laravel is accessible, yet powerful, providing tools needed for large, robust applications.

## Technologies used:
    * Language: **PHP**
    * PHP version: **7.2.2** 
    * Development Environment: **xampp**
    * Framework: **Laravel**
    * Build Automation Tool: **Apache Ant**
    * Database: **MySQL**
    * Service API: **REST**
    * REST Testing Library: **REST Assured**
    * Code editor: **Visual Studio Code**

## Getting Started
These instructions will get you a copy of the project up and running on you local machine for development and testing purposes.

## Local Installation
### Prerequisites
    #### Required
     * Development Environment: **xampp**, **wamp** etc
     * Databese: **MySQL**
     * Git
    
    #### Optional
     * Apache Ant
     * Laravel Composer

**Note: If you want to use command line to run application and tests you need to install softwares mentioned in Optional above**

## Installing and Running Application
Please follow carefully step by step instructions below in order to get the app up and running locally.

1. Open Terminal

2. Get a clone of this project in local machine:
    ```
     git init 
     git clone https://github.com/fisnikcanaj1/laravel-proj.git
     cd laravel-proj
    ```
    * Migrate database to MySQL:
     ```
     php artisan migrate
    ```
 ## API Documentation 
 **Localhost base URL: http://localhost**

  **Note: In order to test API RESTful Endpoints you need to use an HTTP Client Tool, Postman is recommended**

   ### Show Products
    Returns json list of products

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
   Returns json of a specific Product data based on its id
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
        "id": 5,
        "name": "iPhone 8",
        "descrpition": "Apple iPhone 8 Plus smartphone. Announced Sep 2017.",
        "price": 939,
        "quantity": 100,
        "created_at": "2018-03-17 09:52:04",
        "updated_at": "2018-03-17 13:35:03"
     }
     ```

    ### Create Product

    Create new Product from json structure with values sent in body of request

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
            "quantity": 100,
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
            "id": 9
        }
        ```
  ### Delete Product
    Deletes Product by its ID and returns a message if deleted successfully
 
* **URL**
 
   /api/product/:id
    
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