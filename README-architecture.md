# Architecture notes

Browser UI (HTML/CSS/vanilla JS)
        |
        | JSON over same-origin HTTP
        v
Express API (server.js)
        |
        | validated request data / parameterized SQL
        v
SQLite database (src/database.js)

The browser never connects directly to the database. Public suggestions enter the database with `pending` status. Admin-only endpoints require the `x-admin-key` header, and the key is read from an environment variable.
