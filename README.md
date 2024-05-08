# Getting Started

Welcome to the documentation for our API! This API provides endpoints for managing courses, chapters, lessons, user subscriptions, and user information retrieval.

## Authentication

All endpoints require authentication using Token Bearer. Users need to authenticate themselves to access the API.

## Base URL

The base URL for all API endpoints is: `https://ravab.ir/api`

## Course Endpoints

### Get All Courses

- **Method**: GET
- **Endpoint**: `/courses/all`
- **Description**: Retrieves all available courses.
- **Request Parameters**: None
- **Response**: JSON array of courses.

### Find Course by ID

- **Method**: POST
- **Endpoint**: `/courses/find`
- **Description**: Finds a course by its ID.
- **Request Parameters**: `id` (Course ID)
- **Response**: JSON object of the found course.

### Get Chapters of a Course

- **Method**: POST
- **Endpoint**: `/courses/chapters`
- **Description**: Retrieves chapters of a specific course.
- **Request Parameters**: `id` (Course ID)
- **Response**: JSON array of chapters belonging to the course.

### Get Lessons of a Chapter

- **Method**: POST
- **Endpoint**: `/courses/lessons`
- **Description**: Retrieves lessons of a specific chapter.
- **Request Parameters**: `id` (Chapter ID)
- **Response**: JSON array of lessons belonging to the chapter.

## Subscription Endpoints

### Get User Subscription Status

- **Method**: GET
- **Endpoint**: `/subscription/status`
- **Description**: Retrieves the subscription status of the authenticated user.
- **Request Parameters**: None
- **Response**: JSON object representing the user's subscription status.

## User Endpoints

### Get User Information

- **Method**: GET
- **Endpoint**: `/user/get`
- **Description**: Retrieves information about the authenticated user.
- **Request Parameters**: None
- **Response**: JSON object containing user information.

