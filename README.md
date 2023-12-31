# Library System Documentation

## Introduction
This project is an object-oriented implementation of a simple library system in Java. The documentation outlines the purpose, attributes, and methods of each class and interface used in the system.

### 1-Admin Class
* The `Admin` class represents an administrator in a library system.

#### Usage
* This class is used to manage users and perform user-related actions in the library system.

#### Fields
* `idAdmin`: An integer representing the unique identifier of the admin.
* `password`: A string representing the password of the admin.
* `firstName`: A string representing the first name of the admin.
* `LastName`: A string representing the last name of the admin.

#### Methods
* `addUser(Library library)`: Allows the admin to add a new user to the library system.
* `removeUser(Library library)`: Allows the admin to remove a user from the library system.

### 2-User Class
* The `User` class represents a library user in the system.

#### Fields
* `idUser`: An integer representing the unique identifier of the user.
* `firstName`: A string representing the first name of the user.
* `LastName`: A string representing the last name of the user.
* `tier`: An object implementing the `Tiers` interface representing the user's membership tier.
* `numberBorrowedBooks`: An integer representing the number of books currently borrowed by the user.
* `borrowedBooks`: An ArrayList of `Book` objects representing the books currently borrowed by the user.

#### Methods
* `borrowBook(Library library)`: Allows the user to borrow a book from the library (max number of books borrowed at one time based on membership tier).
* `study()`: Allows the user to study based on their membership tier.
* `returnBook(Library library)`: Allows the user to return a book to the library.
* `donateBook(Library library)`: Allows the user to donate a book to the library.
* `upgradeTier()`: Upgrades the user's membership tier.
* `downgradeTier()`: Downgrades the user's membership tier.

### 3-Supplier Class
* The `Supplier` class represents a book supplier in a library system.

#### Usage
* This class is used to facilitate the addition of books to the library.

#### Fields
* `idSupplier`: An integer representing the unique identifier of the supplier.
* `name`: A string representing the name of the supplier.

#### Methods
* `addBooks(Library library)`: Allows the supplier to add books to the library inventory.

### 4-Tiers Interface
* Usage
  * The `Tiers` interface represents a blueprint for membership tier classes (`PremiumTier`, `StandardTier`) for library users.

#### Methods
* `borrowBook(User user, Library library, int idBook)`: Defines the method for borrowing a book based on the user's tier.
* `study()`: Defines the method for studying based on the user's tier.

### 4-a-PremiumTier Class
* Usage
  * This class is used to define the behavior of premium tier users in the library system.

#### Methods
* `borrowBook(User user, Library library, int idBook)`: Implements the method for borrowing a book for premium users.
* `study()`: Implements the method for studying for premium users.

### 4-b-Standard-Tier Class
* Usage
  * This class is used to define the behavior of standard tier users in the library system.

#### Methods
* `borrowBook(User user, Library library, int idBook)`: Implements the method for borrowing a book for standard users.
* `study()`: Implements the method for studying for standard users.

### 5-Bookings Class
* Usage
  * This class is used to manage booking records in the library system.

#### Fields
* `idBooking`: An integer representing the unique identifier of the booking.
* `idUser`: An integer representing the identifier of the user associated with the booking.
* `idBook`: An integer representing the identifier of the booked book.
* `startDate`: A `LocalDate` object representing the start date of the booking.
* `endDate`: A `LocalDate` object representing the end date of the booking (based on membership tier).

### 6-Booking History Class
* The `BookingsHistory` class manages a list of booking records in the library system.

#### Usage
  * This class is used to handle and display the booking history in the library system.

#### Fields
* `listBookings`: An ArrayList to store `Booking` objects.

#### Methods
* `addBooking(Bookings booking)`: Adds a new booking to the list.
* `display()`: Displays information about all bookings in the list.

### 7-Book Class
* The `Book` class represents a book in the library system.

#### Fields
* `idBook`: An integer representing the unique identifier of the book.
* `title`: A string representing the title of the book.
* `author`: A string representing the author of the book.
* `publishDate`: A string representing the publish date of the book.
* `isPremium`: A boolean indicating whether the book is premium or not.

### 8-Menu Class
* The `Menu` class represents the user interface for interacting with the library system.
  It provides a menu-driven interface for users, admins, and suppliers to interact with the library functionalities.

#### Methods
* `LibraryApplication(Library library)`: Initiates the

 main menu loop for the library application.

### 9-Library Class
* The `Library` class represents a library system.

#### Usage
  * This class is used to manage users, books, admins, and booking records in the library system.

#### Fields
* `listUsers`: An ArrayList to store `User` objects.
* `listAdmins`: An ArrayList to store `Admin` objects.
* `listBooks`: An ArrayList to store `Book` objects.
* `bookingsHistory`: An object of `BookingsHistory` class to manage booking records.
* `menu`: An object of `Menu` class represents the user interface.

#### Methods
* addition,search,removal of users
* addition,search,removal of books
* addition,search, of admins
* `displayUsers()`: Displays information about all users in the library system.
* `displayBooks()`: Displays information about all books in the library system.
* `displayAdmins()`: Displays information about all admins in the library system.
* `displayBookings()`: Displays information about all bookings in the library system.

**Note:** In the library system, I chose not to implement the events class as it appeared unnecessary and did not seamlessly integrate with the system I had developed.
