sequenceDiagram
  participant Browser
  participant User
  participant Server
  
  User->>Browser: User responds to form.
  activate Browser
  Browser-->>Server: HTTP POST to new_note.
  deactivate Browser

  Server->>Browser: HTTP status code 302 Found.
  activate Browser
  Browser-->>Server: HTTP request - fetch main.css.
  deactivate Browser
  
  Browser-->>Server: HTTP request - fetch main.js.
  activate Server
  Server->>Browser: Returns main.js file.
  deactivate Server
  
  Browser-->>Server: HTTP request - fetch data.json.
  activate Server
  Server->>Browser: Returns data.json file.
  deactivate Server
  
  Server->>Browser: Creates new note and adds to "notes" array.
  activate Browser
  Browser-->>User: Displays user's note on page.
  deactivate Browser   
  
  Note left of Server: Notes deleted on server reset.
