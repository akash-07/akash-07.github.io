## Regular Expressions to Finite State Automatas in Haskell

| **Title**| **Description**|
|---|---|
|**Project**| Paradigms of Programming|
|**Team Members**|Nikhil Sharma|
|**Mentor**|Dr.Sridhar Chimalakonda|
|**Date**|March - April 2017|

### Description

In this project, we build a regular expression to Finite State Automata converter in Haskell from scratch. Purpose of writing in Haskell is to exploit its functional features like higher order functions, lazy evaluation, pattern matching, immutablility, etc while understanding the fundamentals of code composition in a functional language. The code is concise, readable and is much shorter than any object oriented language like Java or C++.

- We use the Thompson's recursive algorithm for NFA construction from regular expressions. 
- Algorithm for converting regular expressions directly into DFA taken from the book Compilers: Principles, Techniques and Tools by Aho, Ullman, Sethi and Lam.
- Graphviz library is utilized for visualization of finite state automatas.

Please find the instructions for running the code [here](https://github.com/akash-07/Regex-To-NFA).

### Example DFA

```haskell
Regex-To-DFA>ghci
GHCi, version 8.0.1: http://www.haskell.org/ghc/  :? for help
Prelude> :l regToDfa.hs
[1 of 1] Compiling Main             ( regToDfa.hs, interpreted )

regToDfa.hs:376:12: warning: [-Wtabs]
    Tab character found here, and in 19 further locations.
    Please use spaces instead.
Ok, modules loaded: Main.
*Main> main
Initial State:
[1,3,6]

States :
[1,3,6]
[8]
[3,6]
[]


Moves:
[] on c = []
[] on b = []
[] on a = []
[] on # = []
[3,6] on c = [8]
[3,6] on b = [3,6]
[3,6] on a = []
[3,6] on # = []
[8] on c = []
[8] on b = []
[8] on a = []
[8] on # = []
[1,3,6] on c = [8]
[1,3,6] on b = [3,6]
[1,3,6] on a = [1,3,6]
[1,3,6] on # = []


Final States:
[8]

```
![image](https://user-images.githubusercontent.com/24961068/48665785-c5606880-eada-11e8-8eea-f6972469fe31.png)
