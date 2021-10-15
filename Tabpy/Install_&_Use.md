To install tabpy, go to anaconda, select your environment and open a terminal.

Run the code "pip install tabpy", and once it is installed, type tabpy.

To allow python scripts in Tableau, once you are in a Tableau book, go to the Help -> Settings and Performance -> Manage Analytics Extensions Connection.

Under hostname, wihtout the quotes type "localhost". Under port, copy and paste the port that shows under the Terminal once you have started Tabpy. 
It should be in the last line of the terminal. There is no need to sign in with name and password. Then, you can start tabpy, and it is ready to use.

To shutdown tabpy, on mac, use control + c. 


There are 4 types of scripts possible with tabpy:

  SCRIPT_REAL: SCRIPT_REAL function is used when we desire to return an output of type real from the given calculation.
  SCRIPT_INT: SCRIPT_INT function is used when we desire to return an output of type integer from the given calculation.
  SCRIPT_STR: SCRIPT_STR function is used when we desire to return an output of type string from the given calculation.
  SCRIPT_BOOL: SCRIPT_BOOL function is used when we desire to return an output of type boolean from the given calculation.



The syntax should be:

SCRIPT_XXX
(
"
script in python, including importing libraries.

_arg1 = first argument after comma that is used after the script
_arg2 = second argument after comma that is used after the script

",
SUM/AVG/COUNT([Column1]),SUM/AVG/COUNT([Column2])
)




Below, there is an example of script for tabpy:
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
SUM([Carwidth]),SUM([Carlength]))
