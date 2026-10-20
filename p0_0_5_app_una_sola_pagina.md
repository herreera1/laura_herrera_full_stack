```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: Documento HTML 200 OK
    deactivate server

    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: Archivo CSS 200 OK
    deactivate server

    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server
    server-->>browser: Archivo JavaScript spa.js 200 OK
    deactivate server

    Note right of browser: El navegador ejecuta el código JS que pide los datos JSON

    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: Datos json
    deactivate server

    Note right of browser: El navegador ejecuta el callback que renderiza las notas dinámicamente con el DOMof browser: El navegador ejecuta la función callback y renderiza las notas dinámicamente usando el DOM
