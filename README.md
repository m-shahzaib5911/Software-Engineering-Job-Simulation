## 🏦 JPMorgan Chase – Software Engineering Virtual Experience
Transaction Processing System (Tasks 1–5)

This repository contains my completed implementation of Tasks 1–5 from the J.P. Morgan Chase Software Engineering Job Simulation (Forage).
The project simulates a real-world backend workflow used in financial systems, including Kafka-based transaction processing, REST APIs, and database persistence.

##  Overview

The goal of this simulation is to build a simplified backend system capable of:

1. Processing transaction messages from Kafka

2. Calling an external Incentive API

3. Updating sender/recipient account balances

4. Recording transactions into a database

5. Populating users from a file source

6. Exposing a REST endpoint to query balances

## Each task builds upon the previous one, resulting in a complete, functional microservice.

##  Tasks Completed
##  Task 1 – Project Setup

Configured the Spring Boot project with:

1. Spring Web

2. Spring Data JPA

3. Spring Kafka

4. H2 in-memory database

5. Testcontainers & Spring Kafka Test

6. Maven project structure validation

All initial test cases passed successfully.

## Task 2 – Kafka Transaction Listener

1. Implemented a Kafka consumer to:

2. Listen to transaction messages

3. Validate users & balance availability

4. Call external Incentive API using RestTemplate

5. Update user balances (sender & recipient)

6. Store transaction records

7. Log updates for debugging (especially for wilbur)

## Task 3 – User Population System

Built components to load users from a file and persist them:

1. UserPopulator – reads user data

2. DatabaseConduit – saves user records

3. Extended UserRepository with findByName()

4. Verified multi-user processing in tests

## Task 4 – Balance Querying by Name

Added functionality to:

1. Retrieve a user’s balance using their name

2. Log both exact & floored balance values

4. Validate final transaction outcomes

This logic is used in the unit tests for verification.

## Task 5 – REST Balance Controller

Created a REST endpoint:

1. GET /balance?userId=<id>

2. Returns a Balance JSON object

3. Handles missing users by returning a balance of 0

4.  Complete with tests validating all user IDs (0–12)

## Tech Stack

Java 17

Spring Boot 3.2.x

Apache Kafka

H2 Database

Spring Data JPA

Testcontainers

Maven

##  Project Structure
src/
├── main/
│ ├── java/com/jpmc/midascore/
│ │ ├── controller/ # REST endpoints
│ │ ├── component/ # Kafka Listener + DB Conduit
│ │ ├── repository/ # JPA Repositories
│ │ ├── entity/ # Entities (User, Transaction)
│ │ └── foundation/ # DTOs like Balance
│ └── resources/
│ └── application.yml # Kafka + DB config
└── test/
├── TaskOneTests.java
├── TaskTwoTests.java
├── TaskThreeTests.java
├── TaskFourTests.java
└── TaskFiveTests.java

## Included Documentation

A beginner-friendly PDF that fully explains all tasks:

## "Solution.pdf" – Detailed documentation for Tasks 1–5, including code, steps, and notes.

##  What This Project Demonstrates

Understanding of event-driven architecture

REST API development

Database persistence and querying

Kafka message consumption

Clean code, debugging, and test-driven development

Ability to build real-world backend features

##  Author

Muhammad Shahzaib
Cybersecurity & Software Engineering Enthusiast
