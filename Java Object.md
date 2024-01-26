# Java Object

## Explain to me in layman terms!
> Think of a Java object like a real-world object, something you can see and interact with, like a car, a book, or a phone. These real-world objects have two main features: they have characteristics (like color, size, or weight), and they can perform actions (like a car can drive, a book can be opened, a phone can make calls).
>
> In Java, an object is similar. It's a basic unit of what we call 'Object-Oriented Programming.' Just like a real-world object, a Java object has:
> 
> - **Characteristics:** These are like the details about the object. In Java, we call them 'attributes' or 'fields.' For example, if our object is a 'Car,' its attributes might be its color, brand, or the number of doors it has.
>
> - **Actions:** These are things the object can do. In Java, we call these 'methods.' Continuing with our 'Car' example, some methods might be 'startEngine,' 'stopEngine,' or 'honkHorn.'
>
> But where do these objects come from? Imagine a blueprint or a recipe. In Java, this blueprint is called a 'class.' It's not an object itself, but it tells Java how to create an object. The class defines what attributes and methods an object will have. So, you can think of a class as a blueprint for a house, and an object as the actual house built using that blueprint.
> 
>For instance, we might have a 'Car' class in Java. This class is a blueprint that describes what every car object will look like and what it can do. When we create a specific car object from this class, we're building a specific car with its own color, brand, and behaviors, based on the general blueprint.
>
> So, in short, a Java object is like a real-world object with its own set of characteristics and actions, and it is created from a blueprint known as a class.

## What is an Object in Java?
1. **Instance of a Class:** An object is an instance of a class. A class is like a blueprint, and an object is a concrete manifestation of that blueprint.

2. **Attributes and Behavior:** Objects have attributes (also known as properties or fields) and behaviors (methods or functions). Attributes represent the state of an object, while behaviors represent what an object can do.

3. **Real-world Entity:** Objects are often modeled after real-world entities. For example, if you have a class Car, an object of this class could represent a specific car, like a Toyota Camry with specific features.

## Java Object Structure
1. **Class Definition:**
    - A class is the blueprint for objects. It defines the structure and behavior of the objects.
2. **Attributes (Fields):**
    - Attributes represent the properties or state of the object.
    - In Java, it's common practice to declare attributes as private for encapsulation, which means they cannot be accessed directly from outside the class.
3. **Constructor:**
    - A constructor is a special method used to initialize new objects.
    - It typically sets initial values for the object's attributes.
4. **Accessors (Getters and Setters):**
    - **Getters:** 
        - Methods that allow reading the values of an object's attributes. They are used to access the value of private fields from outside the class.
    - **Setters:** 
        - Methods that allow modifying the values of an object's attributes. They provide a controlled way to change the state of an object.
    - Using getters and setters is a fundamental part of Java's encapsulation principle. They allow for controlled and safe read/write operations on the attributes.
5. **Methods:**
    - Methods define the behavior or actions of the objects.
    - They often manipulate the object's attributes or perform other relevant operations.

## Example

> In this enhanced example, Car is the class with private attributes (color and model), accessor methods (getters and setters), a constructor, and a method (displayInfo()). This structure demonstrates the encapsulation and controlled access and modification of object state, which are key concepts in object-oriented programming in Java.

```java
public class Car {
    // Attributes (private for encapsulation)
    private String color;
    private String model;

    // Constructor
    public Car(String color, String model) {
        this.color = color;
        this.model = model;
    }

    // Getters
    public String getColor() {
        return color;
    }

    public String getModel() {
        return model;
    }

    // Setters
    public void setColor(String color) {
        this.color = color;
    }

    public void setModel(String model) {
        this.model = model;
    }

    // Method
    public void displayInfo() {
        System.out.println("Car Model: " + model + ", Color: " + color);
    }
}
```

> This `main method` class is used to create the `Car` object and accessing the attributes. Always remember that you need a `main` method class to use the object you created.
```java
public class Main {
    public static void main(String[] args) {
        // Creating an object of Car
        Car myCar = new Car("Red", "Toyota");

        // Accessing attributes via getters
        System.out.println("Original Color: " + myCar.getColor());

        // Modifying attributes via setters
        myCar.setColor("Blue");
        System.out.println("New Color: " + myCar.getColor());

        // Calling a method on the object
        myCar.displayInfo();
    }
}
```

## What are accessors?
> Imagine you have a personal diary where you keep all your secrets. Naturally, you wouldn't want just anyone to read it or change what's written inside. In the world of computer programming, specifically in a language called Java, we deal with something similar called 'objects' (think of them as digital diaries). Now, to safely manage what's inside these objects, we use special tools called 'accessors.' There are two types: 'getters' and 'setters.' A 'getter' is like asking a trusted friend to read something from your diary and tell you what it says. It allows you to safely look at what's inside without directly opening the diary. On the other hand, a 'setter' is like asking that friend to write something in your diary. It's a safe way to change or add information. Both of these tools ensure that your diary’s contents are accessed and modified in a controlled and secure way, preventing any accidental mishandling or unauthorized access. In Java, using getters and setters is a fundamental practice to maintain the integrity and confidentiality of the data within these digital diaries.

### Getters `getXXXX()`
1. **Real-World Analogy:** Using company department analogy, suppose there is information that needs to be shared but in a controlled way. In such cases, a department might have a procedure or a specific person (like a manager) who can provide this information upon request, ensuring that the data is given out in a correct and intended manner.

2. **Purpose in Java:** Accessor methods (commonly known as getters) serve this role. They are public methods that allow other classes to get the value of private fields, but in a controlled way defined by the class itself.

3. **Benefits:** With accessors, you can control how and what data is provided to the outside. You can apply checks, format the data, or compute results from multiple fields. This maintains the integrity of the data and the encapsulation of the class.

### Setters `setXXXX()`
1. **Real-World Analogy:** Imagine you have a safety deposit box in a bank. You can't just modify the contents of your box from home; you need to go to the bank and follow a specific procedure to access and change what's inside. This procedure ensures that changes are made securely and correctly.

2. **Purpose in Java:** Similarly, setter methods (commonly known as setters) in Java are used to modify the values of private fields. Like getters, setters provide a controlled way to change the state of an object, but they enforce rules or conditions for how these fields can be modified.

3. **Benefits:** Setters allow the encapsulating class to control and potentially validate any changes to its internal state. This ensures the integrity of the object, preventing it from getting into an inconsistent or invalid state.

## More Examples

Each example demonstrates how to:

1. Define a class with private atrributes.
2. Use a constructor to initialize the object's state.
3. Implement accessor methods (getters) to safely retrieve field values.
4. Implement accessor methods (setters) to safely set field values.
5. Create an object and use its accessor methods to retrieve and display information.

### Example 1: Book
#### Book Class
```java
public class Book {
    private String title;
    private String author;
    private int pages;

    public Book(String title, String author, int pages) {
        this.title = title;
        this.author = author;
        this.pages = pages;
    }

    public void setTitle(String title) {
        this.title = title;
    }
    
    public String getTitle() {
        return title;
    }

    public void setAuthor(String author) {
        this.author = author
    }

    public String getAuthor() {
        return author;
    }

    public void setPages(int pages) {
        this.pages = pages;
    }

    public int getPages() {
        return pages;
    }
}
```
#### TestBook Class
```java
public class TestBook {
    public static void main(String[] args) {
        Book book1 = new Book("1984", "George Orwell", 328);
        System.out.println("Book: " + book1.getTitle() + ", Author: " + book1.getAuthor());
    }
}
```

### Example 2: Student 
#### Student Class
```java
public class Student {
    private String name;
    private int age;
    private double gpa;

    public Student(String name, int age, double gpa) {
        this.name = name;
        this.age = age;
        this.gpa = gpa;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }

    public void setAge(int age) {
        this.age = age
    }

    public int getAge() {
        return age;
    }

    public void setGpa(double gpa) {
        this.gpa = gpa;
    }

    public double getGpa() {
        return gpa;
    }
}
```

#### TestStudent Class
``` java
public class TestStudent {
    public static void main(String[] args) {
        Student student1 = new Student("Alice", 20, 3.5);
        System.out.println("Student: " + student1.getName() + ", Age: " + student1.getAge() + ", GPA: " + student1.getGpa());
    }
}
```

### Example 3: Employee
#### Employee Class
```java
public class Employee {
    private String name;
    private String department;
    private double salary;

    public Employee(String name, String department, double salary) {
        this.name = name;
        this.department = department;
        this.salary = salary;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }

    public void setDepartment(String department) {
        this.department = department;
    }

    public String getDepartment() {
        return department;
    }

    public void setSalary(double salary) {
        this.salary = salary;
    }

    public double getSalary() {
        return salary;
    }
}
```

#### TestEmployee Class
```java
public class TestEmployee {
    public static void main(String[] args) {
        Employee emp1 = new Employee("John Doe", "IT", 75000);
        System.out.println("Employee: " + emp1.getName() + ", Department: " + emp1.getDepartment() + ", Salary: $" + emp1.getSalary());
    }
}
```
