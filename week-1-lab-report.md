# Hello, Incoming CSE 15L Students and Myself!
## I am going to do my best to show you how to setup **Remote Access**

***
1. First, you are going to want to install Visual Studio Code by going [here](https://code.visualstudio.com/), and clicking
   download for your Operating System.
   
2. After installing, we are going to try to remotely connect to a server at UCSD.  If you are on Windows you will need to 
   install the program *OpenSSH* [here](https://learn.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse?tabs=gui). This will allow you to connect to other systems that use this type of account.
   
   Now you can either use the terminal built in to your computer or you can use Visual Studio Code. I personally opted to use the
   built in terminal. If you are using VSCode press *Ctrl* or *Command +*. Now input the command `ssh cs15lfa22zz@ieng6.ucsd.edu` but 
   replace the `zz` with the letters in your course-specific account.
   Input your password and connect to the server! It should look something like this: 
   
3. Now try using some commands! Some of the basic commands are `cd`, `ls`, `pwd`, `mkdir`, and `cp`. After using some commands 
   you can log out of the remote server by using *Ctrl-D* or use the command `exit`.

4. Now we are going totry to copy files from our local system to the server. The command to do this is `scp`, and this command is onyl run from the local 
   system not the server. We are going to create a file called `WhereAmI.java` on our local system and in that file include the code:
   ...
   class WhereAmI {
   public static void main(String[] args) {
      System.out.println(System.getProperty("os.name"));
      System.out.println(System.getProperty("user.name"));
      System.out.println(System.getProperty("user.home"));
      System.out.println(System.getProperty("user.dir"));
    }
   }
   ...
   
   If you have Java installed on your computer then compile and run `WhereAmI.java` using `javac` and `java` in your terminal like this:
   ...
   javac WhereAmI.java
   java WhereAmI
   ...
   
   Now that you have a file lets try copying it to the server. In your terminal make sure you are in the directory where your java file is located 
   and type in: `scp WhereAmI.java cs15lfa22zz@ieng6.ucsd.edu:~/`
   Enter the same password you used to login to `ssh`.
   
   Then log in to the server using `ssh` and use the command `ls` to see the file in your home directory.
   Now you can use the `javac` and `java` commands because java is installed on the server.
   
5. Now that we know how to log in, copy files, and run commands, it can get annoying to type in your password everytime you want to log in or copy a file.
   To fix this we can use `ssh` keys. By using `ssh-keygen` we can create two keys, one stays on the server and the other stays on your local system. `ssh` 
   will now use these keys instead of having to type in a password everytime.
   
   To make these keys you want to run `ssh-keygen` in your local system's terminal. Follow the instructions that the terminal shows.
   
   Now to copy the one of the keys to the server run `ssh cs15lfa22zz@ieng6.ucsd.edu` on your local system. Enter your password, and on the server
   enter `mkdir .ssh` and logout of the server.
   
   Now on your local system enter:
   `scp /Users/keyan/.ssh/id_rsa.pub cs15lfa22zz@ieng6.ucsd.edu:~/.ssh/authorized_keys` with your account and username.
   
   Now you should be able to `ssh` and `scp` without having to type in your password which can save a lot of time especially if you are switching
   back and forth multiple times.
   
   
6. To help optimize remote running, I would suggest copying your `cs15lfa22zz@ineg6.ucsd.edu` when you are working on the server so you will not have to 
   enter that everytime and instead just use `Command-V`.
   Also, if you want to confirm that you copied a file to the remote server without having to log in and exit, you can type in
   `ssh cs15lfa22zz@ieng6.ucsd.edu "ls"`, the quotes wil automically run the command and logout for you.
   And my personal favorite thing to do when I am in terminal is to use the up-arrow to run previous commands or add to them.
   
   
