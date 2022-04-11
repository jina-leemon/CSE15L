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

![VScode starting page](https://jina_leemon.github.io/cse15l-lab-reports/Lab_report_1/VScode.png)

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

![SSH](https://jina_leemon.github.io/cse15l-lab-reports/Lab_report_1/SSH-success.png)

