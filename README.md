SIMULATION AND IMPLEMENTATION OF  COMBINATIONAL LOGIC CIRCUITS

AIM: 
 To simulate and synthesis ENCODER, DECODER, MULTIPLEXER, DEMULTIPLEXER, MAGNITUDE COMPARATOR using Xilinx ISE.

APPARATUS REQUIRED:
Xilinx 14.7
Spartan6 FPGA

**LOGIC DIAGRAM**

ENCODER

![image](https://github.com/navaneethans/VLSI-LAB-EXP-2/assets/6987778/3cd1f95e-7531-4cad-9154-fdd397ac439e)


DECODER

![image](https://github.com/navaneethans/VLSI-LAB-EXP-2/assets/6987778/45a5e6cf-bbe0-4fd5-ac84-e5ad4477483b)


MULTIPLEXER

![image](https://github.com/navaneethans/VLSI-LAB-EXP-2/assets/6987778/427f75b2-8e67-44b9-ac45-a66651787436)


DEMULTIPLEXER

![image](https://github.com/navaneethans/VLSI-LAB-EXP-2/assets/6987778/1c45a7fc-08ac-4f76-87f2-c084e7150557)


MAGNITUDE COMPARATOR

![image](https://github.com/navaneethans/VLSI-LAB-EXP-2/assets/6987778/b2fe7a05-6bf7-4dcb-8f5d-28abbf7ea8c2)


  
PROCEDURE:
STEP:1  Start  the Xilinx navigator, Select and Name the New project.
STEP:2  Select the device family, device, package and speed.       
STEP:3  Select new source in the New Project and select Verilog Module as the Source type.                       
STEP:4  Type the File Name and Click Next and then finish button. Type the code and save it.
STEP:5  Select the Behavioral Simulation in the Source Window and click the check syntax.                       
STEP:6  Click the simulation to simulate the program and  give the inputs and verify the outputs as per the truth table.               
STEP:7  Select the Implementation in the Sources Window and select the required file in the Processes Window.
STEP:8  Select Check Syntax from the Synthesize  XST Process. Double Click in the  FloorplanArea/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. 
STEP:9  In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu.
STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here.
STEP:11  On the board, by giving required input, the LEDs starts to glow light, indicating the output.
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
VERILOG CODE

#1
DECODER3to8:-

Code:
~~~

~~~



OUTPUT WAVEFORM:

Simulation:

![image](https://github.com/lycanthrope004/VLSI-LAB-EXP-2/assets/121667830/55e67f15-028f-47ab-81f1-64eb42a874ad)

Elaborated Design:

![image](https://github.com/lycanthrope004/VLSI-LAB-EXP-2/assets/121667830/a6ab2587-f080-4337-8744-a3ce5a48083d)

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
#2
DEMULTIPLEXER 1to8:-

Code:
~~~

~~~

OUTPUT:-

Simulation:

![image](https://github.com/lycanthrope004/VLSI-LAB-EXP-2/assets/121667830/6f259c21-c152-489b-8f03-b319a667cc74)

Elaborated Design:

![image](https://github.com/lycanthrope004/VLSI-LAB-EXP-2/assets/121667830/5e679288-7f30-4cc1-89ab-cf8f9100d6ef)
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
#3
Encoder_8to3:-
Code:
~~~
module encoder_8_to_3(a0,a1,a2,d0,d1,d2,d3,d4,d5,d6,d7);input d0,d1,d2,d3,d4,d5,d6,d7;
output a0,a1,a2;
or g1(a0,d1,d3,d5,d7);
or g2(a1,d2,d3,d6,d7);
or g3(a2,d4,d5,d6,d7);
endmodule

~~~

OUTPUT:-

Simulation:

![image](https://github.com/lycanthrope004/VLSI-LAB-EXP-2/assets/121667830/568bd01a-8eea-45a2-b033-4b433f67f883)

Elaborated Design:

![image](https://github.com/lycanthrope004/VLSI-LAB-EXP-2/assets/121667830/b3745ffe-493a-44c5-9f74-8a99f2c32b28)

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
#4
MAGNITUDE_COMPARATOR:-
Code:
~~~
module comparator(a,b,eq,lt,gt);
input [3:0] a,b;
output reg eq,lt,gt;
always @(a,b)
begin
 if (a==b)
 begin
  eq = 1'b1;
  lt = 1'b0;
  gt = 1'b0;
 end
 else if (a>b)
begin
  eq = 1'b0;
  lt = 1'b0;
  gt = 1'b1;
 end
 else
 begin
  eq = 1'b0;
  lt = 1'b1;
  gt = 1'b0;
 end
end 
endmodule
~~~

OUTPUT:-

Simulation:

![image](https://github.com/lycanthrope004/VLSI-LAB-EXP-2/assets/121667830/8c173599-802a-4297-ad2d-ab1c5b537f77)

Elaborated Design:

![image](https://github.com/lycanthrope004/VLSI-LAB-EXP-2/assets/121667830/3ed0152f-6e86-4c81-adb5-3deb95aa9451)
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
#5
MULTIPLEXER_8to1:-
Code:
~~~
~~~
OUTPUT:-
Simulation:


Elaborated Design:

RESULT:


