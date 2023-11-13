# Sleepy App API & DB Magic

## REST API Stuff

### 1. User Signup:

- **POST `/api/users`**
  - **Body:**
    ```json
    {
      "nickname": "user_nickname"
    }
    ```
  - **Response:**
    ```json
    {
      "userId": "generated_user_id",
      "nickname": "user_nickname"
    }
    ```

### 2. Sleep Issues Duration:

- **POST `/api/sleep-assessment/duration`**
  - **Body:**
    ```json
    {
      "userId": "user_id",
      "duration": "less_than_2_weeks"
    }
    ```
  - **Response:**
    ```json
    {
      "message": "Duration recorded. Sweet!"
    }
    ```

### 3. Sleep Time Entry:

- **POST `/api/sleep-assessment/sleep-time`**
  - **Body:**
    ```json
    {
      "userId": "user_id",
      "sleepTime": "22:00"
    }
    ```
  - **Response:**
    ```json
    {
      "message": "Sleep time noted. Zzz..."
    }
    ```

### 4. Wake Up Time Fun:

- **POST `/api/sleep-assessment/wake-up-time`**
  - **Body:**
    ```json
    {
      "userId": "user_id",
      "wakeUpTime": "07:00"
    }
    ```
  - **Response:**
    ```json
    {
      "message": "Wake up time recorded. Rise and shine!"
    }
    ```

### 5. Daily Sleep Duration Gossip:

- **POST `/api/sleep-assessment/daily-sleep-duration`**
  - **Body:**
    ```json
    {
      "userId": "user_id",
      "hoursOfSleep": 7
    }
    ```
  - **Response:**
    ```json
    {
      "message": "Nice! Daily sleep duration logged."
    }
    ```

## Database Doodle (SQL):

### Users Table:

- **Columns:**
  - `userId` (Primary Key)
  - `nickname` (String)

### SleepAssessment Table:

- **Columns:**
  - `assessmentId` (Primary Key)
  - `userId` (Foreign Key referencing Users table)
  - `duration` (String) - options: "less_than_2_weeks", "2_to_8_weeks", "more_than_8_weeks"
  - `sleepTime` (Time)
  - `wakeUpTime` (Time)
  - `hoursOfSleep` (Decimal)

This is like the behind-the-scenes magic happening when you spill your sleep secrets to our app. 😴✨
