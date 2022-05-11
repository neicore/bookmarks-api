# Bookmarks API
Simple CRUD api with authentication and authorization to help me learn NestJS and backend development in general.

## Tech Stack
- NestJS
- Prisma
- Postgres

## Features
- Create, read, update, delete bookmarks
- Create users and edit user information
- Authenticates users and issues jwt access token

## How to use
To run the project loccally you need to have node installed and a database setup. I don't know much about setting up databases, I used Postgres for this project and Prisma is configured for postgres so if you want to use a different database make sure you update the schema.prisma file. I connected the database to the project using a .env file and had a variable called DATABASE_URL which is the url to the database. The .env is ignored by git, cause I have to practice not pushing my .env file to github 😅.

After having node installed and a database set up, run the following command in the project root to install all dependencies:
`npm install`

After all dependencies are done installing, use the following command to run the project:
`npm run start`

The project will run on http://localhost:3000/ you can change the port in the main.ts file.

### Testing the project:
There are 5 endpoints in this project. You can test them using Postman, Insomnia or any other testing tool that is used for this sort of thing. 

1. https://localhost:3000/api/signup
   - Here you can provide an email and a password to create a new user and get access token for the said user.
   - You can also provide firstname and lastname but those are not required.
   - It accepts a POST request.

2. https://localhost:3000/api/login
   - Here you can provide an email and a password to login and existing user and get access token.
   - It accepts a POST request.

3. http://localhost:3000/user/me
    - Here you can get the user information for the user that is logged in. You will have to provide the access token in the Authorization header.
    - It accepts a GET request.

4. http://localhost:3000/bookmarks
    - Here you can get all the bookmarks for the user that is logged in or create a new bookmark. You will have to provide the access token in the Authorization header.
    - It accepts a GET and POST requests.

5. http://localhost:3000/bookmarks/:id
  - Here you can get, edit, or delete a bookmark using a specific id.
  - It accepts a GET, PATCH, and DELETE requests.