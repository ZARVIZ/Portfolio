OverTheWire: Bandit (Levels 0-10)

This file documents my solutions for the first 10 levels of the OverTheWire Bandit wargame. Each level's objective is to find the password for the next level, teaching a new Linux command or concept along the way.

Level 0 → Level 1

    Objective: Connect to the game using SSH and find the password for the next level, which is stored in a file named readme.

    Command(s):
    Bash

    ssh bandit0@bandit.labs.overthewire.org -p 2220
    # Password is 'bandit0'
    ls
    cat readme

    Explanation:

        ssh bandit0@...: Connects to the server as user bandit0 on port 2220.

        ls: Lists the files in the current directory.

        cat readme: Reads the content of the readme file and prints it to the screen.

    ```Password: ```

Level 1 → Level 2

    Objective: The password is in a file named - (a single dash).

    Command(s):
    Bash

    # (Log in with the password from Level 1)
    ls
    cat ./-

    Explanation: The cat command normally thinks - means "read from standard input." Using ./ tells the shell to look for a file named - in the current directory (.).

    ```Password: ```

Level 2 → Level 3

    Objective: The password is in a file named spaces in this filename.

    Command(s):
    Bash

    ls
    cat "spaces in this filename"
    # OR
    # cat spaces\ in\ this\ filename

    Explanation: To handle filenames with spaces, you must either wrap the entire filename in quotes (") or "escape" each space with a backslash (\).

   ```Password: ```

Level 3 → Level 4

    Objective: The password is in a hidden file inside the inhere directory.

    Command(s):
    Bash

    cd inhere
    ls -a
    cat .hidden

    Explanation:

        cd inhere: Changes directory to inhere.

        ls -a: Lists all files, including hidden ones (those starting with a .).

        cat .hidden: Reads the content of the .hidden file.

    ```Password: ```
    
Level 4 → Level 5

    Objective: The password is in the only human-readable file in the inhere directory.

    Command(s): 
    Bash
    cd inhere
    file ./*
    cat./-file07

    Explanation:

    file ./*: Runs the file command on all files in the directory. This command tells you the type of each file.

    The output will show one file is ASCII text (human-readable) while others are data (binary).

    cat ./-file07: Reads the content of the identified ASCII file.

```Password: ```

