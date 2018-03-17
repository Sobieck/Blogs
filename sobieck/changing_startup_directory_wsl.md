I'm trying to only use npm on the [Windows Linux Subsystem](https://docs.microsoft.com/en-us/windows/wsl/about) when developing in Windows. I've always had a sort of love/hate relationship with NPM on windows. I love it because it makes development easy but I sort of hate it because I always have issues getting it to install correctly. I've never really had issues installing stuff with apt-get on Kali Linux so I figured I could install npm on linux and run all my commands from there and not bother with node for windows. 

So, I want to make it so I log into WSL and then just switch users with `su {username}` and it just go to the directory that I'm going to be using with that user. In the case of this blogs project the command I would need to enter would be `cd /mnt/c/GitHub/blogs`. I'm lazy and I don't want to have to enter that everytime I log into that account. I needed to figure out how to make that happen. 

I'm going to create a user, give it a password, give it sudo privilages, and then change the `.bashrc` file to go to the correct directory on log in. 

Steps in creating `blogs` user.

1. Create the user with this command: `sudo adduser blogs`
2. Give the new user sudo privilages: `sudo adduser blogs sudo` 
3. Login to blogs with this command: `su blogs`
4. I need to go to `/home/blogs` with this command: `cd` 
5. Now I need to edit the `.bashrc` file in this directory: `sudo nano .bashrc`
6. Add the bottom of this file I add `cd /mnt/c/GitHub/blogs` and save.
7. Now when I resign into this account I will go directly to the blogs folder!