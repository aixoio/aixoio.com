---
title: "Why SQL won"
pubDate: 2024-07-14
---

In this post we will be talking about databases
and comparing popular SQL databases to popular
NoSQL databases.

Let's start with explaining what each option is
a SQL database or RDBMS is a way to store data in
rows and columns within a table. Here is an example
users table:

| ID | Username | Password |
| -- | -------- | ---------|
| 1  | Admin    | admin    |
| 2  | User     | user     |
| 3  | Test     | Test     |

Lets say each user has a pet. Here is the pets table:

| ID | User ID | Pet |
| -- | ------- | --- |
| 1  | 1       | Cat |
| 2  | 2       | Dog |
| 3  | 3       | Dog |

As you can see, the data is stored in tables and
you would need to join the tables together to get 
the username, and pet in the same query. With this
it would be easy to count all of the pets or count
all of the users, it is also easy to count all users
who have a pet or not. Some popular RDBMS are MySQL,
PostgreSQL and SQLite. It is easy to find hosting
for SQL databases because they are so common, they
can be harder to scale when compared to NoSQL databases.

Now lets make the same data in a popular NoSQL database,
MongoDB. MongoDB stores data in JSON-like documents without
a structure, so the data types can change over time. Here
is our example in MongoDB:

This would be the users collection:
```json
{
    "_id": "1",
    "username": "Admin",
    "password": "admin"
}
```

Here is the pets collection:
```json
{
    "_id": "1",
    "user_id": "1",
    "pet": "cat"
}
```

However it could also be one collection users:
```json
{
    "_id": "1",
    "username": "Admin",
    "password": "admin",
    "pet": "cat"
}
```

As you can see both NoSQL and SQL databases are good options
but because MongoDB does not force a structure on to your data,
it can be harder to model your data and will change based on your program's
use case because of this it makes SQL easier to use and structure,
when compared to MongoDB.

With all of that in mind I think RDBMS are going to stay
as the best databases to use for most projects.

Thanks for reading.

