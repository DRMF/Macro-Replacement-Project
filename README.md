MacroReplacementProject
=======================

This project inserts DLMF and DRMF macros into unprocesssed TeX based on the regular expressions specified in `function_regex.txt`.

##Usage

To make the replacements, you should run replace.py with the input and output files as arguments. The `-c` option allows you to specify a configuration file other than `function_regex.txt`. 

###Regular Expressions

In order to add new macros/replacements to the functionality of the program, one must edit the `function_regex.txt` file. Entries in the file are in the following form:

    macroformat&macroidentifier&regex_1~-~regex_2~-~...~-~regex_n&replacement_1~-~replacement_2~-~...~-~replacement_n&fullname~?~
    
Where:

* `macroformat` is a template for what the macro should look like in the output file (i.e. pochhammer{a}{n})
* `macroidentifier` is a 1-3 character "code" to help identify occurences of the macro
* `regex_1 - regex_n` are the Python regular expressions that will be used to identify TeX that should be replaced with the macro (a full reference for regular expressions in Python can be found [here](https://docs.python.org/3/library/re.html#module-re).
* `replacement_1 - replacement_n` are the replacements for each corresponding regular expression. Backreferences are supported.
* `fullname` is a formal name/short description for the function
