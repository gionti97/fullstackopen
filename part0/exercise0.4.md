# Exercise 0.4

This is what happens when a user visits the page `https://studies.cs.helsinki.fi/exampleapp/notes` and clicks on the `save` button:

sequenceDiagram
    participant browser
    participant server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    Note right of browser: The browser sends a POST request with payload = {note: userInput}
    server->>browser: HTML Document
    Note left of server: The server response is 302: the server wants the browser to make a new GET request according to the response header's location "/exampleapp/notes"
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    server->>browser: HTML Document
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    server->>browser: CSS Document
    browser->>server: https://studies.cs.helsinki.fi/exampleapp/main.js
    server->>browser: JavaScript File
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    server->>browser: JSON Document
