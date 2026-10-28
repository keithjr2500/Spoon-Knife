
# Local Stack

This diagram shows the frontend, API, and PostgreSQL database in a Docker Compose environment.

```mermaid
flowchart TD
    Browser["Browser"]

    subgraph Network["Docker Compose Network"]
        Frontend["frontend :80"]
        API["api :8000"]
        DB[("db :5432")]
    end

    Volume[("pgdata volume")]

    Browser -->|"localhost:3000"| Frontend
    Browser -->|"localhost:8080"| API
    API -->|"db:5432"| DB
    DB --- Volume
```

**Figure 1.** Local application stack showing published ports, internal database communication, and persistent storage. 
