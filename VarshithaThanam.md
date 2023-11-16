
# CPE/CWE homework

`` cpe:2.3:a:VarshithaThanam:NullPointerDereference:*:*:*:*:*:* ``

CPE Version:
  - ``2.3``
Part:
  - ``a`` : type of application
Vendor:
  - ``VarshithaThanam`` : my name since I'm the creator of the product.
Product:
  - ``NullPointerDereference`` : The name of the file.
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



