# How to login to your course-specific account!

## Step 1, VScode:
* Go to https://code.visualstudio.com/
* Follow the instructions to download VScode on your PC
* Once installed, open the software and you should see an Untitled page

![Step1Screenshot](VScodeImage.png)

## Step 2, Remotely Connecting
* Because I'm on a Mac, I'm able to use ssh without installing OpenSSH, windows users will need this however
* Press Ctrl + ` (tilde) in order to access the VScode terminal
* Type in `ssh cs15lfa22zz@ieng6.ucsd.edu`, but replace the zz with your unique account number

This is what it should look like after typing in the above command:
![Step2Screenshot](RemoteConnectImage.png)

## Step 3, Trying Commands
* In this step, you have some freedom to experiement with the commands you've learned about
* Try using the commands you learned from lecture like cd, ls, cat, and so on

You can try using some of the commands from the screenshot below:
![Step3Screenshot](TryingCommandsImage.png)

## Step 4, Moving Files Across Machines
* First, create a .java files and put it in a place that you know the file path to
* Then, run this scp command in the directory of your .java file, changing the appropriate parts as last time: `scp YourFile.java cs15lfa22zz@ieng6.ucsd.edu:~/`
* The file should now be on the ieng6 machine in the home directory, use the ssh command to login and see if it's there (using ls)!

![Step4Screenshot](SCPCommandImage.png)

## Step 5, Creating an SSH Key
* This step will show us how to avoid having to type our password everytime we want to login
* First run `ssh-keygen`, you should see a bunch of text afterwards, the system is generating the key pair
* When prompted, simply press enter to set the key to the default path
* Now type the following commands to copy the public key to the server account (adjust accordingly)
    1. `ssh cs15lfa22zz@ieng6.ucsd.edu` logs onto server
    2. `mkdir .ssh` creates directory on the server
    3. `scp /Users/yourname/.ssh/id_rsa.pub cs15lfa22@ieng6.ucsd.edu:~/.ssh/authorized_keys` copies the key, make sure to adjust the /Users/ directory to match your default path

![Step5Screenshot](SSHKeyImage.png)

## Step 6, Faster Remote Running
* This step will show us how to quickly edit a file, copy it to the server, and then run it
* First we need to edit the file, we can use `vi YourFile.java` to enter editing mode
* Once that is done, simply paste `scp YourFile.java cs15lfa22zz@ieng6.ucsd.edu:~/; ssh cs15lfa22@ieng6.ucsd.edu "javac WhereAmI.java; java WhereAmI"`