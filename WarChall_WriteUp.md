#   WARCHALL 
The challenges are in [wechall.com](https://www.wechall.net/challenge/warchall/begins/index.php)
```command :
> [ Here are the command needed ] :

cd : change directory.
ls : see all the files in a directory (add -al to see all the hidden files.)
touch : create a file.
nano : Edit a file.
cat : Look at the content of a file.
```
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

## Warchall level 10 [ Choose your path I ] : 
- Step 1 : Go to `/home/level/10_choose_your_path`.
>There are 04 files in this directory but here we're interested in **charp.c** (the C code file), **charp** the compiled executable version of **charp.c** and ***solution.txt*** .

>The key of this level is to achieve of making `charp` output an exit failure. 
- Step 2 : Create a file in your user directory by doing this command `touch /home/user/Username/yourFile`.
- Step 3 : Now, you have to write this command line `./charp "radomWords; cat solution.txt >  /home/user/Username/yourFile`.
 
 Here is what this command line does :

     - first argument [randomwors] : just put a random word in there, this first argument is needed to achieve the condition of making an EXIT_FAILURE.
     - Second argument [solution.txt>~/YourFile] : this argument send the content of solution.txt to the file you created in Step 2 after the exit_failure.
- Step 4 : Go into `~` and open the file you created (in my case it was 10.txt), the password is inside.


## Warchall level 11 [ choose your path II ] :
> - this level is pretty much the same as the precedent one, but the condition of the exit_failure are not the same.
       
> - this one is pretty tricky.


- Step 1 : Go into `/home/level/11_choose_your_path2`
- Step 2 : First, create a symbolic link `ln -s /bin/sh ~/wc`.
This create a link from my personnal directory to the directory where the bash command are located.
- Step 3 : Redirect the default environnement variable to `~` by doing `PATH=~`.
- Step 4 : Execute `./charp2` with the following argument `'/bin/cat/ solution.txt 1>&2'` and the solution will appear.

```
Note :
    - We redirected the variable environnement to make the system look for wc into ~/wc when executing ./charp2
    - /bin/cat is the same as using cat.
    - 1>&2 make it do an error output instead of an standart one.

```



## Warchall level 12 [ Py-Tong ] :
- Step 1 : You have to go to `/home/user/Username/`.
- Step 2 : This level consist of altering a file of our choice. So create two (02) files in this directory.
- Step 3 : In my case i name the first file `sriptContent` who contain a script that indefinitly add "Hi little hacker" to the second file named `12` who's empty.
- Step 4 : Exectute the file `scriptContent` by doing `./scriptContent`.
- Step 5 : Open a new terminal or use putty and log into the server (Don't close the first terminal. You can't use it due to script.) and go to `/home/level/12_pytong/`.
- Step 6 : execute the file `pytong` with the absolute path to the altered file as argument. And a message with the password to validate this level will appear.

## Warchall level 14 [ Live LFI ]
> this level consist of making a directory transversal.

- Step 1 : Go into [Warchall LFI](https://www.wechall.net/challenge/warchall/live_lfi/index.php), and click on the link `Live LFI`.
- Step 2 : Click on one the flag on the page (you will notice in the url that this page is a php one).
The URL will go from : **https://lfi.warchall.net/**
to **https://lfi.warchall.net/index.php?lang=en**
- Step 3 : Replace ***en*** with ***php***.
The url should look like this now `https://lfi.warchall.net/index.php?lang=php`

- Step 4 : Add `://filter/convert.base64-encode/resource=solution.php` at the end of the url and Refresh the page. 
A long ASCII sequence will appear.

>This long sequence is actually the content of solution.php that had been encoded with base64.
```
Note : 
    - php://filter/ is used to initiate convert.base64-encode
    - convert.base64-encode, is encoding solution.php. It make it safer and prevents the security of the browser to interfer with it. (and also make us do more work.)
```

- Step 5 : To get the password, Decode the encrypted sequence using base64 translator online (the easy way) or by using this command line :
```
echo " -encoded sequence" | base64 -d -i

=> the parameter [-d] stand for decode, and [-i] to make it ignore non-alphabet characters.
``` 

## Warchall level 15 [ live RFI ]
> This one is just slightly different from the precedent level. 

- Step 1 : Go into [Warchall RFI](https://www.wechall.net/challenge/warchall/live_rfi/index.php), and click on the link `Live LFI`.
- Step 2 : Click on one the image icon that has `EN` or `DE` next to it.
The URL will go from : **https://lfi.warchall.net/**
to **https://lfi.warchall.net/index.php?lang=en**
- Step 3 : Replace ***en*** or ***de*** with ***php*** at the end of the url next to ***language***.

- Step 4 : Add `://filter/convert.base64-encode/resource=solution.php` at the end of the url and Refresh the page. 
The ASCII sequence will appear at the top of the page, above ***Warning***.

>This long sequence is still the content of solution.php that had been encoded with base64.

```
Note : 
    - php://filter/ is used to initiate convert.base64-encode
    - convert.base64-encode, is encoding solution.php. It make it safer and prevents the security of the browser to interfer with it. (and also make us do more work.)
```

- Step 5 : To get the password, Decode the encrypted sequence using base64 translator online (the easy way) or by using this command line :
```
echo " -ASCII sequence" | base64 -d -i

=> the parameter [-d] stand for decode, and [-i] to make it ignore non-alphabet characters.
``` 
