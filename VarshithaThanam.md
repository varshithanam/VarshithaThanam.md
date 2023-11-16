
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
```public class Main {
    public static void main(String[] args) {
        String n = Null;
        System.out.println(n.length());

    }
}

```
- Exception 

```
 Main 
Exception in thread "main" java.lang.Error: Unresolved compilation problem: 
        Null cannot be resolved to a variable

        at Main.main(NullPointer.java:3)
varshithathanam@varshithas-MacBook-Pro ~ %

```



