## The Three Rules of TDD
1. You are not allowed to write any production code unless it is to make a failing unit test pass.
2. You are not allowed to write any more of a unit test than is sufficient to fail; and compilation failures are failures.
3. You are not allowed to write any more production code than is sufficient to pass the one failing unit test.
Which means the workflow is:
1. Write a failing test. Stop writing the test as soon as it fails.
2. Write the minimal production code required for the test to pass. Stop writing any code once the test passes.
3. Refactor the test code and the production code without altering the functionality. All tests should pass.


## Requirement 1

Write a method `greet(name)` that interpolates `name` in a simple greeting. For example, when `name` is `"Bob"`, the method should return a string `"Hello, Bob."`.

## Requirement 2

Handle nulls by introducing a stand-in. For example, when `name` is null, then the method should return the string `"Hello, my friend."`

## Requirement 3

Handle shouting. When `name` is all uppercase, then the method should shout back to the user. For example, when `name` is `"JERRY"` then the method should return the string `"HELLO JERRY!"`

## Requirement 4

Handle two names of input. When `name` is an array of two names (or, in languages that support it, varargs or a splat), then both names should be printed. For example, when `name` is `["Jill", "Jane"]`, then the method should return the string `"Hello, Jill and Jane."`

## Requirement 5

Handle arbitrarily names of input. When `name` represents more than two names, separate them with commas and close with an Oxford comma and "and". For example, when `name` is `["Amy", "Brian", "Charlotte"]`, then the method should return the string `"Hello, Amy, Brian, and Charlotte."`

## Requirement 6

Allow mixing of normal and shouted names by separating the response into two greetings. For example, when `name` is `["Amy", "BRIAN", "Charlotte"]`, then the method should return the string `"Hello, Amy and Charlotte. AND HELLO BRIAN!"`

## Requirement 7

If any entries in `name` are a string containing a comma, split it as its own input. For example, when `name` is `["Bob", "Charlie, Dianne"]`, then the method should return the string `"Hello, Bob, Charlie, and Dianne."`.

## Requirement 8

Allow the input to escape intentional commas introduced by Requirement 7. These can be escaped in the same manner that CSV is, with double quotes surrounding the entry. For example, For example, when `name` is ["Bob", "\"Charlie, Dianne\""], then the method should return the string `"Hello, Bob and Charlie, Dianne."`.