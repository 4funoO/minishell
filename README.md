# minishell
**Implementation of the shell written on c!**

**For deeper understanding the way our terminal is working...**

**Features:**
1. Displays a prompt when waiting for a new command.
2. Have a working history.
3. Search and launch the right executable.
4. Handles single (') and double (") quotes.
5. Standart redirections implemented, including heredoc.
6. Handling pipes.
7. Enviromental variables is handled as well(including $? for exit code).
8. Ctrl-C, Ctrl-D and Ctrl-\ is handled as well and reacts with the same behaviour as zsh/bash/etc.
9. Following built-ins was implemented: 
   a) echo with option -n, 
   b) cd with only a relative or absolute path
   c) pwd with no options
   d) export with no options
   e) unset with no options
   f) env with no options or arguments
   g) exit with no options
10. All exit status of last executed command is stored as per their exit status and can be accessed through $?.

**About the code:**
1. Divided on 4 parts:
   a) lexer + init          ->   describes all command given by user into logical tockens for execution. (commands/redirects/pipes/quotes and etc.)
   b) signal handler        ->   change the standart behaviour of signals. Was done through "termios.h" library.
   c) build-ins             ->   7 commands, that will work without env given.
   d) redirects + executor  ->   all redirections(reading from file/creating and output to the file) was handled here. 
                                 All the manipulations with forks for child and parents process along with changing
                                 standart inputs to the pipe and returning it back was handled here.

**How to run:**
1. Clone gip repositorie on your pc.
2. Open terminal in the minishell folder and run make. 
   (P.S. if you have error message of "rl_... command not found", 
    you need to install latest version of "readline.h" library and change the path in Makefile to your "readline.h" directory)
   <img width="544" alt="Screen Shot 2022-08-09 at 12 00 25 PM" src="https://user-images.githubusercontent.com/37631996/183621541-36549ed3-fb41-4f8a-9261-17f081c2106d.png">
3. Execute ./minishell
4. Try and have fun.

Here is some examples of commands handled by minishell
<img width="1710" alt="Screen Shot 2022-08-09 at 12 04 05 PM" src="https://user-images.githubusercontent.com/37631996/183622361-7c41b3b4-27d4-4a38-9c28-f9c171cb1a73.png">

Don't hesitate to contact me for any bug found :)

