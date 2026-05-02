sequenceDiagram
    participant browser
    participant server

    Note over browser: User types a note and clicks the "Save" button

    Note right of browser: The event handler prevents the default submit<br/>adds the note to the local list and redraws the notes on the screen

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp
    activate server
    Note right of server: The server saves the note to the notes array
    server-->>browser: HTTP status code 201 Created
    deactivate server

    Note right of browser: The browser stays on the same page and does not make any more requests

<img width="1012" height="378" alt="image" src="https://github.com/user-attachments/assets/28f5ec55-c57d-49f5-9f34-e67132bad4ad" />
