---
author:
  name: "Keivan Shah"
date: 2020-03-07
linktitle: L-System
type:
- post
- posts
title: L-System
weight: 10
series:
- Random
---

## Introduction

Today I came a new term: [L-System](https://en.wikipedia.org/wiki/L-system) and I found it quite fascinating. The idea that simple rules can lead to formation of complex structures which might be used to model tree and organism growth and also generate [fractals](https://en.wikipedia.org/wiki/Fractal#Introduction).


{{< image src="/img/lsystem_tree.png" alt="L-System (FF[++F[-F]+F][F[+F]-F][--F[+F]-F])" position="center" style="border-radius: 8px; width: 300px" >}}

From what I understood the Grammar or rules that define the L-System are very simple. It it kindof like formal grammar that people study in Theory Of Computation or similar courses taught in Computer Science. But instead of applying one rule/production at a time, we apply as many rules as possible in parallel. Hence they are called a `Parallel Rewriting System`. But the rules alone are not interesting, it's when we apply some kind of transformation to convert the generated strings into geometric structures, things start getting interesting! 

(__Note__: If you don't understand what I just said, don't worry even I did not understand them before I was forced to go through the courses as part of my curriculum :P)

## Some Terms

Lets now start by defining some terms.

`Alphabets`: The set of characters we will use in our string. Some of them can be replaced by others via the rules and hece called `variables` and some of them cannot be hence called `constant` (or `terminal`)

`Axiom`: Fancy way of saying a starting string!

`Rules`: The way we will replace variables with a number of variables and constants.

So let's start with an example:
```yaml
Alphabets:
  Variables: A, B
  Constants: none
Axiom: A
Rules: (A→AB), (B→A)
```
This is how algae growth was modelled using L-System. Lets simulate how the rules would work:
```yaml
n=0: A
n=1: AB
n=2: ABA
n=3: ABAAB
n=4: ABAABABA
n=5: ABAABABAABAAB
...
```
As you can see the number of terms starts increasing faster as we get to higher number of generations. If you look closely the number of alphabets at each step(population) follows the [Fibonacci Series](https://en.wikipedia.org/wiki/Fibonacci_number) [1,2,3,5,8,12,...]. 

While the above example is interesting, the visualization is not quite that amazing to look at. It does look like a tree as shown here:
```
n=0:               A
                  / \
n=1:             A   B
                /|    \
n=2:           A B     A
             / | |     | \
n=3:         A B A     A B
           / | | | \   | \ \
n=4:       A B A A B   A B  A
```

But as we start getting into more complex rules, we start getting into more interesting visualizations. For more examples you can have a look [here](https://en.wikipedia.org/wiki/L-system#Examples_of_L-systems). 


## Visualizations
Now from the above strings itself its difficult to visualize the models. So we generally use what's called [Turtle Graphics](https://en.wikipedia.org/wiki/Turtle_graphics) to visualize these models. Some of you might have had prior experience with [Logo](https://en.wikipedia.org/wiki/Logo_(programming_language)), this is quite similar and we use the generated strings as input for our graphic generation.

So, assume you are a robot who is been feed instructions by your master.
You and your master have decided on the following instruction set:

`F`: Go forward by a fixed amount

`-`: Rotate Left by a fixed angle

`+`: Rotate Right by a fixed angle

`[`: Save the current orientation

`]`: Return to the last saved orientation

Apart from this any other instructions are ignored. 

You can come up with more complex instructions but for now these alone should suffice to make some really, really complex structures. Don't Believe me?
Have a look at this visualization created by using these rules [here](https://nylki.github.io/lindenmayer/examples/interactive_lsystem_builder/index.html)!

The above link does create some cool looking but it's not that fun to create visualizations by hand is it? So what if there was an automated ready to see visualization without any need to code/understand? 

This is the [link](https://ehrenjn.github.io/LSystems/lsystems.html) you are looking for!


## Links

Here are some more links that are used to create the above visualizations. 

- [Create Tree Images](https://github.com/TanviKumar/treegen)
- [Complete Code for LSytem Implemenatation](https://github.com/nylki/lindenmayer)
- [Awesome Visualization](https://github.com/ehrenjn/LSystems)