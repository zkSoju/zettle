202210241618
Status: 
Tags: #vim

- Add plugins to init.lua and then PackerSync

- `esc` to leave mode

editting mode
- `i` to enter editting mode before cursor
- `shift + I` editting at beginning
- `a` to enter editting mode after cursor
- `shift + A` editting at end
- `o` to enter editting mode start new line
- `shift + O` edditing at line above

command mode `:`
- `:` to enter command mode
	- `w` to save
	- `q` to quit
	- `!` without saving
	- `{line#}` jump to line number

normal mode
- `/` to search and `n/N` to go forward/backword 
- `space + e` to toggle sidebar
- `space + o` to focus sidebar
- `space + t` to toggle terminal
- `# {left/right/up/down}` to move
- `hjkl` to move 
- `u` to undo
- `ctrl + r` redos
- `r` replace one character
- `w`/`W` to go forward words
	- `dw` to delete a word
	- however if cursor in middle of word, `diw` delete in a word
	- `cw` to change a word
	- `ciw` change in a word
- `b`/`B` to go back words
- `0` goes to beginning of line
- `$` goes to end of line
	- `d$`
	- `d0`
- `ci"` change in quotation marks
- `ci(` or `ci)`
- `ci{` or `ci}`
- `%` jump between opening/closing brackets
- `t{char}` jump to one position before char
	- `t` look after / `T` look behind
	- `dt{char}` delete to one before char
- `f{char}` jump to char
- `gg` beginning of file
- `G` end of file

visual mode `v`
- arrow keys to select
- `d` delete (goes to normal mode)
	- `D` delete rest of the line
- `c` delete/change (goes to insert mode)
	- `C` delete rest of the line
- `y` yank/copy
	- `yy` or `Y`  yanks full line
- `p` paste
	- `p` pastes before
	- `P` pastes after
	- if it contains a new line character it will be on next line or previous line


- combine numbers with actions to exec x # of actions

`shift + W`
`shift + Q`







---
# References

