---
title: Model Checking, What it is and why to use it
categories:
- Software-Architecture
feature_image: "https://picsum.photos/2560/600?image=872"
---

After finish the implementation of the so (or sometimes not) desired system, how do you know that it is (and behave) exactly as expected? Requirements change, people can forget, communications problems occur even in the best companies.

<!-- more -->

<small>
*WIP:* This article is a working in progress. There could be some errors. I will also add some images to help the understanding :)
</small>

## What is Model Checking?

**Model checking** is the technique to check if the behavior of the **State Model** of your system work as expected and notify any **violation**. 

## What is a State Model?

The **State Model** is an abstract **State Machine** that can be in one or various states, so the **Model checker** can verify if the state mode conforms with expected behavior and properties.

### Modeling phase

Describe all possible states and properties to be checked against your system.

You can use Unit Tests, BDD, etc. There are many tools out there to help you.

### Running phase

Run the necessary test of your **State Machine** against the expectations described on the previous phase.

### Analysis phase

Check the results of the previous phase. If the State Model does not conforms with certain behavior or property we ha a **Violation** AKA **Counterexamples**. 

The output of a **Counterexample** must show you exactly how to reproduce the violation, so you system can be fixed.


## When should I do a Model checking?

Always **after implementation** and **before production deploy**. It is untrue that a Software can be perfect during the planning or modeling phases. The beauty of software is that it can change many times before and after its implementation. Business needs flexibility, but we (developers) need to make sure it will work as expected after all those changes.
