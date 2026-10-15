# 01 — Digital Design Basics

## 1. Introduction

Digital design is the process of creating electronic circuits that process information using binary values, 0 and 1. These circuits form the foundation of processors, controllers, memory systems, and System-on-Chip (SoC) designs.

This module introduces the fundamental concepts required to understand digital hardware and develop RTL designs using Verilog HDL.

## 2. Objectives

- Understand binary number systems and Boolean algebra.
- Learn the operation of basic logic gates.
- Design combinational logic circuits.
- Understand sequential logic and memory elements.
- Study multiplexers, decoders, adders, and comparators.
- Understand flip-flops, registers, and counters.
- Learn the basics of finite-state machines (FSMs).
- Prepare for Verilog RTL design and simulation.

## 3. Topics Covered

### 3.1 Number Systems

Digital systems represent information using binary values.

Topics:
- Binary number system
- Decimal number system
- Hexadecimal number system
- Binary-to-decimal conversion
- Decimal-to-binary conversion
- Binary addition and subtraction

### 3.2 Boolean Algebra

Boolean algebra is used to describe and simplify digital logic expressions.

Topics:
- Boolean variables and expressions
- AND, OR, and NOT operations
- NAND and NOR operations
- XOR and XNOR operations
- Boolean identities and simplification
- De Morgan's theorems

### 3.3 Logic Gates

Logic gates perform basic operations on binary inputs.

| Gate | Operation | Output |
|---|---|---|
| AND | Output is 1 when all inputs are 1 | A · B |
| OR | Output is 1 when at least one input is 1 | A + B |
| NOT | Inverts the input | A' |
| NAND | Inverted AND operation | (A · B)' |
| NOR | Inverted OR operation | (A + B)' |
| XOR | Output is 1 when inputs differ | A ⊕ B |
| XNOR | Output is 1 when inputs match | (A ⊕ B)' |

### 3.4 Combinational Logic Circuits

Combinational circuits produce outputs based on the current inputs.

Topics:
- Half adder
- Full adder
- Half
