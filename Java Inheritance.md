# Java Inheritance

Inheritance in Java, like in the real-world analogy, promotes a hierarchical organization of classes, making the code more structured, reusable, and easier to maintain. It's a fundamental aspect of object-oriented programming in Java.

## Explain to me in layman terms!
> Think of inheritance in Java like passing down family traits from parents to children. In a family, children often inherit certain characteristics from their parents, like hair color, height, or eye color. They have these traits by default because they're part of the family. However, each child also develops their own unique traits and skills that aren't necessarily shared with their parents or siblings.
>
> In Java, 'inheritance' works in a similar way. You have 'classes' which are like blueprints or categories. Imagine a general class like 'Vehicle,' which is a broad category describing properties that all vehicles have, such as the ability to start or stop, and attributes like color or brand.
>
> Now, consider more specific types of vehicles, like 'Car' and 'Bicycle.' These are like the children in our family analogy. They automatically inherit the general properties of the 'Vehicle' class (like starting, stopping, color, brand). So, just by being a 'Car' or a 'Bicycle,' they already have certain features.
>
> But cars and bicycles also have their own unique features. For instance, a car might have an attribute like the number of doors, and a method to open and close these doors, which a bicycle doesn't need. Similarly, a bicycle might have attributes like the number of gears, which aren't relevant for a car.
>
> In Java, this inheritance concept allows programmers to create new classes based on existing ones, reducing the need to write new code from scratch. It's like giving a head start by passing down traits, but still allowing for uniqueness and individuality where needed."

## Real-World Analogy for Inheritance
1. **Family Analogy**: Think of inheritance in terms of a family tree. Children inherit certain traits or properties from their parents. For instance, a child might inherit their parents' eye color, hair color, or height. However, each child might also have unique characteristics that are not shared with their siblings.

2. **Extension of Traits:** Inheritance is not just about receiving traits; it's also about extending or adding to them. Children might not only inherit traits from their parents but also develop new ones or modify them.

3. **Efficiency and Relationship:** Inheritance shows a clear relationship (like that of a parent to a child) and avoids repetition. Instead of teaching each child everything from scratch, they automatically learn or inherit certain things from their parents, which is more efficient.

## Inheritance in Java
1. **Basic Concept:** In Java, inheritance is a mechanism where a new class, known as a subclass, is derived from an existing class, known as a superclass. The subclass inherits fields and methods from the superclass.

2. **Code Reusability:** It allows for the reuse of code, avoiding duplication. The subclass can use the fields and methods of the superclass, and it can also have its own unique fields and methods.

3. **Extensibility:** Inheritance makes it easy to extend the existing code. A subclass can add more functionalities on top of what it has inherited from the superclass.

## Code Sample

> **Explanation:** In this example, Employee is a subclass of Person. It inherits the fields and methods (`name, age, setName(), setAge(), getName(), getAge()`) from Person. Additionally, it extends the functionality by adding a new field (salary) and a new method (getSalary()).

#### Person Class [Parent Class]
```java
// Superclass
public class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
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
}
```

#### Employee Class [Child Class]
```java
// Subclass
public class Employee extends Person {
    private double salary;

    public Employee(String name, int age, double salary) {
        super(name, age); // Calling the constructor of Person
        this.salary = salary;
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
        Employee emp = new Employee("John", 30, 50000);
        System.out.println("Name: " + emp.getName() + ", Age: " + emp.getAge() + ", Salary: " + emp.getSalary());
    }
}
```
> This is conider the `main method` class, which is to demonstrate how objects of the subclasses can be created and how their methods can be used, showcasing inheritance and the use of getters and setters in Java.

## More Examples (With two children)

### Example 1: Product Catalog System
This example shows a product catalog system with Product as a superclass and Book and Electronics as subclasses.

#### Product Class [Parent Class]
```java
public class Product {
    private String name;
    private double price;

    public Product(String name, double price) {
        this.name = name;
        this.price = price;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public double getPrice() {
        return price;
    }

    public void setPrice(double price) {
        if(price >= 0) {
            this.price = price;
        } else {
            System.out.println("Price must be non-negative.");
        }
    }
}
```

#### Book Class [Child Class of Product]
```java
public class Book extends Product {
    private String author;

    public Book(String name, double price, String author) {
        super(name, price);
        this.author = author;
    }

    public String getAuthor() {
        return author;
    }

    public void setAuthor(String author) {
        this.author = author;
    }
}
```

#### Electronics Class [Child Class Product]
```java
public class Electronics extends Product {
    private String manufacturer;

    public Electronics(String name, double price, String manufacturer) {
        super(name, price);
        this.manufacturer = manufacturer;
    }

    public String getManufacturer() {
        return manufacturer;
    }

    public void setManufacturer(String manufacturer) {
        this.manufacturer = manufacturer;
    }
}
```

#### Main Class 
```java
public class Main {
    public static void main(String[] args) {
        // Creating a Student
        Student student1 = new Student("Alice", 21, "Computer Science");
        System.out.println("Student Name: " + student1.getName() + ", Age: " + student1.getAge() + ", Major: " + student1.getMajor());

        // Creating a Professor
        Professor professor1 = new Professor("Dr. Smith", 45, "Physics");
        System.out.println("Professor Name: " + professor1.getName() + ", Age: " + professor1.getAge() + ", Department: " + professor1.getDepartment());
    }
}
```

### Example 2: University Class Hierarchy
This example involves a university system with Person as a superclass and Student and Professor as subclasses.

#### Person Class [Parent Class]
```java
public class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        if(age > 0) {
            this.age = age;
        } else {
            System.out.println("Age must be positive.");
        }
    }
}
```

#### Student Class [Child Class Person]
```java
public class Student extends Person {
    private String major;

    public Student(String name, int age, String major) {
        super(name, age);
        this.major = major;
    }

    public String getMajor() {
        return major;
    }

    public void setMajor(String major) {
        this.major = major;
    }
}
```

#### Professor Class [Child Class Person]
```java
public class Professor extends Person {
    private String department;

    public Professor(String name, int age, String department) {
        super(name, age);
        this.department = department;
    }

    public String getDepartment() {
        return department;
    }

    public void setDepartment(String department) {
        this.department = department;
    }
}
```

#### Main Class
```java
public class Main {
    public static void main(String[] args) {
        // Creating a Book
        Book book1 = new Book("The Alchemist", 9.99, "Paulo Coelho");
        System.out.println("Book Name: " + book1.getName() + ", Price: $" + book1.getPrice() + ", Author: " + book1.getAuthor());

        // Creating an Electronics item
        Electronics electronics1 = new Electronics("Smartphone", 299.99, "Samsung");
        System.out.println("Electronics Name: " + electronics1.getName() + ", Price: $" + electronics1.getPrice() + ", Manufacturer: " + electronics1.getManufacturer());
    }
}
```
