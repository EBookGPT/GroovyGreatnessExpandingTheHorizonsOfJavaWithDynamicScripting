# Chapter 7: Object-Oriented Programming with Groovy

Welcome back! In the previous chapter, we learned about control structures in Groovy. Now, in this chapter, we will explore the wonders of object-oriented programming using Groovy.

To do this, we have a special guest joining us, Eric Gamma. Eric Gamma is a renowned computer scientist and co-author of the popular book "Design Patterns: Elements of Reusable Object-Oriented Software".

Together, we will learn how Groovy expands the horizons of Java with its dynamic scripting capabilities that make it easy to use and extend the best practices of object-oriented programming.

We will dive into how Groovy makes it effortless to define classes, interfaces, abstract classes, and more. We will also discover how Groovy adds new features to the Java platform, such as mixins, closures, and the native support of builders, making your code more expressive and concise than ever.

Moreover, we will learn how Groovy's metaprogramming capabilities enable us to write code that is more concise, reusable, and easier to maintain. We will explore how to use these capabilities to add new functionalities to existing classes or to create custom DSLs that better meet our domain-specific needs.

This chapter comes with plenty of code examples and practical exercises to help you gain confidence in using Groovy for object-oriented programming.

Stay tuned for an exciting adventure with Eric Gamma and Groovy's dynamic scripting powers in action!
# The Wizard of Oz and the Object-Oriented Programming in Groovy

Follow the yellow brick road as we take a journey to explore object-oriented programming in Groovy.

Dorothy had learned a lot on her journey so far, but she couldn't shake the feeling there was more to discover. Suddenly, out of nowhere, a man appeared before her.

"Who are you?" asked Dorothy.

The man replied, "I am Eric Gamma, a renowned computer scientist and co-author of the book 'Design Patterns.' I am here to show you the wonders of object-oriented programming using Groovy."

With Eric by her side, Dorothy learned how to define classes and objects in Groovy, how to use inheritance and interfaces, and all the other basic concepts of object-oriented programming.

As they continued down the road, Eric showed Dorothy how to use closures and mixins in Groovy to make their code more expressive and concise. He explained how to use builders and metaprogramming to create DSLs and extend existing classes in ways that Java doesn't allow.

Dorothy was amazed at how easy it was to use Groovy to create complex data structures and how quickly she was able to develop working code using Groovy's dynamic scripting capabilities.

As they approached the Wizard's castle, Dorothy and Eric knew they had gained new powers in their coding ability. They knocked on the door to ask the Wizard for his advice.

"Ah, object-oriented programming with Groovy," said the Wizard. "Truly, it is the perfect way to expand your horizons in Java. And with Groovy's dynamic scripting capabilities, you are sure to find new and innovative ways to solve even the most complex problems."

With the Wizard's blessing, Dorothy and Eric continued on their journey, filled with a newfound appreciation for object-oriented programming and an eagerness to explore the endless possibilities that Groovy offers.

And as they walked into the sunset, Dorothy knew that with the knowledge she gained from Eric Gamma and the power of Groovy, nothing could stand in the way of her coding adventures.
# Explaining the Code for "The Wizard of Oz and the Object-Oriented Programming in Groovy"

In our parable, Dorothy and Eric Gamma journeyed to explore object-oriented programming in Groovy. Let's take a closer look at the Groovy code they might have used to accomplish their goals.

## Defining Classes and Interfaces

To define classes in Groovy, we use the `class` keyword, then the name of the class, and the body wrapped in curly braces. Here's an example:

```groovy
class Wizard {
    String name
    int age
    boolean isHuman = true
    
    void castSpell() {
        println("Abracadabra!")
    }
    
    String getName() {
        return name
    }
}
```

In this example, we defined a `Wizard` class with three properties (`name`, `age`, `isHuman`) and two methods (`castSpell` and `getName`). 

To define interfaces in Groovy, we use the `interface` keyword, then the name of the interface, and the body wrapped in curly braces. Here's an example:

```groovy
interface Flying {
    void fly()
}
```

In this example, we defined a `Flying` interface with one method `fly`.

## Inheritance and Interfaces

To inherit from a parent class in Groovy, we use the `extends` keyword, followed by the name of the parent class. Here's an example:

```groovy
class Witch extends Wizard {
    boolean isGood
    
    void fly() {
        println("I'm flying!")
    }
}
```

In this example, we defined a `Witch` class that extends the `Wizard` class. The `Witch` class has a new property (`isGood`) and implements the `Flying` interface by overriding its `fly` method.

To implement an interface in Groovy, we use the `implements` keyword, followed by the name of the interface. Here's an example:

```groovy
class Pegasus implements Flying {
    void fly() {
        println("I'm galloping through the air!")
    }
}
```

In this example, we defined a `Pegasus` class that implements the `Flying` interface by defining its `fly` method.

## Mixins and Closures

To use mixins in Groovy, we use the `withTraits` method, passing a list of traits as arguments. Here's an example:

```groovy
class Unicorn {
    // properties and methods...
}

trait Horned {
    boolean hasHorn = true
    
    void honk() {
        println("HONK HONK!")
    }
}

def unicornWithHorn = new Unicorn().withTraits(Horned)
```

In this example, we defined a `Unicorn` class and a `Horned` trait. We then created a new instance of the `Unicorn` class with `withTraits`, mixing in the `Horned` trait.

To use closures in Groovy, we define them with the `->` syntax, then we can either pass them as arguments or assign them to variables. Here's an example:

```groovy
def greeting = { name ->
    println("Hello, $name!")
}

greeting("Dorothy") // prints "Hello, Dorothy!"
```

In this example, we defined a `greeting` closure that takes one argument (`name`) and prints a greeting using string interpolation. We then called the closure with the argument `"Dorothy"`, causing it to print `"Hello, Dorothy!"`.

## Metaprogramming and Builders

Metaprogramming in Groovy means that we can modify classes and objects at runtime. Here's an example of using metaprogramming to add a new method to an existing class:

```groovy
class Car {
    // properties and methods...
}

def myCar = new Car()
myCar.metaClass.drive = { speed ->
    println("Driving at $speed mph...")
}

myCar.drive(60) // prints "Driving at 60 mph..."
```

In this example, we defined a `Car` class, created a new instance of it, then used `metaClass` to add a new `drive` method to the instance. We then called the `drive` method on the instance with an argument of `60`. 

To use builders in Groovy, we define them with the `BuilderSupport` class, then use special syntax to create an instance of the builder and call methods with closures. Here's an example:

```groovy
import groovy.util.BuilderSupport

class MyBuilder extends BuilderSupport {
    MyObject object
    
    void setName(String name) {
        object.name = name
    }
    
    void setAge(int age) {
        object.age = age
    }
    
    protected Object createNode(Object name) {
        object = new MyObject()
    }
}

class MyObject {
    String name
    int age
}

def myObject = new MyBuilder().name("Dorothy").age(25).build()
```

In this example, we defined a `MyBuilder` class that extends `BuilderSupport` and creates instances of the `MyObject` class. We defined methods for `setName` and `setAge` that set properties on the `MyObject` instance. We then used special syntax to create an instance of the `MyBuilder` class and call methods with closures to set properties. Finally, we used the `build` method to create a new instance of the `MyObject` class with the set properties.


[Next Chapter](08_Chapter08.md)