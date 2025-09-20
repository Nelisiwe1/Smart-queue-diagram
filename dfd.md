```mermaid
flowchart TD
    Student([Student]) -->|Request Ticket / Check Status| QueueService
    Staff([Staff]) -->|Call Next / Update Status| QueueService
    QueueService[Queue Management Service] -->|Store / Retrieve| DB[(Database)]
    QueueService -->|Trigger Notifications| Notif[Notification Service]
    Notif -->|Push/SMS| Student
