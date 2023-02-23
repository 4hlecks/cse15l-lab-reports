# Lab 7 Challenge ⚔️
## ⚠️ Delete any existing forks of the [repository](https://github.com/ucsd-cse15l-w23/lab7) on your account
If you previously forked the repository, make sure to access the settings and **delete** the fork.
![image](https://user-images.githubusercontent.com/122405896/220771483-11a42637-31a3-41cb-9101-fed713a311f7.png)
## 🍴 Fork the [repository](https://github.com/ucsd-cse15l-w23/lab7)
![image](https://user-images.githubusercontent.com/122405896/220773661-21ce288d-1b27-48fe-bcb2-6d6cad99bb45.png)
## ⏲️ Start the timer!
![image](https://user-images.githubusercontent.com/122405896/220776094-8faa5ea0-621b-4aff-8d0a-1c6c91650139.png)
## 🖥️ Log into ieng6
![image](https://user-images.githubusercontent.com/122405896/220774512-b45eeab8-a0c4-44e9-b7f6-f3685aa6fde4.png)

*Keys pressed: `ssh cs15lwi23alg@ieng6.ucsd.edu <enter>`*

*The `ssh cs15lwi23alg@ieng6.ucsd.edu` command logs me into my remote account.*
## 🧠 Clone your fork of the [repository](https://github.com/ucsd-cse15l-w23/lab7) from your Github account
<img width="407" alt="image" src="https://user-images.githubusercontent.com/122405896/221048429-7d848421-5a30-426d-bef0-eb8252da541f.png">
<img width="632" alt="image" src="https://user-images.githubusercontent.com/122405896/221048580-4201b4e9-e4dc-4cc1-8241-64452dccbfa4.png">

*Keys pressed: `git clone <command> v <enter>`*

*The `git@github.com:4hlecks/lab7.git` URL was copied previously from my repository. The command `git clone git@github.com:4hlecks/lab7.git` clones my repository from github to my remote account's files.*
## 📋 Run the tests, demonstrating that they fail
<img width="805" alt="image" src="https://user-images.githubusercontent.com/122405896/221048848-5b3613b4-4997-44e0-8b0f-a708b74bfbb1.png">

*Keys pressed: `ls <enter>, cd l <tab> <enter>, <command> v <enter>, <command> v <space> <shift> l <tab> <shift> t <tab> <backspace> <enter>`*

*The `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` and `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTest` was copied previously from the Week 7 Lab website. These commands compile the java files and test the ListExamplesTest.java file.*
## 📝 Edit the code file to fix the failing test
![image](https://user-images.githubusercontent.com/122405896/220775196-3fd4ad48-d5db-411f-ace1-e5e905b5b7a5.png)

*Keys pressed: `nano <shift> l <tab> .j <tab> <enter>, <control> v <control> v down down down down down down  <right> <right> <right> <right> <right> <right> <right> <right> <right> <right> <right> <right> <backspace> 2 <control> o <enter>, <control> x`*

*The `nano ListExamples.java` command gives me access to make changes to the ListExamples.java file.*
## ✅ Run the tests, demonstrating that they now succeed
<img width="796" alt="image" src="https://user-images.githubusercontent.com/122405896/221047953-66f2f873-a2e5-469c-a509-6838c9b4bc3f.png">

*Keys pressed: `<up> <up> <up> <enter>, <up> <up> <up> <enter>`*

*The `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` was 3 up in the search history so I used the up arrow 3 times. The `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore` was also 3 up in the search history in which I used the up arrow 3 times.*

## 📨 Commit and push the resulting change to your Github account
<img width="593" alt="image" src="https://user-images.githubusercontent.com/122405896/221049473-9ac9c36c-2acd-4882-aa35-b79c6ad8c8f3.png">

*Keys pressed: `git add <shift> l <tab> .j <tab> <enter>, git commit -m "updated" <enter>, git push <enter>`*

*The `git add ListExamples.java` command prepares changes to be committed to the repository. The `git commit -m "updated"` command creates a snapshot of the changes made with a message. The `git push` command sends the committed changes to the repository on github.com.*

## 👑 Done!
<img width="1164" alt="image" src="https://user-images.githubusercontent.com/122405896/221049785-82f3b829-506a-425a-b6a9-8fdaaba4f304.png">

*Screenshot above is from the repository on github.com showing the changes made.*
I am done! I finished at **01:41:11 seconds**.
