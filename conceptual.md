### Conceptual Exercise

Answer the following questions below:

- What is PostgreSQL?
PostgreSQL is a powerful, open-source relational database management system (RDBMS) that is known for its robustness, extensibility, and compliance with SQL standards. It is commonly used as a backend database for web applications and various types of software.

- What is the difference between SQL and PostgreSQL?
SQL is a language used to interact with relational databases, while PostgreSQL is a specific relational database management system that incorporates the SQL language. PostgreSQL is an implementation of a database system that adheres to the SQL standard, and it provides additional features and capabilities specific to its design and architecture. So, when people refer to PostgreSQL, they are often referring to both the SQL language it supports and the specific database system itself.

- In `psql`, how do you connect to a database?

psql -h hostname -d dbname -U username -W

- What is the difference between `HAVING` and `WHERE`?
HAVING and WHERE clauses are both used in SQL queries to filter and retrieve specific data, but they are used in different contexts.
WHERE clause filters rows before they are grouped, while the HAVING clause filters the results of aggregate functions after grouping. If you are not using aggregate functions or grouping in your query, you would typically use WHERE. If you are working with aggregated data, you would use HAVING to filter the grouped results based on aggregate conditions.

- What is the difference between an `INNER` and `OUTER` join?
The terms "INNER join" and "OUTER join" refer to different types of joins in SQL, which are used to combine rows from two or more tables based on a related column between them. An INNER join returns only the matching rows, while an OUTER join returns all rows from one table and the matching rows from another table, including unmatched rows with NULL values.

- What is the difference between a `LEFT OUTER` and `RIGHT OUTER` join?
The main difference between a LEFT OUTER JOIN and a RIGHT OUTER JOIN lies in the treatment of unmatched rows from the tables involved in the join. Both types of joins are part of the family of OUTER JOINs, which includes LEFT OUTER JOIN, RIGHT OUTER JOIN, and FULL OUTER JOIN. The primary distinction between LEFT OUTER JOIN and RIGHT OUTER JOIN is the table from which all rows are included in the result set. In a LEFT OUTER JOIN, all rows from the left table are included, while in a RIGHT OUTER JOIN, all rows from the right table are included. The choice between them depends on which table's data you want to preserve in the result set, regardless of whether there are matching rows in the other table.

- What is an ORM? What do they do?
ORM stands for Object-Relational Mapping. It is a programming technique and a concept in software development that involves the conversion of data between incompatible type systems, namely object-oriented programming languages and relational databases.

The primary purpose of an ORM is to bridge the gap between the object-oriented programming (OOP) paradigm, which uses objects, and relational databases, which store data in tables with rows and columns. ORMs provide a way to interact with databases using programming language objects instead of writing raw SQL queries.

Key functionalities and tasks performed by an ORM include:

Mapping Objects to Database Tables:

ORM frameworks automatically map the structure of objects in a programming language (such as classes in Java, Python, or C#) to the structure of database tables.
Each object typically corresponds to a row in a table, and object properties (attributes) correspond to table columns.
Data Querying and Retrieval:

ORMs provide a set of APIs or methods for querying and retrieving data from the database using programming language constructs rather than SQL queries.
Developers can use these APIs to perform CRUD (Create, Read, Update, Delete) operations on database records.
Relationship Handling:

ORMs allow developers to define and manage relationships between objects, such as one-to-one, one-to-many, or many-to-many relationships.
The ORM framework takes care of generating the appropriate SQL queries to handle these relationships.
Database Schema Generation:

ORMs often provide tools to automatically generate or synchronize database schemas based on changes in the object model.
This helps in maintaining consistency between the application's data model and the database schema.
Transaction Management:

ORMs often support transaction management, allowing developers to group multiple database operations into a single transaction that is either committed or rolled back as a whole.
Cross-Database Compatibility:

Some ORMs provide a level of abstraction that allows developers to work with different database systems without having to change their application code significantly.
Popular ORM frameworks include Hibernate for Java, Entity Framework for .NET, Django ORM for Python, and Sequelize for Node.js, among others.

While ORMs offer convenience in terms of abstraction and ease of use, it's essential for developers to understand the underlying database system and be mindful of performance implications to use them effectively.

- What are some differences between making HTTP requests using AJAX 
  and from the server side using a library like `requests`?
Making HTTP requests using AJAX (Asynchronous JavaScript and XML) on the client side and using a server-side library like requests in a programming language such as Python involves different approaches and has distinct characteristics. Here are some key differences:

1. Execution Context:

AJAX (Client-Side): AJAX operates on the client side within a web browser. It allows the client to make asynchronous requests to a server without requiring a full page reload.
Server-Side (requests): The requests library is typically used on the server side to initiate HTTP requests from a server or backend application.
2. Language and Environment:

AJAX (Client-Side): AJAX is usually implemented using JavaScript and runs in the browser environment.
Server-Side (requests): requests is a Python library used on the server side within a Python environment.
3. Browser Interaction:

AJAX (Client-Side): AJAX allows for dynamic content updates on a web page without a full page reload. It is often used to update specific parts of a page asynchronously in response to user actions.
Server-Side (requests): requests on the server side is typically used for server-to-server communication or to fetch data from external APIs.
4. Asynchronous vs. Synchronous:

AJAX (Client-Side): AJAX requests are asynchronous by nature. This means that the browser can continue executing other tasks while waiting for the response from the server.
Server-Side (requests): requests can be used both synchronously and asynchronously based on the programming language and the specific library or framework used.
5. Cross-Origin Requests:

AJAX (Client-Side): AJAX requests are subject to the same-origin policy, which restricts requests to the same domain by default. Cross-origin requests may require CORS (Cross-Origin Resource Sharing) headers to be set on the server.
Server-Side (requests): Server-side requests are not subject to the same-origin policy restrictions, allowing servers to make requests to other domains.
6. Error Handling:

AJAX (Client-Side): AJAX requests on the client side typically involve handling errors and responses directly within the JavaScript code.
Server-Side (requests): Error handling for server-side requests is generally implemented within the server-side code using try-catch blocks or similar constructs.
7. Security Considerations:

AJAX (Client-Side): Client-side requests expose sensitive information, and developers need to be cautious about handling security aspects on the client side.
Server-Side (requests): Server-side requests are typically considered more secure since they are controlled and executed on the server, reducing the risk of exposing sensitive information to end-users.

- What is CSRF? What is the purpose of the CSRF token?
CSRF stands for Cross-Site Request Forgery, and it is a type of security vulnerability that occurs when an attacker tricks a user's browser into making an unintended and potentially malicious request on behalf of the user. CSRF attacks exploit the trust that a website has in a user's browser by executing unauthorized actions without the user's consent.

The typical scenario of a CSRF attack involves a user who is authenticated to a website (e.g., logged in) unknowingly submitting a request initiated by an attacker. This attack often happens when the user visits a malicious website or clicks on a specially crafted link in an email or on another website while still authenticated in the target application.

To mitigate CSRF attacks, web developers often use CSRF tokens as a security measure. A CSRF token is a unique and unpredictable value associated with a user's session. The purpose of the CSRF token is to validate that the request being made to the server originates from the legitimate and expected user, not from a malicious attacker.

Here's how the CSRF token works:

Token Generation: When a user logs in or accesses a web page, the server generates a unique CSRF token and associates it with the user's session.

Token Inclusion in Forms or Requests: The CSRF token is included in the HTML form or as a header of any request that can modify the server state (e.g., submitting a form, changing user settings).

Validation on the Server Side: When the user submits a form or performs an action that involves a state-changing request, the server checks whether the included CSRF token matches the one associated with the user's session.

Rejection of Unauthorized Requests: If the CSRF token is missing or does not match, the server rejects the request, preventing the action from being executed. This helps ensure that requests are legitimate and initiated by the user, not by an attacker.

By requiring the inclusion and validation of CSRF tokens, web applications add an extra layer of protection against CSRF attacks, making it significantly more challenging for attackers to forge requests on behalf of authenticated users. It's important for web developers to implement proper CSRF protection measures to secure their applications, especially for actions that involve changing sensitive data or performing critical operations.

- What is the purpose of `form.hidden_tag()`?
In the context of Flask, `form.hidden_tag()` is a function provided by Flask-WTF, an extension for Flask that integrates with the WTForms library to handle web forms in Flask applications.

The `form.hidden_tag()` function is used to generate an HTML `<input>` tag with a hidden type. This hidden input field typically contains a CSRF (Cross-Site Request Forgery) token. CSRF tokens are used as a security measure to protect against Cross-Site Request Forgery attacks.

Here's how it works:

1. **CSRF Protection:**
   - CSRF attacks involve an attacker tricking a user's browser into making an unintended and potentially malicious request on behalf of the user. To prevent this, Flask-WTF includes CSRF protection by default.

2. **Hidden CSRF Token Field:**
   - When you use `form.hidden_tag()` in your HTML form template, it generates a hidden input field that contains the CSRF token associated with the user's session.

3. **Automatic Inclusion in Forms:**
   - Flask-WTF typically takes care of including this CSRF token field in your forms automatically. When you render your form in a template using `{{ form.hidden_tag() }}`, it ensures that the CSRF token is included in the HTML form.

4. **Validation on Form Submission:**
   - When the user submits the form, the hidden CSRF token is sent back to the server. Flask-WTF automatically validates the CSRF token on the server side to ensure that the form submission is legitimate and not part of a CSRF attack.

Here's a simple example of using `form.hidden_tag()` in a Flask template:

```html
<form method="POST">
  {{ form.hidden_tag() }}
  <!-- Other form fields go here -->
  <button type="submit">Submit</button>
</form>
```

In this example, `{{ form.hidden_tag() }}` generates the hidden CSRF token field, which is then included in the form along with other form fields. When the form is submitted, the CSRF token is sent to the server, and Flask-WTF validates it to ensure the legitimacy of the form submission.
