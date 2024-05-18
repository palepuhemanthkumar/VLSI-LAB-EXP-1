# EXPERIMENT-1             SIMULATION AND IMPLEMENTATION OF LOGIC GATES, ADDERS & SUBTRACTOR
# DATE: 
# AIM:
To simulate and synthesis Logic Gates,Adders and Subtractor using vivado 2023.2.

# APPARATUS REQUIRED:
vivado 2023.2

# PROCEDURE:
STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation adn then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.

# Logic Diagram :
# Logic Gates:
![image](https://github.com/Irakamchaitanya/VLSI-LAB-EXP-1/assets/161814091/fb8e903e-177e-4c58-970c-680c22a6c8ee)


# Half Adder:
![image](https://github.com/Irakamchaitanya/VLSI-LAB-EXP-1/assets/161814091/9fb7ff42-6d64-40f1-96a8-178f15b602b7)


# Full adder:
![image](https://github.com/Irakamchaitanya/VLSI-LAB-EXP-1/assets/161814091/57e7f734-2057-4080-865c-272720728ec0)


# Half Subtractor:
![image](https://github.com/Irakamchaitanya/VLSI-LAB-EXP-1/assets/161814091/a8305803-8d15-4190-91e8-551aaa8f5116)


# Full Subtractor:
![image](https://github.com/Irakamchaitanya/VLSI-LAB-EXP-1/assets/161814091/cf0846ed-f231-423b-8c8b-10e8e0875a86)

# 8 Bit Ripple Carry Adder
![image](https://github.com/Irakamchaitanya/VLSI-LAB-EXP-1/assets/161814091/162f888d-511e-420f-ad1a-3b8710613a42)


# VERILOG CODE:
module logic(a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate );

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

# HALF ADDER:
module HalfAdder(a,b,sum,carry);

input a,b;

output sum,carry;

xor (sum,a,b);

and (carry,a,b);

endmodule

# FULL ADDER:
module FA(a,b,cin,sum,cout);

input a,b,cin;

output sum,cout;

wire w1,w2,w3;

xor g1(w1,a,b);

and g2(w2,w1,cin);

and g3(w3,a,b);

xor g4(sum,w1,cin);

or g5(cout,w2,w3);

endmodule

# HALF SUBTRACTOR:
module halfsubtractor(a,b,diff,borrow);

input a,b;

output diff,borrow;

xor g1(diff,a,b);

and g2(borrow,~a,b);

endmodule

# FULL SUBTRACTOR:
module full_sub(a,b,bin,diff,borrow);

input a,b,bin;

output diff,borrow;

wire w1,w2,w3;

xor g1(w1,a,bin);

and g2(w2,~a,b);

xor g3(diff,w1,bin);

or g4(borrow,w2,w3);

and g5(w3,~w1,bin);

endmodule

# 8 BIT RIPPLE CARRY ADDER:
module fa(a,b,c,sum,carry);

input a,b,c;

output sum,carry;

assign sum = a^b^c;

assign carry=(a&b)|(b&c)|(c&a);

endmodule

module rca(a,b,cin,sum,cout);

input [7:0]a,b;

input cin;

output [7:0]sum;

output cout;

wire c1,c2,c3,c4,c5,c6,c7;

fa fa1(a[0],b[0],cin,sum[0],c1);

fa fa2(a[1],b[1],c1,sum[1],c2);

fa fa3(a[2],b[2],c2,sum[2],c3);

fa fa4(a[3],b[3],c3,sum[3],c4);

fa fa5(a[4],b[4],c4,sum[4],c5);

fa fa6(a[5],b[5],c5,sum[5],c6);

fa fa7(a[6],b[6],c6,sum[6],c7);

fa fa8(a[7],b[7],c7,sum[7],cout);

endmodule

# OUTPUT:
# LOGIC GATES:
![image](https://github.com/Irakamchaitanya/VLSI-LAB-EXP-1/assets/161814091/8e9daf0a-09f5-4e9a-bdbd-0fa994bd4588)


# HALF ADDER:
![image](https://github.com/Irakamchaitanya/VLSI-LAB-EXP-1/assets/161814091/94bf8cb0-ab2c-4fbb-9930-2e63c90ab03f)


# FULL ADDER:
![image](https://github.com/Irakamchaitanya/VLSI-LAB-EXP-1/assets/161814091/0a49f2c6-f88f-44ff-afdb-8ea53a4c090f)


# HALF SUBTRACTOR:
![image](https://github.com/Irakamchaitanya/VLSI-LAB-EXP-1/assets/161814091/b4c7e797-da35-4f42-85f6-ab58d6a9721b)

# FULL SUBTRACTOR:
![image](https://github.com/Irakamchaitanya/VLSI-LAB-EXP-1/assets/161814091/0620633c-12e9-49b7-aaed-8181a9e1cfbf)


# 8 BIT RIPPLE CARRY ADDER:
![image](https://github.com/Irakamchaitanya/VLSI-LAB-EXP-1/assets/161814091/7b3de011-9df3-4cfb-b2a7-1b08f3e65815)


# RESULT:
Thus the simulation and synthesis of Logic Gates,Adders and Subtractors using vivado has been sucessfully executed and verified .
