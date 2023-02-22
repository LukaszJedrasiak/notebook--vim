# NORMAL mode

- <kbd>Esc</kbd> - back to NORMAL mode
- <kbd>Ctrl</kbd>+<kbd>c</kbd> - back to NORMAL mode
- <kbd>Ctrl</kbd>+<kbd>[</kbd> - back to NORMAL mode
- <kbd>.</kbd> - repeat the last command

## motion

> word vs. WORD
> 
> word is:
> - a sequence of letters, digits and numbers
> - a sequence of other non-blank characters
>
> WORD is a sequence of letters, digits and numbers that also include other non-blank characters

Pattern:
``[counter] {operator}``

### moving cursor
- <kbd>h</kbd> - move cursor left
- <kbd>l</kbd> - move cursor right
- <kbd>j</kbd> - move cursor line down
- <kbd>k</kbd> - move cursor line up

- <kbd>gj</kbd> - move cursor line down (including wrapped lines)
- <kbd>gk</kbd> - move cursor line up (including wrapped lines)

- <kbd>w</kbd> - move cursor to the first character of next word
- <kbd>W</kbd> - move cursor to the first character of next WORD
- <kbd>b</kbd> - move cursor to the first character of previous word
- <kbd>B</kbd> - move cursor to the first character of previous WORD
- <kbd>e</kbd> - move cursor to the last character of next word
- <kbd>E</kbd> - move cursor to the last character of next WORD
- <kbd>ge</kbd> - move cursor to the last character of the previous word
- <kbd>gE</kbd> - move cursor to the last character of the previous WORD

- <kbd>0</kbd> - move cursor to the start of the line
- <kbd>^</kbd> - move cursor to the first non-blank character in line
- <kbd>$</kbd> - move cursor to the last character in line
- <kbd>g_</kbd> - move cursor to the last non-blank character in line

- <kbd>f{character}</kbd> - move cursor to the next occurence of a character in line
- <kbd>F{character}</kbd> - move cursor to the previous occurence of a character in line
- <kbd>t{character}</kbd> - move cursor just before the next occurence of a character in line
- <kbd>T{character}</kbd> - move cursor just after the previous occurence of a character in line
- <kbd>;</kbd> - go to the next occurence of searched character
- <kbd>,</kbd> - go to the previous occurence of searched character

- <kbd>}</kbd> - jump entire paragraph downwords
- <kbd>{</kbd> - jump entire paragraph backwards
- <kbd>Ctrl</kbd>+<kbd>d</kbd> - move down half a page
- <kbd>Ctrl</kbd>+<kbd>u</kbd> - move up half a page

Examples:
- <kbd>3j</kbd> - move cursor 3 lines down

- <kbd>Ctrl</kbd>+<kbd>G</kbd> - check the current cursor line
- <kbd>G</kbd> - move cursor to the last line
- <kbd>gg</kbd> - move cursor to the first line
- <kbd>{number}G</kbd> - move cursor to the {number} line
- <kbd>{number}gg</kbd> - move cursor to the {number} line

- <kbd>%</kbd> - move cursor to the matching parenthesis or bracket

## insert text
- <kbd>i</kbd> - insert text **before** cursor
- <kbd>a</kbd> - insert text **after** cursor (append)
- <kbd>I</kbd> - insert text at the beginning of the line
- <kbd>A</kbd> - insert text at the end of the line (append)

- <kbd>o</kbd> - put new line below and turn into INSERT mode
- <kbd>O</kbd> - put a new line above and turn into INSERT mode

- <kbd>gi</kbd> - insert text at the last place you left INSERT mode (last change in VSC) and turn on INSERT mode

## search

### searching
- `/{phrase}` - search {phrase} from current position till the **end** of document
- `/<Enter>` - repeat last search forward
- `?{phrase}` - search {phrase} from current position till the **beginning** of document
- `?<Enter>` - repeat last search backward
- <kbd>n</kbd> - search the same phrase again
- <kbd>N</kbd> - search the same phrase again in backward direction
- <kbd>Ctrl</kbd>+<kbd>o</kbd> - back to the previous position
- <kbd>Ctrl</kbd>+<kbd>i</kbd> - move to the next position
- <kbd>\*</kbd> - search the word under cursor forward
- <kbd>#</kbd> - search the word under cursor backward

### substitute
- `:s/{old}/{new}` - replace the first occurence in line of {old} phrase by {new}
- `:s/{old}/{new}/g` - replace all occurences in line of {old} phrase by {new}
- `:{a},{b}s/{old}/{new}/g` - replace all occurences of {old} phrase by {new} between line {a} and {b}
- `:%s/{old}/{new}/g` - replace all occurences of {old} phrase by {new} in the whole file
- `:%s/{old}/{new}/gc` - replace all occurences of {old} phrase by {new} in the whole file, with a prompt whether to substitute or not

### search options
- `:set ic` - turn on case insensitive during followin searching (ignore case)
- `:set noic` - turn off case insensitive during following searching
- `:set hlsearch` - turn on highlighting all searching matches
- `:set nohlsearch` - turn off highlighting all searching matches
- `/{phrase}/c` - ignore case only for this search

### to be done
- <kbd>gn</kbd> - ???
- <kbd>gN</kbd> - ???

## edit
Pattern:
``[counter] {operator} [motion]``

Pattern explanation:
- The **operator** determines which action you want to perform: deleting, changing, yanking, formatting, etc.
- The **counter** allows you to multiply the effect of an operator by performing an action a _counter_ number of times.
- The **motion** represents the piece of text to which to apply the action defined by the operator.

Examples:
- <kbd>5dj</kbd> - delete 5 lines downwards
- <kbd>df'</kbd> - delete everything in the current line from the cursor until the first occurence of the <kbd>'</kbd> character (including the character itself)
- <kbd>dt'</kbd> - delete everything in the current line from the cursor until just before the first occurence of the <kbd>'</kbd> character
- <kbd>ggdG</kbd> - delete the whole document

### changes
- <kbd>u</kbd> - undo the last action
- <kbd>U</kbd> - undo all changes on the line
- <kbd>Ctrl</kbd>+<kbd>R</kbd> - undo the undo's (redo)

### delete text
- <kbd>dw</kbd> - delete text until the start of the next word, **exluding** its first character
- <kbd>de</kbd> - detele text to the end od current word, **including** its last character
- <kbd>d$</kbd> - delete text till the end of the line, **including** the last character
- <kbd>dd</kbd> - delete whole line
- <kbd>dt{char}</kbd> - delete text until {char}
- <kbd>d/{phrase}</kbd> - delete text until {phrase}
- <kbd>D</kbd> - delete text until the end of the line
- <kbd>x</kbd> or <kbd>dl</kbd> - delete the character under the cursor
- <kbd>X</kbd> or <kbd>dh</kbd> - delete the character before the cursor

### replace text
- <kbd>r</kbd> {char} - replace the current single char with the {char}
- <kbd>R</kbd> {chars} - replace the following multiple chars with the {chars} 
- <kbd>s</kbd> or <kbd>ch</kbd> - delete current char and turn on INSERT mode
- <kbd>c{motion}</kbd> - delete a piece of text (determined by {motion}) and turn on INSERT mode
- <kbd>C</kbd> - delete a text until the end of the line and turn on INSERT mode
- <kbd>ce</kbd> or <kbd>cw</kbd> - delete word from cursor to the end and turn on INSERT mode
- <kbd>cc</kbd> - delete whole line and turn on INSERT mode
- <kbd>c$</kbd> - delete text till the end of the line and turn on INSERT mode
- <kbd>ct{char}</kbd> - delete text until {char} and turn on INSERT mode

### format text
- <kbd>g~</kbd> - change letters from lowercase to uppercase and back (switch case)
- <kbd>gu</kbd> - make characters lowercase
- <kbd>gU</kbd> - make characters uppercase
- <kbd>>></kbd> - add indentation
- <kbd><<</kbd> - remove indentation
- <kbd>=</kbd> - formats code (???)

### copy text
- <kbd>y</kbd> - copy text - highlighted in VISUAL mode or according to [motion] (yank)
- <kbd>yw</kbd> - copy one word
- <kbd>yy</kbd> - copy the whole line
- <kbd>Y</kbd> - copy the whole line
- <kbd>yl</kbd> - yank one character
- <kbd>yaw</kbd> - yank a word
- <kbd>yas</kbd> - yank a sentence
- <kbd>yi(</kbd> - yank everyting inside parentheses

### paste text
- <kbd>p</kbd> - paste the copied or deleted text **after** the cursor or in the new line **below** if line is copied (put)
- <kbd>P</kbd> - paste the copied or deled text **before** the cursor or in the new line **above** if line is copied
- <kbd>gp</kbd> - paste after the cursor and put cursor **after** the pasted selection
- <kbd>gP</kbd> - paste before the cursor and put cursor **after** the pasted selection

Useful commands:
- <kbd>yyp</kbd> - duplicate a line below
- <kbd>yyP</kbd> - duplicate a line above
- <kbd>ddp</kbd> - swap lines
- <kbd>{counter}yyp</kbd> - copy the {counter} lines and paste them below
- <kbd>yy{counter}p</kbd> - copy the line and paste it {counter} times below

## registers
- `"` - **unnamed** and default register for copying and cutting
- `a-z` - **named** registers which you may explicitly choose before copying and cutting
- `0` - **yank** register to store the last yanked thing
- `1-9` - **cut** registers to store the last 9 things cutted (d) or changed (c)

> TO DO: registers in VSC that allows you to copy/paste content from clipboard

### usage
`<kbd>"</kbd>{name of register}{y | d | c | p}{motion}`

### preview of the content
- `:reg` - preview of all registers
- `:reg {name of register}` - previev of choosen register

## text objects
Pattern:
``{operator}{selector}{text-object-id}``

> Operators with text objects apply to the whole text object regardless of where the cursor is located inside this object.
> Quotes text objects (surrounded by "'\`) have seeking forward behaviour, so the command can be execute even outside (before) the object. This feature is not supported yet for the other objects, such as parentheses objects (surrounded by [{(). 

Selectors:
- <kbd>i</kbd> - inner: text object without whitespace (inside object-id)
- <kbd>a</kbd> - around: text object with whitespace (around object-id)

Object ids:
- <kbd>w</kbd> - word
- <kbd>s</kbd> - sentence
- <kbd>p</kbd> - paragraph
- <kbd>b</kbd> or <kbd>(</kbd> - block surrounded by ()
- <kbd>B</kbd> or <kbd>{</kbd> - block surrounded by {}
- <kbd>/<</kbd> or <kbd>></kbd> - block surrounded by /</>
- <kbd>[</kbd> or <kbd>]</kbd> - block surrounded by []
- <kbd>t</kbd> - tag (i.e. HTML tag)

Examples:
- <kbd>daw</kbd> - delete a word + whitespaces
- <kbd>das</kbd> - delete a sentence
- <kbd>dis</kbd> - delete inner sentence
- <kbd>da"</kbd> - delete text in double quotes including the quotes
- <kbd>di"</kbd> - delete text in double quotes excluding the quotes

- <kbd>ciw</kbd>change word (cursor can be anywhere in the word)
- <kbd>cit</kbd>change text inside tags (cursor can be anywhere in the tag)


## files
- `:q` - close the file, fails if changes are not saved (quit)
- `:q!` - close the file, without saving changes
- `:qa` - close all the files, fails if changes are not saved
- `:qa!` - close all the files, without saving changes

- `:w` - save the changes in current file (write)
- `:wa` - save the changes in all files
- `:wq` - save the changes and close the file
- `:wqa` - save the changes and close all files
- `:w {FILENAME}` - save file under given {FILENAME}

> You can write a part of file selected via VISUAL mode

- `:r {FILENAME}` - put a content of other file under the cursor (retrieve)

> You can paste to file an output of external command, i.e. <kbd>:r !ls</kbd>

## console commands
- `:help` - help
- `:help {command}` - help about {command}
- `{command}` <kbd>Ctrl</kbd>+<kbd>D</kbd> - autocomplete {command}

## external commands
- `:!{command}` - execute external shell command

Example:
- `:!ls` - list the current directory content

# INSERT mode
## changes
- <kbd>Ctrl</kbd>+<kbd>h</kbd> - delete the **last character** typed
- <kbd>Ctrl</kbd>+<kbd>w</kbd> - delete the **last word** typed
- <kbd>Ctrl</kbd>+<kbd>u</kbd> - delete the **last line** typed

## paste
Pattern:
<kbd>Ctrl</kbd>+<kbd>R</kbd>{register}

Examples:
- <kbd>Ctrl-R "</kbd> - paste the content of the unnamed register
- <kbd>Ctrl-R a</kbd> - paste the content of the 'a' register
- <kbd>Ctrl-R 0</kbd> - paste the content of the yank register

# VISUAL mode
- <kbd>v</kbd> - turn on **character-wise** visual mode
- <kbd>V</kbd> - turn on **line-wise** visual mode
- <kbd>Ctrl</kbd>+<kbd>v</kbd> - turn on **block-wise** visual mode

Pattern:
``{trigger}{counter}{motion}{operator}``

Example:
- <kbd>Vjd</kbd> - delete two lines
