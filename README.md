# Notes Manager

View, create, edit, and delete small notes.

### Features
* All work done to notes is persistent (we save to browser's LocalStorage)
* There are a set of default notes added already (if we detect that the LocalStorage is empty)
* To Create a new blank note, press the + symbol on the bottom right hand of viewport. The new note appears at the upper top left hand of the viewport
* To Edit a note, just simply start typing into it. The webapp saves each edit to LocalStorage
* To delete a note, hit the X symbol on that respective note
* To filter through current notes, enter text into top left most text field

### Libraries
- React
 - for normalized interfacing with DOM and view rendering   
- Alt (Flux implementation)
 - for eventing and data modeling 
- Gulp
 - streaming task runner
- Store.js
 - to normalized interfacing with LocalStorage
 - https://github.com/marcuswestin/store.js/
 
### Architecture
> As per Flux, we have Actions (a la Controller) Stores (a la Model) and Components (a la View)

1. All interactions with the page/DOM fire off events handled by Actions. They are fired via event handlers registered in our Components
2. These Actions all deal with our data model (the list of buddies) in Stores. Stores emit notifications that data has mutated.
3. Our Components listen to our Stores for changes. It will grab the updated value and then re-render.
