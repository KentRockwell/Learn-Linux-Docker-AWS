# Lesson 1

## Cloud9
Log into AWS Console.
Create a Cloud9 project ussing ssh login.
Log into new Cloud9 project.

## Learn basic vi
Learning the vi Editor, Sixth Edition
https://www.oreilly.com/library/view/learning-the-vi/1565924266/

Read first 3 chapters.  You need to know core basic vi commands:
1. Open/create a file
2. Save or quite a file
3. Navigate h, j, k, l
4. Yank a line (copy) yy, ayy
5. Delete a line dd
6. Paste a line p

```bash
vi [First Name-Last-Name]-lesson-1.txt
```
Press 'i' to go into insert mode.
Type your name and today's date.
Press enter key
Press 'o'
Type Lesson 1
Type a brief sentence describing your coffee.
Press enter
Type what you had for breakfast.
Use the h, j, k, and l keys to move through the file.
Yank the first breakfast line.
Place it after the name line.
Save file.

## Bash

Learning the bash Shell, 3rd Edition
https://www.oreilly.com/library/view/learning-the-bash/0596009658/

Read chapters 1 - 3

For each of the basic commands use the man command to see the man page (manual page).

You will need some files to work with, so lets create a few.

```bash
touch afile.txt bfile.txt cfile.text

cp [First Name-Last-Name]-lesson-1.txt  lesson-1a.txt
cp [First Name-Last-Name]-lesson-1.txt  lesson-1b.txt
cp [First Name-Last-Name]-lesson-1.txt  lesson-1c.txt
```

Learn what the options are for each command and try them out.

Use the files you just created for these commands.

ls	Lists a directory’s content
pwd	Shows the current working directory’s path
cd	Changes the working directory
mkdir	Creates a new directory
rm	Deletes a file
cp	Copies files and directories, including their content
mv	Moves or renames files and directories
touch	Creates a new empty file
file	Checks a file’s type
zip and unzip	Creates and extracts a ZIP archive
tar	Archives files without compression in a TAR format
cat	Lists, combines, and writes a file’s content as a standard output
grep	Searches a string within a file
tail	Prints a file’s last ten lines
tee	Prints command outputs in Terminal and a file
locate	Finds files in a system’s database
find	Outputs a file or folder’s location
sudo	Runs a command as a superuser
su	Runs programs in the current shell as another user
chmod	Modifies a file’s read, write, and execute permissions
chown	Changes a file, directory, or symbolic link’s ownership
useradd and userdel	Creates and removes a user account
df	Displays the system’s overall disk space usage
du	Checks a file or directory’s storage consumption
top	Displays running processes and the system’s resource usage
htop	Works like top but with an interactive user interface
ps	Creates a snapshot of all running processes
uname	Prints information about your machine’s kernel, name, and hardware
hostname	Shows your system’s hostname
time	Calculates commands’ execution time
kill	Terminates a running process
ping	Checks the system’s network connectivity
wget	Downloads files from a URL
curl	Transmits data between servers using URLs
history	Lists previously run commands
man	Shows a command’s manual
echo	Prints a message as a standard output
cal	Displays a calendar in Terminal

## Bash Enviornment
When you log into Cloud9, you are logged in as ec2-user, but you are not in your root home directory.

Type the following:

```bash
pwd
```

To to your home directory type

```bash
cd
```

In this case, your could have also typed

```bash
cd ..
```

Type the following command to see "hidden files"

```bash
ls -la
```

You should see your bash files .bashrc .bash_profile and so on.

Make a backup of each of these files. For example.

```bash
cp .bashrc .bashrc_[DD-MM-YYYY]
```

Follow the instructions in the Learning the bash Shell book for customizing your environment.

