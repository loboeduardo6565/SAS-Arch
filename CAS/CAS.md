###### Create CAS session

```
cas mycassession sessopts=(metrics=true); run;
``` 
###### Create a Caslib

```
caslib ORACLE datasource=(                                          
    srctype="oracle",
    uid="user",
    pwd="pass",
    path="path",
    schema="schema" );
``` 

Prueba 2