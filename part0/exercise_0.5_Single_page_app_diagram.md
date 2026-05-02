sequenceDiagram
    participant browser
    participant server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server
    server-->>browser: the JavaScript file (spa.js)
    deactivate server

    Note right of browser: The browser starts executing the spa.js code<br/>which requests the JSON data from the server

    browser->>server: GET https://helsinki.fi
    activate server
    server-->>browser: [{ "content": "Notes -- single page app", "date": "2026-5-2" }, ... ]
    deactivate server

    Note right of browser: The browser executes the callback function<br/>that renders the notes using the DOM-API


<img width="836" height="642" alt="image" src="https://github.com/user-attachments/assets/8f33bc4a-353b-4ac8-984b-0e4137fabc3f" />

