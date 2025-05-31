---
author:
  name: "Keivan Shah"
date: 2024-02-11
lastmod: 2025-05-31
linktitle: RPS-Sim
type:
  - post
  - posts
title: Rock Paper Scissors Battle Simulator
weight: 10
series:
  - Random
---

## Show me what you made!

Yeah, no point going through the technical details if you dont like what I made! So here: https://keivan-shah.github.io/RPS/

[{{< image src="/img/rps.png" alt="RPS Simulator" position="center" style="border-radius: 8px;" >}}](https://keivan-shah.github.io/RPS/)

So this is a Rock-Paper-Scissor battle simulator! 33 players of each type are added to a box, they follow a [Brownian motion](https://en.wikipedia.org/wiki/Brownian_motion) i.e. random movement and then at each encounter, the players change to one that is the most powerful amongst them follwing the classic rules of RPS! They do so till only one type remains which is declared the winner!

[{{< image src="/img/rps-winner.png" alt="Rock wins!" position="center" style="border-radius: 8px;" >}}](https://keivan-shah.github.io/RPS/)

So I made this in Javascript using [Phaser 3](https://phaser.io/), some free assets, Google Gemini, free hosting by Github, a few hours or my time and some lost brain cells! I think its pretty cool as a timepass screensaver or if you want to just do a 3 way toss! 

Can this be improved? Definitely. Will I spend more of my time on this? Nope.

## Introduction

So with all the AI hype regarding LLMs and GenAI, I have been wanting to try a small one day build kinda project with using AI and see how it turns out.

Saw something of this kind on Instagram reels (I know 🤦) and thought that its a very simple but fun idea, maybe even I can build it.! So I decided let's try and build this with 0 knowledge of Javascript or how to even go about it! I decided to give Google Gemini a try and design a game/simulator within a day with the help on AI using a language+library that I have never worked with before. 


## How it went

Overall the result seems fun to me! It went pretty well considering I was able to get something working within 2 hours!
I asked gemini to help me with everything, from figuring out which libraries to use, to how to make to so that it can be hosted via Githb Pages (I did have some idea of what I wanted so did nudge it in the right directions). It did make a lot of silly mistakes needed a lot of prompts to fix those and overall was frustrating figuring out what the error was in the 100s of lines of code it had written. Eventually did have to open the documentation myself and fix/prompt stuff.

But as a baseline, this is great and I feel with more advancements, things will only get easier! I am actually optimistic about AI stuff. Do I think it will replace my job? Atleast not right now, but will it make my job easier? I think I can bet on this. 

You can look at the code here: https://github.com/keivan-shah/RPS


Bye! Thanks for reading!