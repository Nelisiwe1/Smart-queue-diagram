# Smart-queue-diagram

```mermaid
flowchart TB
    Student --> Book[Book Appointment]
    Student --> View[View Queue Status]
    Student --> Cancel[Cancel Appointment]

    Staff --> Serve[Serve Ticket]
    Staff --> Update[Update Queue Info]
    Staff --> Complete[Mark Ticket Completed]

    Admin --> Reports[Generate Reports]
    Admin --> Manage[Manage Users]
    Admin --> Config[Configure Queue Settings]




