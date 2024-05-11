# VLSI-LAB-EXP-5
v.saikumar
212222060211

SIMULATION AND IMPLEMENTATION OF FINITE STATE MACHINE

AIM: To simulate and synthesis finite state machine using Xilinx ISE.

**APPARATUS REQUIRED: **

Xilinx 14.7 
Spartan6 FPGA

**PROCEDURE: **
STEP:1 Start the Xilinx navigator, Select and Name the New project.
STEP:2 Select the device family, device, package and speed. 
STEP:3 Select new source in the New Project and select Verilog Module as the Source type. 
STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it. 
STEP:5 Select the Behavioral Simulation in the Source Window and click the check syntax. 
STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table. 
STEP:7 Select the Implementation in the Sources Window and select the required file in the Processes Window. 
STEP:8 Select Check Syntax from the Synthesize XST Process. Double Click in the Floorplan Area/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. 
STEP:9 In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu. 
STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here. 
STEP:11 On the board, by giving required input, the LEDs starts to glow light, indicating the output.
STEP:12 Load the Bit file into the SPARTAN 6 FPGA 

Logic Diagram :

![image](https://github.com/navaneethans/VLSI-LAB-EXP-5/assets/6987778/34ec5d63-2b3b-4511-81ef-99f4572d5869)


VERILOG CODE:


LOGIC DIAGRAM:

![image](https://github.com/navaneethans/VLSI-LAB-EXP-5/assets/6987778/34ec5d63-2b3b-4511-81ef-99f4572d5869)


FSM:

module fsm(clk,rst,x,y);
input clk,rst,x;
output y;
reg [2:1]present,next;
parameter s0=2'b00,s1=2'b01,s2=2'b10,s3=2'b11;
always@(x,present)
case (present)
s0:if (x)
next=s1;
else
next=s0;
s1:if(x)
next=s1;
else
next=s2;
s2:if(x)
next=s3;
else
next=s0;
s3:if (x)
next=s1;
else
next=s2;
endcase
always@(negedge rst,posedge clk)
if (rst)
present=s0;
else
present=next;
assign z=(present==s3);

endmodule


OUTPUT:![screenshot Image 2024-04-13 at 13 19 50_0c877b3c](https://github.com/Mohanraj7896/VLSI-LAB-EXP-5/assets/166592482/32a0a3e0-9786-4c39-ae2b-0d03d03f11b4)






----Type Verilog Code

OUTPUT:

-----Place a Waveform Generated from Xilinx ISE------------

RESULT:
