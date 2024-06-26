```mermaid
sequenceDiagram
    participant browser 
    participant server

    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server ->> browser: HTML document 
    deactivate server

    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server ->> browser: the css file 
    deactivate server 

    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server 
    server ->> browser: the JavaScript file
    deactivate server

    Note right of browser:browswer starts executing javascript code

    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{"content": "<h1> Hi</h1>", "date": "2024-05-22T21:13:07.319Z"}, ...]
    deactivate server
    Note right of browser: The browser executes the callback function that renders the notes

 ```
