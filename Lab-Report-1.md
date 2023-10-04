# Lab Report 1
**By: Wilson Zhu**

**Step 1:**

![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/a69602ee-5dcd-4c47-89e0-d11503327b47)

_cd no arguement_
* Working directory: `/home`
* Output: Got as expected for CD as it's used for changing directory and we didn't change the directory. Having no arguments means that nothing is being changed here.
* Error?: The output was not an error as we did not change the directory.

_ls no arguement_
* Working directory: `/home`
* Output: It showed what was in the `/home` which was the folder `lecture1` as expected for the list function. No arguments here showed us what files/folders were in the current directory.
* Error?: No error was thrown as the output was as expected.


![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/782072da-b481-45d5-aa55-a23d7a770d94)

_cat no arguement_
* Working directory: `/home`
* Output: There was no output, as there are no files to concatenate/print in the current directory. No arguments here threw the console into a spin, had to abort it using `Control + C`. This result held true when I ran `cat` with no arguments in different directories. See picture above.
* Error?: The command threw the terminal into a spin, and had to abort using `Control + C`. It was trying to concatenate something that it couldn't.


**Step 2:**

![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/62e83d16-25c3-4c82-b865-c7eeeb1ad9a3)

_cd directory arguement_
* Working directory: `/home`
* Output: Got as expected for output, as it took me to the directory I specified, in this case, `lecture1`. Having a directory argument changed my directory to the one specified. 
* Error?: The output was not an error as it changed the directory properly.

_ls directory arguement_
* Working directory: `lecture1`
* Output: It showed what was in the `messages` directory which was the files `de.txt`, `en-us.txt`, `es-mx.txt`, and  `zh-cn.txt` as expected with the list function. If we did no arguments in the `lecture1` directory, it would show us all the files in the `lecture1` directory which were the folder `messages` and the files `Hello.class`, `Hello.java`, and `README`. 
* Error?: No error was thrown as the output was as expected.

_cat directory arguement_
* Working directory: `lecture1`
* Output: The following was outputted: `cat: messages: Is a directory`, which is an error. This output was expected as we tried to concatenate/print a directory.
* Error?: Since the output threw an error, it tells us that we were trying to concatenate a directory, which isn't allowed since it can't print out what the directory is. 

**Step 3:**

![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/fed27f36-4d42-45c2-afce-d50d8a3f6431)

_cd file arguement_
* Working directory: `lecture1`
* Output: The following was outputted: `bash: cd: Hello.java: Not a directory`, which is an error. Output was expected as we tried to change our current directory into a file, which is not a directory.
* Error?: The output was an error as we tried to change our directory into a file.

_ls file arguement_
* Working directory: `lecture1`
* Output: It outputted as expected as it is supposed to list the name of the file. 
* Error?: No error was thrown as the output was as expected.

_cat file arguement_
* Working directory: `lecture1`
* Output: It outputted as expected as it concatenated/printed out everything that was in the `Hello.java` file.
* Error?: The output was not an error as it outputted everything as expected. 
