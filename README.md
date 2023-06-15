# A repository for documentation of VSD-TCL WORKSHOP
# Task: Write a TCL program which reads parameters from an excel sheet and performs Synthesis and STA analysis and display the timing results as a datasheet
Author: Sahil Savanth M

Acknowledgments: TCL Workshop of VlSI System Design by Kunal Ghosh

### DAY 1 report 
**How to create a shell file**
* Press ctrl+alt+t to open terminal
* Type vim *filename*.sh to create a vim file
* The file will be created and to enter the code press i to start insert mode
* Enter the required code and save the file using :wq
#### **HOW DOES THE CODE WORK**
* If no CSV file is found, the code snippet to display an error message is given below
```
if ($#argv != 1) then
        echo "info: pls give csv file name"
        exit 1
endif
```
* If file name does not exist or -help is typed then the following code snippet is executed
```
if (! -f $argv[1] || $argv[1] == "-help") then
        if ($argv[1] != "-help") then
                echo "Error, no files found, bye bye"
                exit 1
       else
               echo "USAGE: ./TCL <csv file> , where the <csv file> consists of 2 columns  -->  1st column is being case sensitive."
                echo "Note if the file is not in the same directory, ensure to include the path along with the <csv file>"
                echo
                echo "<Design Name> is the name of the top module"
                echo
                echo "<Output Directory> is the name of the output directory where you want to dump synthesis script, synthesized netlist and timing report"
                echo
                echo "<Netlist Directory> is the name of the directory where all RTL netlist are present"
                echo
                echo "<Early Library Path> is the file path of the early cell library to be used for STA"
                echo
                echo "<Late Library Path> is the file path of the late cell library to be used for STA"
                echo
                echo "<Constratints file> is the csv file path of constraints to be used for STA"
                echo
                exit 1
        endif

```   


