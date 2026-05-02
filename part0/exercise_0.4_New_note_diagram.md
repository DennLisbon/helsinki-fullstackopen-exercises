sequenceDiagram
    participant browser
    participant server

    Note over browser: User types a note and clicks the "Save" button

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp
    activate server
    Note right of server: The server saves the new note to the array
    server-->>browser: HTTP status code 302 (Redirect to /notes)
    deactivate server

    Note over browser: The browser reloads the Notes page

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    Note right of browser: The browser starts executing the JS code that fetches the JSON

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "Notes", "date": "2026-05-02" }, ... ]
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes

<img width="888" height="652" alt="image" src="https://github.com/user-attachments/assets/223d99ab-4262-4328-8102-76a707f7cdf9" />

