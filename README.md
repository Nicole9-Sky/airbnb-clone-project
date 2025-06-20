# Airbnb Clone Project 🏡

## 🚀 Project Overview

The **Airbnb Clone Project** is a full-stack simulation of the Airbnb platform. This backend project focuses on building the core logic, APIs, and database design needed to support a real-world property booking system.

The system will support user registration, property listings, booking functionality, payment integration, and reviews—emulating the features of Airbnb.

---

## 🎯 Project Goals

- Build secure and scalable backend architecture
- Enable user and host registration, authentication, and profile management
- Implement features for property listing, updates, and deletion
- Design a system for booking and payments
- Allow users to leave property reviews
- Practice modern GitHub workflows and CI/CD pipelines
- Gain real-world team collaboration experience

---

## ⚙️ Technology Stack

- **Backend Framework:** Django, Django REST Framework (DRF)
- **Database:** MySQL
- **API Layer:** REST API & GraphQL
- **Caching & Queues:** Redis & Celery
- **Containerization:** Docker
- **Version Control:** Git & GitHub
- **CI/CD:** GitHub Actions or similar pipelines

---

## 🧑‍💻 Author

Chioma Ezeh  

TEAM ROLES 
### 🔧 Backend Developer
A software developer does the actual job and codes an application. like an app features a front end and a back end, there are front-end and back-end developers.
Front-end developers create the part of an application that users interact with, ensuring that an app offers an equally smooth experience to all—no matter the device, platform, or operational system.

Back-end developers, in turn, implement the core of an app—its algorithms and business logic. Experienced back-end developers not only write code but also do the tasks of an architect—for example, devise an app architecture or design and implement the necessary integrations.
In general, they are Responsible for designing and building API endpoints, managing server-side logic, creating database models, and ensuring secure and efficient data handling. They implement the core functionality of the application using Django and Django REST Framework.

### 🛢️ Database Administrator (DBA)
Manages the structure and health of the MySQL database. They handle data modeling, indexing, optimization, and ensure secure data storage and retrieval.


### ✅ QA Engineer
The job of a quality assurance engineer is to verify whether an application meets the requirements—both functional and non-functional. Functional requirements define what an application should do, while non-functional requirements specify how it should do that. To verify both, QA specialists run various checks, followed by analyzing the test results and reporting on the application quality.

They evaluate an application from different angles—be it functionality, usability, security, or performance (hence, many types of testing)
They Makes sure an application performs according to requirements

Spots functional and non-functional defects.


### 📅 Project Manager
In sequential models, a project manager is responsible for distributing tasks across team members, planning work activities, and updating project status.

In Agile projects where the focus is on self-management, transparency, and shared ownership, a PM sets up the vision of a product, maintains transparency, fosters communication, searches for improvements in the development process, and makes sure a team delivers more value with each iteration.


### 📅 DevOps engineer
Even in Agile environments, development and operations teams can be siloed. DevOps engineers serve as a link between the two teams, unifying and automating the software delivery process and helping strike a balance between introducing changes quickly and keeping an application stable. Working together with software developers, system administrators, and operational staff, DevOps engineers oversee and facilitate code releases on a CI/CD basis.



TECHNOLOGY STACK
 list of technologies used in the Airbnb Clone backend project and their purposes:

### Django
Python web framework that makes it easier to build secure and maintainable web applications. It handles routing, server-side logic, and integrates well with databases.

### Django REST Framework (DRF)
The process of building RESTful APIs. It allows for easy serialization, authentication, and CRUD operations.

### MySQL
Database used to store and manage application data such as user accounts, properties, bookings, payments, and reviews.

### GraphQL
A query language that provides a flexible and efficient way to request exactly the data needed from the backend. Useful for frontend integration.

### Celery
A distributed task queue used to run background jobs such as sending confirmation emails or processing delayed payments without slowing down the main app.

### Redis
An in-memory data store used for caching and managing asynchronous task queues. Helps improve performance by storing frequently accessed data temporarily.

###  Docker
A containerization platform that ensures the project runs consistently across different environments (your laptop, the cloud, etc.).

###  CI/CD Pipelines (GitHub Actions)
Used to automate testing, building, and deploying your code. This helps detect errors early and ensures that updates to the backend are smooth and reliable.

### Postman or Swagger (for API Testing)
Tools used to test your API endpoints during development. They help verify that routes like `/users/` or `/bookings/` work correctly.



Database Design
The database for the Airbnb Clone project follows a relational design. It includes core entities that represent users, properties, bookings, reviews, and payments. These entities are connected to reflect how real-world booking platforms work.

### 🧑‍💼 Users
Represents all users including guests and hosts.

**Important Fields:**
- `id` (Primary Key)
- `username`
- `email`
- `password`
- `is_host` (Boolean to identify hosts)


### 🏠 Properties
Represents properties listed by hosts.

**Important Fields:**
- `id` (Primary Key)
- `title`
- `description`
- `location`
- `price_per_night`
- `owner_id` (Foreign Key to Users)


### 📆 Bookings
Represents the reservation details made by users.

**Important Fields:**
- `id` (Primary Key)
- `user_id` (Foreign Key to Users)
- `property_id` (Foreign Key to Properties)
- `check_in_date`
- `check_out_date`
- `status` (e.g., pending, confirmed, canceled)


### 💳 Payments
Stores payment transaction data for bookings.

**Important Fields:**
- `id` (Primary Key)
- `booking_id` (Foreign Key to Bookings)
- `amount`
- `payment_method`
- `payment_status`


### ✍️ Reviews
Represents feedback given by users for properties.

**Important Fields:**
- `id` (Primary Key)
- `user_id` (Foreign Key to Users)
- `property_id` (Foreign Key to Properties)
- `rating` (e.g., 1 to 5 stars)
- `comment`

###  Entity Relationships Summary

- One **User** can own many **Properties**
- One **User** can make many **Bookings**
- One **User** can write many **Reviews**
- One **Property** can have many **Bookings** and **Reviews**
- One **Booking** has one **Payment**

