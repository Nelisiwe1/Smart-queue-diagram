```mermaid
erDiagram
    USERS ||--o{ TICKETS : requests
    USERS ||--o{ NOTIFICATIONS : receives
    TICKETS }o--|| COUNTERS : served_at
    TICKETS }o--|| FEEDBACK : has
    COUNTERS ||--o{ STAFF : assigned_to

    USERS {
        string user_id PK
        string name
        string email
        string phone
        string role
    }
    TICKETS {
        string ticket_id PK
        string ticketNumber
        string serviceType
        string status
        datetime issuedAt
        datetime calledAt
        datetime servedAt
        string userId FK
        string counterId FK
    }
    COUNTERS {
        string counter_id PK
        string counterNumber
        string serviceType
        string assignedStaffId FK
        string status
    }
    NOTIFICATIONS {
        string notif_id PK
        string userId FK
        string ticketId FK
        string type
        datetime sentAt
    }
    FEEDBACK {
        string feedback_id PK
        string ticketId FK
        string userId FK
        int rating
        string comments
    }
    STAFF {
        string staff_id PK
        string name
        string department
        string role
    }
