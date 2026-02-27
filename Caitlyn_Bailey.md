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

# Lab 5 Notes:


Lab 5 copied over:

### Today
1. Review
2. Permissions
3. Conda environments
4. Running Fastqc
5. Redirection (if there is time)

:::::::::::::::::::::::::::::::::::::::: keypoints

- You can view file permissions using `ls -l` and change permissions using `chmod`.
- The `history` command and the up arrow on your keyboard can be used to repeat recently used commands.
- Conda environments simplify reporducability, dependencies and sharing environments.

::::::::::::::::::::::::::::::::::::::::::::::::::


:::::::::::::::::::::::::::::::::::::::: review

- You can view file contents using `less`, `cat`, `head` or `tail`.
- The commands `cp`, `mv`, and `mkdir` are useful for manipulating existing files and creating new directories.

### Quality scores. Highest score for a base is 41
Quality encoding: !"#$%&'()*+,-./0123456789:;<=>?@ABCDEFGHIJ
                   |         |         |         |         |
Quality score:    01........11........21........31........41

::::::::::::::::::::::::::::::::::::::::::::::::::

*Warm ups: What is the last read in one of the fastq files? How confident are you in this read?
A: 
@SRR097977.249 209DTAAXX_Lenski2_1_7:8:3:441:292 length=36
GGGTAGGTATTACTCAGGACGAGGCGGTCGTGCCAC
+SRR097977.249 209DTAAXX_Lenski2_1_7:8:3:441:292 length=36
C:CCC::CCCCCCCC<8?6A:C28C<608'&&&,'$

I am fairly confident in the frist half of the read, with all the Cs, but the second half seems to drop off in quality 

How big are your fastqs? (Hint: Look at the options for the ls command to see how to show file sizes.)
- hint, it involves 'ls'. See if you can do it using a relative and absolute path
- another hint: There is an option to make it easy to read the file size. Use one of the two methods to find it
A:

```ls -lh``` will list all files in a directory, adding the h will make it in a human readable format, so bites instead of bits.

You can naviate to the directory first and then use this, relative, or you can do an absolute path, like so:

```ls -lh /home/users/cmb1451@ron/gen711/811/shell_data/untrimmed_fastq/"file name"```

### EXERCISE 5.1
Starting in the shell_data/untrimmed_fastq directory, do the following:

Make sure that you have deleted your backup directory and all files it contains.
Create a backup of each of your FASTQ files using cp. (Note: You’ll need to do this individually for each of the two FASTQ files. We haven’t learned yet how to do this with a wildcard.)
Use a wildcard to move all of your backup files to a new backup directory.
Paste the code you used to do each step between the \'\'\' below:

```
cp SRR097977.fastq SRR097977.backup.fastq
cp SRR098026.fastq SRR098026.backup.fastq
mkdir backup
mv *backup.fastq backup
``` 

### File Permissions Help
The first part of the output for the `-l` flag gives you information about the file's current permissions. There are ten slots in the
permissions list. The first character in this list is related to file type, not permissions, so we'll ignore it for now. The next three
characters relate to the permissions that the file owner has, the next three relate to the permissions for group members, and the final
three characters specify what other users outside of your group can do with the file. We're going to concentrate on the three positions
that deal with your permissions (as the file owner).

![](fig/rwx_figure.svg){alt='Permissions breakdown'}

Here the three positions that relate to the file owner are `rw-`. The `r` means that you have permission to read the file, the `w`
indicates that you have permission to write to (i.e. make changes to) the file, and the third position is a `-`, indicating that you
don't have permission to carry out the ability encoded by that space (this is the space where `x` or executable ability is stored, we'll
talk more about this later).

### EXERCISE 5.2
Change the permissions on all of your backup files to be write-protected.

```chmod -w "file"``` Remove write privilege from file

use just ```*``` to select everything in adirectory

can also do ```chmod -w backup/```

How do you know they are write protected?
A: When we try to echo something into it, it doesn't work. An error message appears. It also says that the w is gone in the permissions.

```
chmod ug+rwx SRR097977.fastq
chmod ug+rwx SRR098026.fastq
```

### EXERCISE 5.3: CONDA ENVIRONMENTS AND PROGRAMS

A CONDA environment allows us to talk between Shell Bash, Python, and R

It has a bunch of tools for doing bioinformatics.

After loading a conda environment, where is the program 'fastqc' stored?

```
conda activate genomics
conda deactivate
```

### Explore the fastqc output. Which samples failed at least one of FastQC’s quality tests? What test(s) did those samples fail?


:::::::::::::::::::::::::::::::::::::::: keypoints
- Use `which` for commands/programs to see where they are installed
- You can view file permissions using `ls -l` and change permissions using `chmod`.
- The `history` command and the up arrow on your keyboard can be used to repeat recently used commands.
- Explain what a conda environment is, and how to activate and deactivate it

::::::::::::::::::::::::::::::::::::::::::::::::::

unzip

# Lab 6 Notes

### Today
1. Review, fastqc
2. Redirection and pipes lesson
3. Script writing

```|``` pipes to another command

```>``` pipes to another location

```>>``` sticking files together while making a copy or putting two outputs together

Stuck? cntrl + c !

## review
which for programs
conda environments
chmod for permissions
fastqc


## keypoints
Employ the grep command to search for information within files.
Print the results of a command to a file.
Construct command pipelines with two or more stages.
Use for loops to run the same command for several input files.


## questions for practical
How can I search within files?
How can I combine existing commands to do new things?



## HELP: Nucleotide abbreviations
The four nucleotides that appear in DNA are abbreviated A, C, T and G. Unknown nucleotides are represented with the letter N. An N appearing in a sequencing file represents a position where the sequencing machine was not able to confidently determine the nucleotide in that position. You can think of an N as being aNy nucleotide at that position in the DNA sequence.


## Exercise 1

1. Search for the sequence `GNATNACCACTTCC` in the `SRR098026.fastq` file.
  Have your search return all matching lines and the name (or identifier) for each sequence
  that contains a match.

  ```grep -B1 -A2 GNATNACCACTTCC SRR098026.fastq```

2. Search for the sequence `AAGTT` in both FASTQ files.
  Have your search return all matching lines and the name (or identifier) for each sequence
  that contains a match.

```grep -B1 -A2 AAGTT SRR098026.fastq SRR097977.fastq```

3. How do the search results differ when matching in one file vs. both files? If you wanted to keep the original FASTQ format, how would you get around this?

You can use one command, as I did in question 2. This keeps the format of the fastq while showing the output of both files together. You can also use a wildcard to just do all fastq files. ```*.fastq```

```grep --no-group-separator``` would remove the separator lines between reads.

```grep -h``` removes file names

```grep -v ' '``` Grep without anything that matches the term. Reverse grep. Used with a normal grep command.

4. Make a file called 'bad-reads.fastq' made up of reads with 10 Ns or more in a row.



## Exercise 2

How many sequences are there in `SRR098026.fastq`? Remember that every sequence is formed by four lines.

## Exercise 3

How many sequences in `SRR098026.fastq` contain at least 3 consecutive Ns?

## Exercise 4

Print the file prefix of all of the `.txt` files in our current directory.

## Exercise 5

After renaming the fastqs as demonstrated, remove `_2026` from all of the `.txt` files.

## Exercise 6

We want the script to tell us when it's done.

1. Open `bad-reads-script.sh` and add the line `echo "Script finished!"` after the `grep` command and save the file.
2. Run the updated script.




## keypoints

- `grep` is a powerful search tool with many options for customization.
- `>`, `>>`, and `|` are different ways of redirecting output.
- `command > file` redirects a command's output to a file.
- `command >> file` redirects a command's output to a file without overwriting the existing contents of the file.
- `command_1 | command_2` redirects the output of the first command as input to the second command.
- `for` loops are used for iteration.
- `basename` gets rid of repetitive parts of names.





```bash
curl -O ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR258/004/SRR2589044/SRR2589044_1.fastq.gz
curl -O ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR258/004/SRR2589044/SRR2589044_2.fastq.gz
curl -O ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR258/003/SRR2584863/SRR2584863_1.fastq.gz
curl -O ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR258/003/SRR2584863/SRR2584863_2.fastq.gz
curl -O ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR258/006/SRR2584866/SRR2584866_1.fastq.gz
curl -O ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR258/006/SRR2584866/SRR2584866_2.fastq.gz
```
```bash
$ cd
$ wget ftp://ftp.ensemblgenomes.org/pub/release-37/bacteria/species_EnsemblBacteria.txt
```

or

```bash
$ cd
$ curl -O ftp://ftp.ensemblgenomes.org/pub/release-37/bacteria/species_EnsemblBacteria.txt
```

For loops:
for 'term' in 'file'
do 
command ${variable}
done

type first line and more will appear for the following

example:
```
for fq in *fastq
> do
> wc -l ${fq}
> done
536 bad-reads.fastq
996 SRR097977.fastq
996 SRR098026.fastq
```

Set variables
something1=something2. Check with echo. Ask to echo something1 and the result will be something2.

