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
      "assessmentId": "generated_assessment_id by uuid",
      "nickname": "user_nickname"
    }
    ```

### 2. Duration of Sleep Issues:

- **POST `/api/sleep-assessment/duration`**
  - **Request:**
    ```json
    {
      "assessmentId": "assessment_id",
      "duration": "less_than_2_weeks"
    }
    ```
  - **Response:**
    ```json
    {
      "message": "Recorded duration of sleep issues."
    }
    ```

### 3. Sleep Time:

- **POST `/api/sleep-assessment/sleep-time`**
  - **Request:**
    ```json
    {
      "assessmentId": "assessment_id",
      "sleepTime": "22:00"
    }
    ```
  - **Response:**
    ```json
    {
      "message": "Recorded Sleep Time."
    }
    ```

### 4. Wake Up Time:

- **POST `/api/sleep-assessment/wake-up-time`**
  - **Request:**
    ```json
    {
      "assessmentId": "assessment_id",
      "wakeUpTime": "07:00"
    }
    ```
  - **Response:**
    ```json
    {
      "message": "Recorded wake up time."
    }
    ```

### 5. Daily Sleep Duration:

- **POST `/api/sleep-assessment/daily-sleep-duration`**
  - **Request:**
    ```json
    {
      "assessmentId": "assessment_id",
      "hoursOfSleep": 7
    }
    ```
  - **Response:**
    ```json
    {
      "message": "Recorded daily sleep duration."
    }
    ```

## Database Schema (SQL):

### SleepAssessment Table:

- **Columns:**
  - `assessmentId` (Primary Key)
  - `nickname` (String)
  - `duration` (String) - options: "less_than_2_weeks", "2_to_8_weeks", "more_than_8_weeks"
  - `sleepTime` (Time)
  - `wakeUpTime` (Time)
  - `hoursOfSleep` (Decimal)

