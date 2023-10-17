# Lab Report 2
**By: Wilson Zhu**

**Part 1**

**Part 2**<br>
_Path to private key_
![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/90d2387b-a6a7-4bb7-8318-936d4e5c45f5)
![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/b6ef070a-6019-454c-8931-17d447869289)

The path to the private key is located in `/c/Users/Wilson Zhu/.ssh/id_rsa`. <br>
Note: The private key is hidden in the picture on purpose.

_Path to public key_
![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/10fea80a-e29c-4999-a2a7-cc817d6c5e7f)
The path to the public key is located in `/c/Users/Wilson Zhu/.ssh/id_rsa.pub`.

_Logging into ieng6 without my password_
![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/3c762179-b5f4-4b10-82a6-2db4a3d9d757)

**Part 3**<br>
Something I learned from the week 3 lab that I didn't know before would be the `mkdir` and `scp` commands. The `mkdir` command would make a new directory, inside the current working directory with the specified name. It is also short for `make directory`. The `scp` command would make a **s**ecure **c**o**p**y (SCP) between servers. In our case for the lab, the secure copy was made from my local computer to the remote `ieng6` server that's located in the CSE basement. With the `scp` command it also allowed me to access the `ieng6` server, without the need for my account password as it was "pre-authorized" when we copied the public `ssh` key over.   
