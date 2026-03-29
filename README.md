# LLDDesigns

A collection of Low-Level Design (LLD) diagrams and system architecture documentation.

## Projects

### Booking System
- **File**: [bookingSystem/booking_system_class_diagram.md](bookingSystem/booking_system_class_diagram.md)
- **Mermaid Viewer**: [View on Mermaid.ai](https://mermaid.ai/d/19d6cbdb-110b-4992-9158-4a06f2c569d7)
- **Description**: Class diagram showing the BookingSystem design with Theater, Showtime, Movie, and Reservation classes and their relationships.
- **Key Components**:
  - `BookingSystem`: Main orchestrator for movie searches and reservations
  - `Theater`: Represents a theater with multiple showtimes
  - `Showtime`: Specific movie showing at a theater with seat availability
  - `Movie`: Movie information
  - `Reservation`: Customer booking confirmation with selected seats