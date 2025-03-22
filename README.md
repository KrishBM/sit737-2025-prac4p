# Calculator Microservice

A simple Node.js calculator microservice built with Express and Winston logging, created for SIT737 Task 4.1P.

## Overview

This application provides a REST API for basic calculator operations (addition, subtraction, multiplication, and division) with comprehensive logging capabilities.

## Features

- Four basic arithmetic operations via API endpoints
- Input validation
- Detailed error handling
- Comprehensive logging system using Winston
- JSON responses for all operations

## Project Setup

### Prerequisites

- Node.js and npm installed on your system
- Git installed on your system

### Installation Steps

1. Create a new GitHub repository named `sit737-2025-prac4p`

2. Clone the repository to your local machine:
   ```
   git clone https://github.com/your-username/sit737-2025-prac4p.git
   cd sit737-2025-prac4p
   ```

3. Initialize the Node.js project:
   ```
   npm init -y
   ```

4. Install required dependencies:
   ```
   npm install express winston
   ```

5. Create an `app.js` file with the calculator microservice code.

## Running the Application

Start the application with:
```
node app.js
```

The server will start on port 3001 (or the port specified in the PORT environment variable).

## API Endpoints

### Root Endpoint
- `GET /`: Returns information about the available API endpoints

### Calculator Operations
- `GET /add?num1=X&num2=Y`: Performs addition
- `GET /subtract?num1=X&num2=Y`: Performs subtraction  
- `GET /multiply?num1=X&num2=Y`: Performs multiplication
- `GET /divide?num1=X&num2=Y`: Performs division

### Response Format

All calculator endpoints return JSON responses in the following format:
```json
{
  "operation": "addition",
  "num1": 5,
  "num2": 3,
  "result": 8
}
```

### Error Handling

The API returns appropriate error messages for:
- Invalid parameters (non-numeric inputs)
- Division by zero
- Server errors

## Logging

The application implements a comprehensive logging system:

- Console logs for development
- Error logs stored in `logs/error.log`
- Combined logs stored in `logs/combined.log`

Logs include:
- Request details (method, URL, IP, headers)
- Operation details and results
- Error information with stack traces when applicable

## Code Structure

- **Express Setup**: Initializes and configures the Express application
- **Winston Logger**: Configures logging with multiple transports
- **Middleware**: Parses request bodies and logs incoming requests
- **Helper Functions**: Validates inputs to ensure they are valid numbers
- **API Endpoints**: Implements the calculator operations
- **Error Handling**: Global error handler for server-side issues
