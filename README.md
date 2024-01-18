# Full Stack Open - Part 0


## 0.4: New note diagram
### Create a diagram depicting the situation where the user creates a new note on the page https://studies.cs.helsinki.fi/exampleapp/notes by writing something into the text field and clicking the Save button.

```mermaid
sequenceDiagram
    participant browser
    participant server

    
    Note right of browser: USER writes in the input form and clicks the save button.
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    server-->>browser: Responds STATUS 302 - GET /exampleapp/notes
    deactivate server
    Note right of browser: SATATUS 302 - Requested resource has been moved temporary to a new location.
    Note right of browser: Browser reloads the notes page causing the HTTP REQUESTS

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: Responds STATUS 200  - Display the list of notes
    deactivate server
    Note right of browser : STATUS 200 - The request has been successfull
    
    

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: Responds with STATUS 200 - the css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js

    activate server
    server-->>browser: Responds with STATUS 200 - the javascript file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json


    activate server
    server-->>browser: Responds with STATUS 200 - { "content": "Estas son Reebok o son Nike?", "date": "2024-01-18T14:06:52.180Z" }
    deactivate server
    Note right of browser: Display the list of notes to the USER with the added note
    
    

    
    

    
```
---
## 0.5: Single page app diagram
### Create a diagram depicting the situation where the user goes to the single-page app version of the notes app at https://studies.cs.helsinki.fi/exampleapp/spa.
