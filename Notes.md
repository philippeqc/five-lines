3.1.1. Rule: Five lines of code
3.2.1. Pattern: Extract Method
3.3.1. Rule: Either pass or call
On `draw`, extracted `createGraphics`
On `update`, extracted `handleInputs` and `updateMap`
3.5.1. Rule: If only at the start
On `updateMap`, extracted `updateTile`
On `handleInputs`, extracted `handleInput`
4.1.1 Rule: Never use if with else
Create Input2 interface, the 4 direction classes.
Rename Input to RawInput
Use compiler to fix bug by using Input2.
Use `.isRight` and such in `handleInput`
