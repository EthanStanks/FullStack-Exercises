new note sequenceDiagram <br>
&nbsp; participant browser <br>
&nbsp; participant server <br>
<br>
&nbsp;browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note<br>
&nbsp;activate server<br>
&nbsp;server-->browser: Redirect to the address notes (302 Found).<br>
&nbsp;deactivate server<br>
<br>
&nbsp;browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes<br>
&nbsp;activate server<br>
&nbsp;server-->>browser: HTML document<br>
&nbsp;deactivate server<br>
<br>
&nbsp;browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css<br>
&nbsp;activate server<br>
&nbsp;server-->>browser: the css file<br>
&nbsp;deactivate server<br>
<br>
&nbsp;browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js<br>
&nbsp;activate server<br>
&nbsp;server-->>browser: the JavaScript file<br>
&nbsp;deactivate server<br>
<br>
&nbsp;*Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server*<br>
<br>
&nbsp;browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json<br>
&nbsp;activate server<br>
&nbsp;server-->>browser: [{ "content": "new note", "date": "2025-9-13" }, ... ]<br>
&nbsp;deactivate server<br>
<br>
&nbsp;*Note right of browser: The browser executes the callback function that renders the notes. New note will be present*<br>