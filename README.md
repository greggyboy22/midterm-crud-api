1. What was the most challenging part of building this API?

The most challenging part was connecting the API to the MySQL database and making sure everything worked properly. I also experienced errors when setting up the environment variables and database connection. I learned how to troubleshoot errors and fix them.

2. How does TypeORM make database operations easier compared to raw SQL?

TypeORM makes database operations easier because we can use JavaScript or TypeScript instead of writing SQL queries all the time. It allows us to create, read, update, and delete data using entities and simple commands.

3. Why is it important to exclude the password field from API responses? How did you implement this?

It is important because passwords are private information. If passwords are included in API responses, other people might access them. I implemented this by excluding the password field when returning user information from the API.

4. Describe a scenario where you would need to use database transactions instead of individual operations.

A good example is transferring money from one bank account to another. The system needs to subtract money from one account and add it to another. A transaction makes sure both operations succeed together. If one fails, the changes can be rolled back.

5. What is the difference between synchronize: true and migrations? When should you use each?

synchronize: true automatically updates the database structure based on the entities in the code. It is useful during development and testing.

Migrations are used to make controlled changes to the database structure. They are better for production because they allow developers to track and manage database changes safely.

6. If you had to add a Product entity with a relationship to User (a user can have many products), how would you modify the code?

I would create a new Product entity and connect it to the User entity using a One-to-Many relationship. A user can have many products, while each product belongs to one user.

I would use @OneToMany() in the User entity and @ManyToOne() in the Product entity.

7. What security improvements would you make before deploying this API to production?

I would improve the security by adding password hashing, authentication, and rate limiting. I would also protect private routes, validate user inputs, and use environment variables to keep sensitive information safe. These improvements would help protect the API and its users.

Authentication: Protect endpoints using JWT or session tokens.

Rate Limiting & Validation: Use express-rate-limit to prevent brute-force attacks and validate input with class-validator.

Environment: Set NODE_ENV=production, turn off synchronize, and restrict CORS origins.



7.1
1. What was the most challenging part of building this API?

The most challenging part was connecting the API to the MySQL database and making sure everything worked properly. I also experienced errors when setting up the environment variables. I learned how to troubleshoot and fix these problems.

2. How does TypeORM make database operations easier compared to raw SQL?

TypeORM makes database operations easier because we can use TypeScript instead of writing SQL queries all the time. It allows us to create, read, update, and delete data using simple commands.

3. Why is it important to exclude the password field from API responses? How did you implement this?

It is important because passwords are private information. If passwords are exposed, other people might misuse them. I implemented this by excluding the password field when returning user information from the API.

4. Describe a scenario where you would need to use database transactions instead of individual operations.

One example is transferring money between two bank accounts. The system needs to subtract money from one account and add it to another. A transaction makes sure both operations succeed together. If one fails, the changes can be rolled back.

5. What is the difference between synchronize: true and migrations? When should you use each?

synchronize: true automatically updates the database structure based on the entities in the code. It is useful during development and testing.

Migrations are used to manage database changes manually and safely. They are recommended for production because they help prevent unexpected changes or data loss.

6. If you had to add a Comment entity (tasks can have many comments), how would you modify the code?

I would create a new Comment entity and connect it to the Task entity using a One-to-Many relationship. I would use @OneToMany() in the Task entity and @ManyToOne() in the Comment entity. This allows one task to have multiple comments.

7. What security improvements would you make before deploying this API to production?

I would add password hashing, authentication, and rate limiting. I would also validate user inputs, protect private routes, and use environment variables to protect sensitive information. These improvements would make the API safer.

8. Why did you need to add the ! (definite assignment operator) to your entity properties?

I added the ! symbol because TypeScript requires class properties to be initialized. The symbol tells TypeScript that the properties will receive their values later, usually when TypeORM loads data from the database.

9. What are the benefits of explicitly defining column types (e.g., type: 'varchar') in your entities?

Explicitly defining column types helps TypeORM understand what kind of data will be stored in the database. It also makes the database structure clearer and helps prevent data type errors.

10. How do relationships in TypeORM differ from foreign keys in raw SQL? What are the advantages?

In raw SQL, we manually create foreign keys to connect tables. In TypeORM, we use decorators like @OneToMany() and @ManyToOne() to define relationships between entities. This makes the code easier to understand and manage because TypeORM handles much of the relationship mapping for us.
Advantages: Simplifies nested entity loading (relations: ['comments']), provides compile-time type safety, and eliminates manual SQL JOIN queries.  