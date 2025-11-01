# ASIC Design Flow

## Overview
**ASIC** stands for **Application Specific Integrated Chip** - a custom-designed integrated circuit for a specific application or purpose.

## ASIC Design Flow Stages

### 1. Specification
- Design flow starts with a set of specifications/requirements/features.
- Defines functionality, area constraints, and operating clock frequency.
- Customer provides requirements that the chip must possess.

### 2. Architecture Design
- Top-level engineers design chip architecture as block diagrams.
- High level chip architecture specification includes:-
  * Functionality/ Application
  * Performance
  * Power, Area, Schedule
- Determines different blocks required (ALU, memory unit, etc.) and their interconnections.
- Cost estimation is performed at this stage.
- Proceed to RTL design if everything meets requirements.

### 3. RTL Design Coding
- RTL engineers derive design functions from architecture.
- Write RTL code using HDL (Hardware Description Language)
- **RTL (Register Transfer Level)** includes interconnections of:
  - Combinational elements (logic gates)
  - Sequential elements (registers)
  - All designed as per functionality requirements
- Tools :- IES (cadence), VCS (Synopsys), Questasim (Mentor Graphics).

### 4. Behavioral Modelling
- Represents algorithmic behavior of the design.
- Uses mathematical and arithmetic expressions.
- High-level representation of design functionality.

### 5. Functional Verification (FV/DV)
- A process used to demonstrate the functional correctness of a design.
- Verify and cross-check RTL code against specifications.
- Ensure functionality meets requirements.
- Code modifications and alterations made until specifications are satisfied.
- Iterative process until all errors are resolved.

### 6. Logic Synthesis
Tool converts RTL behavioral model code into structural Verilog code (gate-level netlist).

**Three Stages of Logic Synthesis:**
1. **Translate**: Tool converts high-level RTL circuit into corresponding logic gates (functionality remains unchanged).
2. **Technology Mapping**: Tool maps logic gates to required technology node (28nm, 14nm, etc.).
3. **Optimization**: Tool optimizes for power, area, and timing to achieve best performance.

**Additional Step**: DFT (Design for Test) insertion performed by DFT team

### 7. Logic Verification & Testing
- Gate-level simulation to verify required logic functionality
- Iterations performed until no errors remain
- **Outputs**: Gate-level netlist and SDC constraints file
- These outputs serve as inputs to Physical Design stage
STA and DFT can be performed after this.

### 8. Physical Design
Converts gate-level netlist to GDS (Graphics Data System) - transistor-level layout format for manufacturing

**Physical Design Steps:**
- Design import
- Floorplanning
- Power planning
- Placement
- Clock Tree Synthesis (CTS)
- Routing with optimization at each stage

### 9. Physical Verification & Sign-off
GDS transistor-level layout file undergoes verification with various checks:

- **DRC** (Design Rule Checking)
- **ERC** (Electrical Rule Checking)
- **LVS** (Layout vs Schematic)
- **Timing Analysis**
- **Power Analysis**
- **Crosstalk Analysis**

Iterations and modifications made until all requirements are met

### 10. Fabrication
- Verified GDS file sent to foundry
- Process called **Tapeout**
- Chip is manufactured/fabricated

### 11. Packaging & Testing
- Fabricated chip is packaged
- Final testing performed for any bugs or issues
- Environmental and reliability testing

### 12. Chip to Market
- Bug-free IC is released to market
- Final product available for commercial use
