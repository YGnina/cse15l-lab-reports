**This is a tutorial about how to log into a course-specific account on ieng6.**


Preparation:
1. Look up accounts and reset the password with the link https://sdacs.ucsd.edu/~icc/index.php
2. Install Visual Studio Code

After we get ready, then we can open the VSCode. The window should look like this:
![Image](https://github.com/YGnina/cse15l-lab-reports/blob/main/pictures/vscode.png)


To connect the remote server, we will use the command as below but replace it to your own account name
``` 
$ ssh cs15lwi22zz@ieng6.ucsd.edu
```
and the result you got would be like this:

![Image](https://github.com/YGnina/cse15l-lab-reports/blob/main/pictures/code1.jpg)

Ok, now our terminal is connected to a computer in the CSE basement, and we can use that one to run any commands
Let's try some commands, such as:
``` 
$ cd ~                  //change to home directory
$ cd                    //take to home directory
$ ls -lat               //list all files with latest first
$ ls -a                 //list all files and directoies including hidden ones
```
You should get the result as below:
![Image](https://github.com/YGnina/cse15l-lab-reports/blob/main/pictures/other.jpg)


Let's do more research on some useful commands.

- `scp` to move files

  In order to use this command, first we need to create a file. Let's say we create a WhereAmI.java on our computer, then we want to move this file to our remote     computer and run it on the server, like this:
  ![Image](https://github.com/YGnina/cse15l-lab-reports/blob/main/pictures/scp.jpg)


- `ssh` Key to avoid putting password repeatly

  As we can see from running `scp` above, we need to type our password frequently. Sometimes we even put the password wrong and need to retry it, which is annoying. So we need a shortcut, like `ssh` keys. We just need to do it as below:
  ![Image](https://github.com/YGnina/cse15l-lab-reports/blob/main/pictures/ssh.jpg)
  
Okay, now let's try to optimize remote running, like write a command in quotes  to directly run it on the remote server, or use semicolons to run multiple commands on the same line
``` 
$ ssh cs15lwi22@ieng6.ucsd.edu "ls"
$ cp WhereAmI.java OtherMain.java; javac OtherMain.java; java WhereAmI
``` 

 ![Image](https://github.com/YGnina/cse15l-lab-reports/blob/main/pictures/part7.jpg)
 ![Image](https://github.com/YGnina/cse15l-lab-reports/blob/main/pictures/part7'.jpg)
 
