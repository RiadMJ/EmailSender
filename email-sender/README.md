# Spring Boot Email Sender Application

A simple Spring Boot application that demonstrates sending emails using Gmail SMTP server.

## Project Structure

```
email-sender-app/
├── src/
│   └── main/
│       ├── java/com/example/emailsender/
│       │   ├── EmailSenderApplication.java
│       │   └── EmailController.java
│       └── resources/
│           ├── application.properties
│           └── static/
│               └── index.html
└── pom.xml
```

## Prerequisites

- Java 17 or higher
- Maven
- Gmail account with 2-factor authentication enabled

## Gmail Setup

To use Gmail SMTP, you need to generate an App Password:

1. Go to your Google Account: https://myaccount.google.com/
2. Enable 2-factor authentication if not already enabled
3. Go to App Passwords: https://myaccount.google.com/apppasswords
4. Generate a new app password for "Mail"
5. Copy the generated 16-character password

## Configuration

Edit `src/main/resources/application.properties`:

```properties
spring.mail.username=your-email@gmail.com
spring.mail.password=${MAIL_PASSWORD}
```

- `spring.mail.username`: Set this to your Gmail address.
- `spring.mail.password`: This is configured to use the `MAIL_PASSWORD` environment variable.

## Running the Application

1. Navigate to the project directory:
   ```bash
   cd email-sender-app
   ```

2. Run with Maven, setting the environment variable:
   ```bash
   MAIL_PASSWORD=your-app-password mvn spring-boot:run
   ```
   Replace `your-app-password` with your actual 16-character Gmail App Password.

3. Open your browser and go to:
   ```
   http://localhost:8080
   ```

## Usage

1. Fill in the form with:
   - **To Email**: Recipient's email address
   - **Subject**: Email subject line
   - **Message**: Email body content

2. Click "Send Email"

3. You'll see a success or error message after attempting to send

## Features

- Simple, clean UI with gradient background
- Form validation
- Success/error message display
- Uses Spring Boot Mail component
- Configured for Gmail SMTP server

## Technologies Used

- Spring Boot 3.2.0
- Spring Boot Starter Mail
- Spring Boot Starter Web
- Thymeleaf (for HTML templates)
- Maven
