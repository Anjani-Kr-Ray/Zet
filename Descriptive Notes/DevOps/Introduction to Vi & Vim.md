# Introduction to Vi & Vim
##### Use Cases to Use text Editor in CLI
* Small modification can be faster, especially when you are currently working in the CLI
* Faster to create and edit at the same time
* Supports multiple formats
* When working on a remote server
* Git CLI - writing the GIT Commit Message
* Display Kubernetes Configuration Files
* Quickly editing one line or character in a file

##### Working with Vim Editor
* Install Vim : `sudo apt install vim`
* Vim Editor has two modes
	1. Command Mode
		* This is the default mode
		* We can't edit the text
		* whatever you type is interpreted as a command
		* Navigate, Search, Delete, Undo etc.
		* To comeback to command mode press `esc` key

	2. Insert Mode
		* Allows us to enter text
		* press `i` key to change to insert mode

* `:wq` to save and quit the file
* `:q!` to quit the file without saving the changes
* `dd` to delete entire line
* `d<Number of Line>` to delete next number of lines e.g., `d10` to delete next 10 lines
* `u` to undo changes
* `A` jumps to end of line and switches to insert mode
* `0` jump to begining of line
* `$` to jump to end of the line
* `<Line Number>G` jumps to given line number
* `/pattern` search for pattern & `n` to jump to next match & `N` to jump to previous match
* `%s/old/new` replace old with new throughout the file

> **Note:** All above commands are in command mode




