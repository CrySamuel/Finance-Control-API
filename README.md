# Finance Control API

## Overview

Finance Control API is a backend application developed with **Java 21 and Spring Boot** designed to automate the processing of bank statements.

The system allows users to upload a **bank statement in PDF format (Itaú)**, extract financial transactions, store them in a database, and generate organized financial reports in **Excel spreadsheets**.

This project aims to simplify **personal financial management** while demonstrating backend development practices using the Spring ecosystem.

---

## Problem

Managing personal finances manually often requires:

- Analyzing bank statements
- Manually recording income and expenses
- Organizing financial data in spreadsheets

This process can be repetitive, time-consuming, and prone to errors.

The purpose of this API is to **automatically transform bank statement data into structured financial information**.

---

## Objective

The system processes bank statements and converts them into organized financial data.

Application flow:

1. Export a **bank statement in PDF format from Itaú**
2. Upload the PDF to the API
3. The system reads and processes the document
4. Financial transactions are extracted
5. Data is stored in a database
6. Transactions are categorized and organized
7. The system generates an **Excel spreadsheet with the financial report**

---

## Technologies

### Backend

- Java 21
- Spring Boot

### Spring Dependencies

- Spring Web
- Spring Data JPA
- Spring Validation
- Spring Security

### Security

Authentication and authorization are implemented using:

- JWT (JSON Web Token)
- BCrypt password encryption

Passwords are securely stored using **BCrypt hashing**.

### Database

- PostgreSQL

### PDF Processing

- Apache PDFBox

Used to:

- Read PDF files
- Extract text content
- Process financial transaction lines

### Excel Generation

- Apache POI

Used to:

- Generate Excel spreadsheets
- Export financial reports

---

## Domain Model

The application domain is **personal financial management based on bank statements**.

### User

Represents an authenticated user of the system.

Attributes:

- id
- name
- email
- password (encrypted with BCrypt)

---

### Transaction

Represents a financial movement extracted from a bank statement.

Attributes:

- id
- date
- description
- amount
- type (INCOME / EXPENSE)
- category

---

### BankStatement

Represents a bank statement uploaded by the user.

Attributes:

- id
- bankName
- importDate
- fileName

A bank statement may contain multiple transactions.

---

### Category

Used to organize transactions.

Examples:

- Food
- Transport
- Housing
- Leisure
- Salary

Attributes:

- id
- name
- type
  
---

## Security

The API uses **Spring Security with JWT authentication**.

Authentication flow:

1. User logs in using email and password
2. Credentials are validated
3. Password is verified using BCrypt
4. If valid, a JWT token is generated
5. The token must be included in protected requests

Example request header:

Authorization: Bearer TOKEN
---

## Future Improvements

Possible improvements for the project:

- Automatic expense categorization
- Financial dashboard
- Monthly reports
- Support for multiple banks
- Graphical expense analysis
- CSV and PDF export

---

## Purpose of the Project

This project was created to:

- Practice backend development with **Java and Spring Boot**
- Demonstrate knowledge of **REST API design**
- Work with **file processing (PDF)**
- Implement **authentication and security**
- Generate structured financial reports

It also serves as a **portfolio project** showcasing practical backend development skills.
