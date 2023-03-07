Sequence Diagram

```mermaid
sequenceDiagram
    participant Browser
    participant Server
    
    
     Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/notes
     Server-->>Browser: HTML document
     
     Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
     Server-->>Browser: CSS file
         
     Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
     Server-->>Browser: Javascript file
     
     Note over Browser, Server: The browser starts executing the Javascript code that fetches the JSON from the server
     Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
     Server-->>Browser: [{ "content:" }, ... ]
     
     Browser->>Server: POST https://studies.cs.helsinki.fi/exampleapp/notes
     Note over Browser, Server: new_note is sent to the server / kicks off redirect event
     Server-->>Browser: Get https://studies.cs.helsinki.fi/exampleapp/notes
     
     Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
     Server-->>Browser: CSS file
         
     Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
     Server-->>Browser: Javascript file
     
     Note over Browser, Server: The browser starts executing the Javascript code that fetches the JSON from the server
     Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
     Server-->>Browser: [{ "updated content:" }, ... ]
     
    
    
```
