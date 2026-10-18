```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: HTTP GET [https://studies.cs.helsinki.fi/exampleapp/spa](https://studies.cs.helsinki.fi/exampleapp/spa)
    activate server
    server-->>browser: Documento HTML (200 OK)
    deactivate server

    browser->>server: HTTP GET [https://studies.cs.helsinki.fi/exampleapp/main.css](https://studies.cs.helsinki.fi/exampleapp/main.css)
    activate server
    server-->>browser: Archivo CSS (200 OK)
    deactivate server

    browser->>server: HTTP GET [https://studies.cs.helsinki.fi/exampleapp/spa.js](https://studies.cs.helsinki.fi/exampleapp/spa.js)
    activate server
    server-->>browser: spa.js (200 OK)
    deactivate server

    Note right of browser: El navegador ejecuta el JS que realiza una solicitud GET para obtener los datos JSON

    browser->>server: HTTP GET [https://studies.cs.helsinki.fi/exampleapp/data.json](https://studies.cs.helsinki.fi/exampleapp/data.json)
    activate server
    server-->>browser: data.json 
    deactivate server

    Note right of browser: El navegador ejecuta la función callback y renderiza las notas dinámicamente usando el DOM
