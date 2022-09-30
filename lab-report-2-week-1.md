# Lab Report 2 Week 1

## Step 1: Installing VScode
* Go to the Visual Studio Code website: [Link](https://code.visualstudio.com/)
* following the instruction

* open a window look like this:

![](InstallingVScode.png)

---

## Step 2: Remotely Connecting
* open a terminal in VSCode and type the following command:
`ssh siw031@ieng6.ucsd.edu` and enter the password

* then can see the following messages:

![](RemoteConnect.png)
That means you're successfully logged in to the remote server!

---

## Step 3: Trying Some Commands
* Try `cd`, `ls -a`, `cd ~`, `ls -lat`, `ls <directory>`, `cp /home/linux/ieng6/cs15lfa22/public/hello.txt ~/`, `cat /home/linux/ieng6/cs15lfa22/public/hello.txt`and etc.

* After that, you can see like this:

![](TrySomeCommands.png)
* Run the command `exit` to log out the remote server.

---

## Step 4: Moving Files with scp
* Create a java file named `WhereAmI.java` and copy and paste the following code:

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


* Run the commands below:

```
javac WhereAmI.java
java WhereAmI
```

* Run this command:`scp WhereAmI.java siw031@ieng6.ucsd.edu:~/`
* Log with ssh and run `javac WhereAmI.java` and `java WhereAmI` on the remote server

Then you can see something like this:

![](MoveFileswithScp.png)

---

## Step 5: Setting an SSH Key
* On client, run this command:`ssh-keygen` and following the commands on the following screenshot:

![](SSHkeys.png)

* Then you can log into the remote server without entering password.

---

## Step 6: Optimizing Remote Running
* We can use "" to write a command at the end of `ssh` command to directly run it, for example:

```
ssh siw031@ieng6.ucsd.edu "ls"
```

* We can apply semicolons to run multiple commands, for example:

```
cp WhereAmI.java OtherMain.java; javac OtherMain.java; java WhereAmI
```
* We can use up-arrow to recall commands

Smiliar to the following image:

![](OptimizingRemoteRunning.png)
