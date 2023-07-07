---
title: Credit Suisse OSA
id: 22 OSA* (D)
barcode: https://raw.githubusercontent.com/chrisyalamov/id-repo/main/src/credit-suisse-osa/barcode.jpg
description: Project OSA was a web platform developed for the International Wealth Management (IWM) division at Credit Suisse. It sought to improve management of key processes surrounding due diligence, know-your-client (KYC) and risk identification and mitigation.
properties:
    -   key: Date
        value: 2022
    -   key: Duration
        value: 3 mo
tags:
    - Node.js
    - Test-driven development (TDD)
---
> Sinte is a simple Node.js library for running a workflow based on a JSON file.

**The code for Sinte is available on [Github](https://github.com/Revantpoint/sinte)**

The main component, the orchestrator, takes in a JSON configuration object which defines the flow, and runs the given steps. It also allows for basic flow control like branching and looping. Each step is represented by a block of code which does something, like query a database, send a message, or interact with an API in some other way.

Steps are run inside of V8 isolates— a 'sandbox' which makes sure that untrusted code, even if malicious, doesn't get access to resources that it shouldn't.

I plan on expanding the project by creating a UI which allows for people to build flows visually with little to no coding experience and making the project open source.

# Development and skills

This project was developed in Node.js. As I have been learning about test-driven development, I made sure to implement unit tests within this project. Using Meta's testing framework, JEST, I wrote unit tests which ensure my code is working as expected. The current test coverage sits at 97.4% and all tests are passing.

I have also made an effort to keep my code consistent by using ESLint, which helps enforce styling practices when writing code.

# Future plans for Sinte

When running untrusted code, it may be wise for Sinte to implement more layers of protection against execution of malicious user code. I am currently exploring this using Deno, in a separate project.