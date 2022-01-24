**This is a tutorial about how to log into a course-specific account on ieng6.**


# Preparation:
1. Look up accounts and reset the password with the link https://sdacs.ucsd.edu/~icc/index.php
2. Install Visual Studio Code with the link https://code.visualstudio.com/

After we get ready, then we can open the VSCode. The window should look like this:
![Image](https://github.com/YGnina/cse15l-lab-reports/blob/main/pictures/vscode.png)

# Remotely Connecting
To connect the remote server, we will use the command as below but replace it to your own account name
``` 
$ ssh cs15lwi22zz@ieng6.ucsd.edu
```

For people who first try remote connecting, they might see
  
  ```
  ⤇ ssh cs15lwi22zz@ieng6.ucsd.edu
  The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
  RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
  Are you sure you want to continue connecting (yes/no/[fingerprint])? 
  ```
  
Just enter "yes" in this case and enter the password when they ask to.
The result you got would be like this once you sucessfully log in:

![Image](https://github.com/YGnina/cse15l-lab-reports/blob/main/pictures/code1.jpg)

# Run Some Commands
Ok, now our terminal is connected to a computer in the CSE basement.
We typically call our computer the client and the computer in the basement the server.

Let's try something basic commands, such as:
``` 
$ cd ~                  //change to home directory
$ cd                    //take to home directory
$ ls -lat               //list all files with latest first
$ ls -a                 //list all files and directoies including hidden ones
```
You should get the result as below:
![Image](https://github.com/YGnina/cse15l-lab-reports/blob/main/pictures/other.jpg)


Let's do more research on some useful commands.
## Moving Files over SSH with scp
- `scp` to move files

  In order to use this command, first we need to create a file. Let's say we create a WhereAmI.java on our computer, then we want to move this file to our remote     computer and run it on the server, like this:
  ![Image](https://github.com/YGnina/cse15l-lab-reports/blob/main/pictures/scp.jpg)

##  SSH Keys
- `ssh` Key to avoid putting password repeatly

  As we can see from running `scp` above, we need to type our password frequently. Sometimes we even put the password wrong and need to retry it, which is annoying. So we need a shortcut, like `ssh` keys. We just need to do it by useing codes:
  
  
  
```  # on client (your computer)
$ ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/joe/.ssh/id_rsa): /Users/joe/.ssh/id_rsa
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /Users/joe/.ssh/id_rsa.
Your public key has been saved in /Users/joe/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:jZaZH6fI8E2I1D35hnvGeBePQ4ELOf2Ge+G0XknoXp0 joe@Joes-Mac-mini.local
The key's randomart image is:
+---[RSA 3072]----+
|                 |
|       . . + .   |
|      . . B o .  |
|     . . B * +.. |
|      o S = *.B. |
|       = = O.*.*+|
|        + * *.BE+|
|           +.+.o |
|             ..  |
+----[SHA256]-----+ 
```
  and that's what it looks like on my terminal:
  
  ![Image](https://github.com/YGnina/cse15l-lab-reports/blob/main/pictures/ssh.jpg)
  
# Making Remote Running Even More Pleasant
Okay, now let's try to optimize remote running, like 

write commands that we want to directly run on the remote server in quotes with `ssh` in the beginning: 
``` 
$ ssh cs15lwi22@ieng6.ucsd.edu "ls"
```
or use semicolons to seperate commands and put it all in one line so that we can run them at the same time:
```
$ cp WhereAmI.java OtherMain.java; javac OtherMain.java; java WhereAmI
``` 

Both these two tricks can save our time and make coding more efficient.

The result would be as below:


 ![Image](https://github.com/YGnina/cse15l-lab-reports/blob/main/pictures/part7.jpg)
 ![Image](https://github.com/YGnina/cse15l-lab-reports/blob/main/pictures/part7'.jpg)
 
