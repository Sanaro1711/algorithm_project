# README

This directory contains some sample code for the sorting algorithms and jRAPL.  
The main program is `SortingAlgorithms.java`, where the main sorting algorithms are run on a sample array, and the used
energy is measured using jRAPL.
## Running the program

**IMPORTANT**: jRAPL requires root access.  
Therefore, to run this program correctly, you need to run IntelliJ from the terminal **with root access**.  

The command you use will depend on how you installed IntelliJ on your computer.  
In my case, I run it as an executable from a certain location on the computer.  
Therefore, the command I use looks like this:  
`sudo [IntelliJ install location]/idea`  
If you installed IntelliJ as a package, it will look something like this:   
`sudo intellij`  

Then, you need to navigate to this repository, and run `SortingAlgorithms.java`.  

If everything goes right, you will see the intended output of the program, including the energy usage.  
Otherwise, you will see several `ERROR read_msr(): pread error!` error messages.   

If you are running IntelliJ with root access, but still getting this error, this means the module enabling RAPL on your
machine is off.  
To enable it, type `sudo modprobe msr --first-time` into your terminal.



