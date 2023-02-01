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

### insert text
- <kbd>i</kbd> - insert text **before** cursor
- <kbd>a</kbd> - insert text **after** cursor (append)
- <kbd>I</kbd> - insert text at the beginning of the line
- <kbd>A</kbd> - insert text at the end of the line (append)

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

### edit text
- <kbd>x</kbd> - delete character under the cursor

### files
- <kbd>:q</kbd> - close the file, fails if changes are not saved (quit)
- <kbd>:q!</kbd> - close the file, without saving changes
- <kbd>:qa</kbd> - close all the files, fails if changes are not saved
- <kbd>:qa!</kbd> - close all the files, without saving changes
- <kbd>:w</kbd> - save the changes in current file (write)
- <kbd>:wa</kbd> - save the changes in all files
- <kbd>:wq</kbd> - save the changes and close the file
- <kbd>:wqa</kbd> - save the changes and close all files
