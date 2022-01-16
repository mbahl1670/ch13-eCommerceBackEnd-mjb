# E-Commerce Back End - Challenge #13 in the U of MN Bootcamp

## Built With
* Node.js
* SQL/mysql2
* Sequelize
* Express
* dotenv

## Description
We have set up the back end for an E-commerce database using Express.  To interact with the SQL database we are going to use Sequelize so we can interact with the database using javascript.  The use of dotenv enables us to hide our username & password.

## Table of Contents
* [Installation](#installation)
* [Acceptance Criteria](#acceptance-criteria)
* [Walkthrough Vido](#walkthrough-video)
* [Screenshot of the Application](#screenshot-of-the-application)
* [Git Repository](#git-repository)
* [How this was accomplished](#how-this-was-accomplished)

## Installation
* npm init -y
* update package.json
  * "main": server.js  instead of  "main": "index.js"
  * add scrips
    * "start": "node server.js"
    * "seed": "node seeds/index.js"
* npm install express sequelize mysql2 dotenv


## Acceptance Criteria
* When you add your database name, MySql username & MySql passord to an environmental variable file you are able to connect to the database using Sequelize
* When you enter the schema and seed commands the database is created and seeded with test data
* When you enter the command to invoke the applicaton the server is started and the Sequelize models are synced to the MySql database
* When you open API GET routes in insomnia core for categories, products and tags the data for each is displayed in formatted Json
* When POST, PUT and DELETE routes are tested in insomnia you can create, update and delete information in the database

## Walkthrough Video
https://watch.screencastify.com/v/xXzeGNcFsfBCUgvZYaTm

## Screenshot of the Application
![Screenshot (46)](https://user-images.githubusercontent.com/90292697/149643579-4fb95f45-4d0a-49a7-ba03-9f1f183febb9.png)
![Screenshot (47)](https://user-images.githubusercontent.com/90292697/149643582-2e4fb932-2bbd-4a4b-a571-d15a47eed37e.png)

## Git Repository
https://github.com/mbahl1670/ch13-eCommerceBackEnd-mjb


## How this was accomplished
* Worked on the connection.js file to pull the info from the .env file to log into the database
* Changed the server.js file from app.listen to sequelize.sync to open the connection
* Worked on the Models: Category, Product, Tags, ProductTag.  Followed with the recomendations from the assignment and modules
* Established the connections between the Models.  As one-to-many relationship for Product/Category.  And a many-to-many relationship between products/taga through the third table of ProductTag
* Worked on each route one at a time.  Product routs, Category routes, Tag routes
  * Product Post & Put routes were already done for us
  * For Category delete route it was discovered the model for Product needed to include allowNull: true under category_id, otherwise a category could not be deleted
