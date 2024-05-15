# Exp no:1
# Date:13/02/2024

# SIMULATION AND IMPLEMENTATION OF LOGIC GATES,ADDERS AND SUBTRACTOR

# AIM: To simulate and synthesis Logic Gates,Adders and Subtractor using Xilinx ISE.

# APPARATUS REQUIRED: 
vivado 2023.2

# PROCEDURE: 
STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation adn then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table. Logic Diagram :

# Logic Diagram :

# Logic Gates:
![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/ee17970c-3ac9-4603-881b-88e2825f41a4)

# CODE

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

# Output

![image](https://github.com/maha0213/VLSI-LAB-EXP/assets/159602131/9d0d79a1-2590-4ae3-aeb6-d69c40d61aa3)


# CODE

module HalfAdder(a,b,sum,carry);

input a,b;

output sum,carry;

xor (sum,a,b);

and (carry,a,b);

endmodule
# OTUPUT

![image](https://github.com/maha0213/VLSI-LAB-EXP/assets/159602131/69484bc1-3a98-4c30-bcd6-f8889d11f94c)

# Full adder:

![image](https://github.com/maha0213/VLSI-LAB-EXP/assets/159602131/61b1d9f6-f2d2-42ab-9d00-0a74b38097a7)

# CODE

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

# OUTPUT

![image](https://github.com/maha0213/VLSI-LAB-EXP/assets/159602131/fe7d05d9-5093-4655-83d2-7a6f64650c3b)

# Half Subtractor:

![image](https://github.com/maha0213/VLSI-LAB-EXP/assets/159602131/ed23d76c-da14-40f1-a445-bd94365ca67e)

# CODE

 module halfsubtractor(a,b,diff,borrow);

input a,b;

output diff,borrow;

xor g1(diff,a,b);

and g2(borrow,~a,b);

endmodule

# Full Subtractor:

![image](https://github.com/maha0213/VLSI-LAB-EXP/assets/159602131/bf2d77bb-ddb9-45a1-84e1-54aa6ece0c4d)

# CODE

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
# OUTPUT


![image](https://github.com/maha0213/VLSI-LAB-EXP/assets/159602131/57c3e385-34d2-4ef8-9881-6b6ef219d2e5)

# 8 Bit Ripple Carry Adder
# CODE

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

# OUTPUT

![image](https://github.com/maha0213/VLSI-LAB-EXP/assets/159602131/4b3b542e-11a3-449f-96d6-e4c42e97cd1a)

# RESULT:
Thus the simulation and synthesis of Logic Gates,Adders and Subtractors using vivado has been sucessfully executed and verified .

