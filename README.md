# Experiment--03-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![image](https://github.com/Aslina1315/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/155459437/9c059aa0-21da-4078-94ec-12314aa8cea8)
Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![image](https://github.com/Aslina1315/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/155459437/c8dc0ec3-bd25-4642-8422-177204af2209)
Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Program:

Half Subtractor :

module ex03(A,B,Diff,Borrow);
input A,B;
output Diff,Borrow;
wire X;
xor(Diff,A,B);
not(X,A);
and(Borrow,X,B);
endmodule

Full Subtractor:

module ex03(A,B,C,Diff,Borrow);
input A,B,C;
output Diff,Borrow;
assign Diff = A^B^C;
assign Borrow = ~A & (B^C) | B & C;
endmodule
/*
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by:M.Noorull aslina
RegisterNumber:212223050033  
*/

HALF SUBTRACTOR

Truthtable
![image](https://github.com/Aslina1315/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/155459437/614643d5-8230-4f7b-bd9b-6bd46d122e38)


RTL realization
![image](https://github.com/Aslina1315/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/155459437/0620d9c9-785b-407f-bdc6-35ca1f94b6c4)


Timing diagram
![image](https://github.com/Aslina1315/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/155459437/ce0331d4-fc66-4628-8595-2fbc38f0617c)


FULL SUBTRACTOR

Truthtable
![image](https://github.com/Aslina1315/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/155459437/fa170abc-416f-4665-89ad-cc70b61f8b3b)


RTL realization
![image](https://github.com/Aslina1315/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/155459437/8308f2be-03d1-4c13-9a4d-3dfbc1e1caac)


Timing diagram
![image](https://github.com/Aslina1315/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/155459437/a48effa7-638c-4bb4-925e-ebaa5f54ac2b)


Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.


