# Lab Report 5
**By: Wilson Zhu** <br>

**Part 1:** <br>
Student Post: <br>

Hi, <br> 
I'm trying to run my auto grader, but I ran into this error with what appears to be my JUnit. I have a feeling it may be how I wrote the code to start JUnit in line 28. I've attached my code and the error from the terminal below.

Code: ![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/9f249964-9a6d-4709-83ec-72a785d15fde)
 <br>

Terminal: ![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/653466c4-c14c-4d3c-bcce-cc777f085e68)
 <br>

TA Response: <br>
Hi, <br>
Based on the output in your terminal it appears that your error may be at one of the `cp` lines and `lib` also appears to be omitted. Based on this what information provided, what can we try to do to fix the bug? <br>

Student trying solution:

Code: ![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/d7baaaa6-8eb5-46d3-8ae1-0a8b422e7892) <br>

Terminal: ![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/e1fd0c59-f6b4-457a-a168-fde77add909c) <br>

The bug that caused the program to throw such symptom would be the missing `-r` option used for copy. This option lets it recursively copy all files in the `lib` folder. Without all the files JUnit isn't running properly. <br>

Setup Process: <br>
Note: This bug was derived from the auto-grader repository that was worked on during the week 6 lab. <br>
File and Directory structure needed: ![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/501865f5-4084-4182-bda8-3618786ae128)
Content of each file: Each file remained the same as <https://github.com/ucsd-cse15l-s23/list-examples-grader>, except `grade.sh` as it has been modified. <br>
Modified `grade.sh` before bug fix:
```
CPATH='.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar'

rm -rf student-submission
rm -rf grading-area

mkdir grading-area

git clone $1 student-submission
echo 'Finished cloning'

cd student-submission


if [[ -f ListExamples.java ]]
then
    cp -r ListExamples.java ../grading-area
    cd ..

    cp -r *.java grading-area

    cd grading-area

    cd .. 

    cp lib grading-area
    cd grading-area

    javac -cp ".;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar" *.java
    java -cp ".;lib/junit-4.13.2.jar;lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore TestListExamples > run-results.txt

else
    echo 'resubmit with proper file'
fi



# Draw a picture/take notes on the directory structure that's set up after
# getting to this point

# Then, add here code to compile and run, and do any post-processing of the
# tests

```
To trigger the bug, I simply removed the `-r` option from `cp -r lib grading-area` which caused the bug to trigger. The resulting line became `cp lib grading-area` <br>

To fix this bug, the option `-r` was added to the code, allowing it to read recursively read and copy the contents of `lib` into `grading-area`.

Modified code after bug fix:
```
CPATH='.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar'

rm -rf student-submission
rm -rf grading-area

mkdir grading-area

git clone $1 student-submission
echo 'Finished cloning'

cd student-submission


if [[ -f ListExamples.java ]]
then
    cp -r ListExamples.java ../grading-area
    cd ..

    cp -r *.java grading-area

    cd grading-area

    cd .. 

    cp -r lib grading-area
    cd grading-area

    javac -cp ".;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar" *.java
    java -cp ".;lib/junit-4.13.2.jar;lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore TestListExamples > run-results.txt

else
    echo 'resubmit with proper file'
fi



# Draw a picture/take notes on the directory structure that's set up after
# getting to this point

# Then, add here code to compile and run, and do any post-processing of the
# tests

```



**Part 2:** <br>

In the second half of the quarter, I certainly learned a lot in regards to the functions of VIM. While it was annoying to work with at first, I soon got the hang of it. I found it extremely useful to use VIM when I don't have access to a code editior like VS Code. It may not be as nice or user friendly as visual studio code is, but it got the job done.
