# simple-java-app
Simple Java app which outputs the string "Hello world!".
It also has a few Unit Tests the results of which are saved to a surefire-reports JUnit XML report. Can be used in Jenkins Maven pipeline POCs.

Jenkinsfile can use the shell script with commands to be executed in the "Deliver" stage of the Pipeline. THis script find out the name and version of the final jar from the pom file and then executes the jar.
Jar execution results in "Hello World!" printed on the screen.
