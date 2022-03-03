# Jined - JSON Interface & Editor

## Synopsis
I like JSON. I like vim. I wanted an editor that treats JSON as a 
first-class citizen while giving me fast commands like vim.


## Implementation
This is built in python and uses `click`'s `getchar` function for
async keyboard commands.

Uses a python list "as a stack" to represent the keys of a JSON object.
I call the current node pointer the `cursor`. Initially, the cursor points
to the root level of the JSON object. You can point the cursor to keys relative
to the level of the cursor in the JSON object and `pop` back to navigate back up.


## Features

### Modes!
* Command mode - Inspired by vim. Keys act as commands rather than as text input.
* Execute mode - Inspired by vim. A mode for entering text for commands.

### Viewing!
* View an entire JSON object! (ok, not novel)
* View a portion of JSON with respect to a key! (kinda cool)

### Editing!
* Edit a JSON object by adding or updating keys.
    * Currently, all values added to a key are `text` or `JSON`
* Create nested JSON objects by setting `{}` as the value

### File IO!
* Open JSON files.
* Write JSON files.


## Command Mode
* `:` - Enter `Execute Mode`
* `a` - Add/Update. Prompts for a key, then for a value. If the key exists, update its value otherwise create it.
* `d` - Delete. Prompts for a key. If it exists, delete it.
* `k` - Keys. List keys available at current cursor.
* `>` - Cursor-to. Prompts for a key. If it exists, move the cursor to the key.
* `<` - Cursor-back. Pops the cursor back one level in JSON object. 


## Execute Mode
* `q` - Quit the application.
* `w` - Write JSON object to a file.
* `e` - Open JSON file to edit.


## TODO / Wishlist
### Features
* Tab autocomplete ;_;
* Verbose execution commands - for people who like to type more.
* Execute mode equivalent entries for commands? (I don't know, maybe)

### Sanity
* Refactor code, a lot.
* Write tests.




