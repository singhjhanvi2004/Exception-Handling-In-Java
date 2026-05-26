# Exception-Handling-In-Java
# Error handling

Error Handling refers the mechanism in which we handle compile-time(Checked) and run-time(unchecked) exception for the smooth execution of program.

It uses various Keywords like, try, catch, throw, throws, finally.

**Try Block**

It contain the code that can generate exception.

**Catch Block**

It is used to catch the exception generated in the try block.

**Finally Block**

This block always excecutes.

```javascript
class Main {
    public static void main(String[] args) {
        int []a = {1,2,3};
        try{
            System.out.println(a[4]);
        }
        catch(ArrayIndexOutOfBoundException e)
        {
            System.out.println("Exception caught:" + e);
        }
        finally{
            System.out.println("This block will always excecutes.")
        }
    }
}

```

## 
**Throw**

It is used to explicitly throw an exception.It is used inside a method body.


## 
```java
class Main {
    static void checkAge(int age){
        if(age<18)
        {
            throw new IllegalArgumentException("The age must be greater than 18.");
        }
    }
    
    public static void main(String[] args) {
       checkAge(10);
    }
}
```

## 
**Throws**

It is used to declare that a method might throw an exception.It is used in method signature.
## 
```java
class Main {
    public static void main(String[] args) throws ArithmeticException {
     int a = 5;
     int b = 0;
     try{
         int result = a/b;
         System.out.println(result);
     }
     catch(Exception e)
     {
         System.out.println("Exception Caught.");
     }
    }
}
```
## Custom Exception

It refers to the user defined Exception developed by the programmer for specific error scenario.
## 
```java
import java.util.Scanner;
class InvalidAgeException extends Exception {
    public InvalidAgeException(String m) {
        super(m);  
    }
}
public class Main {
    public static void check(int age) 
      throws InvalidAgeException {
        if (age < 18) {
            throw new InvalidAgeException("Age must be 18 or above.");
        }
        System.out.println("Valid age: " + age);
    }

    public static void main(String[] args) {
        try {
            Scanner sc = new Scanner(System.in);
            System.out.println("Enter your Age:");
            int age = sc.nextInt();
            check(age);
        } catch (InvalidAgeException e) {
            System.out.println("Caught Exception: " + e.getMessage());
        }
    }
}
```
