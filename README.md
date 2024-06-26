# M5LibraryDatabaseProject
Remember to take your time and work through each question diligently! Test your code, make sure it works, and try to find ways to improve. Once you are happy and satisfied with your code, upload it to Github, then turn in your Github link at the bottom of the page!

Don't forget. Make sure this assignment is in it's own repository. Not mixed in with others!

**Project Requirements**

In this project, you will integrate a MySQL database with Python to develop an advanced Library Management System. This command-line-based application is designed to streamline the management of books and resources within a library. Your mission is to create a robust system that allows users to browse, borrow, return, and explore a collection of books while demonstrating your proficiency in database integration, SQL, and Python.

**Integration with the "Library Management System" Project from Module 4 (OOP):**

For this project, you will build upon the foundation laid in "Module 4: Python Object-Oriented Programming (OOP)." The object-oriented structure and classes you developed in that module will serve as the core framework for the Library Management System. You will leverage the classes such as Book, User, Author, and Genre that you previously designed, extending their capabilities to integrate seamlessly with the MySQL database.

**Enhanced User Interface (UI) and Menu:**

Create an improved, user-friendly command-line interface (CLI) for the Library Management System with separate menus for each class of the system.
Welcome to the Library Management System with Database Integration!
****
Main Menu:
```1. Book Operations
2. User Operations
3. Author Operations
4. Genre Operations
5. Quit
```

Book Operations:

```1. Add a new book
2. Borrow a book
3. Return a book
4. Search for a book
5. Display all books
```
User Operations:

```1. Add a new user
2. View user details
3. Display all users
```
Author Operations:

```1. Add a new author
2. View author details
3. Display all authors
```
Genre Operations:

```1. Add a new genre
2. View genre details
3. Display all genres
```
**Database Integration with MySQL:**

Integrate a MySQL database into the Library Management System to store and retrieve data related to books, users, authors, and genres.
Design and create the necessary database tables to represent these entities. You will align these tables with the object-oriented structure from the previous project.
Establish connections between Python and the MySQL database for data manipulation, enhancing the persistence and scalability of your Library Management System.
Data Definition Language Scripts:

Create the necessary database tables for the Library Management System. For instance:

```Books Table:
CREATE TABLE books (
    id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    author_id INT,
    genre_id INT,
    isbn VARCHAR(13) NOT NULL,
    publication_date DATE,
    availability BOOLEAN DEFAULT 1,
    FOREIGN KEY (author_id) REFERENCES authors(id),
    FOREIGN KEY (genre_id) REFERENCES genres(id)
);
Authors Table:
CREATE TABLE authors (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    biography TEXT
);
Genres Table:
CREATE TABLE genres (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    description TEXT,
    category VARCHAR(50)
);
Users Table:
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    library_id VARCHAR(10) NOT NULL UNIQUE
);
Borrowed Books Table:
CREATE TABLE borrowed_books (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT,
    book_id INT,
    borrow_date DATE NOT NULL,
    return_date DATE,
    FOREIGN KEY (user_id) REFERENCES users(id),
    FOREIGN KEY (book_id) REFERENCES books(id)
);
```

## Menu Actions:

Implement the following actions in response to menu selections using the classes you've created:
- Adding a new book with all relevant details.
- Allowing users to borrow a book, marking it as "Borrowed."
- Allowing users to return a book, marking it as "Available."
- Searching for a book by its unique identifier (ISBN or title) and displaying its details.
- Displaying a list of all books with their unique identifiers.
- Adding a new user with user details.
- Viewing user details.
- Displaying a list of all users.
- Adding a new author with author details.
- Viewing author details.
- Displaying a list of all authors.
- Adding a new genre with genre details.
- Viewing genre details.
- Displaying a list of all genres.
- Quitting the application.

## Database Connection:

1. Establish a connection to the MySQL database using the mysql-connector-python library.
2. Create a database cursor to execute SQL queries.

## Functions for Data Manipulation:

1. Create functions for adding new books, users, authors, and genres to the database.
2. Implement functions for updating book availability, marking books as borrowed or returned.
3. Develop functions for searching books by ISBN, title, author, or genre.
4. Define functions for displaying lists of books, users, authors, and genres.
5. Implement functions for user registration and viewing user details.

## User Interface Functions:

1. Create a user-friendly command-line interface (CLI) with clear menu options.
2. Implement functions to handle user interactions using the input() function.
3. Validate user input using regular expressions (regex) to ensure proper formatting.

## Error Handling:

1. Use try, except, else, and finally blocks to manage errors gracefully.
2. Handle exceptions related to database operations, input validation, and other potential issues.
3. Provide informative error messages to guide users.

## Clean Code Principles:

1. Use meaningful variable and function names that convey their purpose.
2. Write clear comments and docstrings to explain the functionality of functions and classes.
3. Follow PEP 8 style guidelines for code formatting and structure.
4. Ensure proper indentation and spacing for readability.

## Modular Design:

1. Organize code into separate modules to promote modularity and maintainability.
2. Create distinct modules for database operations, user interactions, error handling, and core functionalities.

## GitHub Repository:

1. Create a GitHub repository for your project and commit code regularly.
2. Maintain a clean and interactive README.md file in your GitHub repository, providing clear instructions on how to run the application and explanations of its features.
3. Include a link to your GitHub repository in your project documentation.

### Optional Bonus Points:
1. User Authentication (Bonus): Implement a user authentication system that requires users to create accounts and log in before accessing the library. This enhances security and allows for personalized features.
2. Due Dates for Borrowed Books (Bonus): Enhance the system by assigning due dates to borrowed books. When users borrow a book, the system should calculate and display the due date.
3. Fine Calculation (Bonus): Implement a fine calculation system for overdue books. Users who exceed the due date should be charged fines based on predefined rules. Users should have the option to pay fines, and their accounts should be updated accordingly. Effective Project Communication:
4. Create a video presentation or explanation of the Library Management System project.
5. Demonstrate the ability to explain technical concepts and project details in a concise and understandable manner.

💡 **Note:** You can reuse the clean code and functions developed in the "Module 4: Python Object-Oriented Programming (OOP)" project to maintain consistency and reduce redundancy. Emphasize the importance of code reusability and modular design to make it easier to integrate the database functionality into their existing project.

### Submission
- Upon completing the project, submit your code and video, including all source code files, and the README.md file in your GitHub repository to your instructor or designated platform.

### Project Tips
- Reuse Your OOP Project: Take advantage of the object-oriented structure and classes you developed in "Module 4: Python Object-Oriented Programming (OOP)." This will save you time and effort by providing a solid foundation for integrating the database functionality.
- Iterative Development: Start by designing a class hierarchy that represents the library's structure and entities. Test your code iteratively as you implement each feature to identify and address any potential bugs or issues.
- Collaborate and Seek Assistance: Don't hesitate to collaborate with peers and seek assistance when needed. Learning is a collaborative effort, and discussing challenges with fellow learners can lead to valuable insights and solutions.
- Modular Design: Emphasize modular design to keep your code organized and maintainable. Create separate modules for database operations, user interactions, error handling, and core functionalities.
- Clean Code Practices: Follow clean code practices by using meaningful variable and function names, providing clear comments and docstrings, adhering to PEP 8 style guidelines, and ensuring proper code formatting and structure.
- GitHub Repository: Create a GitHub repository for your project and commit code regularly. A version control system like Git will help you track changes and collaborate effectively.
- Interactive README: Maintain an interactive README.md file in your GitHub repository. Provide clear instructions on how to run the application, explanations of its features, and include a link to your GitHub repository in your project documentation.
- Optional Features: Consider implementing optional features such as user authentication, due dates for borrowed books, or fine calculation. These can add depth to your project and demonstrate your ability to adapt to varying requirements.
- Effective Communication: When recording your project explanation video, practice effective communication. Clearly articulate your project's objectives, features, and technical concepts in a concise and understandable manner. Engage your audience, whether technical or non-technical, to effectively communicate project achievements and challenges.
- Remember that this project is an opportunity to showcase your skills, problem-solving abilities, and your understanding of database integration with Python. Enjoy the process, and don't hesitate to ask for help or clarification if needed. Happy coding! 📚🔍🖥️

### Conclusion
The Library Management System with Database Integration project is your chance to combine the power of Python, object-oriented programming principles, and database integration to create a sophisticated solution for managing books and resources. By reusing the clean code and functions from your OOP project, you'll streamline development and maintain consistency.

Throughout this journey, remember to collaborate with your peers, follow clean code practices, and embrace modularity. Utilize Git and GitHub for version control, maintain an interactive README, and consider adding optional features like user authentication, due dates for borrowed books, or fine calculation to enhance your project.

Lastly, don't forget the importance of effective communication. Record a video presentation that clearly explains your project's objectives and technical details, demonstrating your skills in a concise and understandable manner.

With these tips in mind, embark on this coding adventure, and enjoy the process of creating a valuable Library Management System. Happy coding! 📚🔍🖥️
