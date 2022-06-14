# Basic UNIX commands
|          Command               |              Function                  
|--------------------------------|----------------------------------------
|`cd ..`                         | Go to upper directoy |
|`cd <directory>/`               | Go to directory |
|`touch <myfile>`                | Create myfile |           
|`mkdir <myfolder>`              | Create new folder |
|`rmdir <myfolder>`              | Remove folder (Work with empty folder) |
|`rm`                            | Remove file |
|`rm -r`                         | Remove folder with files |recursively
|`nano <myfile>`                 | Open myfile and write in it |
|`cat <myfile>`                  | Write out all content in myfile |
|`cat`                           | Read input until hit end of file (^D) -> Print input to screen |
|`cat > <myfile>`                | Write input into myfile |
|`cat >> <myfile>`               | Add more input to myfile |
|`cat <file1> <file2> > <myfile>`| Write content of 2 files into myfile |
|`sort`                          | Sort alphabetically or numerically |     
|`sort < <myfile>`               | Sort myfile content, output to screen |
|`sort < <file1> > <file2>`      | Sort file1 content, output to file2 |
|`nano ~/.bashrc`                | Open setting file |          
|`source ~/.bashrc`              | Force shell to read .bashrc |  
|`sudo <command>`                | Run command as admin |                   
|`sudo apt update`               | Update app |
|`tree`                          | List content of directory as a tree |   
|`man <command>`                 | Command description |
|`mv <file1>  <filen2/folder>`   | Move or rename file1 to file2 |
|`ls -l`                         |List all file in long listing format | 
|`ls -a`                         | List all file including hidden file |
|`cp <file1> <file2>`            | Copy file1 to file2 |    
|`less <filename>`               | Write the content of a file to the screen (type /<word> to find word in the file) |        
|`clear`                         | Clear screen (ctrl + L) |      
|`pwd`                           | Giver current folder path |
|`*`                             | Match with none or more characters (Eg: `rm *~`: Remove all file with ~) |
|`?`                             | Match with 1 character (Eg: `ls ?ouse`: Match with house, mouse,...) |          
|`head <myfile>`                 | Write myfile's first 10 lines to screen |
|`tail <myfile>`                 | Write myfile's last 10 lines to screen |
|`grep <word> myfile`            | Search for word in my file |
|`grep -i <word> myfile`         | Search and ignore upper/lower case |     
|`grep -i 'my phrase' myfile`    | Search for phrase my phrase in my file |
|`grep -n <word> myfile`         | Search and precede with line number |   
|`wc -w <myfile>`                | Print out number of words in my file |  
|`wc -l <myfile>`                | Print out number of lines in my file |  
|`<command1> \| <command2> \| ...`| Transfer output of command1 to command2 and execute and so on |                                            
|`who`                           | People who are on the same as you |     
|`apropos` <keyword>             | Give the name of command with keyword | 
|`chmod o-rw myfile`             | Change access right (Intro to UNIX) |
|`ps`                            | See information about a process |        
|`sleep <n>`                     | Wait for n seconds before continuing |  
|`<command> &`                   | Run command on the background |        
|ctrl + z                        | Suspend a running process |             
|`bg`                            | Put a suspended process into background |
|`jobs`                          | Show suspended, backgrounded job list |
|`fg <job number>`               | Restart a suspended job |        
|ctrl + c                        | Kill a process running in foreground |
|`kill <job number/PID>`         | Kill a process running in background | 
|`quota -v`                      | Check how much space is used on filesystem |
|`df .`                          | Check how much space is left on fileserver |
|`du -s *`                       | Output total number of kb for each subdirectory |
|`gzip <myfile>`                 | Reduce file size |   
|`gunzip <myfile>`               | Expand file |
|`zcat <myfile>`                 | Output gzipped file w/o uncompressing |
|`diff <file1> <file2>`          | Compare 2 files, output the differences |
|`find`                          | Find a file or directory (read manual) |
|`history`                       | Show command history |
|`set history=100`               | Set the history buffer size to 100 |
|`!gcc`                          | Recall last command with gcc |
|`!n`                            | Recall command number n |
|`file <myfile>`                 | Get information on myfile |
|`setenv`                        | Set the value to an environment variable |
|`untsetenv`                     | Unset the value to an environment variable |
|`env`                           | Print the value of all the environment variable |
|`set`                           | Set or display the value of shell variable |