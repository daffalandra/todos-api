# Todos API
 A simple API for managing todos, built with Ruby on Rails.
 ## Table of Contents- 
 - [Getting Started](#getting-started)
 - [Prerequisites](#prerequisites)
 - [Installation](#installation)
 - [Running the API](#running-the-api)
 - [API Endpoints](#api-endpoints)
 - [Testing](#testing)
 
 ## Getting Started
 This API allows users to create, read, update, and delete (CRUD) todo items. It's designed as a
 basic template to start building and deploying a Ruby on Rails-based API.
 ## Prerequisites
 - **Ruby**: Ensure you have Ruby installed. Version 3.0+ is recommended.
 - **Rails**: The project uses Rails 7+.
 - **Bundler**: `gem install bundler` if you haven't installed it.
 - **Git**: For version control and cloning the repository.
   
## Installation
 1. **Clone the Repository**
   ```bash
   git clone https://github.com/daffalandra/todos-api.git
   cd todos-api
   ```
 2. **Install Dependencies**
   Run the following to install necessary gems:
   ```bash
   bundle install
   ```
 3. **Database Setup**
   Set up and migrate the database:
   ```bash
   rails db:create
   rails db:migrate
   ```
 ## Running the API
 To start the Rails server, run:
 ```bash
 rails s
 ```
 The API will be accessible at `http://localhost:3000`.
 ## API Endpoints
 | Endpoint                | Method | Description              |
 |-------------------------|--------|--------------------------|
 | `/signup`               | POST   | Create new User,         |
 |                         |        | and get Authorization key|
 | `/todos`                | GET    | Retrieve all todos       |
 | `/todos/:id`            | GET    | Retrieve a single todo   |
 | `/todos`                | POST   | Create a new todo        |
 | `/todos/:id`            | PUT    | Update an existing todo  |
 | `/todos/:id`            | DELETE | Delete a todo            |
 | `/todos/:todo_id/items` | POST   | Create a new item        |
 | `/todos/:todo_id/items` | GET    | Retrieve all item on one |
 |                         |        | todo                     |
 | `/todos/:id/items`      | PUT    | Update an existing todo  |
 |                         |        | item                     |
 | `/todos/:id/items`      | DELETE | Delete a todo item       |
 
 
### Sample Requests with postman
- **Create a new User**
  ```bash
  # Signup a new user - get token from here
  POST http://localhost:3000/signup name=ash email=ash@email.com password=foobar password_confirmation=foobar
  # Will return auth_token
  ```
- **Get all Todos** 
  ```bash
  GET http://localhost:3000/todos
  Set Header Authorization = 'auth_token'
  ```
  - **Create a New Todo**
  ```bash
  POST http://localhost:3000/todos?title=Bach&created_by=1
  Set Header Authorization = 'auth_token'
  ```
  - **Update a Todo**
  ```bash
  PUT http://localhost:3000/todos/:id?title=Beethoven (:id = 1)
  Set Header Authorization = 'auth_token'
  ```
  - **Destroy a Todo** 
  ```bash
  DELETE http://localhost:3000/todos/:id (:id = 1)
  Set Header Authorization = 'auth_token'
  ```
  ### Sample Requests- **Get all Items** with postman
  ```bash
  GET http://localhost:3000/todos/:todo_id/items
  Set Header Authorization = 'auth_token'
  ```
  - **Create a New Todo**
  ```bash
  POST http://localhost:3000/todos/:todo_id/items?name=Listen to 5th Symphony&done=false (todo_id = 1)
  Set Header Authorization = 'auth_token'
  ```
  - **Update a Todo**
  ```bash
  PUT http://localhost:3000/todos/:todo_id/items/:id?done=true (todo_id = 1, id = 1)
  Set Header Authorization = 'auth_token'
  ```
  - **Destroy a Todo** 
  ```bash
  DELETE http://localhost:3000/todos/:todo_id/items/:id (todo_id = 1, id = 1)
  Set Header Authorization = 'auth_token'
  ```
 ## Testing
 To run the tests, use:
 ```bash
 bundle exec rspec
 ```
