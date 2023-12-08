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
  - 
