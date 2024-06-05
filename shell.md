# Shell
## Moving in the shell prompt
    CTRL-B Move the cursor left
    CTRL-F Move the cursor right
    CTRL-P View the previous command (or move the cursor up)
    CTRL-N View the next command (or move the cursor down)
    CTRL-A Move the cursor to the beginning of the line
    CTRL-E Move the cursor to the end of the line
    CTRL-W Erase the preceding word
    CTRL-U Erase from cursor to beginning of line
    CTRL-K Erase from cursor to end of line
    CTRL-Y Paste erased text (for example, from CTRL-U)

## Treat an output as file
    <(...)
Example:

    <(./a.out)
## diff
Displaying the differences between two files:

    diff file1.txt file2.txt
Displaying the differences between an output and a text file:

    diff <(./a.out) output.txt
# ITerm
## Broadcast input to all panels in current tabs

    OPTION + CMD + I
## toggle tab
    CMD + <left arrow>
    CMD + <right arrow>

