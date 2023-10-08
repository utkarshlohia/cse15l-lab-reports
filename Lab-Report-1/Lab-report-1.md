# Lab Report 1

## Using commands with no arguments

![No Arguments](https://github.com/utkarshlohia/cse15l-lab-reports/blob/main/Lab-Report-1/No%20Argument.png)

In the first line in the above screenshot, I ran the `cd` command without any arguments, while in the home directory, which did not change anything since the default directory to which cd takes us is the /home directory. This output is not an error.

The working directory was the home directory when I run the `ls` command. There was only one directory in the repository I cloned, which can be seen as the output of the `ls` command. Since the lecture1 directory is the only directory present in the repository, the output is not an error.

The working directory was the home directory when I run the `cat` command. Since I did not provide `cat` with any arguments, it did not print anything. This output is not an error, but there is no meaningful output since an input was not provided.

## Using a directory as an argument

![Directory as Argument](https://github.com/utkarshlohia/cse15l-lab-reports/blob/main/Lab-Report-1/Directory%20as%20Argument.png)

In the first line, I run the command `ls lecture1` while in the home directory. The argument provided is a directory present in the cloned repository. The output lists all the files and directories present in the directory `lecture1`. This is not an error.

In the next line of code, I run the command `cd lecture1` while in the home directory. This changes the working directory to the directory `lecture1`.

I run the command `cd` again to revert back to the home directory to run the last command.

I run the command `cat lecture1`, which gives me an error since `lecture1` is a directory and `cat` prints the arguments provided to it. `lecture1` cannot be printed since it is a directory which contains many files and directories.

## Using a file as an argument

![File as Argument](https://github.com/utkarshlohia/cse15l-lab-reports/blob/main/Lab-Report-1/File%20as%20Argument.png)

In the first line, I run the command `ls lecture1/messages/en-us.txt` with the home directory as the working directory. The path provided is of the file `en-us.txt`, contained in the `messages` directory. The output is the same as the path we gave to the `ls` command. This is an error since the file `en-us.txt` does not contain any files or directories that can be listed.

In the next line of code, I run the command `cd lecture1/messages/en-us.txt` with the home directory as the working directory. The output is an error since the `cd` command changes the working directory to a different directory, and it does not work with the path to a file.

In the nect line of code, I run the command `cat lecture1/messages/en-us.txt` with the home directory as the working directory. The output is "Hello World!", which are the contents of the file `en-us.txt`. The command `cat` prints out the contents of the file whose path is provided, so this output is not an error.






