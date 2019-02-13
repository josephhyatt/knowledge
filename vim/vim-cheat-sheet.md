# Vim Cheat sheet

## Basic Commands

| **Vim Command** | **Description** |
| :--- | :--- |
| `i` | Enter insert mode |
| `Esc` | Enter command mode |
| `x` or `Del` | Delete a character |
| `X` | Delete character is backspace mode |
| `u` | Undo changes |
| `Ctrl + r` | Redo changes |
| `yy` | Copy a line |
| `dd` | Delete a line |
| `p` | Paste the content of the buffer |
| `/<search_term>` | Search and then cycle through matches with n and N |
| `[[` or `gg` | Move to the beginning of a file |
| `]]` or `G` | Move to the end of a file |
| `:%s/foo/bar/gci` | Search and replace all occurrences with confirmation |
| `Esc + :w` | Save changes |
| `Esc + :wq` or `Esc + ZZ` | Save and quit Vim |
| `Esc + :q!` | Force quit Vim discarding all changes |

## Quit and Save

| Vim Command | Description |
| :--- | :--- |
| `:x` | To Exit Vi and save changes |
| **`:q`** | To Exit Vi if there have been no changes |
| **`ZZ`** | Exit Vi in case of saving changes if any have been made |
| **`:q!`** | Exit and ignore any changes |

## Text Deletes Commands

| Vim Command | Description |
| :--- | :--- |
| `x` | Delete character to the right of cursor |
| `X` | Delete character to the left of the cursor |
| `D` | Delete to the end of the line |
| `dd` | Delete current line |
| `:d` | Delete current line |

## Inserting Text Commands

| Vim Command | Description |
| :--- | :--- |
| `i` | Insert before cursor |
| `I` | Insert before line |
| `a` | Append after cursor |
| `A` | Append after line |
| `o` | Open a new line after current line |
| `O` | Open a new line before current line |
| `r` | Replace one character |
| `R` | Replace many characters |

## Navigation commands

| Vim Command | Description |
| :--- | :--- |
| `h` | Move left |
| `j` | Move down |
| `k` | Move up |
| `l` | Move right |
| `w` | Move to next word |
| `W` | Move to next blank delimited word |
| `b` | Move to the beginning of the word |
| `B` | Move to the beginning of blank delimted word |
| `e` | Move to the end of the word |
| `E` | Move to the end of Blank delimited word |
| `(` | Move a sentence back |
| `)` | Move a sentence forward |
| `{` | Move a paragraph back |
| `}` | Move a paragraph forward |
| `0` | Move to the begining of the line |
| `$` | Move to the end of the line |
| `1G` | Move to the first line of the file |
| `G` | Move to the last line of the file |
| `nG` | Move to nth line of the file |
| `:n` | Move to nth line of the file |
| `fc` | Move forward to c |
| `Fc` | Move back to c |
| `H` | Move to top of screen |
| `M` | Move to middle of the screen |
| `L` | Move to botton of screen |
| `%` | Move to associated \( \), { }, \[ \] |

