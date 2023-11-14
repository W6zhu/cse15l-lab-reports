# Lab Report 4
**By: Wilson Zhu** <br.

Logging in:<br>
Typing `ssh cs15lfa23iw@ieng6.ucsd.edu` <br>
![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/c4e407cf-d18d-4308-a308-c43978e768b3) <br>

Cloning fork of the repo from Github:<br>
Typing `git clone git@github.com:W6zhu/lab7.git` <br>
![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/39066174-504d-467e-b57f-f80262c57ac9)<br>

Running the tests and they fail:<br>
Typing: `cd lab7` then `bash test.sh`<br>
![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/ab4521af-2812-4127-a34a-520f787f019a)<br>

Editing code to fix failure:<br>
Typing: `vim ListExamples.java` then `<shift+g> <k> (6 times) <shift+e> <x> <a> <2> <esc> <:wq>`<br>
![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/7f70c8f3-15ff-4c9b-a725-46a7d715c191)<br>
![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/6a26671f-aaac-4595-8915-4fe39a7a8528)<br>
Note: The underlined 2 shows that the code was changed from `index1` to `index2`. <br>

Running the test to show success:<br>
Typing: `bash test.sh`<br>
![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/ffb0fb9a-bd66-49b4-9abd-30dbec896141)<br>

Committing and pushing to GitHub:<br>
Typing: Add using `git add ListExamples.java` then commit using `git commit -m "updated again"` then push using `git push`<br>
![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/b30e9cef-9446-4fce-a004-5f9d155230cc)<br>
Note: The command `git commit "updated!"` was accidental and would not work. For the command to work it would have to be in the form `git commit 'updated!'` using single quotes instead of double. <br>





