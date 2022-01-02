---
author:
  name: "Keivan Shah"
date: 2020-03-07
lastmod: 2022-01-02
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

Today I came across a new term: [L-System](https://en.wikipedia.org/wiki/L-system) and I found it quite fascinating. The idea that simple rules can lead to the formation of complex structures that might be used to model tree and organism growth and also generate [fractals](https://en.wikipedia.org/wiki/Fractal#Introduction) is intriguing to me.


[{{< image src="/img/lsystem_tree.png" alt="L-System (FF[++F[-F]+F][F[+F]-F][--F[+F]-F])" position="center" style="border-radius: 8px; width: 300px" >}}](/L-System/)

This image was created with help of L-System and it's visualization. It can also be used to model far more complicated tree structures. If you are interested you can checkout how I created this image **[here](/L-System/)** and the code for the same can be found [here](https://github.com/keivan-shah/L-System).

From what I understood, the Grammar or rules that define the L-System are very simple. It is kind of like [formal grammar](https://en.wikipedia.org/wiki/Formal_grammar) that people study in [Theory Of Computation](https://en.wikipedia.org/wiki/Theory_of_computation) or similar courses taught in Computer Science (Actually, not only kind of, L-Systems are a strict subset of formal grammar). But instead of applying one rule/production at a time, we apply as many rules as possible in parallel. Hence L-Systems are also called `Parallel Rewriting Systems`. But the rules and generated strings by itself are not that interesting, it's when we apply some kind of transformation to convert these generated strings into geometric structures, things start getting interesting! For now, I don't want to dive into the depths of formal grammar and it's relation with L-Sytems, maybe in the future? 🤷

(**Note**: If you don't understand what I just said, don't worry even I did not understand them before I was forced to go through the courses as part of my curriculum :P, But rest assured it's easy to understand!)

## Some Terms

Lets now start by defining some terms.

`Alphabets`: The set of characters we will use in our string. Some of them can be replaced by others via the rules and hence called `variables` and some of them cannot be hence called `constant` (or `terminal`). Examples we can use any character in the English alphabet like "A" or "B" or even some other fancy characters like "[" or "α".

`Axiom`: Fancy way of saying a starting string! It's just a string made of the characters defined in our alphabet. Example: "A"

`Rules`: The fixed way in which we will replace variables with other variables and constants. Example: Take every instance of "A" and replace it with "AB"[ Written as: (A→AB)]

So let's start with the example:

```yaml
Alphabets:
  Variables: A, B
  Constants: none
Axiom: A
Rules: (A→AB), (B→A)
```

This is how algae growth is modeled using L-System. Let's simulate how the rules would work:

```yaml
n=0: A # Only one rule was applicable here (A→AB)
n=1: AB # Here we can apply both rules
n=2: ABA # Similarly apply the relevant rule for each character
n=3: ABAAB
n=4: ABAABABA
n=5: ABAABABAABAAB
```

As you can see the number of terms starts increasing faster as we get to a higher number of generations. If you look closely the number of alphabets at each step(population) follows the [Fibonacci Series](https://en.wikipedia.org/wiki/Fibonacci_number) [1,2,3,5,8,12,...].

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

While this is a recursion tree that programmers might be familiar with, it is nowhere close to real trees that we see which are claimed to be closely simulated by L-Systems. This is because the rules till now have been quite simple.

As we start getting into more complex rules, we start getting into more interesting visualizations. For more examples, you can have a look [here](https://en.wikipedia.org/wiki/L-system#Examples_of_L-systems) to get an idea about how wide varieties of structures can be modeled by L-Systems.

## Visualizations

Now from the above strings itself, it's difficult to visualize the models. So we generally use what's called [Turtle Graphics](https://en.wikipedia.org/wiki/Turtle_graphics) to visualize these models. Some of you might have had prior experience with [Logo](<https://en.wikipedia.org/wiki/Logo_(programming_language)>), this is quite similar and we use the generated strings as input and map it to instructions for our graphics generation.

So, assume you are a robot who is been feed instructions by your master. Your master will read you the instructions from the generated string one by one.
You and your master have decided on the following instruction set:

`F`: Go forward by a fixed amount

`-`: Rotate Left by a fixed angle

`+`: Rotate Right by a fixed angle

`[`: Save the current orientation

`]`: Return to the last saved orientation

Apart from these, any other instructions are ignored.
You can come up with more complex instructions but for now, these alone should suffice.

With just these instructions you can make some complex structures. Don't Believe me?
Try creating some visualizations by writing your own rules **[here](/L-System/)**. You can also explore the code behind this [here](https://github.com/keivan-shah/L-System).

The above link does create some cool looking but it's not that fun to create visualizations by hand is it? So what if there was an automated visualization with randomly generated rulesets?

This is the [link](https://ehrenjn.github.io/LSystems/lsystems.html) you are looking for! It looks cool and makes you remember the old-school Desktop Wallpapers that people used to have.

For now, this is where I leave you. I will try to update this post as and when I explore more into the world of `L-Systems`

## Links

Here are some more links that I referred to while writing this post.

- [Create Tree Images](https://github.com/TanviKumar/treegen)
- [Complete Code for an L-Sytem Implemenatation](https://github.com/nylki/lindenmayer)
- [Awesome Visualization](https://github.com/ehrenjn/LSystems)
