# Shell
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
## Broadcast input to all panels in current tab

    OPTION + COMMAND + I
