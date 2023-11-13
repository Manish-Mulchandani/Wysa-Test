# Sleep Assessment App API and Database Design

## REST API Interaction Flows

### 1. Create User Profile:

- **Request:**
  - Method: `POST`
  - Endpoint: `/api/users`
  - Body:
    ```json
    {
      "nickname": "user_nickname"
    }
    ```

- **Response:**
  - Status: `201 Created`
  - Body:
    ```json
    {
      "userId": "generated_user_id",
      "nickname": "user_nickname"
    }
    ```

### 2. Duration of Sleep Issues:

- **Request:**
  - Method: `POST`
  - Endpoint: `/api/sleep-assessment/duration`
  - Body:
    ```json
    {
      "userId": "user_id",
      "duration": "less_than_2_weeks"
    }
    ```

- **Response:**
  - Status: `200 OK`
  - Body:
    ```json
    {
      "message": "Duration recorded successfully"
    }
    ```

### 3. Sleep Time:

- **Request:**
  - Method: `POST`
  - Endpoint: `/api/sleep-assessment/sleep-time`
  - Body:
    ```json
    {
      "userId": "user_id",
      "sleepTime": "22:00"
    }
    ```

- **Response:**
  - Status: `200 OK`
  - Body:
    ```json
    {
      "message": "Sleep time recorded successfully"
    }
    ```

### 4. Wake Up Time:

- **Request:**
  - Method: `POST`
  - Endpoint: `/api/sleep-assessment/wake-up-time`
  - Body:
    ```json
    {
      "userId": "user_id",
      "wakeUpTime": "07:00"
    }
    ```

- **Response:**
  - Status: `200 OK`
  - Body:
    ```json
    {
      "message": "Wake up time recorded successfully"
    }
    ```

### 5. Daily Sleep Duration:

- **Request:**
  - Method: `POST`
  - Endpoint: `/api/sleep-assessment/daily-sleep-duration`
  - Body:
    ```json
    {
      "userId": "user_id",
      "hoursOfSleep": 7
    }
    ```

- **Response:**
  - Status: `200 OK`
  - Body:
    ```json
    {
      "message": "Daily sleep duration recorded successfully"
    }
    ```

## Database Schema (SQL):

### Users Table:

- Columns:
  - `userId` (Primary Key)
  - `nickname` (String)

### SleepAssessment Table:

- Columns:
  - `assessmentId` (Primary Key)
  - `userId` (Foreign Key referencing Users table)
  - `duration` (String) - options: "less_than_2_weeks", "2_to_8_weeks", "more_than_8_weeks"
  - `sleepTime` (Time)
  - `wakeUpTime` (Time)
  - `hoursOfSleep` (Decimal)

This schema allows you to store user profiles and sleep assessment data in a structured manner. You can adjust the data types and add more tables if needed based on the specific requirements of your application.

