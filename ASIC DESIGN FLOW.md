ASIC: APPLICATION SPECIFIC INTEGRATED CHIP
specification
architecture
behavioural modelling
rtl design coding
functional verification
logic synthesis
logic verification testing
physical design
physical verification sign off
fabrication
packaging and testing
chip to market

design flow starts with the given set of specifications/requirements/features that chip must posesess i.e. in terms of functionality how much area it must consume with what clock freq it must operate
As per the specification from the customer top level engineers design the architecture of the chip in form of block diagram.
what must ne the different blocks the design must contain like ALU, memory unit etc and its interconnections
cost of the chip is also estimated at this stage and if everything is fine. it is proceeded to the RTL design
Now, from the architecture
RTL engineers derive function of the design and write some RTL code using HDL and that will be understood by the tool
RTL- is the register transfer level which includes interconnections of the comninational elements like logic gates and sequential elements like registers as per the functionality
Behavioral model represents the algorithmic way of representing the behaviour of the design It also uses some mathematical and arithmatic expressions.
Funcational verification i.e to verify and cross check the RTL code whether it satisfies the functionality and specifications. If there are any errors, the code is modified. Alterations are made until the specifications are satisfied.
Logic synthesis- In this stage, the tool converts the RTL behaviour model code into structural verilog code which is a gate level netlist.
Logic synthesis happens in 3 stages
i) translate:- the tool converts the high level rtl cricuit into its corresponding logic gates. The funcationality remains the same however.
ii) technology mapping:- here the tool maps the logic gates with the required technology that we are designing in i.e 28nm,14n, etc.
iii) Optimization:- Tools does optimization in terms of power, area timing to get the best performance
DFT insertion is also done at this stage by the DFT team
now, gate level simulation i.e logic verification and testing is done to check whether it performs the required logic and iterations are done until there are no errors. The o/p of logic sysnthesis are gate level netlist and sdc constrainst file which are given as an i/p to the physical design
the gate level netlist is converted to the gds- graphical database stream. It is nothing but transistor level layour format of a design whuch be manufacturable.
various steps involved in PD are design import floorplaning power plans CDS,and routing with optimization in each stage.
now, obatained gds transistor level layout file is sent for verification and sign off where different checks are performed.
drc,erc,lvs,timing analysis, power analysis crosstalk analysis.
iterations and modifications are made until we meet the requirement 
the gds file after verification is sent to the foundary and this process is called tapeout for fabrication.
Fabricated chip is packeged and is tested again for any bugs.
after final testing bug free IC is released to the market.
