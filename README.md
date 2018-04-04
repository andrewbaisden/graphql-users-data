# Graphql Users Data App

In the root folder run the commands below. You will need to run the express server, and the JSON server to get the app working.

## Installation

Install node

```bash
npm install
```

Run the express server

```bash
npm run dev
```

Run the JSON Server

```bash
npm run json:server
```

http://localhost:4000/graphql for the GraphiQL, in-browser IDE tool, used for queries and mutations.

http://localhost:3000/ for the JSON Server

The database for users and companies is in root/db.json. You can see the changes at http://localhost:3000/ and in the root/db.json file.

Example search user query

```javascript
{
    user(id: "100") {
      firstName
      company {
        id
        name
        description
      }
    }
  }
```

Example add user mutation

```javascript
mutation {
  addUser(firstName: "Karen" age: 35) {
    id
    firstName
    age
  }
}
```

Example delete user mutation

```javascript
mutation {
    deleteUser(id: "40") {
      id
    }
  }
```

Example edit user mutation

```javascript
  mutation {
    editUser(id: "21" firstName: "Lucy" age: 27 companyId: "6") {
      id
      age
      firstName
      company {
          name
      }
    }
  }
```
