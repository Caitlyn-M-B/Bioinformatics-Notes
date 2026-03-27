# Commands

Basic command structure & tips:
- ```clear``` - Clears past commands out of the terminal.
- cntrl c - escape
- ' ' Quotes represent a search area. You may get stuck in carrots if you accidentally open a quote without closing it.
- tab - autocomplete. Saves a lot of time and errors. Capitalization matters.
- --help can give information on modifications for commands
- `>`, `>>`, and `|` are different ways of redirecting output.
    - ```|``` sends output to a dfferent command.
    - ```> 'file'``` redirect. Sends information to a place other than printing it to the screen. Added to the end of a grep or other printing command.
    - `command >> file` redirects a command's output to a file without overwriting the existing contents of the file.
- ```*``` to select everything in adirectory

Navigation and file management:
- ```cd 'file'``` - change directories. Type directory name after cd.
    - ```cd ~``` - brings you back to your home directory
    - ```../``` - back up one step in directories
- ```mkdir 'new directory name'``` - make directory
- ```cp 'old file' 'new file name'``` - copy file
- ```mv 'file' 'directory'``` - move file
- ```rm 'file'``` - remove/delete. Careful!
- ```> 'file'``` redirect. Sends information to a place other than printing it to the screen. Added to the end of a grep or other printing command.
- ```history``` - shows entire history of commands
- 


Looking at what you have:
- ```pwd``` - Print Working Directory. Shows open directories. Like a map showing where within the files you're working; gives you the absolute path.
-  ```ls``` - List. Shows all files and folders in working directory.
    - ```ls -lrth``` - shows more information than just the names, shows permissions, users, file size and more.
    - ```--all``` - shows all files, including hidden files.
    - ```ls .*``` - shows hidden files
    - ``` ls -laF``` - show all files in long form with slash and directory format.
    - ```ls -l``` - shows file permissions
    - ```ls -lh``` - shows file permissions, plus in a human readable format, so file sizes are in bites instead of bits.
- ```head 'file'``` - print out first few lines of files to screen. Must specifiy file.
- ```cat 'file'``` - print whole file. Proceed with caution.
- ```grep '@' 'file'``` - searches a file for given text. Must specifiy in quotes what you're looking for and file to look in.
- ```WC``` - shows line, word, and character count
- ```less``` shows some but not all of the content of a file; more of a preview than head.