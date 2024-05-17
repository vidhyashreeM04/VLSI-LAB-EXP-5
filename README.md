# SIMULATION AND IMPLEMENTATION OF FINITE STATE MACHINE

## AIM: 
To simulate and synthesis finite state machine using Xilinx ISE.

## APPARATUS REQUIRED:
VIVADO 2023.2

## PROCEDURE:
### STEP:1 
Start the Xilinx navigator, Select and Name the New project.<br>
### STEP:2
Select the device family, device, package and speed. <br>
### STEP:3 
Select new source in the New Project and select Verilog Module as the Source type. <br>
### STEP:4 
Type the File Name and Click Next and then finish button. Type the code and save it. <br>
### STEP:5 
Select the Behavioral Simulation in the Source Window and click the check syntax. <br>
### STEP:6 
Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table. <br>
### STEP:7
Select the Implementation in the Sources Window and select the required file in the Processes Window. <br>
### STEP:8 
Select Check Syntax from the Synthesize XST Process. Double Click in the Floorplan Area/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. <br>
### STEP:9 
In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu. <br>
### STEP:10 
Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here. <br>
### STEP:11
On the board, by giving required input, the LEDs starts to glow light, indicating the output.<br>
### STEP:12 
Load the Bit file into the SPARTAN 6 FPGA <br>

## Logic Diagram :


![image](https://github.com/Sachita02/VLSI-LAB-EXP-5/assets/162723490/44a1620d-9e34-44a0-a1c2-02e073a12e93)

## VERILOG CODE:

module fsm(clk,rst,x,z);<br>
input clk,rst,x;<br>
output z;<br>
reg [2:1] ps,ns;<br>
parameter s0=2'b00,s1=2'b01,s2=2'b10,s3=2'b11;<br>
always@(x,posedge clk)<br>
case(ps)<br>
s0:if(x)<br>
ns=s1;<br>
else<br>
ns=s0;<br>
s1:if(x)<br>
ns=s1;<br>
else<br>
ns=s2;<br>
s2:if(x)<br>
ns=s3;<br>
else<br>
ns=s0;<br>
s3:if(x)<br>
ns=s1;<br>
else<br>
ns=s0;<br>
endcase<br>
always@(posedge clk)<br>
if(rst)<br>
ps<=s0;<br>
else<br>
ps=ns;<br>
assign z=(ps==s3);<br>
endmodule<br>

## OUTPUT:

![image](https://github.com/Sachita02/VLSI-LAB-EXP-5/assets/162723490/d481b251-fb24-4223-a929-2cdf83e3a629)



## RESULT:
The simulate and synthesis of finite state machine using VIVADO is successfully verified.



