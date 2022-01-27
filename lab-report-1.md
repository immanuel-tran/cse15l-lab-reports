Lab Report 1 - Week 2
=====================

1: Installing VScode
-----------------
> ![Image](lab1/install.png)
- Go to  [Visual Studio Code's website ](https://code.visualstudio.com)
- Follow instructions to download and install to your computer

2: Remotely Connecting
-------------------
> ![Image](lab1/remoteconnect.png)
- First, [Install OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse)
- Then, using your own CSE15L account and Visual Studio, use the ssh command in the terminal 
    - Example: 
    `ssh cs15lwi22XXX@ieng6.ucsd.edu`
- Say yes to connect and then type your password (nothing will show up because password is hidden)
    - Note: You can logout anytime with __Ctrl + D__ or running the command `exit`


3: Trying Some Commands
--------------------
> ![Image](lab1/commands.PNG)
- You can try some basic commands
    - `cd specifiedDirectory` - Take you to the specified directory
    - `cd ..` - Takes you to the parent directory
    - `ls` - List the files in the current directory 
    - `pwd` - Prints out the pathname of the current directory
    - `mkdir specifiedName`- makes a new subdirectory with the specified name in the current directory 
    - `cp file1 file2` - copies contents of file1 to file2

4: Moving Files with scp
---------------------
> ![Image](lab1/moving1.png)
> ![Image](lab1/moving2.png)
 - Logout of if you are still logged in
 - Create a java file on your computer called WhereAmI.java with the following content: 
```
class WhereAmI {
  public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}
```
- Run `scp WhereAmI.java cs15lwi22zz@ieng6.ucsd.edu:~/ ` from terminal while in the directory you made the file
- It should ask for a password, type it in then your file should be sucessfully transfered


5: Setting an SSH Key
------------------
>![Image](lab1/key1.png)
>![Image](lab1/key2.png)
- Use the command `ssh-keygen` 
    - If on windows follow instructions  [here](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement#user-key-generation)
- This creates a pair of files (a public key file called __id_rsa__ and a private key file called __id_rsa.pub__ in your .ssh directory)
- Login to account agian with ssh command then run the command  `mkdir .ssh`. Then you shold be able to `ssh` or `scp` without having to input a password


6: Optimizing Remote Running
-------------------------
>![Image](lab1/op.png)
- You can directly run commands directly on the remote sever by adding the it in quotes after the `ssh` command
- Additionally you can write multiple commands in one line by seperating them with semicolons

>![Image](lab1/movingOptimized.png)

- Using the information above, after setting up and ssh key and making changes to a local file (or mulitple local files), you should be able to copy it to the remote sever and run it all at once
- It will not require you to enter a password