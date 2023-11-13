# Welcome to My Sleepy App Database

## API Things

### 1. Make an Account:

- **POST `/api/users`**
  - **Write This:**
    ```json
    {
      "nickname": "user_nickname"
    }
    ```
  - **Get This Back:**
    ```json
    {
      "userId": "generated_user_id",
      "nickname": "user_nickname"
    }
    ```

### 2. Sleepy Issues Duration:

- **POST `/api/sleep-assessment/duration`**
  - **Type Something Like:**
    ```json
    {
      "userId": "user_id",
      "duration": "less_than_2_weeks"
    }
    ```
  - **See What Happens:**
    ```json
    {
      "message": "Recorded duration. Hope it's okay!"
    }
    ```

### 3. Sleepy Time Entry:

- **POST `/api/sleep-assessment/sleep-time`**
  - **Write It Down:**
    ```json
    {
      "userId": "user_id",
      "sleepTime": "22:00"
    }
    ```
  - **Get This in Return:**
    ```json
    {
      "message": "Noted your sleep time. Good night!"
    }
    ```

### 4. Wake Up Time Adventure:

- **POST `/api/sleep-assessment/wake-up-time`**
  - **Try Something Like:**
    ```json
    {
      "userId": "user_id",
      "wakeUpTime": "07:00"
    }
    ```
  - **What You Might Get:**
    ```json
    {
      "message": "Wake up time recorded. Morning person vibes!"
    }
    ```

### 5. Daily Sleep Duration Fun:

- **POST `/api/sleep-assessment/daily-sleep-duration`**
  - **Write Something Down:**
    ```json
    {
      "userId": "user_id",
      "hoursOfSleep": 7
    }
    ```
  - **And Maybe Get:**
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
