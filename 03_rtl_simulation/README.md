# RTL Simulation Using Icarus Verilog and GTKWave

## 1. Introduction

RTL simulation is used to verify the behavior of a digital circuit before synthesis and physical design. A testbench provides input signals to the design and checks the resulting outputs.

This stage uses Icarus Verilog for compilation and simulation and GTKWave for waveform visualization.

## 2. Objectives

- Understand the purpose of RTL simulation.
- Write Verilog testbenches.
- Compile Verilog files using Icarus Verilog.
- Generate waveform files in VCD format.
- Analyze signal transitions using GTKWave.
- Identify functional errors before synthesis.

## 3. Tools Used

- Verilog HDL
- Icarus Verilog
- VVP simulation runtime
- GTKWave
- Ubuntu Linux

## 4. Simulation Workflow

1. Write the RTL design.
2. Create a testbench.
3. Compile the RTL and testbench.
4. Run the simulation.
5. Generate a VCD waveform file.
6. Open the waveform in GTKWave.
7. Verify that the output matches the expected behavior.

## 5. Example: 2-to-1 Multiplexer

A 2-to-1 multiplexer selects one of two input signals according to the select signal.

### RTL Design

Create `mux2to1.v`:

```verilog
module mux2to1 (
    input wire a,
    input wire b,
    input wire sel,
    output wire y
);

assign y = sel ? b : a;

endmodule
```

### Testbench

Create `tb_mux2to1.v`:

```verilog
`timescale 1ns/1ps

module tb_mux2to1;

reg a;
reg b;
reg sel;
wire y;

mux2to1 uut (
    .a(a),
    .b(b),
    .sel(sel),
    .y(y)
);

initial begin
    $dumpfile("mux2to1.vcd");
    $dumpvars(0, tb_mux2to1);

    a = 0; b = 0; sel = 0;
    #10;

    a = 1; b = 0; sel = 0;
    #10;

    a = 0; b = 1; sel = 1;
    #10;

    a = 1; b = 0; sel = 1;
    #10;

    $finish;
end

endmodule
```

## 6. Running the Simulation

Run these commands in the directory containing both Verilog files.

### Compile

```bash
iverilog -o mux_sim mux2to1.v tb_mux2to1.v
```

### Execute

```bash
vvp mux_sim
```

### View the Waveform

```bash
gtkwave mux2to1.vcd
```

In GTKWave, select the testbench signals `a`, `b`, `sel`, and `y`, then add them to the waveform display.

<img width="1005" height="490" alt="image" src="https://github.com/user-attachments/assets/9365b37d-a35f-4d3a-bf4c-7b47acaebaec" />


## 7. Expected Results

The output should follow the select signal:

| Select (`sel`) | Output (`y`) |
|---|---|
| 0 | `a` |
| 1 | `b` |

The waveform should show that the output follows input `a` when `sel = 0` and input `b` when `sel = 1`.

## 8. Common Errors

- Compilation fails because of a syntax error.
- A module name does not match the instantiated module.
- The testbench does not generate a V
