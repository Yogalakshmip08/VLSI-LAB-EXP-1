# VLSI-LAB-EXPERIMENTS
AIM: To simulate and synthesis Logic Gates,Adders and Subtractor using Xilinx ISE.

APPARATUS REQUIRED: Xilinx 14.7 Spartan6 FPGA

PROCEDURE: STEP:1 Start the Xilinx navigator, Select and Name the New project. STEP:2 Select the device family, device, package and speed. STEP:3 Select new source in the New Project and select Verilog Module as the Source type. STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it. STEP:5 Select the Behavioral Simulation in the Source Window and click the check syntax. STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table. STEP:7 Select the Implementation in the Sources Window and select the required file in the Processes Window. STEP:8 Select Check Syntax from the Synthesize XST Process. Double Click in the Floorplan Area/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. STEP:9 In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu. STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here. STEP:12 Load the Bit file into the SPARTAN 6 FPGA STEP:11 On the board, by giving required input, the LEDs starts to glow light, indicating the output.

Logic Diagram :

Logic Gates:
![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/ee17970c-3ac9-4603-881b-88e2825f41a4)


Half Adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/0e1ecb96-0c25-4556-832b-aeeedfdfe7b9)


Full adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/9bb3964c-438f-469d-a3de-c1cca6f323fb)


Half Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/731470b7-eb4e-49f8-8bb7-2994052a7184)



Full Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/d66f874b-c1f2-44b3-a035-7149b56430c1)



8 Bit Ripple Carry Adder

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/7385a408-40a5-4203-8050-b72818622d79)


# FULL ADDER
VERILOG CODE:
```

module fa_ha(a,b,c,sum,cout);
input a,b,c;
output sum,cout;
wire wl, w2, w3, w4, w5;
xor x1(w1,a,b);
xor x2 (sum,w1,c) ;
and al(w2,a,b) ;
and a2(w3,b,c);
and a3(w4,a,c) ;
or o1(w5,w2,w3) ;
or o2(cout,w5,w4) ;
endmodule
```
OUTPUT:
![FULL ADDER](https://github.com/Yogalakshmip08/VLSI-LAB-EXP-1/assets/161303457/1675522b-95e1-41db-ba3b-3fe94dd47aa2)
![Screenshot 2024-04-01 144130](https://github.com/Yogalakshmip08/VLSI-LAB-EXP-1/assets/161303457/8ab6f046-fb3f-41df-8531-4277c6a30ad4)


# FULL SUBRACTOR
VERILOG CODE:
```

module full_sub(borrow,diff,a,b,c);
output borrow,diff;
input a,b,c;
wire w1,w4,w5,w6;
xor (diff,a,b,c);
not n1(w1,a);
and a1(w4,w1,b);
and a2(w5,w1,c);
and a3(w6,b,c);
or o1(borrow,w4,w5,w6);
endmodule
```
OUTPUT:
![image](https://github.com/Yogalakshmip08/VLSI-LAB-EXP-1/assets/161303457/e70a180c-7962-434f-9c08-7be7a16b6da0)
![image](https://github.com/Yogalakshmip08/VLSI-LAB-EXP-1/assets/161303457/0632a243-f30a-4367-8a5d-97858d370409)


# HALF ADDER
VERILOG CODE:
```

module half_adder(a,b,sum,carry);
input a,b;
output sum,carry; 
or(sum,a,b);
and(carry,a,b);
endmodule
```
OUTPUT:
![FULL ADDER](https://github.com/Yogalakshmip08/VLSI-LAB-EXP-1/assets/161303457/5e84d015-766b-4b6d-843e-36d676ff36fe)
![WhatsApp Image 2024-04-22 at 13 47 07_c2fb3815](https://github.com/Yogalakshmip08/VLSI-LAB-EXP-1/assets/161303457/e96d2502-df13-410e-83e8-4ebc8507fc5a)


# HALF SUBRACTOR
VERILOG CODE:
```
module halfsubtractor( D,Bo,A,B);
input A,B;
output D,Bo;
wire w1;
xor (D,A,B);
not (w1,B);
and (Bo,B,w1);
endmodule
```
OUTPUT:
![image](https://github.com/Yogalakshmip08/VLSI-LAB-EXP-1/assets/161303457/181982a6-7dbb-4002-b71b-9426bd9e195f)
![image](https://github.com/Yogalakshmip08/VLSI-LAB-EXP-1/assets/161303457/244ae7f8-c171-48de-89d9-72b69c87b8d7)


# LOGIC GATES
VERILOG CODE:
```
module logicgates(a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate);
input a,b;
output andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate;
and(andgate,a,b);
or(orgate,a,b);
xor(xorgate,a,b);
nand(nandgate,a,b);  
nor(norgate,a,b);
xnor(xnorgate,a,b);
not(notgate,a);
endmodule
```
OUTPUT:
![image](https://github.com/Yogalakshmip08/VLSI-LAB-EXP-1/assets/161303457/273cfdb8-2378-42bd-aa09-e6d8b039ae3a)
![image](https://github.com/Yogalakshmip08/VLSI-LAB-EXP-1/assets/161303457/93a8d647-d1d3-47e9-9bcc-b249b1465dc7)


# RIPPLECARRY ADDER_4BIT
VERILOG CODE:
```
module rippe_adder(S, Cout, X, Y,Cin);
 input [3:0] X, Y;
 input Cin;
 output [3:0] S;
 output Cout;
 wire w1, w2, w3;
 fulladder u1(S[0], w1,X[0], Y[0], Cin);
 fulladder u2(S[1], w2,X[1], Y[1], w1);
 fulladder u3(S[2], w3,X[2], Y[2], w2);
 fulladder u4(S[3], Cout,X[3], Y[3], w3);
endmodule
module fulladder(S, Co, X, Y, Ci);
  input X, Y, Ci;
  output S, Co;
  wire w1,w2,w3;
  xor G1(w1, X, Y);
  xor G2(S, w1, Ci);
  and G3(w2, w1, Ci);
  and G4(w3, X, Y);
  or G5(Co, w2, w3);
endmodule
```
OUTPUT:
![WhatsApp Image 2024-04-22 at 13 47 16_9de91174](https://github.com/Yogalakshmip08/VLSI-LAB-EXP-1/assets/161303457/9c68d9b8-6ead-4a44-ade0-68baae9b9a39)
![WhatsApp Image 2024-04-22 at 13 47 10_531e25a3](https://github.com/Yogalakshmip08/VLSI-LAB-EXP-1/assets/161303457/8e88e252-7953-47a0-a49d-f27324ced72e)


# RIPPLECARRY ADDER_8BIT
VERILOG CODE:
```






















RESULT:

