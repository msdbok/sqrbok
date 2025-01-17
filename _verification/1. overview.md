---
title: Verification Overview
category: verification
author: Andrey Sadovykh
layout: page
---

# Software verification

Purpose

    To establish the  quality levels achieved 

    To justify confidence in the software by
    
        Demonstrating that it does what it is supposed to do under its stated conditions

        It doesn’t do what is not supposed to do under adverse conditions

    Verification is a continuous process, is not something that happens at the end


# Software verification techniques

Inspection
Analysis 
Testing
Demonstration

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


# 2. Analysis

## What is (Static) Analysis?
INCOSE
The performance and assessment of calculations (including modeling and simulation) to evaluate requirements or design approaches or compare alternatives. 
The verification method of determining performance (a) by examination of the baseline, (b) by performing calculations based on the baseline and assessing the results, (c) by extrapolating or interpolating empirical data of collected using physical items prepared according to the baseline, or (d) by a combination of all of the above. 
Software practitioner
The verification of software properties through the use of syntactic, behavioral or structural information from the software, e.g. the state space of a program, its patterns of execution, an abstract model, etc.; in contrast to the computed values used in testing
There are two types of software analysis: Dynamic and static

### Uses
Style issues, dangerous constructs
Verification of safety properties
Verification of liveness properties
Verification of fairness properties
Verification of temporal properties
Examples
Security vulnerabilities, memory leaks
Code non-compliances
Resource usage


## Benefits

## Limitations

# 3. Testing

## What is testing?

INCOSE

    The verification method of determining performance by exercising or operating the system or item using instrumentation or special test equipment that is not an integral part of the item being verified. Any analysis of the data recorded in the test and that is needed to verify compliance (such as the application of instrument calibration data) does not require interpretation or interpolation/extrapolation of the test data. 

Software practitioner

    The (more or less) thorough execution of the software with the purpose of finding bugs before the software is released for use and to establish that the software performs as expected
Uses

    Verification of functional and performance requirements

Examples

    When provided with the correct user name and password the user is able to login into the system
    The software is capable of handling a load of thousand transactions per minute


> When we test something, our purpose is to make it fail. As a matter of fact  a good test case is one that uncovers a fault. Goal is to falsify the property, it is much easier then to prove correctness. 


## How tests can be classified? Taxonomy

by Level

    Unit
    Integration
    Thread, function, integration, unit, medium
    System

by Purpose or characteristic being tested

    Functional correctness
    Robustness
    Performance
    Regression
    Acceptance

by Source of test cases

    Specification (Black box testing)
    Structure (White box testing)
    Model based
    Experience (Exploratory testing)

by Targeted faults

    Computational
    Domain
    Variable interactions
    Value propagations
    Variable usages

by Test execution mode

    Manual
    Automated

## Benefits

## Limitations



# 4. Demonstration

INCOSE

    The verification method of determining performance by exercising or operating the item in which instrumentation or special test equipment is not required beyond that inherent to the item and all data required for verification is obtained by observing operation of the item

Practitioner

    Demonstration is the operation of an item to provide evidence that it accomplishes the required functions under specific scenarios. In general, in environments which are not under the control of the developers, e.g. production environments

Uses

    Mostly user acceptance and obtaining feedback through the development process

Examples

    You walk the user through the different usage scenarios and verify that the different screens are shown in a display
    Execution of a system in a production environment

> Demonstration is more positive than testing. Here we are trying to show somebody that what we did indeed does what is supposed to do.



# Discussion. Soundness and completeness

A “sound” static analysis over approximates the behaviors of the program. A sound static analyzer is guaranteed to identify all violations of a property , but may also report some “false alarms", or violations that cannot actually occur

A “complete” static analysis under approximates the behaviors of the program. Any violation of the property  reported by a complete static analyzer corresponds to an actual violation of, but there is no guarantee that all actual violations of  will be reported


>No static analysis can be sound, complete, and terminating

Rice’s Theorem says there are inherent limits on what can be
accomplished by automated analysis of programs

◦ Sound (miss no errors)
◦ Complete (no false alarms)
◦ Automatic
◦ Allow arbitrary (unbounded) memory structures
◦ Final results

For assurance, we need soundness. When told there are no errors, there must be none → we have to accept false alarms. But the main market for static analysis is bug finding in general-purpose software, where they aim merely to reduce the number of bugs, not to eliminate them. Customers in general will not tolerate many false alarms, so tool vendors give up soundness. Others give up full automation: e.g., require user annotation

Commercial tools (e.g., Coverity, Code Sonar, Fortify, KlocWork, LDRA) are neither sound nor complete. 
• Pragmatically effective
• Different tools use different methods, have different capabilities, make different tradeoffs

Lint & Findbugs are pattern matchers (e.g.) are not based on semantics of program execution, neither sound nor complete
• But pragmatically effective for bug finding


# Conclusions: It is worth trying a combination of techniques

> (Adapted from G. Holzmann, Software Analysis and Model Checking, 2002)

The industry average of 0.5 to 5 defects per one thousands lines of code is based on a count of customer complaints. We can suspect that the true number of latent defects is at least an order of magnitude higher, more likely in the range of 0.5 to 5 defects per one hundred lines of source code.

In this context, any new technique that differs sufficiently from other technique should be expected to intercept enough extra defects to justify its application. 
