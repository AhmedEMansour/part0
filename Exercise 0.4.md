```mermaid
  sequenceDiagram
    participant browser
    participant server

      browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
      activate server
        Note right of server: Status 200 OK
      server-->>browser: HTML document
      deactivate server

        Note right of browser : Render HTML

      browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
      activate server
        Note right of server: Status 200 OK
      server-->>browser: the css file
      deactivate server

        Note right of browser : Apply CSS

      browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
      activate server
        Note right of server: Status 200 OK
      server-->>browser: the JavaScript file
      deactivate server

        Note right of browser : Run Js
  
      browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
      activate server
        Note right of server: Status 200 OK
      server-->>browser: [{  "content": "", "date": "2025-10-04T18:53:34.544Z", ... ]
      deactivate server

        Note right of browser : Load notes array

        Note left of browser: Add new note

      browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
      activate server
        Note right of server: Status 302 Found
      server-->>browser: Redirect -> Location: /exampleapp/notes
      deactivate server

        Note right of browser : Starts redirecting with the new payload

      browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
      activate server
        Note right of server: Status 200 OK
      server-->>browser: HTML document
      deactivate server

        Note right of browser : Render HTML

      browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
      activate server
        Note right of server: Status 200 OK
      server-->>browser: the css file
      deactivate server

        Note right of browser : Apply CSS

      browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
      activate server
        Note right of server: Status 200 OK
      server-->>browser: the JavaScript file
      deactivate server

        Note right of browser : Run Js
  
      browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
      activate server
        Note right of server: Status 200 OK
      server-->>browser: [{  "content": "", "date": "2025-10-04T18:53:34.544Z", ... ]
      deactivate server

        Note right of browser : Load notes array
