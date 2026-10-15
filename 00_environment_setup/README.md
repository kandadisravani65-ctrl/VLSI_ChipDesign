# 00 — Environment Setup

## Objective

To prepare a Linux-based development environment for digital design, RTL simulation, logic synthesis, and ASIC physical design using open-source Electronic Design Automation (EDA) tools.

## Development Environment

The project uses Ubuntu Linux as the primary environment for running hardware design and implementation tools.

## Tools and Technologies

| Tool | Purpose |
|---|---|
| Ubuntu Linux | Development environment |
| Git | Version control |
| GitHub | Source code hosting and documentation |
| Docker | Containerized tool installation |
| Icarus Verilog | RTL simulation |
| GTKWave | Waveform visualization |
| Yosys | Logic synthesis |
| OpenSTA | Static timing analysis |
| OpenROAD | Physical design implementation |

## Setup Procedure

1. Prepare the Ubuntu development environment.
2. Install and configure Git.
3. Verify the required EDA tools.
4. Configure Docker when required for tool installation.
5. Organize the project directories.
6. Record tool versions and verification results.

## Verification

The environment will be verified by checking the installed versions of the tools and running basic test commands.

Example commands:

```bash
git --version
docker --version
iverilog -V
yosys -V
sta -version
```

A command should only be recorded as successfully verified after it has been executed in the target environment.

## Results

Add terminal screenshots, tool version outputs, and installation notes after completing the setup.

## Conclusion

This stage establishes the foundation for subsequent RTL design, simulation, synthesis, timing analysis, and physical design experiments.

## Status

Documentation created. Environment verification is pending.
