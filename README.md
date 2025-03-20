# Schematic-to-Layout-of-D-FlipFlop
step-by-step process of designing a D FlipFlop using CMOS technology, from schematic design to analog layout and LVS verification. The implementation is done using SkyWater 130nm PDK.

**Introduction**

This project demonstrates the step-by-step process of designing a D FlipFlop using CMOS technology, from schematic design to analog layout and LVS verification. The implementation is done using SkyWater 130nm PDK.

A D FlipFlop (Data FlipFlop) is a bistable logic circuit that follows the input when the clock (Enable) signal is high and holds the last state when the clock signal is low. It is widely used in digital circuits for temporary data storage.

**1. D FlipFlop Properties**

The D FlipFlop consists of transistors, which are implemented as level-sensitive FlipFlopes that operate based on the enabled signal.

Key Features:

Technology Node: SkyWater 130nm
Type: Clock-Sensitive FlipFlop
Logic Function: Q = D when Enable = 1, Q holds previous state when Enable = 0

**2. Schematic Design**

The first step is designing the D FlipFlop schematic using a circuit design tool like Xschem or Cadence Virtuoso. The schematic consists of:

D FlipFlop schematic
![Clk_D_FlipFlop_schematic](https://github.com/user-attachments/assets/940f47e2-43cd-4319-a6d5-748c3e40ee6b)

The Spice code was extracted from simulation files in .xschem

D FlipFlop schematic's spice code
![Clk_D_FlipFlop _schematic_spice](https://github.com/user-attachments/assets/6f6df938-4faa-4328-b386-6ee0453c6502)

**3. Analog Layout Design**

The next step is to create an analog layout of the D FlipFlop using Magic VLSI.

Steps:

1. Placement of PMOS and NMOS transistors according to the schematic.

2. Routing connections using metal layers.

3. Adding well contacts and vias for connectivity.

4. Ensuring DRC compliance to match fabrication rules.

D FlipFlop analog layout
![Clk_D_FlipFlop ](https://github.com/user-attachments/assets/70eaf9ea-bf06-46c5-9703-3f9fee2623fc)


D FlipFlop layout's spice code
![Clk_D_FlipFlop _Layout_Spice](https://github.com/user-attachments/assets/7ba512d6-654b-4ce0-b04e-8540a8a97f59)

**4. Layout to Spice Extraction**

To verify the layout, we extract the SPICE netlist from the layout using Magic VLSI.

Steps:

1. Open the layout in Magic.
2. Extract the layout using extract all command.
3. Convert it to SPICE format using ext2spice.

![Clk_D_FlipFlop _layout to spice code](https://github.com/user-attachments/assets/4d6606d9-73c0-4d73-945b-eb11ade556e9)

5. LVS Verification

The final step is Layout vs Schematic (LVS) verification to ensure that the schematic and layout match.

Steps:

1. Load both schematic and extracted layout netlists in Netgen.
2. Run netgen lvs command to compare them. (If it doesn't work remove .subckt and .ends in spice code)
3. Fix any mismatches until LVS passes.

![Clk_D_FlipFlop_LVS](https://github.com/user-attachments/assets/406b09a8-7fca-4d6d-babd-8954277dc32e)

**Conclusion**

By following these steps, we successfully designed and verified a D FlipFlop from schematic to layout. The key takeaways from this project include:

1. Understanding CMOS-based D FlipFlop design.
2. Converting schematic to analog layout.
3. Extracting and simulating SPICE netlists.
4. Performing LVS verification for correctness.

This project serves as a foundation for designing more complex digital circuits using SkyWater 130nm technology.

