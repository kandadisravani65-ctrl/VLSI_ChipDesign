# Static Timing Analysis Using OpenSTA

## 1. Introduction

Static Timing Analysis (STA) evaluates whether signal paths in a digital circuit meet the required timing constraints. It analyzes timing paths without applying every possible input pattern through simulation.

OpenSTA is an open-source tool for performing static timing analysis using a netlist, timing libraries, constraints, and parasitic information when available.

## 2. Objectives

- Understand setup and hold timing.
- Learn about clock period and input/output delays.
- Understand timing paths and slack.
- Explore the OpenSTA workflow.
- Learn to interpret timing reports.

## 3. Important Timing Concepts

### Clock Period

The time between consecutive active clock edges for a periodic clock.

### Setup Time

The minimum time data must be stable before the active clock edge at a sequential cell.

### Hold Time

The minimum time data must remain stable after the active clock edge.

### Slack

Slack represents the difference between required time and arrival time, according to the timing check being reported.

- Positive slack generally indicates that the reported timing requirement is met.
- Negative slack indicates a timing violation.

### Critical Path

The path with the most restrictive timing result for the relevant analysis.

## 4. Inputs Required for STA

A typical timing analysis requires:

- A synthesized netlist.
- A compatible Liberty timing library.
- An SDC constraints file.
- Parasitic data such as SPEF when available and appropriate.
- Correct top-module and design configuration.

## 5. Basic OpenSTA Workflow

Start OpenSTA:

```bash
sta
```

A typical Tcl-based script may contain:

```tcl
read_liberty path/to/library.lib
read_verilog path/to/netlist.v
link_design top_module
read_sdc path/to/constraints.sdc
check_setup
report_checks
```

Replace the example paths and top-module name with the actual files and module in your project.

The library, netlist, and constraints must be compatible. A real design may require additional commands to load parasitics and configure analysis.

## 6. Example Timing Constraints

An SDC file may define a clock and input/output delays:

```tcl
create_clock -name clk -period 10 [get_ports clk]

set_input_delay 1 -clock clk [get_ports data_in]
set_output_delay 1 -clock clk [get_ports data_out]
```

This is an illustrative example only. The port names and timing values must match the actual design requirements. Designs with no clock or different interfaces require different constraints.

## 7. Understanding a Timing Report

Review the following information:

- Startpoint and endpoint.
- Clock path information.
- Data arrival time.
- Required time.
- Setup or hold slack.
- Cell and net delays.
- Timing violations, if present.

Do not conclude that a design meets timing based only on a successful tool launch. Inspect the reported paths and constraints.

## 8. Common Problems

- Missing Liberty library.
- Incorrect top-module name.
- Invalid or incomplete SDC constraints.
- Unresolved cell instances.
- Missing parasitic data for analyses that require it.
- Unconstrained timing paths.
- Incorrect clock definitions.

## 9. Learning Outcomes

- Understand the purpose of STA.
- Identify critical timing paths.
- Interpret setup and hold slack.
- Load a netlist and constraints in OpenSTA.
- Recognize common timing-analysis configuration errors.

## 10. Conclusion

Static timing analysis helps determine whether a design satisfies its timing requirements. Reliable results depend on a valid netlist, appropriate timing libraries, correct constraints, and the intended analysis setup.

**Status:** Timing-analysis workflow documented. Actual timing results are pending a configured design and verified reports.

