# simple-shell
1. Summary
You have to implement a SimpleShell that waits for user input, executes commands provided in the user
input, and then repeats until terminated using ctrl-c. The pseudocode for the Shell was discussed in the
Lecture 06 and Lecture 07 slides. This assignment will teach you how to use different system calls. You don’t
have to implement the individual Unix commands that will execute on your SimpleShell.
2. SimpleShell Implementation (“simple-shell.c”)
We are not providing any starter code for this assignment, but a detailed description is provided herewith for
your implementation:
a. The main job of any shell (including SimpleShell) is to read the user command from the standard input,
parse the command string (command and its arguments if any), and execute the command along with
the command line arguments provided by the user. All these three steps should be carried out in an
infinite do-while loop as shown in the Lecture 06 slides.
b. The shell must display a command prompt (of your choice) where user can provide the command as
mentioned above.

c. The user command has certain restrictions to simplify your implementation. The user command is not
supposed to include backslash or quotes. The command and its argument will simply be separated by a
whitespace as shown here:
echo you should be aware of the plagiarism policy
The above command should simply be printed by SimpleShell as:
you should be aware of the plagiarism policy

d. As shown in Lecture 06 slides, the command provided by the user will be executed by calling the
launch method that would create a child process to execute the command provided by the user. Feel
free to use any of the seven exec functions for executing the user command.
e. The commands (and the style) that should be supported by the SimpleShell as follows. As you
don’t have to actually implement the command (e.g., you don’t have to write the implementation of “ls” in
C), your SimpleShell should be able to execute more commands than the ones listed below (of course
not all the Unix commands). You should list some of the commands that will not be supported in your
design document along with a convincing reason behind it (e.g., the reason should not be stated as
some bug in your code).
ls
ls /home
echo you should be aware of the plagiarism policy
wc -l fib.c
wc -c fib.c
grep printf helloworld.c
ls -R
ls -l
./fib 40
./helloworld
sort fib.c
uniq file.txt
cat fib.c | wc -l
cat helloworld.c | grep print | wc -l
The “fib” and “helloworld” are the executables of a Fibonacci number calculator and hello world
programs respectively (c-code) that would be made available in the directory where your simple-shell.c
will reside. The file “file.txt” is some file that you can create with repetitive lines to test “uniq” command.
Note that you might have to know the location of the ELF file for the Unix commands. The “which”
command is helpful that would show you that the commands are stored inside the directory /usr/bin
f. The concepts and system calls discussed in Lecture 06 and 07 is required for the implementation of
your SimpleShell. It should also support pipes.
g. SimpleShell should also support history command that should only show the commands entered on
the SimpleShell command prompt (along with their command line arguments).
h. Terminating the SimpleShell should display additional details on the execution of each command, e.g.,
process pid, time at which the command was executed, total duration the command took for execution,
etc. You don’t need to display details of the commands executed in the past invocations of the
SimpleShell. Basically, display all the mentioned details only for the entries in the history.
