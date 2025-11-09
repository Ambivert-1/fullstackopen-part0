# Creating a New Note — Diagram

This diagram shows what happens when a user creates a new note on the page  
https://studies.cs.helsinki.fi/exampleapp/notes  
by typing something and clicking **Save**.

```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser: Writes a new note and clicks "Save"
    Browser->>Server: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note
    Note right of Browser: The POST request includes the note data
    Server-->>Browser: HTTP 302 Redirect to /exampleapp/notes
    Browser->>Server: HTTP GET /exampleapp/notes
    Server-->>Browser: HTML document
    Browser->>Server: HTTP GET /exampleapp/main.css
    Server-->>Browser: main.css
    Browser->>Server: HTTP GET /exampleapp/main.js
    Server-->>Browser: main.js
    Note right of Browser: The JS code fetches updated notes
    Browser->>Server: HTTP GET /exampleapp/data.json
    Server-->>Browser: data.json (updated note list)
    Browser-->>User: Page is re-rendered with the new note
