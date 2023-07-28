## 0.6 New note in Single page app diagram

 Diagram depicting the situation where the user creates a new note using the single-page version of the app at https://studies.cs.helsinki.fi/exampleapp/spa.

 ```mermaid 
sequenceDiagram
    participant browser
    participant server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    Note over browser : When save button is clicked
    Note right of browser: Request  contains the new note as JSON data containing both the content of the note (content) and the timestamp (date).
    activate server
    Note left of server : The server uses javascript code to add content to current page without refreshing. 
    server-->>browser: Status code (201) with "note created " message object. 
    deactivate server

```
