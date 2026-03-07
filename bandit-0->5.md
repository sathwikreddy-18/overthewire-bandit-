-->SSH(Secure Shell)
  For connection to SSH,command is 
  ssh bandit0@bandit.labs.overthewire.org -p 2220

  2220 is the port number

  For every level, we login to next level using the password from the previous level.

-->Level 0
  Reading password from file called readme

  Idea: Acess the SSH port first and then use the commands needed to do the required operation.

  Commands used:
  ls - Lists files and directories in current directory.
  cat -Reads files and prints the contents in it.

Password retrieved successfully.

-->Level 1
  Read the file named "-"

  Idea:"-" is treated as stdin in "cat -", so we use a extra term (./) in order to fulfill the demands.

  Commands used:
  cat ./-

  Password retrieved successfully.

-->Level 2
  If the file name contains spaces

  Idea:If there are spaces in the file name, we use "\" for each space, so that it takes everything as the same filename.

  Commands used:
  cat ./--spaces\ in\ this\ filename--

Password retrieved successfully.

-->Level 3
  Hidden file inside inhere file

  Idea:We get into the file dire`ctory and then use a -a for ls, inorder to see all the files.

  Commands used:
  ls
  cd inhere
  ls -a -To show all the files in the directory
  cat "hidden file name"

  Password retrieved successfully.

-->Level 4
  Pass in human-readable file only in inhere directory

  Idea:We check the file type, and if the type is ASCII text, then it is human readable file.

  Commands used:
  cd inhere
  ls
  file ./* -To check file types

  Password retrieved successfully.

-->Level 5
  To find a file with the conditions:
  Human readable
  size=1033B
  not executable

  Idea:We use a special command for this, in the command we specify the file requirements needed.

  Commands used:
  find . -type f -size 1033c ! -executable

  Here, f refers to human readable, c refers to bytes.

  Password retrieved successfully.
