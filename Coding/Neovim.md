
## Vim keybinds
`<Esc>` - return to normal mode
`:q!` - force quit without saving
`:wq` - save and quit
`hjkl` - movement keys
`x` - delete letter
`<ENTER>` - when cursor is over linked text to open it
`K` - shift-k, on any word to find its documentation
`u` - undo a change
`U` - undo all changes in a line
`<C-r` - redo the command. ctrl+r

Operator Number Motion
## Add text
`i`  - insert text
`A` - append text
### Deletion
Operator:
`d`

Add operator in front of motion like so:
`dw` - delete word
- `d2w` - delete 2 words
`d$` - delete to the end of the line
## Motions:
`w` - until start of the next word, excluding first char
`e` - until end of the current word, including the last character
`$` - to the end of the line, including the last char

Using a number for a motion
`2w` - move cursor 2 words forward
`2e` - move cursor to the end of the second word forward
`0` - move to start of the line

