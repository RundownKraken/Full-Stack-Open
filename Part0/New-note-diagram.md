sequenceDiagram
  participant Browser
  participant User
  participant Server
  
  User->>Browser: User responds to form.
  Browser-->>Server: HTTP POST to new_note.
  Server->>Browser: HTTP status code 302 Found.
  Browser-->>Server: HTTP request - fetch main.css.
  Browser-->>Server: HTTP request - fetch main.js.
  Browser-->>Server: HTTP request - fetch data.json.
  Server->>Browser: Creates new note.
  Server->>Browser: Adds note to array "notes."
  Browser-->>User: Displays user's note on page.
  
  Note left of Server: Notes deleted on server reset.
