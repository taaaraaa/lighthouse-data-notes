# Bash Introduction

## Commands
- `mkdir Projects` make a directory (ie. Projects)
- `ls` list the contents of a directory (use `man ls` for more options)
- `touch <filename>` create a new file with a file name
- `cat <filename>` print the entire file to the terminal
- `head <filename>` print the first 10 (default) lines of the file
- `head -n 5 <filename>` print the first 5 lines of the file
- `less` displays a file, but doesn't write to the terminal (see note)
- `clear` remove the terminal output from view when overly verbose
- `history` display a history of the commands that you have used

### Less
Provides a view that displays the contents of a file, but doesn't write the file content to the terminal so the terminal output remains clean.  Useful commands:
- Use the `-S` command `less -S` to prevent line wrapping
- Allows use of arrow keys to move around the file
- Type `q` to quit the file
- Type `h` to see the help menu


## Change Directory
Command for changing a directory is `cd` with a supplied path.

- `~` navigate to the home directory from anywhere
- `cd ~/Projects` navigate to an absolute path to a specific directory (ie. Projects)
- `cd ../` go up a single directory relative to current directory
- `cd ../../` go up a multiple directories relative to current directory

## Console Shortcut Commands
- Use `tab` to autocomplete (ie. changing directories)
- `ctrl + a` - go to start of line
- `ctrl + e` - go to end of line

## Configure zshrc using VSCode
- `code .` open the current directory in an IDE
- `code <filename>` open a file for editing in an IDE
- `code <sub-dir>/<filename>` open the current directory in an IDE


## Tips and Tricks
- `code ~/.zshrc ` allow for quick editor of configuration for zsh, which
is a good way to add alias and commands I want to execute in the terminal.
For example, `projs` is an alias I added to `cd` to my projects folder.

    ```bash
    # GENERAL ------------------------------------------------------------

    # Open current folder
    alias o="open ."

    # Change directory to home
    alias h="cd ~"

    # Open .zshrc file for editing
    alias zshrc="code ~/.zshrc"

    # Change directory to projects
    alias projs="cd ~/Projects"

    # BOOTCAMP -----------------------------------------------------------

    alias actenv="conda activate base_env"
    alias jl="jupyter lab"
    alias ajl="actenv && jl"
    ```

- `cat <filename> | awk '{$1=$1;print}' OFS='\t'` print content to terminal and convert tabs to spaces
- `cat <filename> | sort -k1,1nr` sort column 1 (k1) to column 1 numerically in reverse, and for more options type `sort --help`