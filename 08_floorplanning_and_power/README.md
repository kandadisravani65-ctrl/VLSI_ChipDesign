# ASIC Floorplanning and Power Planning

## 1. Introduction

Floorplanning is an early stage of ASIC physical design. It defines the approximate chip or core area and establishes the initial arrangement of major design elements.

Power planning establishes the structures used to distribute supply voltage and ground to the design.

## 2. Objectives

- Understand the purpose of floorplanning.
- Learn about die and core dimensions.
- Understand utilization and placement density.
- Explore power and ground distribution.
- Recognize the importance of pin placement and blockages.
    <img width="597" height="587" alt="image" src="https://github.com/user-attachments/assets/2bdaac0d-0301-4b54-aadd-a6a7b7aa58cc" />


## 3. Key Concepts

### Die Area

The overall physical area of the chip.

### Core Area

The area reserved for the main digital implementation.

### Utilization

A measure of how much of the core area is occupied by the relevant placed cells. The exact reported definition depends on the tool and stage.

### Placement Density

The target density used to guide placement. Very high density may create congestion and make routing more difficult.
 <img width="845" height="416" alt="image" src="https://github.com/user-attachments/assets/f1553fd7-c872-4403-9f8b-a49ff1df1164" />


### Power Distribution Network

A network of power and ground connections intended to deliver supply voltage across the design.

## 4. Floorplanning Activities

- Define the floorplan dimensions.
- Select core and die margins.
- Configure placement density.
- Place input and output pins.
- Define placement blockages if required.
- Create power and ground structures.
- Check floorplan feasibility.
  <img width="847" height="413" alt="image" src="https://github.com/user-attachments/assets/a22e6a6b-afb0-4eef-be55-aa4f67c7aa4e" />


## 5. Typical Workflow

1. Load the synthesized netlist.
2. Load the technology and cell libraries.
3. Initialize the floorplan.
4. Define core and die dimensions.
5. Configure pin placement.
6. Construct the power distribution network.
7. Check placement and power-planning constraints.
8. Save the floorplan database and reports.

## 6. Design Considerations

- Core size affects placement and routing.
- High utilization can increase congestion.
- Pin placement affects routing access.
- Power structures must be compatible with the technology rules.
- Physical dimensions and layer choices depend on the platform configuration.

## 7. Reports to Record

- Core and die dimensions.
- Target and achieved utilization.
- Number of instances.
- Power-network configuration.
- Floorplan or design-rule warnings.
- Screenshots of the floorplan, when available.
   <img width="773" height="428" alt="image" src="https://github.com/user-attachments/assets/6ea2f28b-b61a-4286-8321-579e3ea41bc4" />


## 8. Learning Outcomes

- Understand the role of floorplanning.
- Identify important floorplan parameters.
- Understand power and ground distribution.
- Recognize utilization and congestion trade-offs.
- Learn what to inspect before placement and routing.

## 9. Conclusion

Floorplanning establishes the physical foundation of an ASIC implementation. Appropriate area planning, pin placement, and power distribution help prepare the design for placement and routing.

**Status:** Floorplanning concepts documented. Physical results are pending an executed implementation flow.

