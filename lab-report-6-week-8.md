## 1. My grade.sh:
```
set -e

rm -rf student-submission
git clone $1 student-submission
cd student-submission
if [[ -f ListExamples.java ]]
then 
  echo "found files!"
else
  echo "haven't found files"
  exit 1
fi

cp ListExamples.java ../

cd ..
set +e

javac ListExamples.java 2> errors.txt
if [[ $? -eq 0 ]]
then
  echo "compile successfully"
else
  cat errors.txt
  echo "compile error!"
  exit 1
fi

javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples > JunitOutput.txt
if [[ $? -eq 0 ]]
then
  echo "Full credits"
else
  cat JunitOutput.txt
  a=$(grep -c "filter" JunitOutput.txt)
  if [ "$a" -gt 0 ]
  then 
    echo "Fail filter! 50% correct!"
  else 
    echo "Fail Merge! 50% correct!"
  fi
fi
```
## 2. Screenshots of three different student submissions and their reported grade
* For the correct file:
<img width="838" alt="Screen Shot 2022-11-27 at 17 16 49" src="https://user-images.githubusercontent.com/114370407/204172188-ad3d463a-17e2-4f11-97c5-23310f1b7bf0.png">

* For the file with compile error: <img width="868" alt="Screen Shot 2022-11-27 at 17 18 44" src="https://user-images.githubusercontent.com/114370407/204172233-26c0e5fe-f355-4988-a9e7-e43b023e3b71.png">

* For the file with `filter` in the wrong order:<img width="942" alt="Screen Shot 2022-11-27 at 17 19 23" src="https://user-images.githubusercontent.com/114370407/204172364-82ac61cd-c878-49c9-bba4-0da23dd7d478.png">

## 3. Trace the script of the file with compile error
`rm -rf student-submission`:
| Commands                          | Standard Output                           | Return Code |
| --------------------------------- |:-----------------------------------------:| -----------:|
| `rm -rf student-submission`       | none                                      |0            |
| `git clone $1 student-submission` | Cloning into 'student-submission'...      |0            |
| `cd student-submission`           | none                                      |0            |
| `if [[ -f ListExamples.java ]]`   | none                                      |0            |
| `echo "found files!"`             | found files!                              |0            |
| `echo "haven't found files"`      | not run                                       |
| `cp ListExamples.java ../`        | none                                      |0            |
| `cd ..`                           | none                                      |0            |
| `set +e`                          | none                                      |0            |
| `javac ListExamples.java 2> errors.txt`| none                                 |non-zero     |
| `if [[ $? -eq 0 ]]`               | none                                      |0            |       
| `echo "compile successfully"`     |not run   |
| `cat errors.txt`               |ListExamples.java:15: error: ';' expected result.add(0, s)                        ^1 error    |0     |
| `echo "compile error!"`| compile error!      |0                                   |
| `exit 1`                          |none                                       |1            |

In the command `if [[ -f ListExamples.java ]]`, the truth value will be true since we can find a file with the name "ListExamples.java".
In the command `if [[ $? -eq 0 ]]`, the truth value will be false, since `javac ListExamples.java 2> errors.txt`'s return code is nonzero, which means this file has a compile error.
And the following commands did not run since we detected the compile error and exit.
