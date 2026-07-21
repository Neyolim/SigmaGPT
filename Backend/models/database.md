# Database Notes

---

# Part 1: Database Fundamentals

## 1. What is a Database?

A **Database** is an organized collection of data that allows you to store, manage, retrieve, and update information efficiently.

Instead of storing information in files, applications use databases so data can be accessed quickly and securely.

### Examples of data stored in a database

- User accounts
- Chat messages
- Products
- Orders
- Reviews
- Employee records

### Real-world examples

- Instagram stores user profiles, posts, and comments.
- Amazon stores products, customers, and orders.
- ChatGPT stores your conversation history.

> **Think of a database as a digital storage system for your application's data.**

---

## 2. What is a DBMS (Database Management System)?

A **DBMS (Database Management System)** is software that allows you to create, manage, and interact with databases.

Instead of communicating directly with the database, your application communicates through the DBMS.

### Responsibilities of a DBMS

- Create databases
- Store data
- Retrieve data
- Update data
- Delete data
- Manage users and permissions
- Handle backups
- Improve performance

### Popular DBMS

- MySQL
- PostgreSQL
- MongoDB
- Oracle
- Microsoft SQL Server
- SQLite

### How it works

```text
Application
      ↓
     DBMS
      ↓
 Database
```

> **A DBMS is software that manages a database.**

---

## 3. Why use a DBMS?

A **DBMS (Database Management System)** makes it easy to store, organize, retrieve, and manage data efficiently.

Without a DBMS, applications would have to manage data manually using files, which becomes difficult as the amount of data grows.

### Benefits of a DBMS

- Organizes data efficiently.
- Retrieves data quickly.
- Allows multiple users to access the database safely.
- Reduces data duplication.
- Improves data security.
- Supports backup and recovery.
- Handles large amounts of data.

### Example

Imagine you're building an e-commerce website.

Without a DBMS:

- Customer data might be stored in separate files.
- Searching for an order would be slow.
- Updating data would be difficult.
- Multiple users could accidentally overwrite each other's data.

With a DBMS:

- All data is stored in one organized database.
- Orders can be searched instantly.
- Data remains consistent and secure.
- Thousands of users can use the application at the same time.

> **A DBMS makes storing, managing, and retrieving data easier, faster, and more secure.**

---

## 4. Types of Databases

Databases are generally divided into two main categories.

### 1. Relational Database (RDBMS)

Stores data in **tables** made of rows and columns.

Example:

| ID  | Name  | Age |
| --- | ----- | --- |
| 1   | John  | 22  |
| 2   | Alice | 25  |

Examples:

- MySQL
- PostgreSQL
- Oracle
- Microsoft SQL Server

---

### 2. NoSQL Database

Stores data in flexible formats instead of tables.

Common NoSQL database types include:

- Document databases
- Key-value databases
- Graph databases
- Column-family databases

MongoDB is a **Document Database**.

Example:

```json
{
  "name": "John",
  "age": 22,
  "skills": ["JavaScript", "React"]
}
```

> **RDBMS stores data in tables, while NoSQL stores data in flexible structures like documents.**

---

## 5. What is SQL?

**SQL (Structured Query Language)** is the standard language used to communicate with **Relational Database Management Systems (RDBMS)**.

It allows you to create, read, update, and delete data stored in relational databases.

### What can SQL do?

- Create databases and tables.
- Insert data.
- Retrieve data.
- Update data.
- Delete data.
- Filter and sort data.
- Join multiple tables.

### Example

Retrieve all users:

```sql
SELECT * FROM users;
```

Insert data:

```sql
INSERT INTO users (name, age)
VALUES ('Neyo', 22);
```

Update data:

```sql
UPDATE users
SET age = 23
WHERE name = 'Neyo';
```

Delete data:

```sql
DELETE FROM users
WHERE name = 'Neyo';
```

### Databases that use SQL

- MySQL
- PostgreSQL
- Oracle
- Microsoft SQL Server
- SQLite

> **SQL is the language used to communicate with relational databases.**

---

## 6. Why was NoSQL created?

Traditional relational databases work extremely well for structured data.

However, as applications like Facebook, YouTube, Netflix, and Twitter grew, they faced new challenges:

- Massive amounts of data
- Millions of users
- Frequently changing data structures
- Need for horizontal scaling
- Faster development

RDBMS databases became difficult to scale for these workloads.

NoSQL databases were created to solve these problems by providing:

- Flexible schemas
- Easy scalability
- Faster handling of large datasets
- Better performance for certain workloads

### Example

Suppose you're building a social media application.

User A:

```json
{
  "name": "Neyo",
  "bio": "Developer"
}
```

User B:

```json
{
  "name": "Alice",
  "bio": "Designer",
  "website": "example.com"
}
```

In MongoDB, both documents are valid.

In most relational databases, you'd usually need to modify the table structure to accommodate new fields.

> **NoSQL was created to handle large-scale, flexible, and rapidly changing applications more efficiently.**

---

## 7. RDBMS vs NoSQL

| RDBMS                       | NoSQL                                              |
| --------------------------- | -------------------------------------------------- |
| Stores data in tables       | Stores data as documents or other flexible formats |
| Fixed schema                | Flexible schema                                    |
| Uses SQL                    | Does not require SQL                               |
| Strong relationships        | Flexible relationships                             |
| Best for structured data    | Best for rapidly changing data                     |
| Vertical scaling            | Horizontal scaling                                 |
| Examples: MySQL, PostgreSQL | Examples: MongoDB, Firebase                        |

---

## 8. When should you use RDBMS and when should you use NoSQL?

### Use RDBMS when:

- Data has a fixed structure.
- Relationships between data are important.
- Data consistency is critical.
- Complex SQL queries are required.

### Examples

- Banking systems
- Hospital management
- School management
- Inventory systems
- E-commerce orders

---

### Use NoSQL when:

- Data structure changes frequently.
- Fast development is important.
- Large amounts of data need to be stored.
- High scalability is required.

### Examples

- Chat applications
- Social media
- AI applications
- Content management systems
- Real-time analytics

### Which one should you choose?

There is no "best" database.

Choose the one that fits your application's needs.

- **Choose RDBMS** for structured data with strong relationships.
- **Choose NoSQL** for flexible, scalable, and rapidly evolving applications.

> **The database you choose should depend on your application's requirements, not on which technology is more popular.**

# Part 2: MongoDB & Mongoose

---

## 9. What is MongoDB?

**MongoDB** is a popular **NoSQL document database** that stores data as **documents** instead of tables.

Unlike relational databases, MongoDB stores data in a JSON-like format called **BSON**.

Example:

```json
{
  "name": "Neyo",
  "age": 22,
  "skills": ["JavaScript", "React", "MongoDB"]
}
```

Instead of tables and rows, MongoDB uses:

- **Collections** → Similar to tables.
- **Documents** → Similar to rows.

### Why is MongoDB popular?

- Flexible schema
- Easy to scale
- High performance
- Stores JSON-like data
- Works well with JavaScript and Node.js

### Real-world applications

- Chat applications
- Social media platforms
- E-commerce websites
- AI applications

> **MongoDB is a NoSQL database that stores data as documents inside collections.**

---

## 10. MongoDB vs MongoDB Atlas

Although they sound similar, they are not the same.

### MongoDB

MongoDB is the **database software**.

You install and run it on your own computer or server.

Example:

```text
localhost:27017
```

You are responsible for:

- Installation
- Updates
- Security
- Backups
- Maintenance

---

### MongoDB Atlas

MongoDB Atlas is the **cloud-hosted version** of MongoDB managed by MongoDB Inc.

You don't install MongoDB yourself.

Instead, MongoDB hosts and manages everything for you.

Benefits:

- Cloud hosted
- Automatic backups
- High availability
- Easy scaling
- Free tier available
- Accessible from anywhere

### Comparison

| MongoDB                    | MongoDB Atlas                         |
| -------------------------- | ------------------------------------- |
| Installed locally          | Hosted in the cloud                   |
| You manage everything      | MongoDB manages everything            |
| Best for local development | Best for production and remote access |

> **MongoDB is the database software, while MongoDB Atlas is the cloud service that hosts MongoDB databases.**

---

## 11. What is an ODM (Object Data Modeling)?

**ODM (Object Data Modeling)** is a technique that maps JavaScript objects to MongoDB documents.

Instead of working directly with MongoDB, you work with JavaScript objects.

```text
JavaScript Object
        ↓
     Mongoose (ODM)
        ↓
MongoDB Document
```

### Popular ODM

- Mongoose

> **Mongoose is the most popular ODM for MongoDB in Node.js.**

---

## 12. What is Mongoose?

**Mongoose** is an **ODM (Object Data Modeling)** library for Node.js that makes working with MongoDB easier.

It acts as a bridge between your Node.js application and MongoDB.

```text
Node.js
   ↓
Mongoose
   ↓
MongoDB
```

Instead of writing low-level database queries, you interact with MongoDB using JavaScript objects.

Example:

```js
await User.create({
  name: "Neyo",
  age: 22,
});
```

> **Mongoose simplifies communication between Node.js and MongoDB.**

---

## 13. Why use Mongoose?

Although you can use MongoDB directly, Mongoose provides many helpful features.

### Benefits of Mongoose

- Schemas
- Models
- Data validation
- Middleware (Hooks)
- Cleaner syntax
- Easier CRUD operations
- Better code organization

### Example

Without Mongoose:

```js
db.collection("users").insertOne({
  name: "Neyo",
});
```

With Mongoose:

```js
await User.create({
  name: "Neyo",
});
```

The Mongoose version is shorter, cleaner, and easier to maintain.

> **Mongoose makes MongoDB code cleaner, safer, and more organized.**

---

## 14. What is a Collection?

A **Collection** is a group of related documents in MongoDB.

It is similar to a **table** in a relational database.

Example:

```text
Database
│
├── users
├── chats
├── products
└── orders
```

Here:

- `users`
- `chats`
- `products`
- `orders`

are all collections.

> **A collection stores related documents.**

---

## 15. What is a Document?

A **Document** is a single record stored inside a collection.

It is similar to a **row** in a relational database.

Example:

Collection: **users**

```json
{
  "_id": "123",
  "name": "Neyo",
  "age": 22
}
```

Another document:

```json
{
  "_id": "124",
  "name": "Alice",
  "age": 25
}
```

Each object is a separate document.

> **A document is a single piece of data stored in a collection.**

---

## 16. What are Fields?

A **Field** is a single piece of information stored inside a document.

Think of a field as a **property** or **key-value pair** in a JavaScript object.

Example:

```json
{
  "name": "Neyo",
  "age": 22,
  "email": "neyo@example.com"
}
```

Here:

- `name` is a field.
- `age` is a field.
- `email` is a field.

Each field has:

- A **key** (field name)
- A **value**

Example:

| Field | Value            |
| ----- | ---------------- |
| name  | Neyo             |
| age   | 22               |
| email | neyo@example.com |

---

## 17. BSON vs JSON

MongoDB stores data internally as **BSON (Binary JSON)**.

### JSON

JSON is a lightweight text format used to exchange data between applications.

Example:

```json
{
  "name": "Neyo",
  "age": 22
}
```

---

### BSON

BSON stands for **Binary JSON**.

It is a binary representation of JSON that supports additional data types.

Examples of BSON data types:

- Date
- ObjectId
- Binary Data
- Decimal128

MongoDB automatically converts between JSON and BSON.

### Comparison

| JSON                    | BSON                       |
| ----------------------- | -------------------------- |
| Text format             | Binary format              |
| Easy for humans to read | Optimized for computers    |
| Used for APIs           | Used internally by MongoDB |

> **Applications send JSON, but MongoDB stores data as BSON.**

---

## 18. What is a Schema?

A **Schema** is the blueprint that defines the structure of documents stored in MongoDB.

It specifies:

- Fields
- Data types
- Required fields
- Default values
- Validation rules

Example:

```js
const userSchema = new mongoose.Schema({
  name: String,
  age: Number,
  email: String,
});
```

Here:

- `name` must be a String.
- `age` must be a Number.
- `email` must be a String.

The schema ensures that data follows a consistent structure.

### Why use a Schema?

- Keeps data organized.
- Prevents invalid data.
- Makes the database more consistent.
- Adds validation rules.

> **A schema defines what your data should look like before it is stored in the database.**

# Part 3: Working with Data in MongoDB

---

## 19. What is a Model?

A **Model** is created from a schema and is used to interact with the database.

It allows your application to perform CRUD (Create, Read, Update, Delete) operations.

Example:

```js
const User = mongoose.model("User", userSchema);
```

Now you can use the model to interact with the database.

```js
await User.create({
  name: "Neyo",
  age: 22,
});

const users = await User.find();
```

> **A model is the interface between your application and the database.**

---

## 20. Schema vs Model

Although they are related, a schema and a model serve different purposes.

### Schema

- Defines the structure of the data.
- Specifies fields and validation rules.
- Acts as a blueprint.

### Model

- Created from a schema.
- Used to interact with the database.
- Performs CRUD operations.

### Comparison

| Schema            | Model                                     |
| ----------------- | ----------------------------------------- |
| Blueprint         | Working object                            |
| Defines structure | Interacts with the database               |
| Cannot query data | Can create, read, update, and delete data |
| Created first     | Created from the schema                   |

Think of building a house:

```text
Blueprint
     ↓
House
```

- **Schema = Blueprint**
- **Model = Finished house you can use**

> **Schema defines the structure. Model works with the database.**

---

## 21. What does the `models` folder store?

The **`models`** folder stores all the Mongoose models used in the application.

Each model represents a collection in the MongoDB database and contains:

- A Mongoose schema.
- A Mongoose model.
- Validation rules.
- Schema options (such as `timestamps`).
- Model export.

### Example

```text
models/
├── User.js
├── Chat.js
├── Message.js
└── Thread.js
```

Example: `User.js`

```js
import mongoose from "mongoose";

const userSchema = new mongoose.Schema(
  {
    name: String,
    email: String,
  },
  {
    timestamps: true,
  },
);

const User = mongoose.model("User", userSchema);

export default User;
```

### Why use a `models` folder?

- Keeps database-related code organized.
- Makes models reusable throughout the application.
- Separates database logic from routes and controllers.
- Makes the project easier to maintain as it grows.

> **The `models` folder stores the schemas and models that define and interact with your MongoDB collections.**

---

## 22. What are CRUD Operations?

CRUD represents the four basic operations performed on data.

| Letter | Meaning |
| ------ | ------- |
| C      | Create  |
| R      | Read    |
| U      | Update  |
| D      | Delete  |

### Examples

Create

```js
await User.create({
  name: "Neyo",
});
```

Read

```js
const users = await User.find();
```

Update

```js
await User.updateOne({ name: "Neyo" }, { age: 23 });
```

Delete

```js
await User.deleteOne({
  name: "Neyo",
});
```

Almost every web application performs CRUD operations.

> **CRUD is the foundation of working with databases.**

---

## 23. What is an Enum?

An **Enum (Enumeration)** limits a field to a predefined set of allowed values.

Example:

```js
status: {
  type: String,
  enum: ["pending", "completed", "cancelled"]
}
```

Valid values:

```text
pending
completed
cancelled
```

Invalid values:

```text
done ❌
finished ❌
abc ❌
```

### Why use Enums?

- Prevent invalid data.
- Keep values consistent.
- Improve data validation.

> **An enum restricts a field to a fixed list of allowed values.**

---

## 24. Embedding vs Referencing

There are two common ways to store related data in MongoDB.

### 1. Embedding

Related data is stored inside the same document.

Example:

```json
{
  "name": "Neyo",
  "address": {
    "city": "Kathmandu",
    "country": "Nepal"
  }
}
```

#### Advantages

- Faster reads.
- Simpler queries.

#### Best for

- Data that always belongs together.

---

### 2. Referencing

Related data is stored in different collections and connected using IDs.

Users Collection

```json
{
  "_id": "123",
  "name": "Neyo"
}
```

Orders Collection

```json
{
  "userId": "123",
  "product": "Laptop"
}
```

#### Advantages

- Avoids duplicate data.
- Easier to update shared information.

#### Best for

- Large or frequently changing relationships.

### Comparison

| Embedding                    | Referencing                      |
| ---------------------------- | -------------------------------- |
| Stores related data together | Stores related data separately   |
| Faster reads                 | Better for complex relationships |
| Can duplicate data           | Reduces duplication              |

> **Embed when data belongs together. Reference when data is shared across multiple documents.**

---

## 25. What is Indexing?

An **Index** is a special data structure that helps MongoDB find documents faster.

Without an index, MongoDB may need to scan every document in a collection.

With an index, MongoDB can quickly locate matching documents.

Example:

Without Index

```text
1 → 2 → 3 → 4 → 5 → 6 → 7 → Find "John"
```

With Index

```text
Index
   ↓
John found immediately
```

### Why use Indexes?

- Faster search.
- Faster sorting.
- Better performance.

### Drawback

Indexes use additional storage space and can slightly slow down insert and update operations because MongoDB must maintain the indexes.

> **Indexes improve query performance by making data easier to find.**

---

## 26. What is an Aggregation Pipeline?

An **Aggregation Pipeline** processes documents through multiple stages to transform, filter, group, or summarize data.

Think of it like an assembly line where each stage performs a specific task.

Example:

```text
Documents
      ↓
Filter
      ↓
Group
      ↓
Sort
      ↓
Final Result
```

Common aggregation stages include:

- `$match` → Filter documents.
- `$group` → Group documents.
- `$sort` → Sort documents.
- `$project` → Select specific fields.
- `$limit` → Limit the number of results.

Aggregation is commonly used for:

- Reports.
- Analytics.
- Dashboards.
- Statistics.

> **Aggregation allows MongoDB to process and analyze data efficiently.**
