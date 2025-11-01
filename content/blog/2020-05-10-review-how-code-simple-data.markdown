---
title: "Course Review: How to code simple data"
categories:
  - teachyourselfcs
date: 2020-06-10
url: /htcsd/
rating: 3.5
toc: true
header:
  title: "Offered by"
  text: "The University of British Columbia via edX"
  description: "A great course for introduction to Systematic programming design but taught in a pedantic manner."
  link_title: "Course Page"
  link_text: "https://www.edx.org/course/how-to-code-simple-data"
tags:
  - mooc
  - ossu
  - re
---

How to code simple data is based on the "How to Design Programs" book which is inspired by "Structure and Interpretation of Computer Programs".

The course teaches Systematic programming design starting with basic program requirements. Also, it introduces rudimentary test driven development. Scheme is the preferred language for the course.

Overall, the course was too slow and repetitive. I think the presumed audience of the course is a total beginner to programming.

The course introduces recipes for data definition, functions and arbitrary data types.


## A quick summary of the course.

## 1. Function recipe.
  * The recipe to write a function is as follows.
  * Signature, purpose, stub
    * Signature:  (input type (separated by spaces) -> output type)
    * Purpose: What the function should produce? (Keep it concise)
    * Stub
      * Syntactical empty method return same data type.
        * If Output is 0 -> stub produces number as 0 is number.
  * Check-wrapped examples (Tests)
    * Write example for each edge(boundary case).
    * Write example for every behaviour in the function.
      * `EG?`
  * Template and inventory
    * Use `data driven templates`
  * Write function
  * Test and debug until correct



## 2. Testing Guidelines
### When a test is incorrect.
  - Check definition
  - Check if test is wrong.
  - Check if both are wrong.


### How to deal with a new test case/boundary condition
  - Write a `new test`.
  - Update the affected parts of the design.
    - often involves purpose and/or function definition.
  - Might involve editing existing test or even the signatures.



## 3. Templates

### Enumeration
  - Enumeration is used when we have a `fixed number of distinct items.`
  - The data is usually `one of`.
    - Eg. `traffic light` is *one of* red, green, yellow.
    - 

### Data definitions
   - Describes 
     - How to form `data` of a `new type`
     - How to represent `information` as `data`
     - How to interpret `data` as `information`
     - `Template` for operating on data
   - We represent real world information with `data` in the program.
   - Yellow might be represented with 0 in the program.
   - Helps functions with
     - Restricting data
       - Consumed
       - Produced
     - Helps generate `examples`
     - provides template.

#### Various Data definitions
  - Atomic non-distinct
    - Intervals
  - Atomic Distinct.
    - Enumeration

#### Example: Data definition
* Data definition for Enumeration
  * An example for Traffic lights.  
```
TLcolor is one of 
;; - 0
;; - 1
;; - 2
;; interp. color of a traffic light - 0 is red, 1 yellow, 2 green
```
* Data definition for 

### Interpretation
  - Interpretation helps to understand the `association` between data definition and information.
  - It is the link between the information and its representation (Data).


## 4. How to Design Worlds
Designing world means an interactive program with a GUI.
It is divided into two phases, each of which has sub-parts:

### 4.1 Domain analysis (on a paper)
  - Sketch various program scenarios
    - Imagine the program at various stages like start, middle, end. 
  - Identify constants
  - Identify variables.
  - Identify big-bang options (events, handlers)


### 4.2 Build the actual program
  - Program Constants first.
  - Data definitions using HtDD
  - Functions using HtDF
      -  Main
      - wish list entries for big-bang handlers
  - Work through wish list until done

## Phase1: Domain analysis
Do a domain analysis by hand-drawing three or more pictures of what the world program will look like at different stages when it is running.

Use this picture to 
  - identify `constant` information 
      - the height and width of screen
      -  color of the background
      -  the background image itself
      -  the length of a firework's fuse
      -  the image for a moving cat and so on.
  - Identify `variables`
      -  position of a firework
      -  the color of a light
      -  the number in countdown etc.
  - Identify which big-bang options the program needs.

## How to add new requirements
  - Make changes in the analysis(model).
  - Run through the program catching it up to new analysis.
  - Introduce new constants and then we change functions and tests.


## 5. How to design

### compound data
  - Compound data contains two values (First and Last name)
  - When designing the program, put enough effort to think about the `edge cases.`


### Function
  - Functions should be `modular`.
  - A function should perform `one task` only.
    - It makes testing easier.
    - Decrease chance of error and complexity.

