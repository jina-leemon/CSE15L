# [Lab Report 1: Setting Remote Environments](https://jina-leemon.github.io/cse15l-lab-reports/Lab_report_1.html)

*This is part of a series of UCSD's CSE 15L lab reports*

In this tutorial we will go over....

1. Installing VScode
2. Remote connection
3. Linux commands
4. Moving files from remote to local
5. Setting an **SSH** key

## 1. Install VScode

Download VScode [here](https://code.visualstudio.com)

After you download VScode and open it up, you should see an image like this:

![VScode starting page](https://jina-leemon.github.io/cse15l-lab-reports/Lab_report_1/VScode.png)

Feel free to download themes and languages you use on it.

## 2. Remote Connection

Next, we are going to connect to the UCSD account with out local devices.

Here's a graphic of how it works:

![How remote connection works](https://tableplus.com/assets/images/ssh-tunneling/ssh-works.png)

*Image from [TablePlus](https://tableplus.com/blog/2019/08/ssh-tunnel-secure-database-connection.html)*

Your adress would be:
cs15l + [quarter you're taking it] + [year you're taking it] + XXX (three alphabet) + @ieng6-202

For example, mine was **cs15lsp22XXX@ieng6-202**

**@ieng6-202** is the host name, and you should have your own account to connect to.

`ssh` is the command that allows you to connect to the remote server.

`ssh cs15lsp22XXX@ieng6-202`
allows you to connect to the cse15L account you have.

Enter the command and enter your password. If you successfully connect, you should see this screen:

![SSH](https://jina-leemon.github.io/cse15l-lab-reports/Lab_report_1/SSH-success.png)

## 3. Try Commands:

You can try UNIX commands to see the files in the remote environment.

`ls` commands show what files exist in the current directory.
<br>
`cd` allows you to move around directories
<br>
`cp` copies files (cp file-to-copy location-to-copy-to)
<br>
`mv` moves and renames files.
<br>
`mkdir` makes a new directory

Here are some other commands that you can try:

[Basic UNIX commands from Stanford](http://mally.stanford.edu/~sr/computing/basic-unix.html)

*Thank you Stanford!*

In my current environment, there are 2 directories and more hidden directories (that starts with a .).

![ls-a](https://jina-leemon.github.io/cse15l-lab-reports/Lab_report_1/ls_command.png)


## 4. Moving Files From Remote to Local

Now we will use `scp` to move files from the local to remote.

The command is the following:

`scp <filename> <account address :~/>`

Then you will have to enter a password and the file will be cloned to the remote desktop.

The following example is copying the file WhereAmI.java to the remote server.

![scp](https://jina-leemon.github.io/cse15l-lab-reports/Lab_report_1/scp-success.png)

It lets you see the progress of the file being copied.

## 5. Setting an **SSH** key

Entering the password every time can be a hassle.

To solve this, we are going to generate a key.

The command `ssh-keygen` creates two keys, a **public key** that gets stored in the server and a **private key** that you store locally.

If you're interested in public and private keys, here is a graphic that shows how it works:

![public and private keys](https://sectigo.com/uploads/images/Sectigo-Quantum-Lab-Diagram.png)

*Image from [SECTIGO's website](https://sectigo.com/resource-library/public-key-vs-private-key)*

Make sure to not enter a passphrase (you will have to enter it every time if you do)

When you've created a successful key, you will see something like this:

![ssh-keygen](https://jina-leemon.github.io/cse15l-lab-reports/Lab_report_1/SSH-keygen.png)

Then move this ssh key to the remote server.

`scp /Users/<user-name>/.ssh/id_rsa.pub cs15lsp22zz@ieng6.ucsd.edu:~/.ssh/authorized_keys`

After this, you can enter the remote desktop without entering your password!

![after-keygen](https://jina-leemon.github.io/cse15l-lab-reports/Lab_report_1/after-keygen.png)

## Additional tricks while using ssh

When using the ssh comand, you can add a command to run in the remote desktop in ""

`ssh cs151sp22XXX@ieng6.ucsd.edu "<command here>"`

For example, 
`ssh cs151sp22XXX@ieng6.ucsd.edu "ls -lat"`
<br>
would give you the same output as connecting through ssh and then entering ls -lat.

You can also enter multiple commands seperating them by ;

For example, 
`cd Lab1; ls -lat`
will enter the Lab1 folder and run ls -lat there.

You could combine the two features like this:

`ssh cs151sp22XXX@ieng6.ucsd.edu "cd Lab1; javac WhereAmI.java; java WhereAmI"`

---
<br>
<br>
Thanks for reading this tutorial!
<br>
Happy coding everyone