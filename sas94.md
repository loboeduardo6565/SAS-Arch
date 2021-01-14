## Algunas opciones

###### Ingresar al entorno SAS desde la consola de Linux 

```
/app/sas/SASHome/SASFoundation/9.4/sas -nodms

```

###### Instanciar SAS Management Console desde la consola

```
/app/sas/SASHome/SASManagementConsole/9.4/sasmc
```

###### El procedimiento PRODUCT_STATUS le indica que productos están instalados

```
proc PRODUCT_STATUS;
run;
```

###### Mostrar variables de entorno del sistema con codigo SAS

```
%put %sysget(LD_LIBRARY_PATH);
```
