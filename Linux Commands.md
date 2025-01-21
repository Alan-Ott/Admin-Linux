
man 
	display documentation

ls 
	 list 
	-l 
		display details
	-h 
		file size
	-a
		chow hidden files
	-lct 
		sort by date

cd
	return to user files

cd - 
	return to previous repository

cd .. 
	return to parent repository

cd / 
	return to root of file system

cd /usr/bin/ ou usr/bin

mv 
	move file or directory 
	-f 
		crush destination files without confirmation
	-i 
		request confirmation before crushing 
	-u 
		does not override destination file if it is newer
	mv myFile aRepo/
	mv aRepo/myfile .
	mv aRepo myRepo

cp 
	copy 
	-a
		archive copy retaining rights dates owners groups etc
	-i
		 request confirmation before crushing 
	-f 
		if destination file exists and cannot be opened then destroy it and try again
	-r
		Copy a directory and all its contents, including any subdirectories
	-u
		Copy only newer or non-existent files
	-v
		allows real-time copies to be tracked

rm
	erase / delete 
	**-i**
		Request for confirmation before erasing
	-f
		Do not request confirmation before erasing
	-r
		_Erasively **eras**_. This word means "including its
		subdirectories and their content".

mkdir
	make directory
	-p 
		create parent dir
		- **mkdir -p photos/2005/noel**  
	    Creates the _Christmas_ directory and if they do not exist the _2005_ directories and _photos_

rmdir
	remove dirctory
	**-p**
		 Deletes parent directories if they become empty

pwd 
	print current directory

ln
	link
	-s
		Creates a symbolic link (similar to the shortcut of the Windows world)
    -f
		Forced overwriting of the destination file if it exists
    -d
		Creates a link on a directory (only in sudo or root mode)

find 
		-name-name: Search for a file by name
	    -iname-iname: Same as -name but insensitive to the case
	    -type-type: Search for a file of a certain type
	    -atime-atime: search by time since last access
	    -mtime: search by elapsed time of last modification
	    -newermt-newermt: Search by date of last modification
	    -newerct-newerct: search by deadline for last change
	    -link-link: Search for the number of links to the file
	    -user-user: Search for files belonging to the given user
	    -group-group: Search for files belonging to the given group
	Most frequent actions:
	    -exec-exec: executes the command given to the files found
	    -ok: Same as -exec but asks for confirmation
	    -ls: executes the command ls at each file found
	Most frequent operators:
	    -a: Operator AND
	    -o-o: Operator OR
	    - or -not: Operator NOT

grep
	equivilent to find
		-c-c: Returns the number of lines instead of the lines themselves
	    -n-n: Returns the prefixed lines by their number
	    -i: Insensitive to breakage
	    -r: Search recursively in all subdirectories; the command rgrep can be used
	    -G-G: Search using basic rational expression (default option)
	    -E-E: Search using extended rational expression; control egrep can be used
	    -F: Search using a fixed chain; the command fgrep can be used
	    -v toto: Search for lines that do not contain the word toto
	Examples of use:
	    grep -n montexte monfile
	    Return all the lines as well as their number where mytext appears in monfier

cat
	_concatenate_
		  -n-n: Displays line numbers
	    -v: Displays the characters of controls

more 
	- **-s**-s: Groups consecutive empty lines into one
	- **-f**-f: Do not cut long lines

less 
	-e or -E-E: Automatically leaves the second time the file is completed, or as of the first time with -E.
    -F: Automatically leaves if the file fits on the terminal.
    -m or -M-M: Prompt long to the most.
    -r or -R-R: Authorizes special characters.
    -x: Adjusts the size of the tabulations.
    -~Don't fill the empty lines with .