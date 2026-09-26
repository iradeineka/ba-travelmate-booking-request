# Feature: CANCELLATION OF BOOKING
## Use Case: Cancellation of a booking more than 24 hours before the start time

The main participants in this process are the user, the Travelmate system, the email service, the hotel, and the bank. The diagram illustrates the process of cancelling a reservation more than 24 hours before the scheduled start time.

```mermaid
sequenceDiagram
    autonumber
    actor User as User
    participant System as TravelMate System
    participant Email as Email Service
    participant Hotel as Hotel API
    participant Bank as Payment Gateway / Bank

    User->>System: 1. Clicks "Cancel booking" button
    System-->>User: 2. Asks to confirm the cancellation

    User->>System: 3. Confirms the cancellation
    
    rect rgb(240, 248, 255)
        note over System: Internal System Processing
        System->>System: 4. Changes order status to "Cancelled"
        System->>System: 8. Makes hotel dates available for other users
    end

    par External Notifications & Integrations
        System->>Email: 5. Sends email with cancellation confirmation & refund info
        System->>Hotel: 6. Sends cancellation details to the hotel
        System->>Bank: 7. Sends refund request to the bank
    end
    ```