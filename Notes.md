3.1.1. Rule: Five lines of code
3.2.1. Pattern: Extract Method
3.3.1. Rule: Either pass or call
On `draw`, extracted `createGraphics`
On `update`, extracted `handleInputs` and `updateMap`
3.5.1. Rule: If only at the start
On `updateMap`, extracted `updateTile`
On `handleInputs`, extracted `handleInput`
4.1.1 Rule: Never use if with else
4.1.3 Pattern: Replace type code with classes
Create Input2 interface, the 4 direction classes.
Rename Input to RawInput
Use compiler to fix bug by using Input2.
Use `.isRight` and such in `handleInput`
4.1.5 Pattern: Push code into classes (P4.1.5)
Recopy `handleInput` to all 4 direction classes.
Simplified it
4.1.7 Pattern: Inline method
in `handleInputs`, call directly `current.handleInput();`
4.2 Refactoring a large if statement
Added interface `Tile` and all tile classes. Applied all over.
Error remaining:
- The `map` uses number, not classes.
- `remove`
4.2.2 Pattern: Specialize method
`remove(Tile)` becomes `removeLock1` and `removeLock2`
4.2.4 Rule: Never use switch

apply rule: Never use if with else
with pattern Push code into classes

apply rule: Inline method

4.3
Performed:
- extract method `drawTile`
- push code into class

4.4 Refactoring pair of complex if statements
- Introduce a `isEdible`, push code into class
- Introduce a `isPushable`, push code into class
- content of `moveHorizontal` => push code into class
- content of `moveVertical` => push code into class

4.5 Remove dead code
- Removed `isEdible`, `isPushable`, `isKey1` and `isKey2`

5.1. Unifying similar classes
- Introduce `isStony` and `isBoxy`
- Remove `isStone` and `isBox`
- Unified `FallingStone` and `Stone` by using `Falling` and `Resting`
- Unified `FallingBox` and `Box`

5.1.1 Pattern: Unify similar classes

5.2 Unifying simple conditions

Add method for setting and unsetting the falling condition `drop` and `rest`
Merge the `if`