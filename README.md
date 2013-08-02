Fasm Specification
===================
The lang spec.


# Syntax
* The Fasm language does not contain any instructions that require "arguments" or any consequent instructions
  * Instructions are strictly individual and need no context to run properly
* Any given set of instructions will always do the same operations on an array
  * The result of any given set of instructions is dependent on the array on which they are run
* Any characters the parser encounters that are not instructions are ignored
  * One can incorporate comments into their code
  * May add whitespace to make the code more readable

# Instructions
There are two types of instructions: inverse and individual

## Inverse
Inverse instructions are sets of two instructions that do the same thing in opposite directions
* > and < Navigate up and down the array
* + and - Alter the value in the current slot in the array by one (plus or minus)
* / and \ Copy the value in the current slot in the array either to the next or previous slot
* [ and ] Begin and end the declaration of a loop

## Individual
Individual instructions are not directional
* ^ Pop (return the value and set the slot to 0)
* . Get (return the value in the current slot)
* , Input (halt the program and wait for a character to be entered, put the character into the current slot in the array)
* * Dump (print the array)
* ~ Toggle Output (toggle output mode to print chars vs ints)

# The Rest
* The array by convention is 1024 slots
* The array is initialized with 0's
* Default output mode is chars
* Loops continue until the value of the slot that was selected at the beginning of the loop declaration is 0
* Loops can be nested (there should be no limit, but must explicity allow 2 nested loops)
* GPL v3 is a **requirement**

# Implementations
This is a list of all the official Fasm implementations
* [https://github.com/IsaacJG/fasm](https://github.com/IsaacJG/fasm)
* [https://github.com/IsaacJG/scasm](https://github.com/IsaacJG/scasm)
