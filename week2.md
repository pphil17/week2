# Week 2 Outline

## Review

- [ ] Introductions
- [ ] Syllabus Overview and Questions
	- Assignments due Fridays at _noon_ each week.
	- Class will focus on pragmatics of computing.
	- Plagiarism
		- Searching for solutions online will probably be necessary at some point, but credit must be given.
- [ ] The Linux Virtual Machine
	- May be easiest to run directly off of flash drive or OneDrive
	- For flash drives that move b/w Windows and Mac, will need to have FAT32 format and will need to reduce memory size of VM
- [ ] Markdown and Outlines
	- Can take notes directly in file - maybe use block quotes?
	- In Atom, install these packages:
		1. `markdown-preview`
		2. `language-markdown`
		3. Toggle preview on and off with Shift-Ctrl-M

> This is a block quote.
> This might be an easy way to add your own notes.<br>
> To write notes on new lines, add two empty spaces or `<br>` at the end of a line.

- [ ] GitHub and Homework
	- Repositories
		- Collections of related files (often code)
		- Formalizing as a repository allows Git to keep track of changes you make in these files through time
		- You can also copy someone else's repository (fork), make your own changes (commits), then ask the original owner to include your changes (pull request)
	- Pull Requests
		- Can also use these to share notes

```
GitHub exercise

1. Go to the `week 2` repository on the class GitHub page
2. Click the `fork` button in the upper-right of the page
3. Go to your newly forked copy of the repository
4. Add your name here:
	- Jeremy
5. Create a pull request
6. Add a commit message to your request to indicate the change you made
7. Submit your pull request
```


## Filesystem Structure

- [ ] Review last week's exercise
	- Recreate files and folders, if necessary

```
 ~/Desktop/Biology/
				README.txt
				CellBiology/
					ImportantCellBioTopics.txt
				Ecology/
					ImportantEcolTopics.txt
				Evolution/
					ImportantEvolTopics.txt
					Phylogenetics/
```

- [ ] The Unix root (/)
	- The very base of the filesystem
- [ ] Absolute paths
	- All absolute paths begin at the root
- [ ] Relative paths
	- Working directories
	- Shortcuts for current and parent directories
- [ ] Hidden files and folders
	- Names begin with `.`
	- Usually used for configuration files

```
Filesystem Exercise

1. Based on the directory structure above, find the Population Genetics folder.
2. Write the absolute path to that folder.
3. If Population Genetics is your working directory, write the relative path to the Phylogenetics folder.
4. If Biology is your working directory, write the relative path to Phylogenetics
```

## Practical Computing Advice

- [ ] Naming files and folders
	- camelCaseLooksLikeThis
	- `underscores_can_work`
	- __NEVER__ use spaces
	- Generally a good idea to avoid special characters
- [ ] Plain text files
	- Human readable
	- ASCII and UniCode
		- [ASCII on Wikipedia](https://en.wikipedia.org/wiki/ASCII)
		- [UTF-8 on Wikipedia](https://en.wikipedia.org/wiki/UTF-8)
- [ ] New line characters
	- [New Lines on Wikipedia](https://en.wikipedia.org/wiki/Newline)
- [ ] Activity Monitor
	- CPU Activity
	- Memory
	- Disk spaces
	- Jobs and IDs

## Introduction to the Command Line

- [ ] Terminal
	- Built in to Linux (and Mac OS X)
	- By default, uses the bash shell (interpreter)
	- The command prompt
	- Tab completion
	- Scrolling through history
- [ ] Commands related to navigating the filesystem
	- `pwd` - print working directory - or - "where am I?"
	- `ls` - list directory contents
		- ll - long list
			- Everything has three types of permissions
				- Read
				- Write
				- Execute
			- And three groups whose permissions can be controlled
				- Owner
				- Group
				- Others
			- [Wikipedia on Unix Permissions](https://en.wikipedia.org/wiki/File_system_permissions#Notation_of_traditional_Unix_permissions)
		- la - list with hidden files
	- `cd` - change directory
		- will accept absolute or relative paths
	- `chmod` - change permissions - specify who (ugo), how (+ or -), and what (rwx)
	- `man <command>` - gives us the manual page and options for any Unix command

```
First Command-Line Exercise (add commands run as notes as you go)

1. Change directories to the Desktop
2. List the visible contents of the directory
3. Now list _all_ contents of the directory (including hidden files and folders)
4. Chage directories to your home directory (remember the shortcut)
5. List the visible contents of the directory
6. List all contents of the directory
```

- [ ] Commands related to files and folders
	- `cp` - copies a file
		- `cp originalFile.txt newFile.txt`
	- `mv` - moves __or__ renames a file
		- To change location, use paths: `mv myFile.txt ./folder/myFile.txt`
		- To change name, just use different names: `mv myFile.txt newName.txt`
	- `cat` - view file contents - can be called on multiple files and will conCATenate their contents
	- `head -n #` - view the first # of lines of a file
	- `tail -n #` - view the last # of lines of a file
	- `less` - view the contents of a file a little at a time
	- `touch` - quickly create a new file
	- `nano` - this is actually an entire text editing program
	- `wc` - print out the length of a file in lines, words, and characters
	- `>>` - appends to file
		- echo "some text here" >> myTextFile.txt
	- `>` - writes to (or over!) file
		- echo "more text here" > myTextFile.txt
	- WARNING - BIG WARNING - PAY ATTENTION - `rm` _permanently_ removes a file
		- No going back - always use this VERY carefully
		- I know people who've accidentally erased their entire computers using this command
			- `rm -r` recursively removes a directory and everything inside it - even more dangerous than just `rm`!
		- This is the reason permissions are so important. If someone doesn't have write permissions on a file or folder, they shouldn't be able to delete it.
	- `mkdir` - create a new (empty) directory
	- `rmdir` - remove an empty directory
	- wildcards - * is especially useful - matches anything
	- `grep` - find only lines matching some particular string

	- [ ] Commands related to the Unix environment
		- Can create a variable and assign value using `=`
			- myVariable=2
		- Can print value of variable using `echo` and starting name with `$`
			- echo $myVariable
		- `|` - the Unix pipe can be used to send the output of one command into the input of another
			- `history | tail -n 20 >> endOfHistory.txt`

## Week 2 Assignment (Due. Fri, Aug. 31, at NOON)

1. Using the `mkdir`, `touch`, `echo`, and/or `nano` commands, recreate the directory and file structure above.
2. Using `cd` with an _absolute_ path, change your working directory to phylogenetics.
3. Using nano, create and save a new text file with your favorite phylogenetic fact (e.g.,
	"Birds are actually descended from dinosaurs!"). Feel free to search online, if you don't have one ready.
4. Using `cd` with a _relative_ path, change directories to Biology.
5. Using `ll` or `ls -l`, list the contents of Biology and send it to a new file called `BioContents.txt`.
6. Now, __carefully__ delete the Cell Biology folder and any files it contains.
7. Using `history`, a pipe, and `tail`, create a file (`myCommands.txt`) that shows the history of commands you ran for steps 1-6.
8. On GitHub, fork the `week2` repository.
9. On your computer, create a folder with your name and put the entire Biology directory hierarchy inside it.
10. While looking at your fork of `week2` on GitHub, go to the `week2Assignments` folder, click the `Upload files` button in the upper right, then upload the directory with your name by dragging and dropping. Add a commit message and commit the new files and directories.
11. After committing the new files, submit a pull request to the class page.
