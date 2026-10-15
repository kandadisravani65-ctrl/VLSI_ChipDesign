# Placement and Clock Tree Synthesis

## 1. Introduction

Placement assigns physical locations to standard cells inside the core. Clock Tree Synthesis (CTS) builds a clock distribution network that delivers the clock signal to sequential elements.

These stages influence timing, congestion, power, and physical implementation quality.

## 2. Objectives

- Understand global and detailed placement.
- Learn why clock distribution is required.
- Understand clock skew and insertion delay.
- Explore placement and CTS reports.
- Recognize common timing and congestion issues.

## 3. Placement

Placement determines where standard cells are located in the core.

### Global Placement

Estimates cell locations while optimizing objectives such as timing and density.

### Detailed Placement

Legalizes and refines cell locations to satisfy placement rules.

## 4. Clock Tree Synthesis

CTS inserts and arranges clock buffers or inverters to distribute the clock to sequential cells.

### Clock Skew

The difference in clock arrival time between relevant sequential elements.

### Clock Insertion Delay

The delay from the clock source to a clock endpoint.

### Clock Buffering

Clock buffers help drive the clock network and control its distribution characteristics.

## 5. Typical Workflow

1. Start with a valid floorplan and power plan.
2. Perform global placement.
3. Refine placement and legalize cells.
4. Analyze placement timing and congestion.
5. Build the clock tree.
6. Optimize the design after CTS.
7. Review clock, timing, and placement reports.

The exact command sequence depends on the selected physical-design tool and platform configuration.

## 6. Important Reports

- Placement utilization.
- Congestion estimates.
- Cell displacement or legalization issues.
- Clock-tree statistics.
- Clock skew and insertion delay.
- Setup and hold timing.
- Buffer and inverter counts.

## 7. Common Issues

- Excessive placement density.
- Routing congestion.
- Unplaced or illegal cells.
- Poor clock distribution.
- Setup timing violations.
- Hold timing violations.
- Incomplete clock definitions.

## 8. Learning Outcomes

- Understand standard-cell placement.
- Distinguish global and detailed placement.
- Understand the purpose of CTS.
- Interpret basic clock-tree metrics.
- Recognize common physical-design issues.

## 9. Conclusion

Placement determines the physical locations of standard cells, while CTS distributes the clock to sequential elements. Both stages are essential for achieving a physically implementable design with acceptable timing.

**Status:** Placement and CTS concepts documented. Implementation results are pending tool execution.

