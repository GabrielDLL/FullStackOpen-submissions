note over user:
user writes something in the note form and hit submit
end note
user-> note form: WRITE HTML is easy 
note form-->user:"HTML is easy"
user-> note form: HITS Submit
note form->server: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note
note over server:
the server add a line to data.json, with the content sent by the user
end note
server-> data.json: [{content: ..., date: ...},]
note over data.json:
the file is now changed, so its new data is saved
end note
data.json-->server: data.json
browser->server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/notes
server-->browser: HTML-code
browser->server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
server-->browser: main.css
browser->server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.js
server-->browser: main.js

note over browser:
browser starts executing js-code
that requests JSON data from server 
end note

browser->server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json
server-->browser: [{ content: "HTML is easy", date: "2019-05-23" }, ...]

note over browser:
browser executes the event handler
that renders notes to display
end note