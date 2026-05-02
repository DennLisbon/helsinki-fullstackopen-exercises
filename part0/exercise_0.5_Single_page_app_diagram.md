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
    server-->>browser: [{ "content": "Single Page App", "date": "2026-5-2" }, ... ]
    deactivate server

    Note right of browser: The browser executes the callback function<br/>that renders the notes using the DOM-API

