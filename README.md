# 13 Object-Relational Mapping (ORM): E-Commerce Back End


    ``Internet retail, also known as e-commerce, is the largest sector of the electronics industry, generating an estimated $29 trillion in 2019. 
    
    This is a back-end e-commerce site that uses the latest technologies so that the company can compete with other e-commerce companies. You’ll configure a working Express.js API to use Sequelize to interact with a MySQL database.``



## Functionality 

* Connect to a database using Sequelize by adding database name, MySQL username, and MySQL password to an environment variable file.

* Entering schema and seed commands will create a development database and is seeded with test data

* Entering a command to invoke the application will start the server and the Sequelize models are synced to the MySQL database

* Opening API GET routes in Insomnia Core for categories, products, or tags will display the data for each of the routes in a formatted JSON.

* Testing API POST, PUT, and DELETE routes in Insomnia Core will able to successfully create, update, and delete data in my database

## Mock-Up

* The following animation shows the application's GET routes to return all categories, all products, and all tags being tested in Insomnia Core:

    ![In Insomnia Core, the user tests “GET tags,” “GET Categories,” and “GET All Products.”.](./Assets/13-orm-homework-demo-01.gif)

* The following animation shows the application's GET routes to return a single category, a single product, and a single tag being tested in Insomnia Core:

    ![In Insomnia Core, the user tests “GET tag by id,” “GET Category by ID,” and “GET One Product.”](./Assets/13-orm-homework-demo-02.gif)

* The following animation shows the application's POST, PUT, and DELETE routes for categories being tested in Insomnia Core:

    ![In Insomnia Core, the user tests “DELETE Category by ID,” “CREATE Category,” and “UPDATE Category.”](./Assets/13-orm-homework-demo-03.gif)

* A walkthrough video that shows the POST, PUT, and DELETE routes for products and tags being tested in Insomnia Core.

## Getting Started

* MySQL2: https://www.npmjs.com/package/mysql2
* Sequeliz: https://www.npmjs.com/package/sequelize
* dotenv:https://www.npmjs.com/package/dotenv

Use the `schema.sql` file in the `db` folder to create your database with MySQL shell commands. Use environment variables to store sensitive data like your MySQL username, password, and database name.

### Database Models

Your database should contain the following four models, including the requirements listed for each model:

* `Category`

  * `id`: Integer, not null values, primary key, auto increment.

  * `category_name`: String, not null values

* `Product`

  * `id`Integer, not null values, primary key, auto increment.

  * `product_name`: String, not null values.

  * `price`: decimal, not null values, Validates the value is a decimal.

  * `stock`: Integer, not null values, default value of `10`, validates the value is numeric.

  * `category_id`: Integer, references the `Category` model's `id`.

* `Tag`

  * `id`: Integer, not null values, primary key, auto increment.

  * `tag_name`: String.

* `ProductTag`

  * `id`: Integer, not null values, primary key, auto increment.

  * `product_id`: Integer, References the `Product` model's `id`.

  * `tag_id`: Integer, References the `Tag` model's `id`.

### Associations

You'll need to execute association methods on your Sequelize models to create the following relationships between them:

* `Product` belongs to `Category`, and `Category` has many `Product` models, as a category can have multiple products but a product can only belong to one category.

* `Product` belongs to many `Tag` models, and `Tag` belongs to many `Product` models. Allow products to have multiple tags and tags to have many products by using the `ProductTag` through model.


### Fill Out the API Routes to Perform RESTful CRUD Operations

Fill out the unfinished routes in `product-routes.js`, `tag-routes.js`, and `category-routes.js` to perform create, read, update, and delete operations using your Sequelize models.

Note that the functionality for creating the many-to-many relationship for products has already been completed for you.


### Seed the Database

After creating the models and routes, run `npm run seed` to seed data to your database so that you can test your routes.

### Sync Sequelize to the Database on Server Start

Create the code needed in `server.js` to sync the Sequelize models to the MySQL database on server start.


---
© 2021 Hewan Redie.
