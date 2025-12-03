🏦 JPMorgan Chase – Software Engineering Virtual Experience
Transaction Processing System (Tasks 1–5)

This repository contains my completed implementation of Tasks 1–5 from the J.P. Morgan Chase Software Engineering Job Simulation (Forage).
The project simulates a real-world backend workflow used in financial systems, including Kafka-based transaction processing, REST APIs, and database persistence.

📌 Overview

The goal of this simulation is to build a simplified backend system capable of:

Processing transaction messages from Kafka

Calling an external Incentive API

Updating sender/recipient account balances

Recording transactions into a database

Populating users from a file source

Exposing a REST endpoint to query balances

Each task builds upon the previous one, resulting in a complete, functional microservice.

✅ Tasks Completed
🔹 Task 1 – Project Setup

Configured the Spring Boot project with:

Spring Web

Spring Data JPA

Spring Kafka

H2 in-memory database

Testcontainers & Spring Kafka Test

Maven project structure validation

All initial test cases passed successfully.

🔹 Task 2 – Kafka Transaction Listener

Implemented a Kafka consumer to:

Listen to transaction messages

Validate users & balance availability

Call external Incentive API using RestTemplate

Update user balances (sender & recipient)

Store transaction records

Log updates for debugging (especially for wilbur)

🔹 Task 3 – User Population System

Built components to load users from a file and persist them:

UserPopulator – reads user data

DatabaseConduit – saves user records

Extended UserRepository with findByName()

Verified multi-user processing in tests

🔹 Task 4 – Balance Querying by Name

Added functionality to:

Retrieve a user’s balance using their name

Log both exact & floored balance values

Validate final transaction outcomes

This logic is used in the unit tests for verification.

🔹 Task 5 – REST Balance Controller

Created a REST endpoint:

GET /balance?userId=<id>


Returns a Balance JSON object

Handles missing users by returning a balance of 0

Complete with tests validating all user IDs (0–12)

🛠️ Tech Stack

Java 17

Spring Boot 3.2.x

Apache Kafka

H2 Database

Spring Data JPA

Testcontainers

Maven

📁 Project Structure
src/
 ├── main/
 │    ├── java/com/jpmc/midascore/
 │    │     ├── controller/        # REST endpoints
 │    │     ├── component/         # Kafka Listener + DB Conduit
 │    │     ├── repository/        # JPA Repositories
 │    │     ├── entity/            # User & Transaction models
 │    │     └── foundation/        # DTOs like Balance
 │    └── resources/
 │          └── application.yml    # Kafka + DB config
 └── test/
       ├── TaskOneTests.java
       ├── TaskTwoTests.java
       ├── TaskThreeTests.java
       ├── TaskFourTests.java
       └── TaskFiveTests.java

📄 Included Documentation

A beginner-friendly PDF that fully explains all tasks:

📘 "Markdown to PDF.pdf" – Detailed documentation for Tasks 1–5, including code, steps, and notes.

🎯 What This Project Demonstrates

Understanding of event-driven architecture

REST API development

Database persistence and querying

Kafka message consumption

Clean code, debugging, and test-driven development

Ability to build real-world backend features

🧑‍💻 Author

Muhammad Shahzaib
Cybersecurity & Software Engineering Enthusiast
