# README 
## Get call relationships between caller and callee methods.

### Dependencies
JDK 8 (javac 1.8.0_192)

IntelliJ Idea

### Usage
```
java -jar toolName {path_to_jar_file}

e.g.
java -jar callrelationship.jar C:\Users\fbk\Desktop\app_jar_file.jar
```

### Expected Output
On command prompt it will print out the number of call relationships in the app and also inform that a “.txt” file has been created with the full `caller->callee method relationship.`

e.g.
```
----------------------------------- executing ----------

[*] Found 12610 call links
[*] call_links.txt created - check this directory
```

### Important Notes
We skip the analysis of third party libs, we only focused on analysing resources coming from `IPZS resources (it.ipzs.cieid)`.

If you would like to include all resources on the app, and that includes resources coming from `com.android.*` for example, you just need to comment an if-statement on the code and then
on the gradle tools(TAB) do `clean and then click on others > customJar`

This is the line you should comment out to include all resources.
![image1](https://user-images.githubusercontent.com/9632716/70535381-4a427800-1b5d-11ea-8746-c709e416b38e.png)



### How to Construct the Call Graph
Using the .txt file created with the tool you will have results similar to this:
```
"it/ipzs/cieid/CieIDApplication.<init>"->"android/app/Application.<init>"
"it/ipzs/cieid/CieIDApplication.onCreate"->"android/app/Application.onCreate"
"it/ipzs/cieid/CieIDApplication.onCreate"->"com/google/firebase/analytics/FirebaseAnalytics.getInstance"
"it/ipzs/cieid/CieIDApplication.onCreate"->"b/d/a/a.a"
"it/ipzs/cieid/CieIDApplication.onCreate"->"b/a/a/a/f/a.a"
"it/ipzs/cieid/CieIDApplication.onCreate"->"j/a/b.a"
```

This is the right format to pass to Graphviz (https://www.graphviz.org/) and generate something like:
![image](https://user-images.githubusercontent.com/9632716/70535942-321f2880-1b5e-11ea-85d8-e8e06332d7d3.png)


