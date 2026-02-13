# Hello! This is my notebook!
# Lab 1 Notes:
This first lab hasn't been too bad.
# Lab 2 Notes:
Idk if this work is for lab 2 or 3 but this is the second time in this room so we'll figure that out later.
# Lab 3 Notes:

## Commands

- ```pwd``` - Print Working Directory. Shows open directories. Like a map showing where within the files you're working.
-  ```ls``` - List. Shows all folders in working directory.
    - ```ls lrth``` shows many useful things
- ```clear``` - Clears past commands out of the terminal.
- ' ' Quotes represent a search area. You may get stuck in carrots if you accidentally open a quote without closing it.
- cntrl c - escape
- tab - autocomplete. Saves a lot of time and errors.
- ```cd 'file'``` - change directories. Type directory name after cd.
    - ```cd ~``` brings you back to your home directory
- ../ - back up one step in directories
- ```head 'file'``` - print out first few lines of files to screen. Must specifiy file.
- ```cat 'file'``` - print whole file. Proceed with caution.
- ```rm 'file'``` - remove/delete. Careful!
- ```history``` - shows entire history of commands
- ```grep '@' 'file'``` - searches a file for given text. Must specifiy in quotes what you're looking for and file to look in.
- ```> 'file'``` redirect. Sends information to a place other than printing it to the screen. Added to the end of a grep or other printing command.
- ```|``` sends output to a dfferent command.
- ```WC``` - shows line, word, and character count
- ```less``` shows some but not all of the content of a file; more of a preview than head.

#### 1. What are 3 (4) ways to change directories to your home directory from the  untrimmed_fastq directory?
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

# Lab 4 Notes:
### EXERCISE 1: NAVIGATION PRACTICE
Navigate to your untrimmed_fastq directory in one command:

```cd gen711-811/shell_data/untrimmed_fastq/```

Good practice to write this as one line for reproducability, plus it's just nicer as one line as opposed to three, one for each cd command

```ls ../../``` lists directories going back as many .. as you add. Two in this case, back to home. ```../``` kind of means "take a step back".

### EXERCISE 2: WILDCARDS
What would the output look like if the wildcard could *not* be matched? Compare the outputs

```ls *fq```
ls: cannot access '*fq': No such file or directory

### EXERCISE 3: NAVIGATING PRACTICE
Navigate to your home directory. From there, list the contents of the untrimmed_fastq directory.

```ls gen711-811/shell_data/untrimmed_fastq/```

### EXERCISE 4: FINDING HIDDEN DIRECTORIES
First navigate to the shell_data directory. There is a hidden directory within this directory. Explore the options for ls to find out how to see hidden directories. List the contents of the directory and identify the name of the text file in that directory.

Hint: hidden files and folders in Unix start with ., for example .my_hidden_directory

What is the hidden file name in the hidden directory?
.hidden

```ls --``` shows all list commands to choose what you want to list. 
- ```--all``` shows all files, including hidden files.
- Hidden files have a period in front of them as convention. May not be needed for average user to run code, but needed to make it work. Becasue of this convention, hidden files can also be found with ```ls .*```

``` ls -laF``` show all files in long form with slash and directory format.

### EXERCISE 5: HISTORY
Find the line number in your history for the command that listed all the .sh files in /usr/bin. Rerun that command.

```history | grep 'search term'``` to find past commands including the search term

141 ```ls /usr/bin/*.sh```

### EXERCISE 6: FILE CONTENTS
Print out the contents of the ~/shell_data/untrimmed_fastq/SRR097977.fastq file. What is the last line of the file?

C:CCC::CCCCCCCC<8?6A:C28C<608

### EXERCISE 7: PATHS
From your home directory, and without changing directories, use one short command to print the contents of all of the files in the ~/shell_data/untrimmed_fastq directory.

### EXERCISE 8: LESS
What are the next three nucleotides (characters) after the first instance of the sequence quoted above?

hit q to escape less!
Type /sequence to search in a less document. For example, /TTTTT will show all sequences of TTTTT.

Three nucleotides = CAC

```mkdir 'new directory name'``` make directory

```cp 'old file' 'new file name'``` copy file

```mv 'file' 'directory'``` move file