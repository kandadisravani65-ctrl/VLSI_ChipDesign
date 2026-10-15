# Logic Synthesis and Gate-Level Simulation

## 1. Introduction

Logic synthesis converts synthesizable RTL into a gate-level representation. The synthesis tool analyzes the design and maps its logic to available cells or a generic gate-level netlist.

Gate-level simulation (GLS) checks the behavior of a synthesized netlist using a simulation tool.

## 2. Objectives

- Understand the purpose of logic synthesis.
- Convert Verilog RTL into a synthesized netlist.
- Inspect synthesis statistics.
- Understand the difference between RTL and gate-level representations.
- Learn the basic purpose of gate-level simulation.

## 3. Synthesis Flow

1. Read the RTL files.
2. Check and elaborate the design.
3. Perform logic optimization.
4. Map the design to the selected cells or gate representation.
5. Generate a netlist.
6. Review the synthesis statistics.

## 4. Tools Used

- Yosys
- Verilog HDL
- Icarus Verilog
- GTKWave
- Standard-cell libraries when technology mapping is required

## 5. Example: Synthesis with Yosys

For a simple Verilog design named `mux2to1.v`, start Yosys:

```bash
yosys
```

Inside the Yosys prompt, run:

```text
read_verilog mux2to1.v
hierarchy -top mux2to1
proc
opt
check
stat
write_verilog mux2to1_netlist.v
```

Exit Yosys:

```text
exit
```
<img width="794" height="773" alt="image" src="https://github.com/user-attachments/assets/97c3e3c5-0587-44b8-af6f-22ab87514618" />


The command `write_verilog` writes the resulting netlist to `mux2to1_netlist.v`.

These commands produce a basic synthesized representation. Technology mapping and physical-design timing analysis require additional setup.

## 6. Understanding Synthesis Statistics

Important report items include:

- Number of wires and wire bits.
- Number of cells.
- Types of cells used.
- Unused or unresolved logic.
- Cell area, if supported by the selected mapping and library setup.

The exact statistics depend on the RTL and synthesis flow.
   <img width="798" height="778" alt="image" src="https://github.com/user-attachments/assets/1a071086-dbe1-49a2-914d-1abe89d14f19" />

## 7. RTL Simulation vs Gate-Level Simulation

| Feature | RTL Simulation | Gate-Level Simulation |
|---|---|---|
| Input design | RTL source | Synthesized netlist |
| Representation | Behavioral or RTL logic | Gate or cell instances |
| Main purpose | Verify intended functionality | Verify netlist behavior |
| Timing model | Usually RTL-level behavior | May include cell delays |
| Library dependency | Often unnecessary | Required for technology-mapped cells |

A gate-level simulation does not automatically include accurate timing. Timing-aware GLS requires appropriate delay information and simulation configuration.

## 8. Gate-Level Simulation Workflow

1. Synthesize the RTL design.
2. Generate the gate-level netlist.
3. Prepare a compatible testbench.
4. Include the required simulation models for mapped cells.
5. Compile the netlist, testbench, and models.
6. Run the simulation.
7. Compare the observed behavior with the RTL simulation.
    <img width="795" height="770" alt="image" src="https://github.com/user-attachments/assets/b8715e27-e0ca-4add-95e6-88cc707dec7c" />


## 9. Common Issues

- Unsupported or nonsynthesizable RTL constructs.
- Incorrect top-module selection.
- Missing technology libraries.
- Missing cell simulation models.
- Differences in reset or initialization behavior.
- Incorrect timing or delay configuration.
   <img width="797" height="765" alt="image" src="https://github.com/user-attachments/assets/57ef1b15-d1a3-4f1e-a7ff-627b18de32d5" />


## 10. Learning Outcomes

- Understand the RTL-to-netlist conversion process.
- Run a basic Yosys synthesis flow.
- Inspect synthesis statistics.
- Understand the role of gate-level simulation.
- Recognize the additional requirements of technology-mapped GLS.

## 11. Conclusion

Synthesis transforms RTL into a hardware netlist suitable for further implementation. Gate-level simulation provides an additional way to verify the synthesized design before progressing through timing analysis and physical design.

**Status:** Basic synthesis workflow documented. Netlist generation and GLS results should be verified by running the tools.

