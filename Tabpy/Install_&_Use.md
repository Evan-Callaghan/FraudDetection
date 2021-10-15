# Guide through Tabpy

## Installing and Starting Tabpy in Tableau

* To install tabpy, go to anaconda, select your environment and open a terminal.

* Then, run the following code

        pip install tabpy
        
 * Once tabpy is installed, run the following command

        tabpy

* To allow python scripts in Tableau, once you are in a Tableau book, go to Help -> Settings and Performance -> Manage Analytics Extensions Connection.

* Under hostname, wihtout the quotes type "localhost". Under port, use the 4-digits number that appears in the last line of the terminal after running the command tabpy. There is no need to sign in with name and password. Then, you can start tabpy, and it is ready to use.

## Shut down Tabpy in your local machine

* To shutdown tabpy, in your mac terminal, use control + c. 

## Types of script for tabpy
There are 4 types of scripts possible with tabpy:

* ### SCRIPT_REAL: 
    SCRIPT_REAL function is used when we desire to return an output of type real from the given calculation.

* ### SCRIPT_INT: 
    SCRIPT_INT function is used when we desire to return an output of type integer from the given calculation.

* ### SCRIPT_STR: 
    SCRIPT_STR function is used when we desire to return an output of type string from the given calculation.

* ### SCRIPT_BOOL: 
    SCRIPT_BOOL function is used when we desire to return an output of type boolean from the given calculation.

## Syntax format

    SCRIPT_XXX
    
    (
    
    "
    script in python, including importing libraries.

    _arg1 is a reference to the first column inserted from tableau
    _arg2 is a reference to the second column inserted from tableau
    
    return x ## Used to return a number/list from the calculation in python

    ",
    
    SUM/AVG/COUNT([Column1]),SUM/AVG/COUNT([Column2]) ## Here we specify the input columns from the data set
    
    )


## Syntax example

    SCRIPT_INT(
    
    "
    import pandas as pd

    df = pd.DataFrame(_arg1,_arg2)

    n = df.shape[0]

    lists = []

    for i in range(0,n):
        lists.append(0 + _arg1[i])

    return n
    
    ",
    
    SUM([Carwidth]),SUM([Carlength])
    
    )
