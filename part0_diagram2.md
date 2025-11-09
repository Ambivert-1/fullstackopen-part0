# 0.5: Single Page App Diagram

This diagram describes what happens when a user goes to  
https://studies.cs.helsinki.fi/exampleapp/spa

```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser: Enters URL https://studies.cs.helsinki.fi/exampleapp/spa
    Browser->>Server: HTTP GET /exampleapp/spa
    Server-->>Browser: HTML document
    Browser->>Server: HTTP GET /exampleapp/main.css
    Server-->>Browser: main.css
    Browser->>Server: HTTP GET /exampleapp/spa.js
    Server-->>Browser: spa.js
    Note right of Browser: The browser executes spa.js
    Browser->>Server: HTTP GET /exampleapp/data.json
    Server-->>Browser: data.json (list of notes)
    Note right of Browser: JavaScript renders notes on the page dynamically
    Browser-->>User: The page is displayed with notes (no reloads)
