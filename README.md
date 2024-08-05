# Advanced Library Management System

## Overview

The Advanced Library Management System is a robust application that simulates a real-world library network with multiple branches, advanced search capabilities, and complex reporting features. This project demonstrates advanced PHP techniques, complex object-oriented programming (OOP) concepts, and practical application of design patterns.

## Objective

The primary goal is to implement a sophisticated library management system showcasing advanced PHP and OOP skills, including abstract classes, interfaces, traits, design patterns, and complex data structures.

## Features

1. **Multi-branch Library System**: Manage multiple library branches with centralized control.
2. **Advanced Book Categorization**: Support for genres, tags, and age groups.
3. **Book Reservation System**: Patrons can reserve books across branches.
4. **Inter-library Loan Processing**: Handle loans between different library branches.
5. **Fine Calculation and Payment System**: Various strategies for fine calculation and payment.
6. **Event Management**: Organize events such as book clubs and author talks.
7. **Inventory Management**: Monitor stock levels and alert on low inventory.
8. **User Reviews and Ratings**: Patrons can review and rate books.
9. **Recommendation System**: Suggest books based on user preferences and borrowing history.

## Folder Structure

        library_management_system/
        │
        ├── src/
        │ ├── Models/
        │ │ ├── Books/
        │ │ │ ├── Book.php
        │ │ │ ├── PhysicalBook.php
        │ │ │ └── EBook.php
        │ │ ├── People/
        │ │ │ ├── Person.php
        │ │ │ ├── Author.php
        │ │ │ ├── Patron.php
        │ │ │ └── Employees/
        │ │ │ ├── Employee.php
        │ │ │ ├── Librarian.php
        │ │ │ └── Administrator.php
        │ │ ├── LibraryCard.php
        │ │ ├── Loan.php
        │ │ ├── Library.php
        │ │ ├── LibraryBranch.php
        │ │ ├── Publisher.php
        │ │ ├── Genre.php
        │ │ └── Shelf.php
        │ │
        │ ├── Services/
        │ │ ├── SearchService.php
        │ │ ├── ReportingService.php
        │ │ ├── FineCalculationService.php
        │ │ ├── RecommendationService.php
        │ │ └── InventoryManagementService.php
        │ │
        │ ├── Interfaces/
        │ │ ├── IReportGenerator.php
        │ │ ├── ISearchable.php
        │ │ ├── IReservable.php
        │ │ └── IFineCalculator.php
        │ │
        │ ├── Abstracts/
        │ │ └── Searchable.php
        │ │
        │ ├── Traits/
        │ │ ├── LoggingTrait.php
        │ │ └── TimestampTrait.php
        │ │
        │ ├── Factories/
        │ │ └── BookFactory.php
        │ │
        │ ├── Observers/
        │ │ ├── ReservationObserver.php
        │ │ └── LowStockObserver.php
        │ │
        │ ├── Decorators/
        │ │ ├── BookDecorator.php
        │ │ ├── NewArrivalDecorator.php
        │ │ └── BestSellerDecorator.php
        │ │
        │ ├── Exceptions/
        │ │ ├── BookNotFoundException.php
        │ │ ├── InvalidLoanException.php
        │ │ └── InsufficientPrivilegeException.php
        │ │
        │ └── Utils/
        │ ├── DatabaseConnection.php
        │ └── DIContainer.php
        │
        ├── config/
        │ └── config.php
        │
        ├── public/
        │ └── index.php
        │
        └── README.md


## Implementation Details

### Models

- **Books**
  - `Book.php`: Abstract class with properties like title, ISBN, and genre. Defines abstract methods for late fees and availability.
  - `PhysicalBook.php`: Inherits from `Book`. Adds properties for shelf location.
  - `EBook.php`: Inherits from `Book`. Adds properties for download links.

- **People**
  - `Person.php`: Abstract class with common properties and methods.
  - `Author.php`: Represents authors of books.
  - `Patron.php`: Represents library patrons.
  - `Employee.php`: Abstract class for employees.
    - `Librarian.php`: Manages library operations.
    - `Administrator.php`: Manages administrative tasks.

- **Other Models**
  - `LibraryCard.php`: Represents a library card for patrons.
  - `Loan.php`: Represents a book loan.
  - `Library.php`: Manages library-wide operations.
  - `LibraryBranch.php`: Manages operations for a specific branch.
  - `Publisher.php`: Represents book publishers.
  - `Genre.php`: Represents book genres.
  - `Shelf.php`: Represents shelves in a library branch.

## Services

### SearchService

- **Purpose**: Provides advanced search functionality for finding books and authors within the library system.
- **Features**:
  - **Fuzzy Search**: Supports partial matches and typo tolerance for book titles and author names.
  - **Advanced Filtering**: Allows users to filter search results by genre, publication date, availability, and more.

### ReportingService

- **Purpose**: Generates detailed reports and analytics about various aspects of the library system.
- **Features**:
  - **Branch Performance Reports**: Provides insights into the performance of different library branches, including circulation statistics and event attendance.
  - **Popular Genres**: Analyzes and reports on the most popular genres based on borrowing trends.
  - **Patron Demographics**: Generates reports on patron demographics and borrowing patterns.

### FineCalculationService

- **Purpose**: Manages the calculation of fines for overdue books.
- **Features**:
  - **Flat Rate Strategy**: Calculates fines based on a fixed rate per day overdue.
  - **Percentage-Based Strategy**: Calculates fines as a percentage of the book's value.
  - **Customizable Strategies**: Allows for easy addition of new fine calculation methods.

### RecommendationService

- **Purpose**: Provides book recommendations based on user preferences and borrowing history.
- **Features**:
  - **Personalized Recommendations**: Suggests books based on individual patron’s borrowing history and preferences.
  - **Popularity-Based Recommendations**: Suggests popular books or new arrivals based on general library trends.

### InventoryManagementService

- **Purpose**: Manages the inventory of books within the library system.
- **Features**:
  - **Stock Tracking**: Monitors book stock levels across different branches.
  - **Low Stock Alerts**: Generates alerts when stock levels fall below a predefined threshold.
  - **Book Transfers**: Facilitates the transfer of books between branches to balance inventory.
