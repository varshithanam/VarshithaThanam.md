
# CPE/CWE homework

`` cpe:2.3:a:VarshithaThanam:NullPointer:14.0.0:*:*:*:*:*:* ``


CPE Version:
  - ``2.3``
Part:
  - ``a`` : type of application
Vendor:
  - ``VarshithaThanam`` : my name since I'm the creator of the product.
Product:
  - ``NullPointer`` : The name of the file.
Version:
  - `` 14.0.0`` : This represents the version number.
Rest:
  - ``*:*:*:*:*:*`` : all the other informations which is not required.

## CWE
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



