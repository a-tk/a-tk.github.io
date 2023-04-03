---
layout: post
title:  "C# Calculator"
date:   2023-04-03 20:13:02 -0700
categories: New Project
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

### Block Diagram 

```mermaid
  graph TD;
    GUI
    Executer 
    Execute Stack
  ```
