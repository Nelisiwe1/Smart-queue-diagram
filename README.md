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
