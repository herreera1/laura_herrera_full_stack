```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: HTTP POST con datos de formulario
    activate server
    Note over server: El servidor crea la nota y la añade a la lista
    server-->>browser: HTTP 302 (REDIRECCIÓN a /notes)
    deactivate server

    browser->>server: HTTP GET /notes
    activate server
    server-->>browser: HTML
    deactivate server

    browser->>server: HTTP GET main.css
    activate server
    server-->>browser: archivo CSS
    deactivate server

    browser->>server: HTTP GET main.js
    activate server
    server-->>browser: archivo JS
    deactivate server

    browser->>server: HTTP GET data.json
    activate server
    server-->>browser: [{ "content": "nueva nota", "date": "2026-10-17" }]
    deactivate server
