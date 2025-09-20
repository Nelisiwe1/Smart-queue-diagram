```mermaid
sequenceDiagram
    participant Staff as Staff Dashboard
    participant API as API Gateway
    participant Queue as Queue Service
    participant Notif as Notification Service
    participant Student as Student App

    Staff->>API: POST /counters/:id/call
    API->>Queue: selectNextTicket()
    Queue->>Queue: update ticket.status = "called"
    Queue->>Notif: notifyUser(ticketId)
    Notif->>Student: Push notification: "Proceed to counter X"
    Student->>Staff: Arrives at counter
    Staff->>API: POST /counters/:id/complete
