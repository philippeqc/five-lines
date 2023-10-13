5.1

Make Stone and FallingStone similar
- add each part of the `moveHorizontal` to `moveHorizontal`
- add a `falling` field
- change `isFallingStone` to return `falling`
- compile
- make `falling` a parameter of constructor
- compile
- Remove `FallingStone`
- compile

- look at `moveHorizontal`, violate Never use if with else
- Expose `falling` as an enum `FallingState`
- Apply "Replace type code with classes" on the `FallingState` enum
- Apply "Push code into classes (P4.1.5)" on `moveHorizontal`
- Apply "Try Delete then Compile"
  - Removed `isResting`


# Replace type code with classes
1. Add interface
- one if per enum
1. Add classes for interface
1. Rename the enum
- Replace usage by new function from class
- Fix the type used
- Rename interface to new name
1. Remove old enum


# 5.1.1 Unify Similar Classes
1. Make all the non-basis methods equal
  1. In the body of each version of the method, add `if (true)` around the code.
  1. Replace `true` with expression calling basis methods
  1. Copy the body of each version and paste it with an `else` into all other versions
1. Introduce a field for each method in the basis and assign its constant in the constructor.
1. Change the methods to return the new fields instead of the constants.
1. Compile
1. For each class, on field at a time:
  1. Make the default value a parameter
  1. Insert the defautl value as an argument
1. Delete all but one unified class. Fix compile errors
1. Is the interface still needed? If no, delete it and rename the unified class

# 5.2.1 Combine Ifs
1. Verify that the bodies are indeed the same.
2. Select the code between the closing parenthesis of the first `if` and the opening
parenthesis of the `else if`, press Delete, and insert an `||`. Insert an opening
parenthesis after the `if` and a closing parenthesis before `{`. We always keep
the parentheses around the expressions to make sure we do not change the
behavior.

# 5.4.2 INTRODUCE STRATEGY PATTERN
1 Perform EXTRACT METHOD on the code we want to isolate. If we want to unify it
with something else, make sure the methods are identical.
2 Make a new class.
3 Instantiate the new class in the constructor.
4 Move the method into the new class.
5 If there are dependencies on any fields:
  a Move along any fields to the new class, making accessors for the fields.
  b Fix errors in the original class by using the new accessors.
6 Add a parameter to replace this for the remaining errors in the new class.
7 INLINE METHOD (P4.1.7) to reverse the extraction from step 1.