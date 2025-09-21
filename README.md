# Smart-queue-diagram

```mermaid
flowchart LR
    Student([Student]) --> UI[Web/Mobile UI]
    Staff([Staff]) --> UI
    Admin([Admin]) --> UI

    subgraph "Smart Queue Management System"
        UI --> API[API Gateway]
        API --> Queue[Queue Service]
        API --> Notif[Notification Service]
        API --> AI[AI/Analytics Service]
        Queue --> DB[(Database)]
        Notif --> DB
        AI --> DB
    end
    
    ```mermaid
    usecaseDiagram
    actor Student
    actor Staff
    actor Admin

    Student --> (Book Appointment)
    Student --> (View Queue Status)
    Staff --> (Serve Ticket)
    Staff --> (Update Queue Info)
    Admin --> (Generate Reports)
    Admin --> (Manage Staff)

