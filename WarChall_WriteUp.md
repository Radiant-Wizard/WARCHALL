#   WARCHALL 
The challenges are in [wechall.com](https://www.wechall.net/challenge/warchall/begins/index.php)
##   Chapter I Warchall begins 
> There are 6 flags to get.
### First flag [ level 00 ] 
- Step 1 : Create an ssh account on log into the server with the password typed into the form.
- Step 2 : Inside the server, use the command ` ls ` to see the contents of the directory your are located.
- Step 3 : The password is in the file "WELCOME.md".

### Second flag [ level 01 ]
- Step 1 : Go into `/home/level` using the command `cd` .
- Step 2 : Use the command `ls ` and you will see the list of the files and directory in this location.
- Step 3 : Go into `/01_choice_tree`
- Step 4 : You do not need to look at the content of README.md, go into `/home/level/01_choice_tree/blue/hats/grey/solution/patience` the flag is in the file `SOLUTION.txt`.
  
### Third flag [ level 02 ]
- Step 1 : Return into `/home/level` and go into `/02`.
- Step 2 : Use the command line `ls -al` to see the hidden content.
- Step 3 : Go into `/.porb`, the password to get this flag is in `.solution`. This file is hidden so you need to use `ls -al` to see it.

### Fourth flag [ level 03 ]
- Step 1 : Return into `/home/level` and go into `/03`.
- Step 2 : All the contents in /03 are hidden so use `ls -al` to see them.
- Step 3 : The password to get this flag is in `.bash_history`. Use the command  `cat` to look inside that file. 

### Fifth flag [ level 04 ]
- Step 1 : Go into `/home/user/YourUsername/level/04_kwisatz`.
- Step 2 : There are two files `README.txt` and `README2.md` .
- Step 3 : The password is in `README2.md`, use the command `chmod ugo+rwx YourUsername` to get the access to that file.

### Sixth Flag [ level 05 ]
- Step 1 : Go into `home/level/05_privacy/`.
- Step 2 : The solution is in the file [README.md].



## Warchall level 12 [ Py-Tong ] :
- Step 1 : You have to go to `/home/user/Username/`.
- Step 2 : This level consist of altering a file of our choice. So create two (02) files in this directory.
- Step 3 : In my case i name the first file `sriptContent` who contain a script that indefinitly add "Hi little hacker" to the second file named `12` who's empty.
- Step 4 : Exectute the file `scriptContent` by doing `./scriptContent`.
- Step 5 : Open a new terminal or use putty and log into the server (Don't close the first terminal. You can't use it due to script.) and go to `/home/level/12_pytong/`.
- Step 6 : execute the file `pytong` with the absolute path to the altered file as argument. And a message with the password to validate this level will appear.