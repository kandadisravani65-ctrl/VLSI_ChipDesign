# 02 — Verilog RTL Design

## 1. Introduction

Verilog Hardware Description Language (HDL) is used to describe and model digital electronic circuits. Register Transfer Level (RTL) design describes how data moves between registers and how logic operations are performed on that data.

This module focuses on writing synthesizable Verilog code for combinational circuits, sequential circuits, and finite-state machines.

## 2. Objectives

- Understand Verilog syntax and module structure.
- Learn Verilog data types and operators.
- Implement combinational logic using continuous assignments and procedural blocks.
- Design sequential circuits using clocked processes.
- Understand blocking and non-blocking assignments.
- Develop reusable RTL modules.
- Write synthesizable code for digital hardware.
- Prepare RTL designs for simulation and synthesis.

## 3. Verilog Module Structure

A Verilog module describes the interface and behavior of a digital circuit.

Example:

```verilog
module and_gate (
    input  wire a,
    input  wire b,
    output wire y
);

assign y = a & b;

endmodule
```

**Explanation:**
- `module` defines the circuit.
- `input` declares input ports.
- `output` declares an output port.
- `assign` describes continuous combinational logic.
- `&` represents the bitwise AND operation.
- `endmodule` marks the end of the module.

## 4. Verilog Data Types

### 4.1 Wire

A `wire` represents a signal driven by a continuous assignment or another signal source.

```verilog
wire a;
wire y;

assign y = a;
```

### 4.2 Reg

A `reg` is a variable that can hold a value assigned inside a procedural block. It does not necessarily represent a physical register; the hardware depends on how it is used.

```verilog
reg q;

always @(*) begin
    q = a & b;
end
```

### 4.3 Vectors

Vectors represent multi-bit signals.

```verilog
input wire [3:0] data;
output wire [3:0] result;
```

These signals contain four bits each.

## 5. Verilog Operators

| Operator | Description |
|---|---|
| `&` | Bitwise AND |
| `|` | Bitwise OR |
| `~` | Bitwise NOT |
| `^` | Bitwise XOR |
| `+` | Addition |
| `-` | Subtraction |
| `==` | Equality comparison |
| `!=` | Inequality comparison |
| `&&` | Logical AND |
| `||` | Logical OR |
| `<<` | Left shift |
| `>>` | Right shift |

## 6. Combinational Logic Design

Combinational logic produces outputs based on the current inputs.

 <img width="894" height="454" alt="image" src="https://github.com/user-attachments/assets/fdc6cfdf-021e-4e5c-9dd0-a0880af84d25" />


### Example: 2-to-1 Multiplexer

```verilog
module mux2to1 (
    input  wire a,
    input  wire b,
    input  wire sel,
    output wire y
);

assign y = sel ? b : a;

endmodule
```

**Operation:**
- When `sel = 0`, output `y` follows `a`.
- When `sel = 1`, output `y` follows `b`.

Other combinational circuits to implement:
- Logic gates
- Half adder and full adder
- Multiplexers and demultiplexers
- Encoders and decoders
- Comparators

## 7. Sequential Logic Design

Sequential logic stores information and typically updates its state in response to a clock edge.

### Example: D Flip-Flop

```verilog
module d_flip_flop (
    input  wire clk,
    input  wire rst,
    input  wire d,
    output reg  q
);

always @(posedge clk or posedge rst) begin
    if (rst)
        q <= 1'b0;
    else
        q <= d;
end

endmodule
```
    <img width="601" height="583" alt="image" src="https://github.com/user-attachments/assets/9e3bca29-5c1c-4937-9638-30a014a60bb6" />

**Operation:**
- When `rst` becomes high, `q` is cleared to zero.
- On a rising edge of `clk`, `q` captures the value of `d`.
- The output retains its stored value between clock edges.

This example uses an asynchronous, active-high reset.

## 8. Blocking and Non-Blocking Assignments

| Assignment | Symbol | Common usage |
|---|---|---|
| Blocking | `=` | Combinational procedural logic |
| Non-blocking | `<=` | Clocked sequential logic |

Blocking assignments execute in procedural order. Non-blocking assignments schedule updates for the end of the current simulation time step.

Following these conventions helps avoid unintended simulation behavior.

## 9. Conditional Statements and Case Statements

Conditional statements describe decision-making logic.

Example:

```verilog
always @(*) begin
    if (sel)
        y = b;
    else
        y = a;
end
```
<img width="903" height="462" alt="image" src="https://github.com/user-attachments/assets/9d1762b5-5e0a-4f37-b147-010b453c375e" />

Case statements are useful for selecting among multiple input conditions or defining finite-state machine behavior.

When writing combinational procedural logic, ensure all outputs receive assignments for every possible branch to avoid unintended latch inference.

 <img width="773" height="455" alt="image" src="https://github.com/user-attachments/assets/3d5ca52a-b5e6-4bdd-ac23-b5e5f6c78d79" />

## 10. Finite-State Machine Design

An FSM represents a sequential circuit using states, transitions, inputs, and outputs.

Typical design steps:
1. Define the required states.
2. Identify the inputs and outputs.
3. Draw the state diagram.
4. Write the state transition logic.
5. Implement the state register.
6. Verify transitions using a testbench.

FSMs are commonly used in controllers, communication protocols, and digital sequence detectors.

## 11. Coding and Verification Workflow

1. Define the circuit specification.
2. Create the Verilog module.
3. Check the syntax and port declarations.
4. Write a testbench.
5. Simulate using Icarus Verilog.
6. Inspect waveforms using GTKWave.
7. Synthesize the design using Yosys.
8. Review the synthesis results and document observations.

## 12. Tools Required

- Verilog HDL
- Icarus Verilog
- GTKWave
- Yosys
- Ubuntu Linux
- Git and GitHub

## 13. Expected Learning Outcomes

After completing this module, I aim to:
- Write Verilog modules for basic digital circuits.
- Understand continuous assignments and procedural blocks.
- Implement combinational and sequential logic.
- Use appropriate assignment styles.
- Develop reusable and synthesizable RTL.
- Prepare RTL code for functional verification and logic synthesis.

## 14. Conclusion

RTL design connects digital logic concepts with hardware implementation. By developing and verifying Verilog modules, this module establishes the foundation for simulation, synthesis, and subsequent ASIC design stages.

## 15. Status

**Documentation:** Created

**Implementation:** RTL examples, testbenches, and verified results will be added progressively.
