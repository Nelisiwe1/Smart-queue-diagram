```mermaid
erDiagram
    USERS ||--o{ TICKETS : "requests"
    USERS ||--o{ NOTIFICATIONS : "receives"
    TICKETS }o--|| COUNTERS : "served_at"
    TICKETS }o--|| FEEDBACK : "has"
    
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
        string userId FK
    }
    COUNTERS {
        string counter_id PK
        string counterNumber
        string serviceType
        string assignedStaffId
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
