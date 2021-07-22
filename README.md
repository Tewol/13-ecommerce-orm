# 13 Object-Relational Mapping (ORM): E-Commerce Back End


    This is a back-end e-commerce site that uses the latest technologies to compete with other e-commerce companies.


## Functionality 

* Connect to a database using Sequelize by adding database name, MySQL username, and MySQL password to an environment variable file.

* Entering schema and seed commands will create a development database and is seeded with test data

* Entering a command to invoke the application will start the server and the Sequelize models are synced to the MySQL database

* Opening API GET routes in Insomnia Core for categories, products, or tags will display the data for each of the routes in a formatted JSON.

* Testing API POST, PUT, and DELETE routes in Insomnia Core will able to successfully create, update, and delete data in my database

## Demo

* GET routes to return all categories, all products, and all tags being tested:

    ![Tests “GET tags,” “GET Categories,” and “GET All Products.”.](./images/demo1.gif)

* GET routes to return a single category, a single product, and a single tag being tested:

    ![Tests “GET tag by id,” “GET Category by ID,” and “GET One Product.”](./images/demo2.gif)

* POST, PUT, and DELETE routes for categories being tested:

    ![Tests “DELETE Category by ID,” “CREATE Category,” and “UPDATE Category.”](./images/demo3.gif)


## Installation and Usage 

* npm init
* npm install sequelize
* npm install mysql2
* npm install --save mysql
* npm install dotenv

* npm run seed to seed data to your database.
* npm start


## Database Models

Database contain the following four models, including the requirements listed for each model:

* `Category`

  * `id`: Integer, not null values, primary key, auto increment.

  * `category_name`: String, not null values

* `Product`

  * `id`: Integer, not null values, primary key, auto increment.

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

## Associations

* `Product` belongs to `Category`, and `Category` has many `Product` models.

* `Product` belongs to many `Tag` models, and `Tag` belongs to many `Product` models.


## API Routes to create, read, update, and delete operations using sequelize models.

* `product-routes.js` 
* `tag-routes.js`
* `category-routes.js` 


## Submission

* URL of the GitHub repository: https://github.com/Tewol/13-ecommerce-orm

* A video demonstrating the entirety of the app's functionality: https://app.scre.io/#/my-videos/1

---
© 2021 Hewan Redie.
