# 0.6: New Note in Single Page App Diagram

This diagram describes what happens when the user creates a new note  
using the single-page version of the app:  
https://studies.cs.helsinki.fi/exampleapp/spa

```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser: Writes a new note and clicks "Save"
    Note right of Browser: JavaScript captures input event
    Browser->>Browser: Adds the new note to the local list and re-renders UI
    Browser->>Server: HTTP POST /exampleapp/new_note_spa (note data as JSON)
    Server-->>Browser: HTTP 201 Created
    Note right of Browser: The browser does not reload the page
    Browser-->>User: New note appears immediately on the page
