# Polymorphism & Composition Homework - Quiz

# Polymorphism

1. What does the ___word___ 'polymorphism' mean?

Polymorphism (many shapes) is a computer programming term that refers on how different classes that inherit from a class or implements an interface can "take many shape".

2. What can we use to implement polymorphism in Java?

Abstract Classe (inheritance from them) and interfaces

3. What does it mean when we apply polymorphism to OO design? Give a simple Java example.

If a method was supposed to take an object from a parent class (or an especific interface), any object that includes this interface or inherits from this class could fit on the memory spot allocated for it, even if it is not that class (but a subclass of it).

___Example___:

```
public class Computer {
private int ram;
private int hddSize;

private IOutput outputDevice;
private IInput inputDevice;

public Computer(int ram, int hddSize, IOutput outputDevice) {
       this.ram = ram;
       this.hddSize = hddSize;
       this.outputDevice = outputDevice;
       this.inputDevice = null;
   }
}
```

We could assign any object implementing interface IOutput on the this.outputDevice parameter.

4. How many 'forms' can an object take when using polymorphism?

Using inheritance one, using interfaces, as many interfaces you have

5. Give an example of when you could use polymorphism.

When you want to have, for example, an arraylist of Components (abstract class) that could be different classes (a Mouse, a Keyboard, a Monitor...)

# Composition

6. What do we mean by 'composition' in reference to object-oriented programming?

When a object is compose of many different classes as oposed to be described as "an instance of" a higher class. "A Car is composed of parts" oposed to: "A polar bear is a kind of Bear"

7. When would you use composition? Provide a simple example in Java.

When I want an object to use methods reserved to an specific interface, but I don't want to implement that interface on the object. For example, having a Wizard that could fly on a flying object, but I don't want it to implement 'IFlyable' on him.

```java
//Wizard.java

package wizard_management.people;
import wizard_management.behaviours.*; //NEW

public class Wizard {
 String name;
 private IFlyable ride; //UPDATED

 public Wizard(String name, IFlyable ride){ //UPDATED
   this.name = name;
   this.ride = ride; //UPDATED
 }

 public String getName(){
   return this.name;
 }

 public IFlyable getRide(){ //UPDATED
   return this.ride;
 }

 public String fly(){
   return this.ride.fly(); //UPDATED
 }

}
```

8. What is/are the advantage(s) of using composition?

You can let objects to use methods reserved to different interfaces, and also, implementing interfaces is not limited to one (like inheritance) so you could implement many interfaces using this approach.

9. What happens to the behaviours when the object composed of them is destroyed?

Nothing. They're independent.
