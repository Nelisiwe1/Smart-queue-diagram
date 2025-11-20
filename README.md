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



User Smartphone → QR Scan → Frontend App → REST API → Backend Server → Database
                                                                      ↘
                                                                       ML Prediction Engine
Backend Server → Notification Service → User Alerts
Admin Portal → Backend Server → Queue Management

end    
