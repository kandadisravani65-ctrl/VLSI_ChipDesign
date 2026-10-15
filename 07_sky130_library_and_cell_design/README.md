# SKY130 Standard-Cell Library Exploration

## 1. Introduction

The SKY130 platform is an open-source-oriented 130 nm CMOS technology platform used in digital integrated-circuit design and educational ASIC flows.

Standard-cell libraries provide predefined logic cells that synthesis and physical-design tools can use to implement a digital circuit.

## 2. Objectives

- Understand the purpose of standard-cell libraries.
- Explore basic logic and sequential cells.
- Understand Liberty library files.
- Learn how synthesis uses cell libraries.
- Recognize the importance of library compatibility.

## 3. Common Standard Cells

Examples of standard-cell functions include:

- Inverter (NOT).
- Buffer.
- NAND and NOR gates.
- AND and OR gates.
- XOR and XNOR gates.
- Multiplexers.
- Flip-flops.
- Latches.
- Clock-related cells.

The availability of each cell depends on the specific library and its configuration.

## 4. Important Library Concepts

### Liberty File

A Liberty (`.lib`) file describes cell functionality and timing and power characteristics.

### Cell Area

The library may specify an area value for each cell.

### Timing Arcs

Timing arcs describe delays between related input and output pins under specified conditions.

### Drive Strength

Different cell variants may provide different drive strengths and electrical characteristics.

### Process, Voltage, and Temperature

Cell timing and power behavior depend on operating conditions. The selected library corner should match the intended analysis.

## 5. Exploring a Library

Locate the actual library files in your installed platform.

Useful commands include:

```bash
find . -type f -name "*.lib"
```

To locate Verilog cell models:

```bash
find . -type f -name "*.v"
```

To inspect a Liberty file:

```bash
less path/to/library.lib
```

Replace the example path with a real file from your environment.
  <img width="852" height="441" alt="image" src="https://github.com/user-attachments/assets/e148c101-90a6-4a63-bf70-80c5ea720e4f" />


## 6. How Standard Cells Are Used

1. RTL describes the required logic.
2. Synthesis optimizes and maps the logic.
3. The cell library supplies available implementations.
4. Timing analysis uses library timing information.
5. Physical-design tools arrange and connect the selected cells.
  <img width="956" height="505" alt="image" src="https://github.com/user-attachments/assets/13be08de-7207-4239-ba5e-c163ae34d05a" />


## 7. Important Considerations

- Use compatible Liberty and Verilog model files.
- Confirm the library process corner.
- Check the units used by the library.
- Use the intended cell naming and pin conventions.
- Do not assume every library contains the same cells.
- Verify the platform configuration before running synthesis or physical design.

## 8. Learning Outcomes

- Understand standard-cell libraries.
- Identify basic logic and sequential cells.
- Explore Liberty and Verilog model files.
- Understand the relationship between synthesis and library mapping.
- Recognize the importance of process corners and library compatibility.

## 9. Conclusion

Standard-cell libraries connect logical RTL designs to technology-specific hardware implementations. Understanding the available cells and their timing characteristics is important for synthesis and ASIC implementation.

**Status:** Library concepts documented. The actual installed SKY130 files and selected library corner must be verified before reporting results.

