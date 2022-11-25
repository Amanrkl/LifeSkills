# **OOPS Concepts**

* Object-Oriented Programming or OOPs refers to languages that use objects in programming. 
* Object-oriented programming aims to implement real-world entities like inheritance, hiding, polymorphism, etc in programming. 
* The main aim of OOP is to bind together the data and the functions that operate on them so that no other part of the code can access this data except that function.
 

  
##  **Characteristics of an Object Oriented Programming language**

![img](https://media.geeksforgeeks.org/wp-content/uploads/OOPs-Concepts.jpg)

-------

## **Class**


* A Class is a collection of similar types of objects. It is commonly known as the 'blueprint of an object'.

* They are composed of name, attributes, and methods.

* We create individual objects using class. Class is a user-defined data type. Also, a class doesn't occupy any memory.



For example,

we can create a class known as "Plane" which will be its name. It consists of the attributes/fields and methods that each plane will have.

**We can have the following attributes-**

- plane_number
- total_seats
- airline_class
- pilot_name

**Our "Plane" class can contain the following methods-**

- seatAvailability()- this checks how many seats are available or vacant on that plane.
- selectClass()- lets you choose the class in which you want to travel- eg. business class or economy class.

In short, the "Plane" class is a blueprint that represents a plane in a flight management system and we have to create it to represent a real-world entity.

**Syntax:**
```Java
public class Plane {
    //attributes
    //methods
}
```
-------

## **Object**

* Objects are the building blocks of OOP.

* They are real-world entities which have a certain state and behavior. Objects are commonly known as an 'instance of a class'.

For example, 
We can create objects from the 'Plane' class. Each object will have the attributes and methods defined in that class. To create an object of class "Plane" , we use the following syntax.

**Syntax:**
```Java
Plane P1 = new Plane();  
```

So this P1 object will contain its characteristics like its number, total seats, plane class(business, economy, etc.), and pilot. Creating another object of class "Plane" will give it all the attributes that were defined in that class.

* Objects interact with each other and share information. This technique is termed Message Passing.
* Objects are allocated memory space and address too.

-------

## **Encapsulation**

* Encapsulation is the process of binding data and methods together in a single unit.
This is done to protect the data from outside interference and to camouflage the implementation from the rest of the program.

* In encapsulation, data in the class is hidden from other functions and classes. 

* The data is inaccessible by other classes and can be accessed only by that class in which it is declared. Hence, it is also known as 'Data Hiding'.

<center><img src="https://digstraksi.com/wp-content/uploads/2020/11/encapsulation.png" alt="" width="400"/></center>

Example-

```Java
public class Plane{
  private int plane_number; 
}
```

Explanation- We created a private data member plane_number which can only be accessed and changed by that class itself and no other class, it is the process of encapsulation.

### **Advantages of encapsulation-**

* Better control of class attributes and methods
* Class attributes can be made read-only (if you only use the get method), or write-only (if you only use the set method)
* Flexible: the programmer can change one part of the code without affecting other parts
* Increased security of data

------

## **Abstraction**

* Abstraction means displaying only essential information and hiding the details. 

* Data abstraction refers to providing only essential information about the data to the outside world, hiding the background details or implementation.

    - *Abstraction using Classes*
    - *Abstraction in Header files*

* For example, while driving a car, you do not have to be concerned with its internal working. Here you just need to concern about parts like steering wheel, Gears, accelerator, etc.


* Data abstraction simplifies database design.
 

<center><img src="https://media.geeksforgeeks.org/wp-content/uploads/3-173.png" alt="" width="500"/></center>

1. **Physical Level:** 
    It describes how the records are stored, which are often hidden from the user. It can be described with the phrase, “block of storage.” 
     
2. **Logical Level:** 
    It describes data stored in the database and the relationships between the data. The programmers generally work at this level as they are aware of the functions needed to maintain the relationships between the data. 
     
3. **View Level:** 
    Application programs hide details of data types and information for security purposes. This level is generally implemented with the help of GUI, and details that are meant for the user are shown. 

-------

## **Inheritance**

* Inheritance is a property of OOPs in which member functions and data members of one class can be used by another class.
* Reusability of code can be achieved because of inheritance. If we want to create a class that already has some common methods which we want to define within another class, we can use the already existing class as a base class or a parent class and then inherit from it.
* Hence the code can be reused as we don't need to write the same piece of code again and can use it in the derived class or child class.

    - Base class- a class from which member functions and data members are used by another class.
    - Derived class- a class that uses the properties of the base class and can also add its properties.

### **Types of Inheritance-**

    - Single
    - Multiple
    - Multilevel
    - Hybrid
    - Hierarchical 

<center><img src="https://media.geeksforgeeks.org/wp-content/uploads/20200911171738/InheritanceinObjectOrientedProgramming.png" alt="" width="800"/></center>
    

For Example-

```Java
import java.io.*;
  
class Inheritance {
    public static void main(String[] args)
    {
        System.out.println("Inheritance!");
  
        Dog dog = new Dog();
        dog.name = "Bull dog";
        dog.color = "Brown";
        dog.bark();
        dog.run();
  
        Cat cat = new Cat();
        cat.name = "Rag doll";
        cat.pattern = "White and slight brownish";
        cat.meow();
        cat.run();
  
        Animal animal = new Animal();
  
        animal.name = "My favourite pets";
  
        animal.run();
    }
}
  
class Animal {
    String name;
    public void run()
    {
        System.out.println("Animal is running!");
    }
}
  
class Dog extends Animal { 
/// the class dog is the child and animal is the parent
    String color;
    public void bark()
    {
        System.out.println(name + " Wooh ! Wooh !"
                           + "I am of colour " + color);
    }
}
  
class Cat extends Animal {
    String pattern;
    public void meow()
    {
        System.out.println(name + " Meow ! Meow !"
                           + "I am of colour " + pattern);
    }
}
```
-----

## **Polymorphism**

* The word polymorphism means having many forms. 
* It is the ability to create a function, variable, or an object that has more than 1 form.
* Polymorphism is extensively used in implementing inheritance.


**There are two types of polymorphism:**

1. **Compile Time Polymorphism**:

   The overloaded functions are invoked by matching the type and number of arguments. This information is available at the compile time and, therefore, compiler selects the appropriate function at the compile time. It is achieved by function overloading and operator overloading which is also known as static binding or early binding.
   - *Operator Overloading*: The process of making an operator to exhibit different behaviours in different instances is known as operator overloading.
   - *Function Overloading*: Function overloading is using a single function name to perform different types of tasks.

2. **Run-time Polymorphism**:
   Run time polymorphism is achieved when the object's method is invoked at the run time instead of compile time. It is achieved by method overriding which is also known as dynamic binding or late binding


<center><img src="https://static.javatpoint.com/cpp/images/cpp-polymorphism.png" alt="" width="500"/></center>
    


|Compile time polymorphism                                   | Run time polymorphism                                        |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| The function to be invoked is known at the compile time.     | The function to be invoked is known at the run time.         |
| It is also known as overloading, early binding and static binding. | It is also known as overriding, Dynamic binding and late binding. |
| Overloading is a compile time polymorphism where more than one method is having the same name but with the different number of parameters or the type of the parameters. | Overriding is a run time polymorphism where more than one method is having the same name, number of parameters and the type of the parameters. |
| It is achieved by function overloading and operator overloading. | It is achieved by virtual functions and pointers.            |
| It provides fast execution as it is known at the compile time. | It provides slow execution as it is known at the run time.   |
| It is less flexible as mainly all the things execute at the compile time. | It is more flexible as all the things execute at the run time. |

-----
## **Advantages of OOPs**

* It models the real world very well. 
 
* With OOP, programs are easy to understand and maintain. 
 
* OOP offers code reusability. Already created classes can be reused without having to write them again. 
 
* OOP facilitates the quick development of programs where parallel development of classes is possible. 
 
* With OOP, programs are easier to test, manage and debug.

----
## **Disadvantages of OOPs**

* With OOP, classes sometimes tend to be over-generalized. 
 
* The relations among classes become superficial at times. 
 
* The OOP design is tricky and requires appropriate knowledge. Also, one needs to do proper planning and design for OOP programming. 
 
* To program with OOP, the programmer needs proper skills such as design, programming, and thinking in terms of objects and classes, etc. 


----

## **References Section**
* [Documentation from Guru99](https://www.guru99.com/java-oops-concept.html)
* [Documentation from Geeksforgeeks](https://www.geeksforgeeks.org/oops-object-oriented-design/?ref=rp)
* [Video on OOPS Concept](https://www.youtube.com/watch?v=he_5GXDz83g)
* [Documentation from ScalerTopics](https://www.scaler.com/topics/java/oops-concepts-in-java/)
* [Documentation on java OOPs](https://www.w3schools.com/java/java_oop.asp)