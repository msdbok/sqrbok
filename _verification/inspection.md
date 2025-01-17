---
title: Overview. 1. Inspection
category: verification
author: Andrey Sadovykh
layout: page
---


# 1. Inspection

## What is Inspection?
International Council on System Engineering (INCOSE)
The verification method of determining performance by examining (a) engineering documentation produced during development or modification or (b) the item itself using visual means or simple measurements not requiring precision measurement equipment
Software practitioner
The scrutiny by people other than the producer, of human oriented development artifacts with the aim of meeting contractual obligations, finding non-compliances with standards or uncovering defects based on the premise that individuals might be blind to some of the trouble spots in their own work and in consequence it is beneficial to have someone else look at it
Uses
Complements  testing. Comes earlier in the process. Germane to the verification of faults of omission, design problems, style issues
Examples
The review of code to find if it properly commented and styled
Faults of omission and misunderstandings
Duplications
Problems in documentation

## Benefits of inspection

Reduce the number of defects in software earlier in the development process
Hewlett-Packard, ROI 10 to 1. Savings estimated at $21.4 million per year. [1]
AT&T Bell, ten-fold improvement in quality and a 14 percent increase in productivity at Bell Laboratories [2]
Bell Northern Research, average savings of 33 hours of maintenance effort per defect discovered [3]
CISCO, Some of our results exactly match those from established literature[4]
Uncover defects that would be difficult or impossible to discover by means of testing
Improve learning and communication within the software team

[1] Grady, Robert B., and Tom Van Slack. “Key Lessons in Achieving Widespread Inspection Use,” IEEE Software, Vol. 11, No. 4 (July 1994), pp. 46-57.
[2] Humphrey, Watts S. Managing the Software Process. Reading, Massachusetts: Addison-Wesley, 1989
[3] Russell, Glen W. “Experience with Inspection in Ultra large-Scale Developments,” IEEE Software, Vol. 8, No. 1 (January 1991), pp. 25-31.
[4] J. Cohen, Code Review at Cisco Systems, 2006


## Family of inspection techniques
Adapted from K. Wiegers, Peer Reviews in Software: A Practical Guide, 2002    

{% mermaid %}

timeline

    title Inspection Techniques (From Most Formal to Least Formal)
    Fagan inspections: A technique with well-defined entry and exit conditions, where somebody other than the author of the artifact presents it to the participants. There are many types of inspections: Fagan’s, N-fold, Phased, Gilb’s.
    Team review: A process or meeting during which a software product is presented to project personnel, managers, users, customers, user representatives, or other interested parties for comment or approval.
    Walkthrough: A technique in which a designer or programmer leads members of the development team and other interested parties through a software product. Participants ask questions and make comments about possible errors, violation of development standards, and other problems.
    Tool-assisted code review: An integral part of the coding process. One developer writes code, another developer is asked to review that code providing a line-by-line critique. Assisted by tools, e.g., diff, annotations, email, review history, online commenting.
    Pair programming: Two developers work together at one workstation, sharing the task of writing and reviewing code in real-time.
    Adhoc review: The least formal technique, involving unstructured and spontaneous reviews without predefined rules or documentation.

{% endmermaid %}
