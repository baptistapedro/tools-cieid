# README 
## Get ratio of invoked and non invoked methods.

### Dependencies
JDK 8 (javac 1.8.0_192)

IntelliJ Idea

### Usage
```
java -jar toolName {path_to_jar_file}

e.g.
java -jar ratioMethods.jar C:\Users\fbk\Desktop\app_jar_file.jar
```

### Expected Output
On command prompt we will have a couple prints specifically for the number of invoked methods and number of non invoked methods.

A note that 2 “.txt” files have been created. One named invoked_methods.txt which has the methods’ name invoked in the application and another one named nonInvoked_methods.txt
which contains the methods’ name not invoked in the app.

e.g.
```
Number of Non Invoked Methods: 1014
Number of Invoked Methods: 3560

Please check this directory, invoked_methods.txt has been created
and nonInvoked_mehotds.txt has been created
```

### Important Notes
We skip the analysis of third party libs, we only focused on analysing resources coming from IPZS resources (it.ipzs.cieid).

If you would like to include all resources on the app, and that includes resources coming from com.android.* for example, you just need to comment an if-statement on the code and then
on the gradle tools(TAB) do clean and then click on others > customJar

This is the line you should comment out to include all resources.

![image1](https://user-images.githubusercontent.com/9632716/70535381-4a427800-1b5d-11ea-8746-c709e416b38e.png)
