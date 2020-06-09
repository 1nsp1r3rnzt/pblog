---
title: "Clean Code: A Handbook of Agile Software Craftsmanship"
excerpt: "A Handbook of Agile Software Craftsmanship Summary"
date: 2018-05-22
header:
  role: "Author"
  image: /assets/images/books/clean-code.jpg
  image_alt: "logo"
  text: "Robert Cecil Martin"
  description: "This book is a must for any developer, software engineer, project manager, team lead, or systems analyst with an interest in producing better code.
"
type: "book"
toc: true
tags:
  - programming
url: /notes/clean-code/

rating: 5
---

Clean Code is one of the top 5 recommended reading for Software Developers.
The Book is divided into 3 parts. 

1) principles, practices of writing clean code.   
2) Case studies (take days to complete).       
3) Nutshell containing heuristics.   

## Introduction
There are two parts to learning:
1) Craftsmanship 
2) Knowledge.

Learning to Clean Code is hard work.
It requires practice.

As the mess builds, the productivity of the team continues to decrease, asymptotically approaching zero. 

The time spent on reading vs writing code is 10:1.
So, code should be written as clean as possible.

## Meaningful Names

### use intention revealing names
The name should tell you why it exists.   
Eg. of bad name.
`int d`

Eg of good name.
`int elapsedTimeInDays;`

### Avoid disinformation
Don't name variable with reserved keyword like `accountList` unless it is really a `list`.    
Name it `accountGroup`    

### Make meaningful distinctions.
Programmer make mistakes when they write variable names solely to satisfy the compiler or interpreter.
Don't add noise words or random numbers to make distinct variables.

#### Number series naming
it is non-informative as it provides no context.
`(a1,a2...an)`

#### Noise words
Noise words are words like `variable` `table` which adds no additional meaning to the variable name.

#### Use distinct names
Names such as `money` and `moneyAccount` are difficult to distinguish and creates ambiguity.

#### Use pronounceable Names
Use names like `generationTimestamp` instead of `genymdnms`

#### Use searchable Names
Use searchable names instead of constants.
Use `MAX_CLASSES_PER_STUDENT` instead of 7

#### Avoid Encodings

#### Member prefixes
Avoid member prefixes.
Your class should be small enough to that you don't need them.
Example.. use `String description` instead of `String m_desc`

#### Interface and implementation
The `I` in `IShapeFactory` provides too much information.
Its better to name it as `ShapeFactory`.
Its better to encode the implementation with either `ShapeFactoryImpl` or `CShapeFactory`

#### Avoid mental Mapping
Use single letters i,j,k when the scope is very small.
This adds the overhead of mapping the letters to its original context.
> Clarity is the king.


### Class Names
Class name should be a noun or noun phrase like `Customer` , `WikiPage`
`Account` `AddressParser`.
Avoid words like `Manager`, `Data`, `Processor` in the name of a class.

### Method Names
Methods should have verb or verb phrase. 
`postPayment`, `deletePage`, `save`

#### When constructors are overloaded
`Complex fulcrumPoint` = Complex.FromRealNumber(23.0);

is better than    
`Complex fulcrumPoint` = new Complex(23.0);
so, use static methods for this. 
> Make constructor private to enforce this.

### Don't use slangs or cultural jokes
* Use `deleteItems` instead of `holyHandGrenades`.    
* use `kill` instead of `whack`

### Pick one word per concept
Be clear.
* The words `fetch`, `retrieve` and `get` imply same meaning.    
* Pick one word per abstract concept.


### use solution Domain Names
* Use names from computer science.    
* Most programmer would know about JobQueue or AccountVisitor implying visitor pattern.


### Use problem domain names
* Separating solution and problem domain concepts is part of the job of a good programmer.
* Use names from problem domain when there is no programming name for what you are doing.

