# SAS CAS Administration Cheat Sheet

## Gestión de Sesiones

1. **`cas`**
   - Inicia una nueva sesión CAS.

2. **`cas mySession;`**
   - Inicia una sesión CAS con un nombre específico.

3. **`cas mySession terminate;`**
   - Termina una sesión CAS específica.

4. **`caslib _all_ assign;`**
   - Asigna todas las librerias CAS disponibles.

5. **`caslib _all_ list;`**
   - Lista todas las librerias CAS disponibles.

## Gestión de Tablas

6. **`table.save / caslib="casuser" name="myTable.sashdat";`**
   - Guarda una tabla CAS en un archivo SASHDAT.

7. **`table.loadtable / caslib="casuser" path="myTable.sashdat" casout={name="myTable"};`**
   - Carga una tabla CAS desde un archivo SASHDAT.

8. **`table.droptable / table="myTable";`**
   - Elimina una tabla CAS.

9. **`table.fetch / table="myTable" to=10;`**
   - Obtiene las primeras 10 filas de una tabla CAS.

10. **`table.tableinfo / caslib="casuser" name="myTable";`**
    - Muestra información sobre una tabla CAS.

## Gestión de Usuarios y Roles

11. **`casadmin adduser / username="myUser" password="myPassword";`**
    - Añade un nuevo usuario a CAS.

12. **`casadmin deleteuser / username="myUser";`**
    - Elimina un usuario de CAS.

13. **`casadmin listusers;`**
    - Lista todos los usuarios en CAS.

14. **`casadmin addrole / rolename="myRole";`**
    - Añade un nuevo rol a CAS.

15. **`casadmin deleterole / rolename="myRole";`**
    - Elimina un rol de CAS.

## Gestión de Caslibs

16. **`caslib myCaslib datasource=(srctype="path") path="/my/caslib/path";`**
    - Crea una nueva libreria CAS (caslib).

17. **`caslib myCaslib drop;`**
    - Elimina una libreria CAS (caslib).

18. **`caslib _all_ list;`**
    - Lista todas las caslibs disponibles.

## Supervisión y Diagnóstico

19. **`cas casadmin listnodes;`**
    - Lista todos los nodos en el clúster CAS.

20. **`cas casadmin listmetrics;`**
    - Muestra métricas de rendimiento del clúster CAS.
