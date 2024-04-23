# VLSI-LAB-EXPERIMENTS
**AIM:** To simulate and synthesis Logic Gates,Adders and Subtractor using Vivado 2023.

**APPARATUS REQUIRED:** Vivado 2023 Spartan6 FPGA

**PROCEDURE:** STEP:
1. Open Vivado: Launch Xilinx Vivado software on your computer.

2. Create a New Project: Click on "Create Project" from the welcome page or navigate through "File" > "Project" > "New".

3. Project Settings: Follow the prompts to set up your project. Specify the project name, location, and select RTL project type.

4. Add Design Files: Add your Verilog design files to the project. You can do this by right-clicking on "Design Sources" in the Sources window, then selecting "Add Sources". Choose your Verilog files from the file browser.

5. Specify Simulation Settings: Go to "Simulation" > "Simulation Settings". Choose your simulation language (Verilog in this case) and simulation tool (Vivado Simulator).

6. Run Simulation: Go to "Flow" > "Run Simulation" > "Run Behavioral Simulation". This will launch the Vivado Simulator and compile your design for simulation.

7. Set Simulation Time: In the Vivado Simulator window, set the simulation time if it's not set automatically. This determines how long the simulation will run.

8. Run Simulation: Start the simulation by clicking on the "Run" button in the simulation window.

9. View Results: After the simulation completes, you can view waveforms, debug signals, and analyze the behavior of your design.
Logic Diagram :

# Logic Gates:
![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/ee17970c-3ac9-4603-881b-88e2825f41a4)

**Program**:
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

**OUTPUT WAVEFORM:**:

![image](https://github.com/Yogalakshmip08/VLSI-LAB-EXP-1/assets/161303457/48ba7e88-9e1a-475b-8f9b-6e89d31894a7)


# Half Adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/0e1ecb96-0c25-4556-832b-aeeedfdfe7b9)

**Program**:

module half_adder(a,b,sum,carry);

input a,b;

output sum,carry;

xor g1(sum,a,b);

and g2(carry,a,b);

endmodule

**OUTPUT WAVEFORM:**:

![image](https://github.com/Yogalakshmip08/VLSI-LAB-EXP-1/assets/161303457/e9a7f5cc-414e-4ed4-b3c0-f5dfd70f550c)




# Full adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/9bb3964c-438f-469d-a3de-c1cca6f323fb)

**Program**:

module fulladder(a,b,c,sum,carry);

input a,b,c;

output sum,carry;

wire w1,w2,w3;

xor(w1,a,b);

xor(sum,w1,c);

and(w2,w1,c);

and(w3,a,b);

or(carry,w2,w3);

endmodule

**OUTPUT WAVEFORM:**:

![image](https://github.com/Yogalakshmip08/VLSI-LAB-EXP-1/assets/161303457/9a2c376b-023e-4b76-bf0a-707467e196ad)


# Half Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/731470b7-eb4e-49f8-8bb7-2994052a7184)

**Program**:

module halfsub(a,b,diff,borrow);

input a,b;

output diff,borrow;

xor(diff,a,b);

and(borrow,~a,b);

endmodule

**OUTPUT WAVEFORM:**

![image](https://github.com/Yogalakshmip08/VLSI-LAB-EXP-1/assets/161303457/f4ffcffd-90d2-4682-897c-d9ae787a4afd)


# Full Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/d66f874b-c1f2-44b3-a035-7149b56430c1)

**Program**:

module fs(a,b,bin,d,bout);

input a,b,bin;

output d,bout;

wire w1,w2,w3;

xor(w1,a,b);

xor(d,w1,bin);

and(w2,~a,b);

and(w3,~w1,bin);

or(bout,w3,w2);

endmodule

**OUTPUT WAVEFORM:**

![image](https://github.com/Yogalakshmip08/VLSI-LAB-EXP-1/assets/161303457/e0b6c2be-0961-4488-9522-2b6fbf807d47)


# 8 Bit Ripple Carry Adder

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/7385a408-40a5-4203-8050-b72818622d79)

**Program**:

module fulladder(a,b,c,sum,carry);

input a,b,c;

output sum,carry;

wire w1,w2,w3;

xor(w1,a,b);

xor(sum,w1,c);

and(w2,w1,c);

and(w3,a,b);

or(carry,w2,w3);

endmodule

module rca_8bit(a,b,cin,s,cout);

input [7:0]a,b;

input cin;

output [7:0]s;

output cout;

wire [7:1]w;

fulladder f1(a[0], b[0], cin, s[0], w[1]);

fulladder f2(a[1], b[1], w[1], s[1], w[2]);

fulladder f3(a[2], b[2], w[2], s[2], w[3]);

fulladder f4(a[3], b[3], w[3], s[3], w[4]);

fulladder f5(a[4], b[4], w[4], s[4], w[5]);

fulladder f6(a[5], b[5], w[5], s[5], w[6]);

fulladder f7(a[6], b[6], w[6], s[6], w[7]);

fulladder f8(a[7], b[7], w[7], s[7], cout);

endmodule

**OUTPUT WAVEFORM:**
![image](https://github.com/Yogalakshmip08/VLSI-LAB-EXP-1/assets/161303457/b694213e-9611-4c82-9476-30be9b87c760)


# RESULT:
The simulation and synthesis of Logic Gates,Adders and Subractor using Vivado Software are succesfully verified.
