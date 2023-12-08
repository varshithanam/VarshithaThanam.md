#TASK 1 

  - I used the SSH command provided in the discord. `ssh -p 2223 leviathan0@leviathan.labs.overthewire.org`
  - Later it after saying yes it prompted for a password and the password was mentioned in the leviathan site. `leviathan0`
  - I finally entered and did `ls`. Nothoin showed up and did ls again but there was nothing.
  - Then I `la` and found a hidden directory `.backup`
  - The directory has a html file. `bookmarks.html`
  - Used `cat` to view the contents of the file. It was too big. I couldn't find a password.
  - After some google search I found we could use `grep`. `grep password bookmarks.html`
  - The password is `PPIfmI1qsA`
  - `exit

#TASK 2
  - ssh into the level 1 using `ssh -p 2223 leviathan1@leviathan.labs.overthewire.org`
  - `ls` and file was found `check`
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
  - `exit`

#TASK 3



  

