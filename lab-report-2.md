# Lab Report 2
**By: Wilson Zhu**

**Part 1**<br>
`StringServer` Code:<br>
![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/32e2deaf-1356-4ea9-a75e-de833a6d3c56)

`/add-message` with input `raccoon`: <br>
![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/644410e9-de18-4c15-82a3-be91062e06d6) <br>
Methods: The method that was called would be `handleRequest.` as `/add-message?s=raccoon` is a valid input for this method. <br>
Relevant arguments/fields: The relevant arguments would be the line `if (url.getPath().contains("/add-message"))` as it checks for `/add-message` otherwise it would return `404 not Found!`. The values of any relevant fields were `raccoon` when it got passed into the `ArrayList<String> strngs` field and `1. raccoon\n` when it got passed into `String out1` field. <br> 
Change to the relevant field: `strngs` which was originally empty, now contains one element `raccoon`. `out1` which was originally an empty string, and now reads `1. raccoon\n`. The `\n` in this case would make a new line. <br>


`/add-message` with input `sleep deprived raccoon`: <br>
![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/dccec8fc-19bb-48dd-b3c2-1ee2adf96dc2) <br>

Methods: The method that was called would be `handleRequest.` as `/add-message?s=sleep%20deprived%20raccoon` is a valid input for this method. The `%20` in the input indicates a space between words. <br>
Relevant arguments/fields: The relevant arguments would be the line `if (url.getPath().contains("/add-message"))` as it checks for `/add-message` otherwise it would return `404 not Found!`. The values of any relevant fields were `sleep%20deprived%20raccoon` when it got passed into the `ArrayList<String> strngs` field and `2. sleep deprived raccoon\n` when it got passed into `String out1` field. <br> 
Change to the relevant field: `strngs` which originally contained the element `raccoon`, now contains an additional element `sleep deprived raccoon`. `out1` which originally contained the string `1. raccoon\n` is now cleared and reads `2. sleep deprived raccoon\n`. The `\n` in this case would make a new line.<br>



**Part 2**<br>
_Path to private key_<br>
![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/90d2387b-a6a7-4bb7-8318-936d4e5c45f5)
![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/b6ef070a-6019-454c-8931-17d447869289)

The path to the private key is located in `/c/Users/Wilson Zhu/.ssh/id_rsa`. <br>
Note: The private key is hidden in the picture on purpose for security and privacy reasons.

_Path to public key_<br>
![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/10fea80a-e29c-4999-a2a7-cc817d6c5e7f)
The path to the public key is located in `/c/Users/Wilson Zhu/.ssh/id_rsa.pub`. <br>
Note: The terminal command `cd authorized_keys` was accidental. `cd authorized_keys` shouldn't have worked as `authorized_keys` was a file and not a directory.

_Logging into ieng6 without my password_
![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/3c762179-b5f4-4b10-82a6-2db4a3d9d757)

**Part 3**<br>
Something I learned from the week 3 lab that I didn't know before would be the `mkdir` and `scp` commands. The `mkdir` command would make a new directory, inside the current working directory with the specified name. It is also short for `make directory`. The `scp` command would make a **s**ecure **c**o**p**y (SCP) between servers. In our case for the lab, the secure copy was made from my local computer to the remote `ieng6` server that's located in the CSE basement. With the `scp` command it also allowed me to access the `ieng6` server, without the need for my account password as it was "pre-authorized" when we copied the public `ssh` key over.   
