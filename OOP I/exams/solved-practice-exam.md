# Practice Question Solutions – CS 201

*Note: These solutions are written in the most readable form. Your version might differ slightly, and that's okay. Focus on understanding the logic and structure.*



## Data Types

**Q1:**  
Write a Java program that declares variables of the following types: `int`, `double`, `char`, `boolean`, and `String`. Initialize each variable with a value and print their values to the terminal.

```java
public class DataTypesDemo {
    public static void main(String[] args) {
        int myInt = 10;
        double myDouble = 3.14;
        char myChar = 'A';
        boolean myBoolean = true;
        String myString = "Hello, World!";

        System.out.println("int: " + myInt);
        System.out.println("double: " + myDouble);
        System.out.println("char: " + myChar);
        System.out.println("boolean: " + myBoolean);
        System.out.println("String: " + myString);
    }
}
```

**Q2:**  
Explain the difference between `primitive data types` and `reference data types` in Java. Provide one example.

Primitive: Stores actual values (int, boolean, char, etc.)
Reference: Stores the memory address of an object (String, arrays, classes, etc.)


## Loops & Conditional Statements

**Q3:**  
Write a Java program using an if-else statement that checks whether a number is positive, negative, or zero.
```java
public class NumberCheck {
    public static void main(String[] args) {
        int number = 5;

        if (number > 0) {
            System.out.println("The number is positive.");
        } else if (number < 0) {
            System.out.println("The number is negative.");
        } else {
            System.out.println("The number is zero.");
        }
    }
}
```

**Q4:**  
Write a Java program that uses a for loop to print all even numbers between 1 and 20.

```java
public class EvenNumbers {
    public static void main(String[] args) {
        for (int i = 1; i <= 20; i++) {
            if (i % 2 == 0) {
                System.out.println(i);
            }
        }
    }
}
```

## Methods

**Q5:**  
Create a Java method named max that takes two integer parameters and returns the larger value. Write a main method to test your max method.

```java
public class MaxDemo {
    public static int max(int a, int b) {
        return (a > b) ? a : b;
    }

    public static void main(String[] args) {
        int result = max(10, 20);
        System.out.println("The larger number is: " + result);
    }
}
```

**Q6:**
What is the difference between a static method and an instance method in Java? Provide an example of each.

```java
public class MethodTypes {
    static void staticMethod() {
        System.out.println("Static method");
    }

    void instanceMethod() {
        System.out.println("Instance method");
    }

    public static void main(String[] args) {
        staticMethod(); // called without object

        MethodTypes obj = new MethodTypes();
        obj.instanceMethod(); // called on an object
    }
}
```
Static methods belong to the class and can be used without creating an object.
Instance methods belong to an object and require an object to be used.

## Arrays

**Q7:**  
Write a Java program that creates an array of 10 integers, initializes the array with values, and calculates the sum.

```java
public class ArraySum {
    public static void main(String[] args) {
        int[] numbers = new int[10];

        for (int i = 0; i < numbers.length; i++) {
            numbers[i] = i + 1;
        }

        int sum = 0;
        for (int num : numbers) {
            sum += num;
        }

        System.out.println("The sum of the array elements is: " + sum);
    }
}
```

**Q8:**  
Write a method called `findMax` that takes an array of integers as a parameter and returns the largest number.

```java
public class FindMax {
    public static int findMax(int[] array) {
        int max = array[0];
        for (int i = 1; i < array.length; i++) {
            if (array[i] > max) {
                max = array[i];
            }
        }
        return max;
    }

    public static void main(String[] args) {
        int[] numbers = {3, 7, 2, 9, 4};
        System.out.println("The maximum value is: " + findMax(numbers));
    }
}
```

## Inheritance

**Q9:**  
Create a base class named Animal with a method `makeSound()` that prints a generic sound. Then, create a `subclass Dog` that overrides the method.

```java
class Animal {
    public void makeSound() {
        System.out.println("Generic animal sound");
    }
}

class Dog extends Animal {
    @Override
    public void makeSound() {
        System.out.println("Woof!");
    }
}

public class InheritanceDemo {
    public static void main(String[] args) {
        Animal generic = new Animal();
        Dog dog = new Dog();

        generic.makeSound(); // Output: Generic animal sound
        dog.makeSound();     // Output: Woof!
    }
}
```


## File I/O

**Q10:**  
Write a Java program that reads the contents of a text file and prints them.

```java
import java.io.*;

public class FileReaderExample {
    public static void main(String[] args) {
        String fileName = "example.txt";

        try (BufferedReader reader = new BufferedReader(new FileReader(fileName))) {
            String line;
            while ((line = reader.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            System.out.println("An error occurred: " + e.getMessage());
        }
    }
}
```

**Q11:**  
Write a Java program that writes an array of strings to a file, one string per line.

```java
import java.io.*;

public class FileWriterExample {
    public static void main(String[] args) {
        String[] lines = {"Line 1", "Line 2", "Line 3"};
        String fileName = "output.txt";

        try (BufferedWriter bw = new BufferedWriter(new FileWriter(fileName))) {
            for (String line : lines) {
                bw.write(line);
                bw.newLine();
            }
            System.out.println("File written successfully.");
        } catch (IOException e) {
            System.out.println("An error occurred: " + e.getMessage());
        }
    }
}
```


## Recursion

**Q12:**  
Write a recursive method to compute the factorial of a number.

```java
public class Factorial {
    public static long factorial(int n) {
        if (n <= 1) return 1;
        return n * factorial(n - 1);
    }

    public static void main(String[] args) {
        int number = 5;
        System.out.println("Factorial of " + number + " is " + factorial(number));
    }
}
```

**Q13:**  
Write a recursive method to compute the nth Fibonacci number.

```java
public class Fibonacci {
    public static int fibonacci(int n) {
        if (n <= 0) return 0;
        if (n == 1) return 1;
        return fibonacci(n - 1) + fibonacci(n - 2);
    }

    public static void main(String[] args) {
        int n = 6;
        System.out.println("The " + n + "th Fibonacci number is " + fibonacci(n));
    }
}
```

## Multiple Choice Questions – Answers

1. **B** – To define a blueprint for objects  
2. **C** – int  
3. **A** – new  
4. **A** – A  
5. **A** – Defining multiple methods with the same name but different parameter lists  
6. **B** – Handle errors and other exceptional conditions during program execution  
7. **B** – int[] arr = new int[5];  
8. **C** – The class inherits from another class  
9. **A** – The ability of a variable, function, or object to take on multiple forms  
10. **C** – Recursion involves a method calling itself

