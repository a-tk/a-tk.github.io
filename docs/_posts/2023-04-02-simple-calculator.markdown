---
layout: post
title:  "C# Calculator"
date:   2023-04-02 20:13:02 -0700
tags: [Mermaid]
categories: New Project
mermaid: true
---

A calculator is a great way to gain familiarity with a new language or technique.

In my career I have written plenty of Java, but never professionally written C#.

From a school example, I remember that the syntax and semantics of the language
is very similar to Java. So I'm going to do a small calculator project as a demonstration. 

## Requirements

My calculator has the following requirements:

  1. Reverse Polish Notation
  2. 4 functions (add, subtract, multiply, divide)
  3. Real number range, up to +/- Doule.MaxValue
  4. Execution and result history
  5. GUI to display input, output, errors and settings
  6. Proper error handling for Div/0
  7. Proper Automated Testing

Possible Future Requirements to have in mind

  1. More execution modes than RPN
  2. Additional functions, like sqrt and exponential
  3. Persist history on restart

## Architecture

Since I am using C# for this, it will use the .NET framework. This will provide a
simple way to build a GUI for the calculator, as well as supply access to useful
library of functionality. 

There will be 4 logical components. The GUI interface, the Execution Engine, and the Execute
Stack. With a purely RPN design, we can use a simple stack to store the data. However, 
we might need to implement other execution paradigms, and to do so at a later
date might require a re-architecture.

To prevent this, we are going to start looking at some examples of how simple (not scientific or
programmable calculators) behave. 

### Examples

#### RPN

Example A

    1 2 + 3 /
    Result is 1

In this example, the user will need to press an enter key to input numbers not immediately followed
by a function key. They'll press 1 ENTER 2 + 3 /.

Upon each press of a function key, a computation is displayed for the user. After the + is pressed, 
They'll see a 3, and after the /, they'll see a 1 (the result). 

#### Standard Arithmetic

Example A

    ( 1 + 2 ) / 3
    Result is 1

Example B

    1 + 2 / 3
    Result is 1.66666....


### Program Design

Now that we understand some common expressions (note that the parenthesis doesn't need a
command, its simply part of a tree structure), we can move forward creating our program architecture. 

There is a requirement for a GUI, as specified above, and we'll need some kind of 'backend'
for that GUI that will accept commands from it, and perform some operations, and 
return values to it, including errors.

In addition to that, there needs to be a datastructure that can support the execution 
paradigms. Given the models above, we'll use a tree structure. In the RPN case, 
the tree is very simple indeed. Having an execution support class makes sense for 

Therefore, the architecture requires 4 logical components: 

  1. GUI
  2. Service for the GUI
  3. Execution Class
  4. Tree datastructure




