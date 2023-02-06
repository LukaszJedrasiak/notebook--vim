# NORMAL mode

## motion
Pattern:
``[counter] {operator}``

### moving cursor
- <kbd>h</kbd> - move cursor left
- <kbd>l</kbd> - move cursor right
- <kbd>j</kbd> - move cursor down
- <kbd>k</kbd> - move cursor up

- <kbd>w</kbd> - move cursor to the first character of next word
- <kbd>e</kbd> - move cursor to the last character of next word
- <kbd>0</kbd> - move cursor to the start of the line
- <kbd>^</kbd> - move cursor to the first non-blank character in line
- <kbd>$</kbd> - move cursor to the last character in line

Examples:
- <kbd>3j</kbd> - move cursor 3 lines down

- <kbd>Ctrl</kbd>+<kbd>G</kbd> - check the current cursor line
- <kbd>G</kbd> - move cursor to the last line
- <kbd>gg</kbd> - move cursor to the firs line
- <kbd>{number}G</kbd> - move cursor to the {number} line

- <kbd>%</kbd> - move cursor to the matching parenthesis or bracket

### insert text
- <kbd>i</kbd> - insert text **before** cursor
- <kbd>a</kbd> - insert text **after** cursor (append)
- <kbd>I</kbd> - insert text at the beginning of the line
- <kbd>A</kbd> - insert text at the end of the line (append)

## search

### searching
- `/{phrase}` - search {phrase} from current position till the **end** of document
- `?{phrase}` - search {phrase} from current position till the **beginning** of document
- <kbd>n</kbd> - search the same phrase again
- <kbd>N</kbd> - search the same phrase again in backward direction
- <kbd>Ctrl</kbd>+<kbd>o</kbd> - back to the previous position
- <kbd>Ctrl</kbd>+<kbd>i</kbd> - move to the next position

### substitute
- `:s/{old}/{new}` - replace the first occurence in line of {old} phrase by {new}
- `:s/{old}/{new}/g` - replace all occurences in line of {old} phrase by {new}
- `:{a},{b}s/{old}/{new}/g` - replace all occurences of {old} phrase by {new} between line {a} and {b}
- `:%s/{old}/{new}/g` - replace all occurences of {old} phrase by {new} in the whole file
- `:%s/{old}/{new}/gc` - replace all occurences of {old} phrase by {new} in the whole file, with a prompt whether to substitute or not

## edit
Pattern:
``[counter] {operator} [motion]``

### changes
- <kbd>u</kbd> - undo the last action
- <kbd>U</kbd> - undo all changes on the line
- <kbd>Ctrl</kbd>+<kbd>R</kbd> - undo the undo's (redo)

### delete text
- <kbd>dw</kbd> - delete text until the start of the next word, **exluding** its first character
- <kbd>de</kbd> - detele text to the end od current word, **including** its last character
- <kbd>d$</kbd> - delete text till the end of the line, **including** the last character
- <kbd>dd</kbd> - delete whole line

### replace text
- <kbd>r_</kbd> - replace the current char with the _ character
- <kbd>s</kbd> - delete current char and turn on INSERT mode
- <kbd>ce</kbd> or <kbd>cw</kbd> - delete word from cursor to the end and turn on INSERT mode
- <kbd>cc</kbd> - delete whole line and turn on INSERT mode
- <kbd>c$</kbd> - delete text till the end of the line and turn on INSERT mode

### edit text
- <kbd>x</kbd> - delete character under the cursor

### paste text
- <kbd>p</kbd> - paste the copied or deleted text **after** the cursor or in the new line if line is copied (put)

### files
- <kbd>:q</kbd> - close the file, fails if changes are not saved (quit)
- <kbd>:q!</kbd> - close the file, without saving changes
- <kbd>:qa</kbd> - close all the files, fails if changes are not saved
- <kbd>:qa!</kbd> - close all the files, without saving changes

- <kbd>:w</kbd> - save the changes in current file (write)
- <kbd>:wa</kbd> - save the changes in all files
- <kbd>:wq</kbd> - save the changes and close the file
- <kbd>:wqa</kbd> - save the changes and close all files
- <kbd>w</kbd> {FILENAME} - save file under given {FILENAME}

> You can write a part of file selected via VISUAL mode

- <kbd>:r</kbd> {FILENAME} - put a content of other file under the cursor (retrieve)

> You can paste to file an output of external command, i.e. <kbd>:r !ls</kbd>

### external commands
- <kbd>:!{command}</kbd> - execute external shell command

Example:
- <kbd>:!ls</kbd> - list the current directory content

