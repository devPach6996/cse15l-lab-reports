# How to log into a course-specific account on `ieng6`

## Step 1: Your CSE15L account
  Please click on the link below
  * https://sdacs.ucsd.edu/~icc/index.php
  * If you need help, please follow this tutorial. [[TUTORIAL] How to Reset your Password](https://docs.google.com/document/d/1hs7CyQeh-MdUfM9uv99i8tqfneos6Y8bDU0uhn1wqho/edit)
## Step 2: Installing VS code
  Please follow this [link](https://code.visualstudio.com/) to download VScode apporpriate for your Operating System.
  * You should see a picture like this below:
    ![VScodeStart](https://user-images.githubusercontent.com/122571122/212420079-e26722fa-de64-49cb-9de8-86e154e0704d.png)
## Step 3: Connecting Remotely
  1. You need to install Git for Windows
     Follow this [Link for installing Git](https://gitforwindows.org/)
  2. Now you need to set your default terminal to use the git bash in Visual Studio Code
     Follow this [Tutorial for using GitBash for VSCODE](https://stackoverflow.com/a/50527994)
  3. Now Using Ctrl/Command + \` Or Terminal --> New Terminal from the taskbar, open a new Terminal Window
  4. Type `ssh cs15lwi23aa@ieng6.ucsd.edu` on your terminal. Instead of `aa`, you should use your CSE 15L account.
  5. If everything worked fine, it should ask you if you will want to continue connecting. You should say `yes`.
  6. Then, you should enter your password. **Be Careful: Even if you press key on the keyboard, it may not show it typed the password on the terminal. But, it DOES type the password.**
  7. After you have typed the password correctly, It should show something like this:
      ![image](https://user-images.githubusercontent.com/122571122/212422517-890edc73-f7c6-495e-ac54-c11b5e3043a4.png)
  ### Hooray! You have successfully connected your computer to the remote Computer. Well Done!
  * `cd ~`
     Takes you to the home directory.  
  * `cd`
     Changes the directory from the present direcotory to the directory mentioned after `cd`
  * `ls`
     displays all the file present in the direcotory 
  * `ls -lat`
     Displays all the file including the hidden files with their name, time created, and size.
  * `ls -a`
      Displays all the file including the hidden files with their name
  * `cp`
      Copies one file into another
  * `cat`
      Displays the content in the given file
  * `pwd`
      print the current directory you are working in.    
  ## Here is the screenshot of some commands that you can try
  ![image](https://user-images.githubusercontent.com/122571122/212558689-c82022c4-b948-4188-94b5-ca18184aab6a.png)
  ![image](https://user-images.githubusercontent.com/122571122/212558766-02103885-2b25-48c5-90a1-9d8ae8608511.png)
  ![image](https://user-images.githubusercontent.com/122571122/212558855-c4ddda6c-9faa-464f-855f-c4c55352234c.png)


  

 
    
