## Vim keybinds
`:help` or `F1` - help menu 
`<Esc>` - return to normal mode
`:q!` - force quit without saving
`:wq` - save and quit
`hjkl` - movement keys
`<ENTER>` - when cursor is over linked text to open it
`K` - shift-k, on any word to find its documentation
`u` - undo a change
`U` - undo all changes in a line
`<C-r` - redo the command. ctrl+r
`<C-w> <C-w` - move to next window
`:!<cmd>` - to run bash commands


Operator Number Motion
## Insert text
`I` - insert text at the start of the line
`i`  - insert text BEFORE cursor
`A` - append text at the end of the line
`a` - append text AFTER cursor
`O` - open new line before the current line
`o` - open new line after the current line and enter insert mode

### Deletion
Operator:
`d`
- `dd` to delete whole line
	- can add a number to the operator
`x` - delete letter

Add operator in front of motion like so:
`dw` - delete word
- `d2w` - delete 2 words
`d$` - delete to the end of the line
`d <NUMBER> <MOTION>`
### Put
say, you deleted some text or a line, this saves to neovim register and you can place it back
`p` - put previously deleted text AFTER the cursor
`P` - put the deleted text BEFORE the cursor

### Replace
`r` - replace the text at the current cursor with another character
- ex. `rw` - replace text with w letter
`R` - replace more than one char

### Change operator
`c` - change the letters after and enters INSERT mode
- `ce` - deletes until end of word from cursor and enters INSERT mode
- `c <NUMBER> <MOTION> ` - similar to delete operator
## Motions:
`w` - until start of the next word, excluding first char
`e` - until end of the current word, including the last character
`$` - to the end of the line, including the last char
`0` - move to start of the line

Using a number for a motion
`2w` - move cursor 2 words forward
`2e` - move cursor to the end of the second word forward

### Cursor location and File status
`<C-g>` - ctrl-g, show your location in a file and the file status
`G` - to move to a line in the file
- just by itself, move to end of file
- `<NUMBER>G` - move to that line
`gg` - move to start of file

### Search command
`/` - type `/` followed by a phrase and `ENTER` to search for that phrase
`n` - move to next location for the phrase
`N` - move to opposite location for the phrase
`?` - search for the phrase in the backward direction
`<C-o>` - to go back to where you were, repeat it to go back further
`<C-i>` - goes forward

### Matching parenthesis search
`%` - to find a matching `), }, or ]`

### Substitute command
Type `:s/<old>/<new>/g` - to substitute old word with new word on the line
- `g` is for changing all occurrences of old to new on the line 
- `gc` can be used to ask for permission for each change
`:#,#s/<old>/<new>/g` - change all occurrences of old to new between 2 specified lines where `#` is the line number
`:%s/<old>/<new>/g` - change all occurrences of old to new in the entire file

### Copy and paste text
`y` - yank the highlighted text. Can be used as an operator
- yank, and then put `p`

### Visual Mode
Typically `<C-v>` but doesn't work on windows terminal so use `<C-q>`
`v` - to highlight text
### Terminal
`<leader-h>` to open horizontal terminal
`<C-\> <C-n>` - to exit terminal mode

### Completion
start a command, `:<letters>`, press `<C-d>` to show list of commands that begin with what you typed
`<TAB>` to complete the command