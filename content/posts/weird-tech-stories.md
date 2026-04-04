---
author:
  name: "Keivan Shah"
date: 2026-04-04
lastmod: 2026-04-04
linktitle: Weird Tech stories
type:
  - post
  - posts
title: "Weird Bugs: When Logic Meets Reality"
weight: 10
series:
  - Random
---

I've always loved "haunted" tech support stories, the ones that make you go "How is that even possible?!". Listing some of my favorites here for you to enjoy! Initially this was on my todo list that I intended to write a post about but after delaying writing about it for years, I decided better an AI generated version of the stories than never posting it!

## 1. The Email with a 500-mile Geofence
A university admin once received a report that emails couldn't be sent further than 500 miles. 
*   **The Cause:** An OS upgrade reset a timeout to 3 milliseconds.
*   **The Math:** Light in a vacuum travels at roughly 186,282 miles per second. In 3 milliseconds, it travels approximately 558 miles—nearly exactly the "radius of failure" reported by the professor. Because the signal had to travel both ways, any distance approaching that 500-mile mark simply didn't allow enough time for a round-trip response before the 3ms timeout triggered.
*   **Source:** [The 500-mile Email (Trey Harris)](https://www.ibiblio.org/harris/500milemail.html)

## 2. The Tuesday-Only Printing Bug
In 2009, Ubuntu users found that OpenOffice would print perfectly every day of the week—except on Tuesdays.
*   **The Cause:** The Linux `file` utility misidentified PostScript files starting with `Tue` (from the date metadata) as **Erlang JAM** files.
*   **The Result:** Since the system only saw "Tue" once a week, the printing pipeline would incorrectly reject the document as a non-printable binary file every Tuesday.
*   **Source:** [Ubuntu Bug #248619](https://bugs.launchpad.net/ubuntu/+source/file/+bug/248619)

## 3. The Car that "Hates" Vanilla Ice Cream
A customer complained to GM that his Pontiac worked for every flavor of ice cream except vanilla. 
*   **The Cause:** **Vapor Lock**. In older car designs, engine heat could cause the liquid fuel in the lines to turn into gas (vapor), which would prevent the car from restarting until it had enough time to cool down and let the fuel re-liquefy.
*   **The Reason:** Vanilla was the most popular flavor and was kept in a quick-access case at the front of the store. A "vanilla run" took less than two minutes—not enough time for the engine heat to dissipate and the vapor lock to clear. Buying other flavors required a long walk to the back of the store, giving the car just enough time to cool down and start reliably.
*   **Source:** [CMU Humor Archive: Car Problems](https://www.cs.cmu.edu/~wkw/humour/carproblems.txt)

## 4. The Song That Could Kill Hard Drives
Playing the music video for Janet Jackson's "Rhythm Nation" would crash certain laptops, even those sitting nearby.
*   **The Cause:** **Resonant frequency**. 
*   **The Physics:** The song contains a specific frequency that matched the natural resonant frequency of a 5400-RPM hard drive model. The vibration from speakers was enough to make the drive head crash. It is now tracked as [CVE-2022-38392](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2022-38392).
*   **Source:** [Microsoft: The Old New Thing](https://devblogs.microsoft.com/oldnewthing/20220816-00/?p=106994)

## 5. Hunting Cosmic Rays with a Hex Editor
In 2000, Google’s search indexer began failing mysteriously, producing corrupt or outdated results despite no software changes.
*   **The Discovery:** To find the bug, engineers (including Jeff Dean and Sanjay Ghemawat) sat down to inspect a raw **hex dump** of the corrupted index files. By manually binary-diffing them against the source data, they found single-bit flips—specifically, 0s that had spontaneously become 1s in memory.
*   **The Lesson of Scale:** Cosmic rays are incredibly rare for a single PC, but they aren't rare for a fleet. Google realized that even if a bit flip is a "one-in-a-million" event, it becomes a daily guarantee once you have a million machines.
*   **The Result:** This incident proved that "impossible" hardware errors are inevitable at scale. It forced Google to mandate ECC memory and design its entire infrastructure to assume that hardware is constantly failing.
*   **Source:** [Google experience reveals the importance of ECC memory (ZDNet)](https://www.zdnet.com/article/google-experience-reveals-the-importance-of-ecc-memory/)

***

Tech is really weird! If you have any other stories you think I should add to the list, [email](mailto:keivan.shah@gmail.com) them to me!

_Note: This post was written with the help of AI._
