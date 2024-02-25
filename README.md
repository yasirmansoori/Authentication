<h1 align="center">LEAP Bootcamp Assignment</h1>
<div align="center">
Welcome to the LEAP Bootcamp documentation and codebase, before you get started please read the following instructions.
</div>

## Tech Stack Used
![Javascript](https://img.shields.io/badge/Javascript-F0DB4F?style=for-the-badge&labelColor=black&logo=javascript&logoColor=F0DB4F)
![express](https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white)
![Nodejs](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![npm](https://img.shields.io/badge/npm-CB3837?style=for-the-badge&logo=npm&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)
![Api](https://img.shields.io/badge/Api-4EA94B?style=for-the-badge&logo=api&logoColor=white)
![Markdown](https://img.shields.io/badge/Markdown-000000?style=for-the-badge&logo=markdown&logoColor=white)
![VSCode](https://img.shields.io/badge/Visual_Studio-0078d7?style=for-the-badge&logo=visual%20studio&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-black?style=for-the-badge&logo=github&logoColor=white)

## 🔑 Key Features

### Role-Based User Authentication:
- Define Roles:
  - Admin
  - User
- Role Assignment by Admin
- Authorization Middleware
- Seperate admin and user routes
- User and Admin authentication using JWT
- Protected Routes

## 📦 Getting Started

- Clone the repository:
```sh
git gh repo clone yasirmansoori/Authentication
```
- Install dependencies:
```sh
 npm install
```
- Start the development server:
```sh
  npm run dev
```

## 📝 Environment Variables

- Create a .env file in the root of the server directory and add the following environment variables:
```sh
MONGODB_URI = "Your MongoDB URI"
DATABASE_NAME = "Your Database Name"
SECRET_KEY = "Your Secret Key"
ACCESS_TOKEN_SECRET = "Your Access Token Secret"
REFRESH_TOKEN_SECRET = "Your Refresh Token Secret"
```
## Note:
You can generate your own access and refresh token secrets by running the following command in your terminal 2 times:
```sh
node -e "console.log(require('crypto').randomBytes(32).toString('hex'));"
```
or you can use the secretGenerator.js file in the directory `src/config` to generate your secrets.

## 📚Schema Overview
-   ### User

    -   `_id` _(auto-generated-unique)_ 
    -   `name`
    -   `email` _(unique)_
    -   `username` 
    -   `role` _(admin/user)_
    -   `password` _(encrypted)_

## **🚀API Router Endpoints** 

<h1>General Routes -</h1>
<table>
  <tr>
    <th colspan="3" style="text-align:center">User</th>
  </tr>
  <tr>
    <td>Endpoints</td>
    <td>Method</td>
    <td>Description</td>
  </tr>
  </tr>
  <tr>
    <td>/</td>
    <td>GET</td>
    <td>Welcome API</td>
  </tr>
  <tr>
    <td>/protected</td>
    <td>GET</td>
    <td> Protected Routes</td>
  </tr>
</table>

## Note:
- Here protected routes means that they are only accessible when a user is logged in and has a valid JWT token, you can create your own protected routes by using the `protect` middleware in the routes.


<h1>Admin Routes -</h1>
<table>
  <tr>
    <th colspan="3" style="text-align:center">User</th>
  </tr>
  <tr>
    <td>Endpoints</td>
    <td>Method</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>/api/admin/users</td>
    <td>GET</td>
    <td>Get all the users in the database.</td>
  </tr>
  <tr>
    <td>/api/admin/users/:id</td>
    <td>GET</td>
    <td>Get a single user by id.</td>
  </tr>
    <tr>
    <td>/api/admin/users/:id</td>
    <td>PUT</td>
    <td>Update a user by id.</td>
  </tr>
  <tr>
    <td>/api/admin/users/:id</td>
    <td>DELETE</td>
    <td>Delete a user by id.</td>
  </tr>
</table>

<h1>User Routes -</h1>
<table>
  <tr>
    <th colspan="3" style="text-align:center">User</th>
  </tr>
  <tr>
    <td>Endpoints</td>
    <td>Method</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>/api/user/register</td>
    <td>POST</td>
    <td>Welcome aboard! Register as a new user.</td>
  </tr>
  <tr>
    <td>/api/user/login</td>
    <td>POST</td>
    <td>Dive into the your website. Login and receive a JWT token.</td>
  </tr>
    <tr>
    <td>/api/user/refresh-token</td>
    <td>POST</td>
    <td>Ran out of time? Get a new JWT token.</td>
  </tr>
  <tr>
    <td>/api/user/logout</td>
    <td>DELETE</td>
    <td>Time to say goodbye? Logout and expire your JWT.</td>
  </tr>
</table>

## **API Response Codes**
|                    | `200` | `201`   | `400`       | `401`        | `403`     | `404`     | `500`                 | `503`               |
| ------------------ | ----- | ------- | ----------- | ------------ | --------- | --------- | --------------------- | ------------------- |
| API Response Codes | OK    | Created | Bad Request | Unauthorized | Forbidden | Not Found | Internal Server Error | Service Unavailable |

## **API Response Structure**
|                    | `status`           | `message`                | `data`        | `error`                |
| ------------------ | ------------------ | ------------------------ | ------------- | ---------------------- |
| API Response Codes | HTTP Response Code | Response message Created | Response data | Error message (if any) |

<div align="center">Made with ❤️</div>