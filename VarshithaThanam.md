
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

## CVE

Null Pointer Dereference:

  A nullptr is a value that doesn't reference to anything on the memory location. This exception is mainly thrown when an application attempts to use null in place of an object when required. Few of th comman scenarios where people run into this error are:
    - Calling methods on a null object
    - Accessing a null object’s properties
    - Accessing an index element of a null object. Ex: like in an array
    - Passing null parameters to a method
    - Throwing null from a method that throws an exception


Links used for reserch
  - https://docs.oracle.com/javase/8/docs/api/java/lang/NullPointerException.html
  - https://rollbar.com/blog/how-to-catch-and-fix-nullpointerexception-in-java/
  - https://cwe.mitre.org/data/definitions/476.html#Potential_Mitigations
  - https://medium.com/analytics-vidhya/nullpointerexception-a869bc49b50d 

## CWE

- The code below is one example of how we run into a Null Pointer Error. We run into this error beacuse the string is initialized to null. `String n = null;`. Later we try to access the lenght of the `n`. But the `n` is initiallzed to a `null` which gives us the error.

```public class NullPointer {
    public static void main(String[] args) {
        String n = null;
        System.out.println(n.length());

    }
}

```

- Exception : This is the erroe we are likely to get when we run the above code. 

```
Exception in thread "main" java.lang.NullPointerException: Cannot invoke "String.length()" because "n" is null
        at NullPointer.main(NullPointer.java:4)
varshithathanam@varshithas-MacBook-Pro ~ % 

```
- There a many ways we can fix this problem. One of the 



