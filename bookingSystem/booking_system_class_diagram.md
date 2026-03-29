---
config:
  layout: elk
---
classDiagram
direction TB
    class BookingSystem {
	    -List~Theater~ theaters
	    +searchMovies(title: String) List~Showtime~
	    +getShowtimesAtTheater(theater: Theater) List~Showtime~
	    +book(showtimeId: String, seatIds: List~String~) Reservation
	    +cancelReservation(confirmationId: String) void
    }

    class Theater {
	    -String id
	    -String name
	    -List~Showtime~ showtimes
	    +getShowtimes() List~Showtime~
	    +getShowtimesForMovie(movie: Movie) List~Showtime~
    }

    class Showtime {
	    -String id
	    -Theater theater
	    -DateTime datetime
	    -String screenLabel
	    -Movie movie
	    -List~Reservation~ reservations
	    +getId() String
	    +getTheater() Theater
	    +getDatetime() DateTime
	    +getMovie() Movie
	    +isAvailable(seatId: String) boolean
	    +getAvailableSeats() List~String~
	    +book(reservation: Reservation) void
	    +cancel(reservation: Reservation) void
    }

    class Movie {
	    -String id
	    -String title
	    +getId() String
	    +getTitle() String
    }

    class Reservation {
	    -String confirmationId
	    -Showtime showtime
	    -List~String~ seatIds
	    +getConfirmationId() String
	    +getSeatIds() List~String~
	    +getShowtime() Showtime
    }

	note "This is a sample note"

    BookingSystem "1" *-- "*" Theater : owns
    Theater "1" *-- "*" Showtime : hosts
    Showtime "*" --> "1" Movie : plays
    Showtime "1" *-- "*" Reservation : contains
    Reservation "*" --> "1" Showtime : back-references
