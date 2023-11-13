## REST API Interaction Flows

### 1. Create User Profile:

- **POST `/api/users`**
  - **Request:**
    ```json
    {
      "nickname": "user_nickname"
    }
    ```
  - **Response:**
    ```json
    {
      "userId": "generated_user_id by uuid",
      "nickname": "user_nickname"
    }
    ```

### 2. Duration of Sleep Issues:

- **POST `/api/sleep-assessment/duration`**
  - **Request:**
    ```json
    {
      "userId": "user_id",
      "duration": "less_than_2_weeks"
    }
    ```
  - **Response:**
    ```json
    {
      "message": "Recorded duration. Hope it's okay!"
    }
    ```

### 3. Sleep Time:

- **POST `/api/sleep-assessment/sleep-time`**
  - **Request:**
    ```json
    {
      "userId": "user_id",
      "sleepTime": "22:00"
    }
    ```
  - **Response:**
    ```json
    {
      "message": "Noted your sleep time. Good night!"
    }
    ```

### 4. Wake Up Time:

- **POST `/api/sleep-assessment/wake-up-time`**
  - **Request:**
    ```json
    {
      "userId": "user_id",
      "wakeUpTime": "07:00"
    }
    ```
  - **Response:**
    ```json
    {
      "message": "Wake up time recorded. Morning person vibes!"
    }
    ```

### 5. Daily Sleep Duration:

- **POST `/api/sleep-assessment/daily-sleep-duration`**
  - **Request:**
    ```json
    {
      "userId": "user_id",
      "hoursOfSleep": 7
    }
    ```
  - **Response:**
    ```json
    {
      "message": "Wow, your daily sleep duration is now a fact!"
    }
    ```

## Database Things (SQL):

### Users Table:

- **Columns:**
  - `userId` (Main Key thing)
  - `nickname` (Just a word)

### SleepAssessment Table:

- **Columns:**
  - `assessmentId` (Main Key magic)
  - `userId` (Something linking to Users)
  - `duration` (Words like "less_than_2_weeks", "2_to_8_weeks", "more_than_8_weeks")
  - `sleepTime` (The time when Zzz happens)
  - `wakeUpTime` (Morning time)
  - `hoursOfSleep` (A number, like 7)

This is like the special code my app uses to keep track of your sleep adventures. 🌙✨
