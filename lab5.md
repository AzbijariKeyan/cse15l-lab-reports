# Lab Report 5
***
## My grade.sh script
```
# Create your grading script here

rm -rf student-submission
mkdir student-submission
git clone $1 student-submission

cp TestListExamples.java student-submission
cd student-submission
echo "In student-submission"

if [ -f "ListExamples.java" ]; then
    echo "You have the right file. +1. SCORE : 1/4"
else 
    echo "You don't have the right file. +0. SCORE : 0/4"
    exit 1
fi 

javac -cp .:../lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar *.java 2> CompileError.txt

if [[ $? -eq 0 ]]; then
    echo "Compiled. +1. SCORE : 2/4"
else
    echo "Failed to compile. +0. SCORE : 1/4"
    cat CompileError.txt
    exit 1
fi

java -cp .:../lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples > output.txt 2> ExecuteError.txt
if [[ $? -eq 0 ]]; then
    echo "Both Test Passed. Good Job! +2. FINAL SCORE : 4/4"
else    
    FAILURE=$(grep "There " output.txt | grep -Eo "[1-2]") #Used inspiration from @jankwong705 GitHub
    PASSED="$((4 - FAILURE))"
    echo "Failed Tests"
    echo "FINAL SCORE : $PASSED/4"
fi
```
Here are some examples of my autograder running: 

![Image](https://azbijarikeyan.github.io/cse15l-lab-reports/ListExamplesCorrected.png)
In this examples my grader is running on a correct version of ListExamples. The student gets full credit.

![Image](https://azbijarikeyan.github.io/cse15l-lab-reports/ListExamplesSyntaxError.png)
In this examples my grader is running on a version of ListExamples where there is a syntax error in the file. My grader will let the student know the
error and where it is.

![Image](https://azbijarikeyan.github.io/cse15l-lab-reports/ListExamplesWrongName.png)
In this examples my grader is running on a version of ListExamples where the file is incorrectly named. My grader will let the student know that the
file doesn't exist.

***
For my trace through, I will be tracing the example where the file name is incorrect.
```
Line 3 - 4: No standard out or standard error, both have an exit code of zero
Line 5: Cloning into 'student-submission'..., No standard error, exit code of zero
Line 7 - 8: No standard error or output, exit code of zero
Line 9: No standard error, has an output of “In student-submission”, exit code 0
Line 11: Return false, checks if the file exists with the correct name which it doesn't
Line 12: Doesn't run but if the file existed, prints out the given string, with an exit code of 0
Line 13 - 15: runs because the file doesn't exist and prints out the given string and exits with an exit code of 1

The rest of the lines of code don't run because of the `exit` statement on line 15. This prevents any of the rest of the script to run because the student
submitted an incorrect file which can't be graded by the autograder.
```

Had an amazing semester in this class! Thank You!

