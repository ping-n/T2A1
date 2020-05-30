# **T2A1 - Workbook 2**
---

## Table of Content
---

| #   | Content                                                                 |
| --- | ----------------------------------------------------------------------- |
| 1   | [Brief](#brief)                                                         |
| 1   | [Describe the architecture of a typical Rails application](#question-1) |
| 2   | [Discuss Rails common database: Pros and Cons](#question-2)             |

## Brief

---

The ACME Corporation is interested in building a marketplace web application (app) using Rails for one of it’s product lines. To help it choose the vendor who will undertake the project they have released a RfQ. As an aspiring junior dev at an up and coming Sydney software startup (CAx-Dev) your manager has assigned you to assist with preparation of the RfQ response.

You are assigned (required) to complete all the questions from the technical section of the RfQ - which are presented below.

Being a highly valued junior dev you are expected to continue working on your other ongoing projects and schedule time for this project accordingly.

## Question 1: 
Describe the architecture of a typical Rails application.

---

<img src="./docs/rails_arch.png" width="80%">

Ruby on rails typical architecture revolve around the usage of the Model-View-Controller (MVC) architecture in the development of applications, MVC architecture aims to improve the maintainability of applications. MVC software design pattern is one of most frequently used web development framework in the industry, it allow developers to create a scalable project by separating the application development into three main logical components with each component built to handle different aspect of the applications. 

#### Model
---
The Model layer is responsible for the business logic of the application and the rules that govern how the data is being manipulated. In a typical Rails application the model main purpose is to manages the interaction with corresponding elements within the database table, overall the model is the representation of information within the application which allows developers to establish relations and validations for appropriate data in the database.

#### View
---
The view is the front-end of the application, in a simple term it is what the users of an application see when they interact with the application. In Rails the view are html files with embedded ruby codes, most ruby codes within the view are simple conditional statement of loops to display information to the users. The main purpose of the view is to provide relevant data to the browser when web pages are requested by a user, the controller renders information through the view and the view would display the appropriate data to the user within the browser.

#### Controller
---
The controller can be consider the conductor within a Rails application if Rails was an orchestra. The main purpose of the controller is process requests from the browser, interact with the model to perform CRUD actions or retrieve the data from the model. Once the data requested from the controller is then passed to the view which render the information to the user through the browser.

#### Route
---
RESTful architecture style is implemented by default in Rails, Rails provide developers with ability to create a RESTful routes through the use of resources key way in route.rb which implement CRUD route for the associated model. Developer are given the ability to customizes the route to perform action relevant to their application by defining appropriate routes for the model.

```ruby
# Rails resource key word that create CRUD routes for the users model
resources: :users

# Limiting routes to only have index, and show page which give developer customize their own routes for that model
resources: :users, only: [:index, :show]

# For developer who want to assign route without using the resource key word
get "/users", to: "users#index"
```

Using Rails resource key word provide the following routes:
<img src="./docs/rails-route.png" width="80%">

Resources:

- https://adrianmejia.com/ruby-on-rails-architectural-design/
- https://medium.com/podiihq/understanding-rails-routes-and-restful-design-a192d64cbbb5
- https://guides.rubyonrails.org/routing.html

## Question 2: 
Identify a database management system (DBMS) commonly used in web applications (including Rails) and discuss the pros and cons of this database.

---

#### PostgresSQL
---

PostgreSQL is a powerful and popular database system among Rails developers, PostgreSQL is a open-source object-relational database with origin dated back to 1986 as part of the POSTGRES project for the University of California with more than 30 years of active development. PostgreSQL is advertise as a database system that make uses of SQL language with heavy focus on features that safely store data and a scalable data workloads for applications. The main advantage of using PostgreSQL is the extensive documentations that PostgreSQL provide to developers who seek relevant information how to solve problems and the access to community resources and supports due to the popularity of PostgreSQL among the active tech communities.

The Pros and Cons of Postgres:

| Pros                     | Explanation                                                                                                                                                                                                                                                                                     |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Data Types               | Support many data types from primitives: string boolean numbers, structures: array, range, date/time, document: JSON/JSON, key-value, XML etc                                                                                                                                                   |
| Data Integrity           | built in data integrities and validation such as NULL, UNIQUE, primary key, foreign keys, exclusion constraints and explicit lock                                                                                                                                                               |
| Platform Compatibilities | Having over 30 years of active development meant that PostgreSQL is compatible on all major platforms and is ACID-compliant since 2001                                                                                                                                                          |
| Partitioning             | PostgreSQL allow developers to partition tables which meant that big table can be split into smaller pieces. This allow queries to perform faster through partition pruning                                                                                                                     |
| Security Features        | PostgreSQL boast by many developers as having many security feature to protect the data and important data of users. Some of these features include robust access-control system, numerous type of authentication: GSSAPI, SSPI, LDAP, SCRAM-SHA-256, Certificate, column and row security etc. |

| Cons               | Explanation                                                                                                                                                                                                                                                                                                                             |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Slower Performance | The performance of PostgreSQL can be slower than other database system. The relational structure of PostgreSQL meant that when you query something, it would need to go through different table to access the data, and this will result significant performance loss if there are a large number data stores in each table.            |
| Open Source        | Being an open source project have many perks but can also bring many negative perks along with it. As an open-source program it does not offer any warranty or protection in using the application and being managed by the community meant that it can lack many user-friendly features that we come to expect from other applications |

In conclusion, PostgreSQL is a powerful database system that offer developers the flexibilities to create highly complex database at the cost of performance. The open-source nature of the application meant that anyone can use it without having to pay anything to anyone at the trade off of the protection and warranty that you get from paid application. The popular nature of PostgreSQL meant that developers can interact with the active community for answers to quickly solve problems. Overall PostgreSQL is free and flexible therefore developer should give PostgreSQL a look when consider which database system they need for their application.

Resource:
- https://www.postgresql.org/about/
- https://www.aalpha.net/blog/pros-and-cons-of-using-postgresql-for-application-development/
- https://dataintoresults.com/post/postgresql-for-data-science-pro-and-cons/
- https://www.trustradius.com/products/postgresql/reviews