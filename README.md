# # RentalFlix - Movie Rental Service

## Overview

RentalFlix is a web-based API designed to manage a movie rental service efficiently. This system replaces the outdated method of tracking movies, customers, and rentals with a digital solution. The service handles movie inventory, customer information, rental records, and reservations, providing a seamless experience for both staff and customers.

## Problem Domain

The primary goal of RentalFlix is to manage its movie inventory, customer information, and rental records effectively. The service includes the following features:

- Management of movie details and formats.
- Storage of customer information.
- Tracking of movie rentals and returns.
- Handling of movie reservations by customers.

## Application Specifications

### Requirements

**Movies:**
- Each movie has a unique identifier (MovieID), title, genre, director, release year, and rating.
- Movies are available in multiple formats (DVD, Blu-ray, Digital).
- Each movie format has a unique identifier and may have different quantities available.

**Customers:**
- Each customer has a unique CustomerID, name, address, phone number, and email.
- Customers can rent multiple movies but must return them within a specified period.

**Rentals:**
- A record of each rental must be kept, including the customer who rented the movie, the movie format rented, the rental date, and the due date.
- The system should also track the return date when a movie is returned.

**Reservations:**
- Customers can reserve movies that are currently rented out by others.
- A reservation record includes the customer ID, movie ID, reservation date, and the status of the reservation (active, fulfilled, canceled).

## ERD Components

### Movie
- **MovieID (PK):** Unique identifier for each movie.
- **Title:** Title of the movie.
- **Genre:** Genre or category of the movie.
- **Director:** Director of the movie.
- **ReleaseYear:** The year the movie was released.
- **Rating:** Movie rating (e.g., PG, PG-13, R).

### MovieFormat
- **FormatID (PK):** Unique identifier for each movie format.
- **MovieID (FK):** Identifier of the movie.
- **FormatType:** Type of format (DVD, Blu-ray, Digital).
- **QuantityAvailable:** Number of copies available for rent.

### Customer
- **CustomerID (PK):** Unique identifier for each customer.
- **Name:** Name of the customer.
- **Address:** Address of the customer.
- **Phone:** Contact phone number.
- **Email:** Contact email address.

### Rental
- **RentalID (PK):** Unique identifier for each rental record.
- **CustomerID (FK):** ID of the customer who rented the movie.
- **FormatID (FK):** ID of the movie format that was rented.
- **RentalDate:** Date when the movie was rented.
- **DueDate:** The date when the movie is due to be returned.
- **ReturnDate:** Date when the movie was returned (nullable).

### Reservation
- **ReservationID (PK):** Unique identifier for each reservation.
- **CustomerID (FK):** ID of the customer who reserved the movie.
- **MovieID (FK):** ID of the reserved movie.
- **ReservationDate:** Date when the reservation was made.
- **Status:** Status of the reservation (active, fulfilled, canceled).

## Relationships
- **Movie to MovieFormat:** Each movie can have multiple formats (1:Many).
- **Customer to Rental:** Each customer can have multiple rentals (1:Many).
- **Rental to Customer and MovieFormat:** Each rental record is associated with one customer and one movie format (Many:1).
- **Movie to Reservation:** Each movie can have multiple reservations (1:Many).
- **Reservation to Customer and Movie:** Each reservation is associated with one customer and one movie (Many:1).


###  [ERD Diagram](https://github.com/IbrahimNimer/RentalFlix/blob/RentalFlixERD/RentalFlix.PNG)



