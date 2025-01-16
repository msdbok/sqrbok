---
title: Testing Overview
category: verification
author: Andrey Sadovykh
layout: page
---

# Testing

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

### Unit testing

A “unit” (object, procedure, subprogram) usually created by a single developer
Typical faults: missing/wrong functionality, domain faults, data corruption, error conditions
Defects found are typically kept private and fixed by the same person that developed the code
Can take place before and/or after code review
Runs in a simulated environment (drivers and stubs)
Adequacy measured through statement, branch, basis path, MC/DC coverage or mutation testing

![alt text](image-2.png)

{% mermaid %}
sequenceDiagram
    actor Customer
    participant SC as ShoppingCart
    box "Unit Under Test"
        participant O as Order
    end
    participant I as Item

    Customer->>SC: Add items and get total
    SC->>O: Create order
    O->>I: Get item prices
    I-->>O: Return item prices
    O-->>SC: Return total price
    SC-->>Customer: Display total price
{% endmermaid %}

#### Mocking
{% mermaid %}
sequenceDiagram
    actor Developer
    participant TestFramework
    participant CodeUnderTest
    participant MockService

    Developer->>TestFramework: Write test cases
    TestFramework->>CodeUnderTest: Call functions with inputs
    CodeUnderTest->>MockService: Send mock API call
    MockService-->>CodeUnderTest: Return mock response
    CodeUnderTest-->>TestFramework: Return output
    TestFramework->>Developer: Compare output with expected results
    alt Output matches expected
        TestFramework->>Developer: Test passed
    else Output does not match expected
        TestFramework->>Developer: Test failed
    end
{% endmermaid %}








