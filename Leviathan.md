#TASK 0 

  - I used the SSH command provided in the discord. `ssh -p 2223 leviathan0@leviathan.labs.overthewire.org`
  - Later it after saying yes it prompted for a password and the password was mentioned in the leviathan site. `leviathan0`
  - I finally entered and did `ls`. Nothoin showed up and did ls again but there was nothing.
  - Then I `la` and found a hidden directory `.backup`
  - The directory has a html file. `bookmarks.html`
  - Used `cat` to view the contents of the file. It was too big. I couldn't find a password.
  - After some google search I found we could use `grep`. `grep password bookmarks.html`
  - The password is `PPIfmI1qsA`
  - `exit

#TASK 1
  - ssh into the level 1 using `ssh -p 2223 leviathan1@leviathan.labs.overthewire.org`
  - `ls -lah` and setuid file was found `check`
  - tried cat check but it was all encrypted
  - Tried `ls -lah` : `-r-sr-x---  1 leviathan2 leviathan1  15K Oct  5 06:19 check`
  - Used `ltrace` command which helps in debbuging. It propmted for password.
  - I pressed enter thrice in a row and it later outputed leviathan1@gibson:~$ ltrace ./check
```
__libc_start_main(0x80491e6, 1, 0xffffd5f4, 0 <unfinished ...>
          printf("password: ")                                                     = 10
getchar(0xf7fbe4a0, 0xf7fd6f90, 0x786573, 0x646f67password: 
)                      = 10
getchar(0xf7fbe4a0, 0xf7fd6f0a, 0x786573, 0x646f67
)                      = 10
getchar(0xf7fbe4a0, 0xf7fd0a0a, 0x786573, 0x646f67
)                      = 10
strcmp("\n\n\n", "sex")
```
  - Then `man strcmp` found out that it compares tw strings
  - So, the command was comparing the password I typed to the main password `sex`
  - To verify `./check`
  - typed in `sex` and it's right.
  - `ls` check file was found and it's encrypted.
  - Tried `sex` as the password for next task but it's not the passsword
  - In the main page of leviathan it says use `/etc/leviathan_pass/`
  - `cat /etc/leviathan_pass/leviathan2
  - password : `mEh5PNl10e`
  - `exit`

#TASK 2 (very hard)
  - `ssh -p 2223 leviathan2@leviathan.labs.overthewire.org`
  - `ls -lah` to see the file found another setuid file `printfile`
  - `ltrace ./printfile` to see if it has anything. It outputted
```
leviathan2@gibson:~$ ltrace ./printfile 
__libc_start_main(0x80491e6, 1, 0xffffd5f4, 0 <unfinished ...>
puts("*** File Printer ***"*** File Printer ***
)                                             = 21
printf("Usage: %s filename\n", "./printfile"Usage: ./printfile filename
)                            = 28
+++ exited (status 255) +++
```
  -  Googled alot found `ltrace ./printfile /etc/passwd`
```
leviathan2@gibson:~$ ltrace ./printfile /etc/passwd
__libc_start_main(0x80491e6, 2, 0xffffd5e4, 0 <unfinished ...>
access("/etc/passwd", 4)                                                 = 0
snprintf("/bin/cat /etc/passwd", 511, "/bin/cat %s", "/etc/passwd")      = 20
geteuid()                                                                = 12002
geteuid()                                                                = 12002
setreuid(12002, 12002)
```
  -  So created a temporary directory `mktemp -d`. Directory : `/tmp/tmp.xwYiWD6qKQ`
  -  `cd /tmp/tmp.xwYiWD6qKQ` : Enter the directory
  -  `touch 'file;bash'` this helps with command injection.
  -  `cd` exit directiry.
  -  `./printfile /tmp/tmp.xwYiWD6qKQ/file\;bash` : Permission is denined since we try to run the bash file but we escalte into leviathan3.
```
leviathan2@gibson:/tmp/tmp.xwYiWD6qKQ$ cd
leviathan2@gibson:~$ ./printfile /tmp/tmp.xwYiWD6qKQ/file\;bash 
/bin/cat: /tmp/tmp.xwYiWD6qKQ/file: Permission denied
leviathan3@gibson:~$
```
  -  `cat /etc/leviathan_pass/leviathan3`
  -  Password: `Q0G8j4sakn`

#TASK 3
 - `ssh -p 2223 leviathan3@leviathan.labs.overthewire.org`
 - `ls` : level3
 - `ltrace ./level3` like we did for task 1
 - we can see the password `strcmp("snlprintf\\n\n", "snlprintf\n")` similar to task 1 but we also get `strcmp("h0no33", "kakaka") `
 - Tried both and got in with `snlprintf`
 - `cat /etc/leviathan_pass/leviathan4`
 - Password : `AgvropI4OA`
 - `exit`

#TASK 4 
 - `ssh -p 2223 leviathan4@leviathan.labs.overthewire.org`
 - `ls -lah` since the file is hidden
 - `bin` setuid file is found
 - `./bin` and `01000101 01001011 01001011 01101100 01010100 01000110 00110001 01011000 01110001 01110011 00001010` gives binary output.
 - Put this into a binary to ascii converter for the password.
 - Password: `EKKlTF1Xqs`
 - `exit`
 - `ssh -p 2223 leviathan5@leviathan.labs.overthewire.org`

```
leviathan5@gibson:~$ whoami
leviathan5
leviathan5@gibson:~$
```




Links used for research:
 - https://www.cbtnuggets.com/blog/technology/system-admin/linux-file-permissions-understanding-setuid-setgid-and-the-sticky-bit
 - https://www.rapidtables.com/convert/number/binary-to-decimal.html
 - https://man7.org/linux/man-pages/man1/ltrace.1.html
 - https://www.linode.com/docs/guides/using-mktemp-command/
 - https://programmercave.com/blog/2020/01/06/Leviathan-Level-2-3-Basic-Exploitation-Techniques
   
 



  

