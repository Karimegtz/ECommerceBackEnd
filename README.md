# Project: ECommerceBackEnd

## Description
The ECommerceBackEnd project is an application that builds the backend for an e-commerce website using Node.js, Express.js, Sequelize, and MySQL. This backend includes the configuration of a RESTful API that allows you to manage CRUD (Create, Read, Update, Delete) operations for products, categories, and tags, as well as the associations between these models.

## Installation
To run this project on your local machine, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/Karimegtz/ECommerceBackEnd.git
    ```

2. Navigate to the project directory:

 cd ECommerceBackEnd

3. Install the dependencies:
npm install

4. Set up your environment variables:

* Install the dependencies:

    ```bash
    npm install
    ```

5. Set up your environment variables:

    * Create a `.env` file in the root of the project and add your MySQL configuration:

        ```bash
        DB_NAME='your_database_name'
        DB_USER='your_mysql_username'
        DB_PASSWORD='your_mysql_password'
        ```

6. Create the database using the `schema.sql` file:

    * Open MySQL Shell and run the command:

        ```sql
        source db/schema.sql;
        ```
7.  Seed the database with test data:

    ```bash
    npm run seed
    ```

8. Start the server:

    ```bash
    npm start
    ```

## Usage

1. Use Insomnia or any similar tool to test the API routes.
    
2. Available routes include:
    
    * **GET** `/api/categories`, `/api/products`, `/api/tags`
    * **GET** `/api/categories/:id`, `/api/products/:id`, `/api/tags/:id`
    * **POST** `/api/categories`, `/api/products`, `/api/tags`
    * **PUT** `/api/categories/:id`, `/api/products/:id`, `/api/tags/:id`
    * **DELETE** `/api/categories/:id`, `/api/products/:id`, `/api/tags/:id`
    
3. Data is returned in JSON format.
    
## Database Models

The database includes the following models with their respective columns:

* **Category**
    * `id`: Integer, Primary Key, Auto Increment
    * `category_name`: String, Not Null

* **Product**
    * `id`: Integer, Primary Key, Auto Increment
    * `product_name`: String, Not Null
    * `price`: Decimal, Not Null
    * `stock`: Integer, Not Null, Default 10
    * `category_id`: Integer, Foreign Key

* **Tag**
    * `id`: Integer, Primary Key, Auto Increment
    * `tag_name`: String

* **ProductTag**
    * `id`: Integer, Primary Key, Auto Increment
    * `product_id`: Integer, Foreign Key
    * `tag_id`: Integer, Foreign Key

## Associations

* **Product** belongs to **Category**, and **Category** has many **Product** models.
* **Product** belongs to many **Tag** models, and **Tag** belongs to many **Product** models through the **ProductTag** model.

## Walkthrough Video

Include a demonstration video showing the main functionalities of the project. Upload the video to a platform like YouTube and place the link here.

[Link to Walkthrough Video](#)

## Repository

The source code for the project is available on GitHub:

[GitHub Repository](https://github.com/Karimegtz/ECommerceBackEnd)

## License

This project is licensed under the MIT License. See the LICENSE file for more details.



