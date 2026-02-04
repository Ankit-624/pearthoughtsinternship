## ER Diagram

```mermaid
erDiagram
    USER ||--|| DOCTOR : has
    USER ||--|| PATIENT : has

    DOCTOR ||--o{ APPOINTMENT : attends
    PATIENT ||--o{ APPOINTMENT : books

    DOCTOR ||--o{ APPOINTMENT_SLOT : provides

    APPOINTMENT ||--o{ CHAT_MESSAGE : contains
    APPOINTMENT ||--o{ APPOINTMENT_HISTORY : logs
