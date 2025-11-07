# ConnectEase

A Java Spring Boot web application for data management, featuring user authentication and multiple pages.

## Features

- **Web Pages**: Home, About, Service, Signup, Login, Contact
- **Templates**: Thymeleaf-based views for all pages
- **Database**: MySQL with JPA/Hibernate integration
- **Security**: Basic Spring Security for authentication

## Prerequisites

- Java 17 or higher
- Maven 3.6+
- MySQL 8.0+

## Installation and Setup

1. **Clone the repository**:
   ```
   git clone <repository-url>
   cd ConnectEase
   ```

2. **Database Setup**:
   - Install and start MySQL
   - Create a database named `data_manager` (or configure as needed)

3. **Configure Database**:
   - Update `src/main/resources/application.properties` with your MySQL credentials:
     ```
     spring.datasource.url=jdbc:mysql://localhost:3306/data_manager
     spring.datasource.username=your_username
     spring.datasource.password=your_password
     ```

4. **Build and Run**:
   ```
   mvn clean install
   mvn spring-boot:run
   ```

5. **Access the Application**:
   - Open your browser and navigate to `http://localhost:8082`
   - Note: The root path "/" is not mapped; use `/home` as the entry point

## Available Endpoints

- `/home` - Home page
- `/about` - About page
- `/service` - Service page
- `/signup` - User registration
- `/login` - User login
- `/contact` - Contact page

All endpoints render Thymeleaf templates.

## Project Structure

- `src/main/java/` - Java source code
- `src/main/resources/` - Application properties and templates
- `src/main/resources/templates/` - Thymeleaf view templates
- `pom.xml` - Maven configuration

## Technologies Used

- Spring Boot
- Spring MVC
- Spring Security
- Thymeleaf
- JPA/Hibernate
- MySQL
- Maven

## Project Flow

The ConnectEase application follows a user-centric workflow for managing personal contacts and reminders. Below is the complete flow:

### Public Access
1. **Entry Point**: Users access the application at [`http://localhost:8082](https://connectease.up.railway.app/home)` (root redirects to `/home`)
2. **Public Pages**: Browse informational pages including Home, About, Service, and Contact without authentication

### User Registration & Authentication
3. **Sign Up**: Navigate to `/signup` to create a new account with email, password, and profile details
4. **Login**: Use `/loginPage` to authenticate with email and password
5. **Dashboard**: After successful login, users are redirected to their personal dashboard showing contact count and quick stats

### Contact Management
6. **View Contacts**: Access `/user/contacts` to see all saved contacts with search and filter capabilities
   - Search by name, email, or phone
   - Filter favorites
   - View contact details
7. **Add Contacts**: Create new contacts via `/user/contacts/add` with fields like name, email, phone, address, description, and social links
8. **Edit/Delete Contacts**: Modify or remove existing contacts with proper ownership validation
9. **Contact Actions**:
   - Mark/unmark as favorite
   - Export contacts to CSV
   - Import contacts from CSV
   - Bulk operations (favorite, unfavorite, delete multiple contacts)

### Reminder Management
10. **View Reminders**: Access `/user/reminders` to see all scheduled reminders
11. **Manage Reminders**: Add, edit, and delete reminders linked to specific contacts or standalone

### User Profile Management
12. **Profile**: View and update personal information at `/user/profile`
13. **Settings**: Modify account settings at `/user/settings` including:
    - Update profile details
    - Change password
    - Delete account (with confirmation)

### Security & Navigation
- All user-specific endpoints require authentication
- Spring Security handles login/logout and session management
- Users can only access their own data (contacts, reminders, profile)

The application ensures data integrity with validation, error handling, and user-friendly feedback messages throughout the workflow.

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

