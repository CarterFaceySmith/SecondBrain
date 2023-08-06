# Unix Commands

So ya wanna use the terminal, the command line, the big daddy programmer hacker interface? Well it's kinda shit for human legibility so use this cheatsheet.

- ls: listings, displays things in current directory location
	- Modifiers:
		- -a: displays hidden items
		- -F: displays extensions
		- -s: displays sizes
		- -l: displays in a longform listing, contains more information per file
- cd: change directory, moves ya
- ../: one level up from whatever you're in
- mkdir: makes a directory
- nano: opens the nano text editor, can be postfaced with a name for the file you wanna create
- rm: deletes shit, can only be used on files not directories
- mv: moves a file or directory, can be used to rename a file by saying basically move this file to the same direct it's currently in but using this name now
- cp: copy a file
- wc: wordcount, counts the lines, words and chars in a file
	- Modifiers:
		- -l: lines only
		- -w: words only
		- -c: chars only
- example command > examplefilename.txt: sends the output of your command to a file, if the file doesn't exist it's created and if it does it's overwritten
- cat: concatenate, prints the contents of a file one after the other
- sort: doesnt change file contents but displays contents of file sorted to screen
- head -1: get first line of file, -1 can be changed to get top x number of lines of the file from head
	- See also:
		- tail, same as head but from tail of file
		- split, split a file into pieces
		- cut, remove sections from each line of files
		- uniq, report or omit repeated lines
- x | y: a pipe, tells the comp that we want to take the output of the left side (x) and write it to the right side (y) without creating a temp file
	- can be chained together
- grep x filename.txt: finds and prints lines in file containing x
	- -i: case insensitive
	- -w: match whole words
	- -n: numbers lines that match the query
	- -v: prints anything that doesn't match the query
- find: finds files
- tree: prints file directory as tree structure
- alias aliasname=xyz xyz xyz: can be used to create shortcuts, where xyz is the shortcut bound to the alias name, you can then simply call the alias name instead of typing the entire command out
- ssh username@computername: remote access a computer, will prompt for password
- scp username@computername:/filedirectory location username@secondcomputername:/filedirectory location: copies one file from a computer to a remote other computer
	- -r: copies a directory and it's contents


See also:
- [[UNIX]]
- [[Unix Permissions]]
- Terminal
- Command Prompt