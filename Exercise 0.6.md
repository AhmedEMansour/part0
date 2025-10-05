
```mermaid
  sequenceDiagram
    participant browser
    participant server

      browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
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

      browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
      activate server
        Note right of server: Status 200 OK
      server-->>browser: the JavaScript file
      deactivate server

        Note right of browser : Run Js
  
      browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
      activate server
        Note right of server: Status 200 OK
      server-->>browser: [{  "content": "", "date": "2025-10-04T18:53:42.342Z", ... ]
      deactivate server

        Note right of browser : Load notes array

        Note left of browser: Adding new note

      browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
      activate server
        Note right of server: Status 201 Created
      server-->>browser: Response: {"message":"note created"}
      deactivate server

        Note right of browser : Adds the new payload {"content":"One more time","date":"2025-10-05T07:29:12.423Z"}
