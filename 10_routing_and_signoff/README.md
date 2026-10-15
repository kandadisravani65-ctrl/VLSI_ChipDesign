# Routing and Physical Design Signoff

## 1. Introduction

Routing creates the metal interconnections between cells and design pins. Signoff checks evaluate whether the implementation satisfies relevant physical and timing requirements.

A design is not ready for signoff simply because routing completes; the resulting reports must also be reviewed.

## 2. Objectives

- Understand global and detailed routing.
- Learn about routing layers and design rules.
- Understand parasitic extraction.
- Review timing after routing.
- Recognize common physical verification checks.
   <img width="943" height="389" alt="image" src="https://github.com/user-attachments/assets/1f41e11d-c406-425b-aac1-fad5d739e670" />


## 3. Global Routing

Global routing plans approximate routes and estimates congestion without necessarily creating the final detailed metal geometry.

## 4. Detailed Routing

Detailed routing creates the actual metal routes while following the technology's routing and design rules.
 <img width="943" height="485" alt="image" src="https://github.com/user-attachments/assets/ee4eb054-5009-421b-963a-4f54f7cc1e40" />

## 5. Parasitic Extraction

Interconnects introduce resistance and capacitance. Parasitic extraction estimates these effects so timing analysis can better reflect the routed implementation.

## 6. Important Checks

### Design Rule Checking

Checks physical geometry against applicable manufacturing design rules.
 <img width="951" height="418" alt="image" src="https://github.com/user-attachments/assets/39a35afc-c357-4680-b22a-26594fffd33f" />


### Timing Analysis

Checks whether timing requirements are satisfied using the available implementation data and constraints.

### Connectivity

Checks whether intended electrical connections have been made.

### Antenna Checks

Evaluates potential antenna-rule violations during fabrication-related processing.

### Power Integrity

Evaluates power-distribution concerns where the required analysis tools and models are available.

The specific checks depend on the process platform and project requirements.

## 7. Typical Workflow

1. Complete placement and CTS.
2. Perform global routing.
3. Perform detailed routing.
4. Extract parasitic information.
5. Run timing analysis using the appropriate data.
6. Run applicable physical verification checks.
7. Review and resolve violations.
8. Save the final reports and implementation outputs.

## 8. Results to Record

- Routing completion status.
- Signal wire length, if reported.
- Routing congestion.
- Design-rule violations.
- Setup and hold slack.
- Extracted parasitic data.
- Final verification status.

Record only values actually reported by the tools.

## 9. Learning Outcomes

- Understand the purpose of routing.
- Distinguish global and detailed routing.
- Understand interconnect parasitics.
- Recognize common physical verification checks.
- Understand why signoff requires report review.

## 10. Conclusion

Routing connects the placed cells, while signoff checks assess the physical and timing quality of the implementation. A successful flow requires reviewing the results and resolving applicable violations.

**Status:** Routing and signoff concepts documented. Final results are pending a completed and verified implementation flow.

