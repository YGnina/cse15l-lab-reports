# Streamlining ssh Configuration

## Show my .ssh/config file
First we change the directory to `.ssh`.
Since I don't have config file, I create it before I use `~/.ssh/config` to tells SSH what username to use when logging into specific servers.
Code as below:

![Image](/pictures/lab3pic1.jpg)

We can change the nickname as nina for example:

![Image](/pictures/lab3pic5.jpg)

But because I still prefer to use `ieng6`, I change it back.

![Image](/pictures/lab3pic3.jpg)

## Show the ssh command logging 
Now the username is still `ieng6` and we want to log into the server, we need to use 
```
ssh ieng6
```
![Image](/pictures/lab3pic2.jpg)

## Show an scp command copying a file

As we know we have a WhereAmI.java file on Desktop, so we just use `scp` to copy the file to the server.
Code as below:

![Image](/pictures/lab3pic4.jpg)
