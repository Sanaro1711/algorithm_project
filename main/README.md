# README

This directory contains some sample code for the sorting algorithms and jRAPL.  
The main program is `SortingAlgorithms.java`, where the main sorting algorithms are run on a sample array, and the used
energy is measured using jRAPL.

## jRAPL Compatibility

Before running the program, check if your machine is compatible with jRAPL.  
You can do this by running `sudo java -cp ./jRAPL-1.0.jar jRAPL.Demo ArchSpec`.  
This will print out something similar to this:     
```
MICRO_ARCHITECTURE: 8e  
MICRO_ARCHITECTURE_NAME: KABYLAKE
```  
If `MICRO_ARCHITECTURE_NAME` says something like `UNDEFINED_ARCHITECTURE`, jRAPL is not compatible with your machine.

## Running the program

### Setting up

In order to run the program, you need to first add `jRAPL-1.0.jar` to the project's libraries.  
To do this, go into "File" -> "Project Structure" -> "Libraries", click the + icon, and add the .jar file in this repo.

**IMPORTANT**: jRAPL requires root access.  
Therefore, to run this program correctly, you need to run IntelliJ from the terminal **with root access**.

The command you use will depend on how you installed IntelliJ on your computer.  
In my case, I run it as an executable from a certain location on the computer.  
Therefore, the command I use looks like this:  
`sudo [IntelliJ install location]/idea`  
If you installed IntelliJ as a package, it will look something like this:   
`sudo intellij`  

Then, you need to navigate to this repository, and open `SortingAlgorithms.java`.  
Usually, the root version of IntelliJ is completely separate to the non-root version, so this might mean cloning the repository
from scratch.  

### Modifying the program

The program **will not run as intended without any changes**.  
This is because the provided sample CSV file may have a different location on your computer.  [^1]
[^1]: This will probably be changed in the future, to simplify development.  
You need to go to line 26:
```
String path = "/root/IdeaProjects/algorithm_project1/main/src/Random Numbers 3 (Max and Min for Java, 500k) - Sheet1.csv";
```
and change the value of `path` to the absolute path of the sample CSV file on your system.

You also need to **remove the comments** on lines 17-18, 21, 69, 72-73 and 78-81.  
These lines contain the jRAPL code. They have been commented out, so that I can run the code on my non-Intel desktop.


If everything goes right, you will see the intended output of the program, including the energy usage.  
Otherwise, you will see several `ERROR read_msr(): pread error!` error messages.

If you are running IntelliJ with root access, but still getting this error, this means the module enabling RAPL on your
machine is off.  
To enable it, type `sudo modprobe msr --first-time` into your terminal.




