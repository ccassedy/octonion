# Octonion

This repo contains a proof-of-concept puzzle on integral octonions, and some scripts to explore octonions. This is a joint work with [Roice Nelson](https://github.com/roice3). This puzzle is a proof of concept of non-associative puzzles. It was created so that we can have a taste of the difficulty level and non-associative solving experience. We are working on improving it and making it more intuitive. We are also working on other non-associative puzzles. An introduction can be found [here](https://docs.google.com/document/d/1q0x0Z2-emntmOZ_VIPZn1jVLFZktUCo1ROIcNNfM4uE/edit?usp=sharing)

## How to run the integral octonions puzzle?
- Install Python, 2.* or 3.*.
- Install numpy.
- Run puzzle_python2.py or puzzle_python3.py depending on the Python version you installed.
- Follow the instructions to solve it. You may want to refer to the explanations below.

## About [octonions](https://en.wikipedia.org/wiki/Octonion#Definition):
- Octonions are a number system extended from complex numbers and quaternions. 
- Each octonion can be thought of as a vector of 8 real numbers, or a sum of 8 basis vectors.
- Addition, subtraction, multiplication, inverse, norm, conjugate can be defined similar to complex numbers, with a more complicated multiplication table.
- Octonion multiplication is not commutative (a * b != b * a) and not associative ((a * b) * c != a * (b * c)) in general.

## About [integral octonions](https://en.wikipedia.org/wiki/Octonion#Integral_octonions):
- They are octonions whose coordinates are all integers or all half-integers satisfying certain properties.
- The minimum nonzero norm of integral octonions is 1. There are 240 integral octonions with norm = 1.
- The identity octonion, (1, 0, 0, 0, 0, 0, 0, 0), is a unit norm integral octonion.
- The set of 240 unit norm integral octonions is closed under octonion multiplication. That is, the product of two numbers in this set stays in the set.
- If we start from three generators
  - i = (0, 1, 0, 0, 0, 0, 0, 0),
  - j = (0, 0, 1, 0, 0, 0, 0, 0),
  - h = (0, 1, 1, 1, 1, 0, 0, 0)/2,
    
  and use the octonion multiplication *, we can generate all 240 integral octonions with unit norm.

## Summary of the Rubik's Cube, as an analogy:
- All the states of the Rubik's Cube are generated from generators U, D, L, R, F, B, and the group operation of concatenating moves.
- We draw a random one from all the states as the initial state or scramble.
- In each step
  - We input any generator individually, or in general, any sequence of generators as an expression.
  - (The new state) = (the old state) * (input).
- We win when the state is the identity or "solved" state.


## About this integral octonions puzzle:
- All the 240 unit norm integral octonions are generated by i, j, and h.
- We pick a random unit norm integral octonion as the initial state or scramble.
- In each step
  - We input an expression of i, j, h, and the octonion multiplication *, with parenthesis (). For example, h * (i * j).
  - The input expression is evaluated. By construction, it is also a unit norm integral octonion.
  - (The new state) = (the old state) * (input expression).
- We win when the state is the identity octonion (1, 0, 0, 0, 0, 0, 0, 0).


## Why input expression rather than individual generators? Non-associativity:
  - Since the multiplication is not associative: state * (a * b) != (state * a) * b, applying the expression (a * b) as input is different from applying a and then applying b.
  - If you only input i or j or h individually and do not use multiplication in the input expression, it is unlikely (with 20% chance) you will be able to solve the puzzle.
  - Therefore, we highly recommend trying at least (i * h) if you are stuck.

