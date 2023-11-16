
# CPE/CWE homework

`` cpe:2.3:a:VarshithaThanam:NullPointer:14.0.0:*:*:*:*:*:* ``


- CPE Version:
  - ``2.3`` : Since this is the latest definition version of the CPE.

- Part:
  - ``a`` : This specifies what tupe of entry was made. In this case it's an application. 
- Vendor:
  - ``VarshithaThanam`` : This feild specifies the name of the creator or developer.
- Product:
  - ``NullPointer`` : This tells us the name of the application that is created.
- Version:
  - `` 14.0.0`` : This represents the version number of the application.
- Rest:
  - ``*:*:*:*:*:*`` : all the other generic information.

## CWE

Null Pointer Dereference:









```public class NullPointer {
    public static void main(String[] args) {
        String n = null;
        System.out.println(n.length());

    }
}


```
- Exception 

```
Exception in thread "main" java.lang.NullPointerException: Cannot invoke "String.length()" because "n" is null
        at NullPointer.main(NullPointer.java:4)
varshithathanam@varshithas-MacBook-Pro ~ % 

```



