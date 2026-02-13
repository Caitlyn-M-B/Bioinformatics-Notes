# Hello! This is my notebook!
This first lab hasn't been too bad.
# Lab 2 Notes
Idk if this work is for lab 2 or 3 but this is the second time in this room so we'll figure that out later.
# Lab 3 Notes

## Commands

- ```pwd``` - Print Working Directory. Shows open directories. Like a map showing where within the files you're working.
-  ```ls``` - List. Shows all folders in working directory.
    - ```ls lrth``` shows many useful things
- ```clear``` - Clears past commands out of the terminal.
- ' ' Quotes represent a search area. You may get stuck in carrots if you accidentally open a quote without closing it.
- cntrl c - escape
- tab - autocomplete. Saves a lot of time and errors.
- ```cd file``` - change directories. Type directory name after cd.
    - ```cd ~``` brings you back to your home directory
- ../ - back up one step in directories
- ```head``` - print out first few lines of files to screen. Must specifiy file.
- ```cat file``` - print whole file. Proceed with caution.
- ```rm file``` - remove/delete. Careful!
- ```history``` - shows entire history of commands
- ```grep '@' file``` - searches a file for given text. Must specifiy in quotes what you're looking for and file to look in.
- ```> file``` redirect. Sends information to a place other than printing it to the screen. Added to the end of a grep or other printing command.
- ```|``` sends output to a dfferent command.
- ```WC``` - shows line, word, and character count
- ```less``` shows some but not all of the content of a file; more of a preview than head.

#### 1. What are 3 ways to change directories to your home directory from the  untrimmed_fastq directory?
1. ```cd ~``` Sends you  home from any directory.
2. ```cd $HOME``` Brings you home by opening a variable that is holding the address of the home directory.
3. ```cd ../../../``` Backstepping enough will bring you back to where you started.
4. ```cd home/users/cmb1451``` Brings me back to my directory. This adress can be found using ```pwd```.

#### 3b. How many programs in /bin 
2. Do each of the following tasks from your current directory using a single ls command for each:
    - List all of the files in /bin that start with the letter ‘c’.
    - List all of the files in /bin that contain the letter ‘a’.
    - List all of the files in /bin that end with the letter ‘o’.
    - Bonus: List all of the files in /bin that contain the letter ‘a’ or the letter ‘c’.

#### Answers here
- Start with the letter c __```ls c*```__
- Start with the letter a __```ls a*```__
- Start with the letter o __```ls o*```__
- Contain the letter ‘a’ or the letter ‘c’ ____