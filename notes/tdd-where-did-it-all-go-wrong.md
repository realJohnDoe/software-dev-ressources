---
id: zhsasa7my0cp3larm30ghef
title: TDD - Where Did It All Go Wrong?
desc: ''
updated: 1673449235606
created: 1673251039104
---


[Link to the video][youtube]

[youtube]: https://www.youtube.com/watch?v=EZ05e7EMOLM

### Motivation

- Staying for longer than 2 years makes it possible to learn from mistakes that
  you would otherwise not have noticed.
- Having much more test code than implementation seems a bit weird.
- Tests with many mocks tend to break when refactoring, which seems wrong.
  Changing the implementation details should not require the tests to change.
- "Programmer Anarchy" is about developing products with only developers.
- Tests whose intent is unclear should be a warning sign. For example tests that
  only test mocks and no acutal code.
- Large Acceptance Tests are often red for a significant amount of time, without
  the devs knowing if they are broken, due to unimplemented features or due to
  bugs.
  => Developers started ignoring them and did not want to write them.
  This not changing even after a long time, is also a warning sign.

### What did go wrong?

- "Test-Driven Development" by Kent Beck seems alright, maybe we overloaded the
  concept with other, less helpful concepts.
  It already has answers for many issues we face with TDD today.
  For examples:
  > Avoid testing implementation details, test behaviors
- => Focus on testing the public API, i.e.
  - the "exports" from a module
- > The system under test is not a class
  - The SUT is the "exports" from a module
  - The old "unit" means a module, not a "class"
  - Refactoring is a key step to distinguish stuff implementation details and
    stable interfaces, "behaviors"
- Definition of unit is how the product can be separated so it can be tested in
  parallel.
  - Accessing the file system or a database is bad because it makes the tests
    less independent, and it improves speed.
    If both are no issue, it is okay to access external systems during testing.
