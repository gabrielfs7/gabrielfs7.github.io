---
title: Object Modeling Principles
categories:
- Software-Architecture
feature_image: "https://picsum.photos/2560/600?image=87"
---

There are 4 important *Principles* when modeling objects! They are the **ADEG**. Yes, as always I have invented a word to memorize them! Lets talk about them.

<!-- more -->

<small>
*WIP:* This article is a working in progress. There could be some errors. I will also add some images to help the understanding :)
</small>

An brief history review, first:

# 1960's

During the 1960's there was the **Imperative Paradigm** where programs basically were composed of routines that interact with other small routines and shared the same **Global Variables**. The processing were really expensive and the focus were most about hardware capacity than in the solution itself. 

This was the age of [Cobol](https://en.wikipedia.org/wiki/COBOL), [Fortran](https://en.wikipedia.org/wiki/Fortran) and others **Imperative Programing** languages.

# 1970's 

In this period of time we had a huge progress and now developers could use **local variables** without being worried about mess up the system by trusting in shared global variables. 

Also the first scratch of what would become an "object" in the future was created, the **Abstract Type** or Structs.

In this time, programs started being divided in multiple files and C header file was introduced.

This was the age of [Algol](https://www.computerhope.com/jargon/a/algol.htm), [C](https://www.learn-c.org/), [Pascal](https://www.freepascal.org/advantage.var) and other programing languages that allowed developers to use Abstract Types and local variables.

**C Struct example:**

``` js
struct Person
{
    char name[50];
    int citNo;
    float salary;
};
```

# 1980's to now

Finally the concept of object was applied to program languages and became possible split the problem and classes and methods and became easier to use business language in the code.

As examples of languages we can mention [Java](https://en.wikipedia.org/wiki/Java_(programming_language)), C++, C# among many others object oriented languages.

**Java class example**

``` js

public class Car
{
    private String brand;
    private String model;

    public Car(String brand, String model)
    {
        brand = brand;
        model = model;
    }

    
    public String getModel()
    {
        return model;
    }

    public void setModel(String model)
    {
        model = model;
    }

    public String getBrand()
    {
        return brand;
    }

    public void setBrand(String brand)
    {
        brand = brand;
    }
}
```

## 1. Abstraction
 
The abstraction principle consists in "abstract" the general business needs into classes and methods without concert too much about details. 

At this point the idea is not mature yet and the goal is to translate the initial problem to a high level code base.

## 2. Decomposition

As we start digging we find more business needs we did not think before the problem becomes bigger and bigger.

Instead of get crazy, we start breaking down (or decomposing) the previous classes in more and specialized ones. We create abstractions, interfaces, new entities are discovered and so on. 

The goal here is to go deep in the details by decomposing the big problem in smaller and controlled solutions.

### Types of Decomposition relations

#### Association

- Relationship is optional
- Associated classes are completely independent.

{% include post-figure.html image="uml-class-diagram-association.png" caption="UML class diagram Association example" %}

#### Aggregation

- Weak **has-a** relationship.
- One object does not need to have the other to exist.

{% include post-figure.html image="uml-class-diagram-aggregation.png" caption="UML class diagram aggregation example" %}

#### Composition

- Strong **has-a** relationship
- Associated classes are **completely dependent**. Example, an object **Human** always has an object **Brain** associated, otherwise it cannot exist.

{% include post-figure.html image="uml-class-diagram-composition.png" caption="UML class diagram composition example" %}


## 3. Encapsulation

When decomposing the classes we start creating new methods and attributes that concern only for those classes. It is time to use inheritance, abstraction and access modifiers to to restrict for them. 

We have some conventions for this like "getters" and "setter" methods, besides today they are controversial in some cases after the surge of Object Calisthenics.


## 4. Generalization

When a class inherits behavior or interface from a superior (super) class we call it **Generalization**. It can happen in two ways:

{% include post-figure.html image="uml-class-diagram-generalization.png" caption="UML class diagram Generalization example" %}

### By Abstraction 

An abstract class (cannot be instantiated) has some methods (behavior) or properties that can be shared with the **child classes**.

### By Interface

An interface (or Contract) is created, so the classes that implement this interface can entirely manage the internal implementation of the interface's expected behavior.

Then comes in place the **Polymorphism**.
